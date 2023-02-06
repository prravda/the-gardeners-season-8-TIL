# MQTT

- mqtt 시범강의 준비를 위해 HiveMQ 의 [mqtt essentials series](https://prravda.notion.site/mqtt-protocol-539da7454a4b4520ab358d1190bcc024) 를 다 보고 정리했다.
  - 추가로 github 에 [mqtt client side hands on](https://github.com/prravda/mqtt-hands-on-clinet) 도 어느정도 구성해서 올렸다. 전체적인 커리큘럼을 커버하려면 아직은 갈 길이 멀긴 하지만, 일단은 테스트 격인 시범강의만 준비하는 거니 기초를 잘 준비해서 가자.
- 이론 10분은 MQTT essentials 쪽 개념들을 설명하면 끝날 거 같고, 실습 10분은 client side 의 구성 및 mosquitto 에서 제공하는 test 용 broker 에 물리는 정도로 마무리할까 한다.

# Discrod bot

- 그리고 쭉 기다리던 discord bot 도 개발을 시작했는데, discord 문서에선 javascript 로 만들었던 걸 같이 작업하는 분이 강타입 언어를 좀 더 선호하셔서 [typescript boilerplate](https://github.com/prravda/discord-bot-typescript) 를 구성하였다.
- 물론 이거도 갈 길이 멀다. 일단 javascript 로 구성된 코드를 기반으로 typescript 로 '그대로' 옮기려니 미묘한 에러들이 자꾸 발생한다.
  - 특히 [VerifyDiscordAccount](https://github.com/prravda/discord-bot-typescript/blob/main/infra/discord-utils.ts#L9) method 를 옮기는 데 첫 번째 verifying 과정에서 validity 를 검증하는 데 자꾸 `false` 값이 반환되고 있다.

# Reflection

- 간만에 코드를 만지면서 느낀 점인데, 차분한 문제 정의 능력이 많이 떨어졌다.
  - 물론 그렇다고 '예전에 문제정의를 잘 했느냐?' 라고 물어본다면 그것은 아니다만, 작업을 한 뒤 돌아보면 무작정 우다다다 달리기만 하고 일단은 해결해야겠다는 급한 마음만 먹지 않았던가 한다.
- 구체적인 예를 들자면 [이것처럼](https://github.com/MericcaN41/discordjs-v14-template-ts) 요즈음 사람들이 더 잘 가꿔놓은 TypeScript discord bot boilerplate code 들을 보았을 땐 `Client` 라는 discord.js 의 구현체를 이용하는데, 나는 그것도 모르고 있던 채로 '어떻게 하면 `VerifyDiscordAccount` 라는 걸 해결할 수 있을까? 라는 거에만 몰두했었다. 자명하게 더 나은 방법이 존재함에도 불구하고 이전에 썼던 비효율적인 방식을 통해 꾸역꾸역 해결하려는 내 태도가 썩 좋진 않았다.
- 상황 판단 -> 문제 정의 -> 함축적이고 복합적 문제를 쪼개지지 않으며 독립적인 문제들로 나눔 -> 문제 해결방법 도출 -> 짧은 주기로 문제 해결 및 해결여부 검증 과정을 밟자.

---

사실 꾸준히 코딩하는 게 정답인듯?
