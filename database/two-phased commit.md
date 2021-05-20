# 2단계 커밋

2단계 커밋(two-phased commit)은 분산된 데이터베이스에서 원자성을 보장하는 방법이다.

## 용어 뜻풀이

양방향 통신을 2번 수행해서 커밋을 완료한다. 그래서 2단계 커밋이라고 부른다.

## 과정

분산된 데이터베이스의 참가자(participant)들 중 작업을 수행할 진행자(coordinator)가 나타나면, 진행자는 다른 참가자들에게 자신의 작업을 공유할 필요가 있다.
이때 2단계 커밋은 아래 과정을 거쳐 작업을 공유한다.

- 1단계
	- 진행자는 참가자들에게 수행할 작업을 알려준다. 진행자를 포함한 참가자들은 작업을 커밋 직전까지 수행한다.
	- 참가자들은 진행자에게 커밋을 완료할 수 있을지 여부를 알려준다.
- 2단계
	- 진행자는 참가자들의 응답을 보고 커밋을 완료할지, 작업을 되돌릴지 결정해서 참가자들에게 알려준다.
	- 참가자들은 커밋을 완료하거나, 작업을 되돌려서 진행자에게 알려준다.

```
Coordinator                                         Participants
                              QUERY TO COMMIT
                -------------------------------->
                              VOTE YES/NO           prepare*/abort*
                <-------------------------------
commit*/abort*                COMMIT/ROLLBACK
                -------------------------------->
                              ACKNOWLEDGMENT        commit*/abort*
                <--------------------------------  
end
```


# 참고
- [Two-phased commit protocol, 위키피디아](https://en.wikipedia.org/wiki/Two-phase_commit_protocol#Implementing_the_two-phase_commit_protocol)
