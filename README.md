<p align="center">
    <img src="https://raw.githubusercontent.com/MellDa1024/RendogClientAsset/main/assets/RendogClient.png" style="width: 90%">
</p>

## RendogDataBase
RendogClient의 데이터베이스를 불러오는 Repo입니다.  
무기의 정보를 WeaponDataV2에 담아서 pull request로 보내주세요.  
기존 WeaponData형식은 수많은 무기의 정보를 담는데에는 무리가 있다고 판단되어 새로운 방식으로 바꿨습니다.

## 예시
```Json
{
  "WeaponName": "< 초월 > [ :: 흑월참 :: ]", //강화 수치, MAX, SPECIAL을 뺀 무기의 이름
  "maxlevel": 1, //최대 강화 수치(MAX 포함), SPECIAL은 -1
  "changebylevel" : false, //강화 수치에 따라 쿨타임의 변경 여부, 바뀌면 true, 아니면 false
  //changebylevel이 false일 경우 cooldown의 array len은 1로 고정,
  //changebylevel이 true일 경우 cooldown의 array는 강화 단계에 따른 수치가 됩니다. (2번째 예제 참고)
  "LeftCoolDown" : [17.0], //좌클릭 스킬의 쿨타임, 
  "RightCoolDown" : [17.0], //우클릭 스킬의 쿨타임
  "InVillage" : false // //무기의 스킬이 마을에서 사용이 가능한지에 대한 여부입니다.
  //사용가능할 시 True, 사용불가능할시 False.
}
```
## 예시 2
```json
{
    "WeaponName": "[ 각성 ] [ :: 잔월효성 :: ]",
    "maxlevel": 5,
    "changebylevel" : true,
    "LeftCoolDown" : [16.0, 13.0, 10.0, 7.0, 4.0],
    "RightCoolDown" : [15.0, 15.0, 15.0, 15.0, 15.0],
    "InVillage" : false
}
```



### 예시(Old WeaponData) :
```Json
{
  "WeaponName" : "[ 데모닉 ] [ +1 ]", //무기의 이름이 들어갑니다.
  "RightCoolDown" : 16, //무기의 오른쪽 클릭 스킬 쿨타임이 들어갑니다.
  "LeftCoolDown" : 3, //무기의 왼쪽 클릭 스킬 쿨타임이 들어갑니다.
  "InVillage" : false //무기의 스킬이 마을에서 사용이 가능한지에 대한 여부입니다.
  //사용가능할 시 True, 사용불가능할시 False.
}
```