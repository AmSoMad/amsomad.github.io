---
title: "[Android-Kotlin] ListView 클릭이벤트 추가하기"
excerpt: "listView에서 클릭이벤트로 Activity 이동"

categories:
  - 자바
  
tags:
  - [자바, Kotlin, Android]

permalink: 

toc: true
toc_sticky: true
 
date: 2022-06-22
last_modified_at: 2022-06-22
---


# 😬 안드로이드 ListView 클릭이벤트 추가하기 🏭👩‍🏭👨‍🏭

---

Activity안에 ListView가 있다. <br>
헌데 ListView에 들어올 리스트는 유동적으로 표현하고싶다면 <br>
Adapter를 달아주면된다. 

## Class 부분
---
```java
import java.io.Serializable;

class CostCenter (
    var CostCenter: String,
    var CalendarType: String,
    var CostCenterName: String,
    var WorkType: String,
    var MeasureUnit: String

) : Serializable
```

## Adapter 부분

---

```java
class ListViewAdapter (val context: Context, val list: ArrayList<CostCenter>) : BaseAdapter() {

    //xml 파일의 View와 데이터를 연결하는 핵심 역할을 하는 메소드이다.
    override fun getView(position: Int, convertView: View?, parent: ViewGroup?): View {
        /* LayoutInflater는 item을 Adapter에서 사용할 View로 부풀려주는(inflate) 역할을 한다. */
        val view: View = LayoutInflater.from(context).inflate(R.layout.recycler_view_item, null)


        ... //로직구성
        
        //클릭 이벤트 추가
        view.setOnClickListener(View.OnClickListener { v -> //해당 리스트 클릭시 이벤트

            val intent  = Intent(v.context, MenuResultDetailActivity::class.java);
            intent.putExtra("ClickObject",list.get(position));

            //putExtra로 객체를 전달할경우 해당 객체가 
            //Serializable (직렬화) 로 전달해야한다.

            v.context.startActivity(intent);
            
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

## Activity 이동 후

---

```java
    var list  = intent.getSerializableExtra("ClickObject") as CostCenter;
    ... //로직 구현
    list.CostCenter.toString();
```



<br>



**Note:** `만들고나니 내것이 아니었다.` 