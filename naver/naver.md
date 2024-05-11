** 과제 구현 내용에 대한 설명을 작성해 주세요 **


1. logo
2. login form
    2-1. email
    2-2. pw   
    2-3. submit
3. remember-me / ip-security



<하면서 어려웠던 점>
1. IP 보안 옆 클릭 시 마다 ON/OFF 변하도록 구현하는 것
-> 현재 checkbox를 활용하여 구현하였는데, 맞는 방식으로 구현한것인지 잘 모르겠습니다.
label, for 를 사용해서 label 클릭 시 input 태그의 checkbox가 체크되고 안되고를 활용하여 구현하였습니다.
checkbox의 경우 hidden으로 처리하여 보이지는 않게 하였습니다.
또한 키보드를 통해 tab 이동시, hidden 처리한 checkbox에 focus가 가는 점이 곤란했는데,
css에서 
.ip-security input[type="checkbox"]:focus + label .switch-label,
.ip-security input[type="checkbox"]:focus-visible + label .switch-label {
    outline: 2px solid #24388d;
}
위와 같은 코드를 통해 checkbox에 focus가 갔을 때 label도 outline이 생성되도록 추가해주었습니다.
뭔가 정형화되어있지 않은 방법으로 억지로 구현한것같아 더 좋은 방법이 있을지 알고싶습니다!


2. IP 보안과 ON/OFF 쪽 align 맞추는 것이 어려웠는데,
css에서 중복되는 코드들을 지우다보니 얼떨결에 적용이 되었습니다. 다른 적용 방법이 있는지 궁금합니다. 
또한 크기 및 위치 맞출때 어떻게 어디서부터 설계하면 좋은지 알고싶습니다! 어디에 적용을 해서 맞춰나가야 하는지 잘 모르겠습니다.
제대로 된 설계를 하지 않고 무작정 코드부터 작성하다보니 중복되는 코드들이 많아져서 한군데의 수정으로 제대로 적용이 되지 않는 문제가 있던 것 같습니다.


3. 전체 크기가 줄어 모바일 버전으로 되었을 때, '로그인 상태 유지'를 오른쪽으로 옮기고, 'IP 보안' 쪽을 안보이도록 구성하는 것이 어려웠습니다.
@media (max-width: 767px) {
    .container {
        max-width: none;
        padding: 1rem 1.25rem;
    }

    .login-form {
        max-width: 100%;
    }

    .ip-security {
        display: none;
    }

    .options {
        justify-content: end;
    }
}

ip-security 쪽을 display: none, options에 justify-content: end 를 적용하는 것을 생각해내기 힘들었습니다.

