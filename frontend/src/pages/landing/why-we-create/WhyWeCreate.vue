<template>
  <div>
    <div class="f4">우리A.I는 왜 만들어졌나요?</div>
    <div class="d-flex align--center">
      <div class="card-left d-flex align--center justify--center">
        <img src="@/../public/img/landing-page/ChildDanger.png" alt="dangerous child" class="example-image">
      </div>
      <div class="card-right justify--center">
        <div class="subtitle">아이는 미래이니까</div>
        <div class="detail">
          <p class="mt-5 mb-5">”아이는  밖에 나가서 뛰고 노는게 일이다” 라는 말처럼</p>
          <p class="mt-5 mb-5">모든 아이는 몸을 움직이고 놀면서 세상을 배웁니다</p>
          <p class="mt-5 mb-5">하지만, 아이의 호기심보다도 밖은 많이 위험하며</p>
          <p class="mt-5 mb-5">언제나 부모님의 관심과 시선이 필요합니다</p>
        </div>
      </div>
    </div>
    <hr style="margin:3rem;">
    <div class="d-flex align--center">
      <div class="card-left">
        <div class="subtitle">늘 곁에 있어주고 싶으니까</div>
        <div class="detail">
          <p class="mt-5 mb-5">모든 부모는 늘 마음만은 아이 곁에 있을 것입니다</p>
          <p class="mt-5 mb-5">하지만 불가피하게 아이의 곁을 지킬 수 없을 때</p>
          <p class="mt-5">아이가 위험하지는 않은지 걱정되시는 모든분께</p>
          <p class="mt-4"><span style="font-size:2.7vw; font-weight:bold;">우리A.I</span>가 도움이 되었으면 합니다</p>
        </div>
      </div>
      <div class="card-right d-flex align--center justify--center">
        <img src="@/../public/img/landing-page/ForChild.png" alt="dangerous child" class="example-image">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'why-we-create',
}
</script>

<style>
.example-image {
  width: 90%;
  box-shadow: 3px 3px 10px #a8a8a8;
  border-radius: 2rem;
}

.subtitle {
  color: #52d08f;
  font-weight: bold;
  font-size: 2.5vw;
  text-shadow: 1px 1px 3px #a8a8a8;
  margin-bottom: 3rem;
}

.card-left {
  width: 100%;
}

.card-right {
  width: 100%;
}

.detail {
  font-size: 1.5vw;
}

</style>
