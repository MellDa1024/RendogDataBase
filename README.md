<p align="center">
    <img src="https://raw.githubusercontent.com/MellDa1024/RendogClientAsset/main/assets/RendogClient.png" style="width: 90%">
</p>

## RendogDataBase
RendogClient의 데이터베이스를 불러오는 저장소(Repo)입니다.  
무기 정보는 WeaponDataV3 형식에 맞춰 작성하여 Pull Request로 제출해주세요.  
기존의 WeaponData 및 WeaponDataV2 형식은 다양한 무기 정보를 담기에는 한계가 있다고 판단되어, 새로운 구조로 개편하였습니다.

## V3 (Current Version)
### 예시 1
```Json
{
  "WeaponName": "< 초월 > [ :: 흑월참 :: ]", // 무기 이름에서 강화 수치, MAX, SPECIAL을 제외한 순수 이름
  "maxLevel": 1, // 최대 강화 수치(MAX 포함), SPECIAL 무기는 -1로 설정
  "changeByLevel" : false, // 강화 수치에 따라 쿨타임이 변하면 true, 고정이면 false
  // changeByLevel이 false일 경우 cooldown array의 길이는 1로 고정,
  // changeByLevel이 true일 경우 cooldown array는 강화 단계에 따른 수치가 됩니다. (2번째 예제 참고)
  "LeftCoolDown" : [17.0], // 좌클릭 스킬의 쿨타임 (초 단위)
  "RightCoolDown" : [17.0], // 우클릭 스킬의 쿨타임 (초 단위)
  "InVillage" : false, // 마을 내에서 스킬 사용 가능 여부 (true: 사용 가능, false: 사용 불가)
  "CoolDownGroup": "dark_moon_slash" // 쿨타임을 공유하는 그룹의 고유 ID (임의로 설정 가능하나 알아 볼 수 있게)
}
```
### 예시 2
```json
{
  "WeaponName": "[ 각성 ] [ :: 잔월효성 :: ]",
  "maxLevel": 5,
  "changeByLevel" : true,
  "LeftCoolDown" : [16.0, 13.0, 10.0, 7.0, 4.0],
  "RightCoolDown" : [15.0, 15.0, 15.0, 15.0, 15.0],
  "InVillage" : false, 
  "CoolDownGroup": "fading_moon"
}
```

## 지원 종료(구 버전, Deprecated)
### V2
```Json
{
  "WeaponName": "< 초월 > [ :: 흑월참 :: ]", // 무기 이름에서 강화 수치, MAX, SPECIAL을 제외한 순수 이름
  "maxLevel": 1, // 최대 강화 수치(MAX 포함), SPECIAL 무기는 -1로 설정
  "changeByLevel" : false, // 강화 수치에 따라 쿨타임이 변하면 true, 고정이면 false
  // changeByLevel이 false일 경우 cooldown array의 길이는 1로 고정,
  // changeByLevel이 true일 경우 cooldown array는 강화 단계에 따른 수치가 됩니다.
  "LeftCoolDown" : [17.0], // 좌클릭 스킬의 쿨타임 (초 단위)
  "RightCoolDown" : [17.0], // 우클릭 스킬의 쿨타임 (초 단위)
  "InVillage" : false, // 마을 내에서 스킬 사용 가능 여부 (true: 사용 가능, false: 사용 불가)
}
```

### V1
```Json
{
  "WeaponName" : "[ 데모닉 ] [ +1 ]", //무기의 이름이 들어갑니다.
  "RightCoolDown" : 16, //무기의 오른쪽 클릭 스킬 쿨타임이 들어갑니다.
  "LeftCoolDown" : 3, //무기의 왼쪽 클릭 스킬 쿨타임이 들어갑니다.
  "InVillage" : false //무기의 스킬이 마을에서 사용이 가능한지에 대한 여부입니다.
  //사용가능할 시 True, 사용불가능할시 False.
}
```