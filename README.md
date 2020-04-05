# ScienceProject
## 과학프로젝트, 날씨에 학교를 더하다

2019년 2학기말에 시작한 프로젝트 였고, 5인 프로젝트입니다.
  #### 조별프로젝트기에 노션을 이용해서 소통했고, 브레인 스토밍과 개발 과정까지 공유했습니다.
  https://www.notion.so/Science_Project-9c3b5deffd7446eda3b27296d446757e

## 버전관리
### ver1(2020-2-15) 개발목표에(제안서, 계획서) 맞는 웹을 개발하였습니다.
날씨정보중 등하교 날씨, 아침운동 시간의 날씨를 가져와, 그외의 날씨정보(온도, 기상상황, 미세먼지등등)과 함께  
그에맞는 피드백을 제공해주는(아침운동 확률을 예측해주는) 웹을 개발, 배포하였습니다.

### ver2(2020-4-1) 크롤링과 DB 업데이트 자동화로, 웹의 콘텐츠가 매일 갱신됩니다.
<a href="#versionUp">개발과정은 아래에 덧붙였습니다.</a>  
3일간의 삽질 끝에 크롤링과 DB 자동 업데이트를 구현했습니다.  
앞으로 서버 갱신만 한달에 한번씩 확인해준다면(무료계정의 비애),  
매일매일 그날의 날씨에 맞는 정보를 제공합니다.

***
### 개발목표 - 
우리학교의 등하교시간, 아침운동시간의 날씨정보와 날씨정보로 아침운동확률도 예측하는 웹사이트

### 개발기간 - 
2019년 12월 20일 ~ 2월 15일
### 개발단계 - 
1. 데이터 크롤링 프로그램 구현, mysql로 DB 구축 (동현, 수필, 두평, 19.12.20. ~ 20.1.4.) 
2. DB 서버 연동, 백엔드 프론트엔드 나뉘어 구현 (두평, 현호, 종근, 20.12.20. ~ 20.1.16.)
3. 프론트 백 연결 문제로 무산 (20.1.16 ~ 20.2.1.)
4. 장고로 웹 구현, 로컬서버로 프론트에 DB값 출력 성공 (20.2.2. ~ 20.2.7.)
5. 웹 디자인, 퍼블리싱 완료, 원격서버로 배포 완료, 프로젝트 끝! (20.2.8. ~ 20.2.15.)

(백 프론트상 연결이 도무지 안되고, 갈등으로 프론트가 잠수타버리는 바람에 데이터 크롤링파트인 저혼자 장고로 웹구현 하게 됬다는 슬픈 전설..)
***
## 실제 웹 링크 - 
http://bosal.pythonanywhere.com/
### 웹 캡쳐 -
<img src="/readme_img/1.png" width="450px" height="auto" title="메인컨텐츠" alt="프로젝트웹사이트캡처"></img><br/>
<img src="/readme_img/2.png" width="450px" height="auto" title="세부정보컨텐츠" alt="프로젝트웹사이트캡처"></img><br/>
<img src="/readme_img/3.png" width="450px" height="auto" title="시간별컨텐츠" alt="프로젝트웹사이트캡처"></img><br/>
<img src="/readme_img/4.png" width="450px" height="auto" title="푸터" alt="프로젝트웹사이트캡처"></img><br/>

(pythonanywhere를 활용했으며, 프로젝트로 처음 장고와 원격배포를 해봤기에 많이 어리숙합니다.
버전업한다면, DB업데이트가 수동이 아닌 자동으로 되게하며, 반응형 웹으로 구현할 예정입니다.)

***

## ver 2, 크롤링, DB 업로드 자동화<a name="versionUp"></a>
(2020.3.31.~4.2.)
pythonanywhere의 database를 python script로 접근, db를 자동으로 업데이트 하는 코드 + 크롤링 자동화까지 개발에 종지부를 찍었습니다.

친절하게도 pythonanywhere에서 스크립트 기능을 제공하는데,  
불친절하게도 db 접근시 생기는 오류에 대해서 대충 명시해서, 삽질좀 했습니다.

문제 해결과정(삽질)에 대해서 자세한 내용은, pythonanywhere_access/ 폴더를 참고하시면 되겠습니다. 

<a href="https://github.com/Kimdonghyeon7645/ScienceProject/tree/master/pythonanywhere_access">바로가기</a>

***

## backup?

(2020-4-6)  
정말 울뻔했습니다. git bash로 폴더들의 이름을 변경하려고 했는데, 뭐가 잘못됬는지, git mv 원래이름 새이름이 안됬습니다.  
그래서 구글링으로 찾은 방법들을 실행하다가, 브런치를 삭제하는 명령어였나.? 왜그랬는지는 모르겠지만,     
로컬에 있는 브런치를 삭제하고 원격으로 다시 받아올려는 생각이였는 가본데,   
> git status

하고 상태를 보니까 이상하게 폴더의 모든 파일이 삭제됬다 하는 겁니다.  
그리고 git push 를 하려니까 아이디랑 비밀번호를 입력하라 하더라구요...  

#### 그리고 나서 모든 파일이 삭제되었습니다 (이 원격 저장소안의 모든 폴더, 파일)

머리속도 같이 하얘졌고, git reset 으로 복구는 안됬습니다.  
(당연하게도 로컬저장소로 복구해봤자 원격저장소는 복구 할 수 없는데,)  
그땐 머리가 굳어서 git reset 을 했는데 원격저장소가 왜 그대론가 슬펐습니다.  

정말 1시간동안 정말 울뻔했지만, 어떻게든 맨탈을 잡고, 저장소 복구에 성공했습니다.

> https://jupiny.com/2019/03/19/revert-commits-in-remote-repository/  
정말 감사합니다

덕분에 깃허브의 공포의 쓴맛을 오랜만에 만났고, 더욱이 지식이 늘었습니다.   
그리고 다음부터 모르는 건, 특히 아이디와 비번을 입력해야 되는 것은 함부로 안할 것 같습니다. ^^;;
