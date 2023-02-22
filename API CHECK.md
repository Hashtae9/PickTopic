## API CHECK

### [POST]localhost:8080/ingre_refri/api/addIngre

+ 재료가 만약 기존에 없다면 추가하고 재료와 냉장고를 이용해 IngreRefri에 재료 등록 및 유통기한 냉동상태 추가

```
{
    "ingreInfo" : {
        "ingreName": "치킨",
        "imgSource": "img_Source1",
        "defaultIngre": "True"
    },
    "IngreRefriInfo" : {
        "refriExpirDate": "2024-02-17",
        "frozen": "True"
   }
}
```



### [DELETE]localhost:8080/ingre_refri/api/deleteIngre

+ 냉장고의 재료 1개 제거

```
{
    "ingreName": "치킨",
    "imgSource": "img_Source1",
    "defaultIngre": "True"
}
```



### [GET]localhost:8080/ingre_refri/api/ingreInRefri

+ 냉장고 속 재료 다 뽑아오기



### localhost:8080/refrigerator/api/{RefriName}

+ 냉장고 이름 변경

