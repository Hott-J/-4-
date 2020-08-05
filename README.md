# * 피파온라인4 채팅 봇
- - -

      피파온라인4 유저 프로필, 선수 정보 검색(급여, 오버롤, 상세스텟 등 / 피파 어딕트 사이트 파싱), 진행중인 이벤트, 
      1vs1 / 2vs2 공식경기와 볼타라이브 전적 검색이 가능한 채팅봇입니다.
      8월5일-> 최근 공식경기와 감독모드 매치기록 상세 검색과 최근 이적시장 거래내역 조회 기능 추가 (open Api 사용)

<br/>

## * 사용법
- - -

    < 템플릿으로 출력되는 것들은 모두 해당 칸을 누를 시 각 링크로 이동하여 상세정보를 볼 수 있습니다.>
     
     
     1. !정보 (유저명) : 유저 프로필 검색
     
     2. !이벤트 : 진행중인 이벤트 검색
     
     3. !일대일 (유저명) : 공식경기 1vs1 전적 검색(10000위 안에 진입시 검색 가능)
     
     4. !이대이 (유저명) : 공식경기 2vs2 전적 검색(10000위 안에 진입시 검색 가능)
     
     5. !감모 (유저명) : 공식경기 감독모드 전적 검색(10000위 안에 진입시 검색 가능)
     
     6. !볼타전체 (유저명) : 볼타라이브 전체 전적 검색(10000위 안에 진입시 검색 가능)
     
     7. !볼타격수 (유저명) : 볼타라이브 격수 전적 검색(10000위 안에 진입시 검색 가능)
     
     8. !볼타미드 (유저명) : 볼타라이브 미드 전적 검색(10000위 안에 진입시 검색 가능)
     
     9. !볼타수비 (유저명) : 볼타라이브 수비 전적 검색(10000위 안에 진입시 검색 가능)
     
     10. !선수 (선수명) : 선수 정보 상세 검색(피파 어딕트 사이트에서 파싱)
     
     11. !매치 (유저명) : 유저의 최근 공식경기 상세 전적 검색 가능
     
     12. !감모매치 (유저명) : 유저의 최근 감독모드 공식경기 상세 전적 검색 가능

<br/>

## * 사용 예시 ( 유사한 명령어들은 대표적인 것 하나만 예시로 들고 생략하였습니다.)
- - -

     !정보 (유저명)
   ![KakaoTalk_20200802_172253278_09](https://user-images.githubusercontent.com/47052106/89119153-e2271480-d4e6-11ea-91af-c2cd3d630aa3.jpg)

<br/>

     !이벤트
   ![KakaoTalk_20200802_172253278_07](https://user-images.githubusercontent.com/47052106/89119155-ec491300-d4e6-11ea-8d39-a03113fa2168.jpg)

<br/>

     !일대일 (유저명)
   ![KakaoTalk_20200805_151051236_02](https://user-images.githubusercontent.com/47052106/89378549-fa897000-d72e-11ea-8b55-e85116dca47b.jpg)
   
<br/>

     !볼타격수 (유저명)
  ![KakaoTalk_20200802_172253278](https://user-images.githubusercontent.com/47052106/89119052-2e258980-d4e6-11ea-80ff-16b52947afbc.jpg)
  
<br/>

     !선수 (선수명)
  ![KakaoTalk_20200802_172253278_02](https://user-images.githubusercontent.com/47052106/89119185-21edfc00-d4e7-11ea-8a60-9fb32e8767f4.jpg)
  
     해당 칸 클릭 시 아래와 같이 선수 특징, 스텟, 클럽 경력, 시세 등 상세정보 볼 수 있음
  ![KakaoTalk_20200802_172253278_04](https://user-images.githubusercontent.com/47052106/89119195-3205db80-d4e7-11ea-9438-d6e62c5f35ee.jpg)
   
<br/>

      !매치 (유저명)
   ![KakaoTalk_20200805_151724357_01](https://user-images.githubusercontent.com/47052106/89378561-fd846080-d72e-11ea-9d66-7521b200aff1.jpg)
   
<br/>

      !거래 (유저명)
   ![KakaoTalk_20200805_151724357](https://user-images.githubusercontent.com/47052106/89378558-fc533380-d72e-11ea-8960-cf194ed54c5c.jpg)
   
<br/> 

## * 구현 로직
- - -

     선수 검색 시에 템플릿 type-object가 리스트이고, 리스트가 5개일시, 만약 리스트가 5개미만이라면 형식에 맞지 않아
     전부다 공백으로 출력됩니다. 따라서, try-catch 문을 활용하여 검색결과가 없을시에, 공백이 반환되도록 예외처리를 하였습니다. 
     선수 검색의 경우 피파어딕트 사이트를, 공식경기와 볼타라이브 전적 검색은 피파온라인4 홈페이지를 파싱하였습니다.
     NEXON DEVELOPERS 의 FIFA ONLINE4 Open Api를 사용하여, 매치기록과 거래명과 유저의 access Id를 가져왔습니다.

<br/>

## * 문제점
- - -

![숭실대요청](https://user-images.githubusercontent.com/47052106/89379645-1d1c8880-d731-11ea-8bda-009ff20f695c.JPG)
![숭실대응답](https://user-images.githubusercontent.com/47052106/89379651-1e4db580-d731-11ea-9151-aa9735deb9ac.JPG)
![유저네임리퀘스트](https://user-images.githubusercontent.com/47052106/89379655-1ee64c00-d731-11ea-8b92-647d7022b94a.JPG)
![유저네임응답](https://user-images.githubusercontent.com/47052106/89379658-1f7ee280-d731-11ea-9f1d-f5950c1010cf.JPG)
![유저아이디응답](https://user-images.githubusercontent.com/47052106/89379659-20177900-d731-11ea-97ad-2047de2cec19.JPG)

![리퀘스트](https://user-images.githubusercontent.com/47052106/89379673-29a0e100-d731-11ea-9dd3-923b77509a29.JPG)
      
