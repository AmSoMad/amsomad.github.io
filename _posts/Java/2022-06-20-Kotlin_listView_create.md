---
title: "[Android-Kotlin] ListView 출력방법(gRPC통신)"
excerpt: "Return gRPC-String to Json parse"

categories:
  - 자바
  
tags:
  - [자바, Kotlin, Android, gRPC]

permalink: 

toc: true
toc_sticky: true
 
date: 2022-06-10
last_modified_at: 2022-06-10
---


# 😬 안드로이드 ListView 구현방법 🏭👩‍🏭👨‍🏭

---

Activity안에 ListView가 있다. <br>
헌데 ListView에 들어올 리스트는 유동적으로 표현하고싶다면 <br>
Adapter를 달아주면된다. 

## 1. gRPC 통신으로 받을 Class를 구성

> 클래스 생성

```java

//값을 받을 형태의 클래스를 생성해주고.
class CostCenterReport(
    var CostCenter: String,
    var CalendarType: String,
    var CostCenterName: String,
    var WorkType: String,
    var MeasureUnit: String

)
```

## 2. 반복해서 보여줄 형태 layout 생성
> Layout 안에 5개의 TextView가 있다. 
> 해당 Layout을 ArrayList로 생성하여
> Adapter에 주입시킬것이다.

```xml
<?xml version="1.0" encoding="utf-8"?>
  <androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
  xmlns:app="http://schemas.android.com/apk/res-auto"
  xmlns:tools="http://schemas.android.com/tools"
  tools:context=".MainActivity"
      android:layout_width="365dp"
      android:layout_height="56dp"
      app:layout_constraintEnd_toEndOf="parent"
      app:layout_constraintStart_toStartOf="parent"
      tools:layout_editor_absoluteY="6dp">

  <TextView
      android:id="@+id/costCenter"
      android:layout_width="50dp"
      android:layout_height="48dp"
      android:layout_marginStart="16dp"
      android:textSize="12sp"
      android:textStyle="bold"
      app:layout_constraintBottom_toBottomOf="parent"
      app:layout_constraintStart_toStartOf="parent"
      app:layout_constraintTop_toTopOf="parent"
      tools:text="C01" />

  <TextView
      android:id="@+id/calendarType"
      android:layout_width="50dp"
      android:layout_height="48dp"
      android:textSize="12sp"
      app:layout_constraintBottom_toBottomOf="@+id/costCenter"
      app:layout_constraintStart_toEndOf="@+id/costCenter"
      app:layout_constraintTop_toTopOf="@+id/costCenter"
      tools:text="1" />

  <TextView
      android:id="@+id/costCenterName"
      android:layout_width="50dp"
      android:layout_height="48dp"
      android:textSize="12sp"
      app:layout_constraintBottom_toBottomOf="@+id/calendarType"
      app:layout_constraintStart_toEndOf="@+id/calendarType"
      app:layout_constraintTop_toTopOf="@+id/calendarType"
      tools:text="건조" />

  <TextView
      android:id="@+id/workType"
      android:layout_width="50dp"
      android:layout_height="48dp"
      android:textSize="12sp"
      app:layout_constraintBottom_toBottomOf="@+id/costCenterName"
      app:layout_constraintStart_toEndOf="@+id/costCenterName"
      app:layout_constraintTop_toTopOf="@+id/costCenterName"
      app:layout_constraintVertical_bias="0.0"
      tools:text="2" />

  <TextView
      android:id="@+id/measureUnit"
      android:layout_width="50dp"
      android:layout_height="48dp"
      android:textSize="12sp"
      app:layout_constraintBottom_toBottomOf="@+id/workType"
      app:layout_constraintStart_toEndOf="@+id/workType"
      app:layout_constraintTop_toTopOf="@+id/workType"
      tools:text="EA" />

</androidx.constraintlayout.widget.ConstraintLayout>
```



## 3. Adapter 생성

> ArrayList를 생성한 클래스형태로 만들고 추가.

```js
class ListViewAdapter (val context: Context, val list: ArrayList<CostCenterReport>) : BaseAdapter() {

    //xml 파일의 View와 데이터를 연결하는 핵심 역할을 하는 메소드이다.
    override fun getView(position: Int, convertView: View?, parent: ViewGroup?): View {
        /* LayoutInflater는 item을 Adapter에서 사용할 View로 부풀려주는(inflate) 역할을 한다. */
        val view: View = LayoutInflater.from(context).inflate(R.layout.recycler_view_item, null)


        /* 위에서 생성된 view를 recycler_view_item.xml 파일의 각 View와 연결하는 과정이다. */
        val costCenter = view.findViewById<TextView>(R.id.costCenter)
        val calendarType = view.findViewById<TextView>(R.id.calendarType)
        val costCenterName = view.findViewById<TextView>(R.id.costCenterName)
        val workType = view.findViewById<TextView>(R.id.workType)
        val measureUnit = view.findViewById<TextView>(R.id.measureUnit)

        /* ArrayList<boardList>의 변수의 데이터를 TextView에 담는다. */
        val insertArraylist = list[position]

        costCenter.text = insertArraylist.CostCenter
        calendarType.text = insertArraylist.CalendarType.toString()
        costCenterName.text = insertArraylist.CostCenterName
        workType.text = insertArraylist.WorkType.toString()
        measureUnit.text = insertArraylist.MeasureUnit

        view.setOnClickListener(View.OnClickListener { v -> //해당 리스트 클릭시 이벤트
            Toast.makeText(v.context, list.get(position).CostCenterName, Toast.LENGTH_SHORT)
                .show();

        })

        return view

    }

    //ListView에 속한 item의 전체 수를 반환한다.
    override fun getCount(): Int {
        return list.size
    }

    //해당 위치의 item을 메소드이다.
    // Int 형식으로 된 position을 파라미터로 갖는다.
    // 예를 들어 1번째 board item을 선택하고 싶으면 코드에서 getItem(0)과 같이 쓸 수 있을 것이다.
    override fun getItem(position: Int): Any {
        return list[position];
    }

    //해당 위치의 item id를 반환하는 메소드이다.
    // 이 예제에서는 실질적으로 id가 필요하지 않아서 0을 반환하도록 설정했다.
    override fun getItemId(position: Int): Long {
        return 0
    }

}
```

## 4. gRPC통신 - ListView 생성

> gRPC 통신으로 받은 Json타입의 String을 parse 한다.

```java

//Layout Xml의 리스트뷰를 받는다.
val resultListView = findViewById<ListView>(R.id.resultListView)
var gRPC_return : JSONArray;

CoroutineScope(Dispatchers.Main).launch {
    
    // grpc 통신의 리턴값을 받는다.
    // GetAll_CenterType_CostCenter 메서드에서 gRPC통신의 결과를 JSONArray로 변환하여 
    // 리턴한다.
    gRPC_return = gRPC_Communication.GetAll_CenterType_CostCenter(1)

    for (i: Int in 0..(gRPC_return.length() - 1)) {
        costReport.add(
            //받을 값의 형태와 같은 클래스를 생성해주고
            //값을 추가하여 리스트에 추가
            CostCenterReport(
                gRPC_return.getJSONObject(i).get("Parse 한 변수명").toString(),
                ... 
            )
        )
    }

    resultListView.adapter = ListViewAdapter(this@MenuResultActivity, costReport);
}

```

```java
    suspend fun GetAll_CenterType_CostCenter(centertype : Int): JSONArray {
            val request = CostCenterRequest.newBuilder().setCenterType(centertype)
                .build()
            val response = costCenterService.costCenterList(request)            
            var stringToJsonVal = JSONArray(response.jsonResult);
            stringToJsonVal.length()
            //Log.i("결과: ", StringToJsonVal.getString("CostCenterName"))

        return stringToJsonVal;
    }
```

---


<br>



**Note:** `만들고나니 내것이 아니었다.` 