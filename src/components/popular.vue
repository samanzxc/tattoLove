<template>
  <main>
    <p class="title">Популярные категории <span class="blue">&darr;</span></p>
    <div class="popular__block">
      <div class="teg"><p>Геометрия</p></div>
      <div class="photo__block">
        <div class="photo">
          <img src="/src/assets/img/geom1.jpg" alt="" />
          <img src="/src/assets/img/geom2.jpg" alt="" />
          <img src="/src/assets/img/geom3.jpg" alt="" />
          <img src="/src/assets/img/geom4.jpg" alt="" />
        </div>
        <div class="text r">
          <p>
            <span class="blue">Геометрические татуировки</span> представляют собой красивое
            сочетание искусства и математики, создавая изящные и сложные узоры с помощью простых
            форм, Лучшая идея для тех кто хорош учился и линий.
          </p>
        </div>
      </div>
    </div>

    <div class="popular__block rever">
      <div class="teg"><p>Цветы</p></div>
      <div class="photo__block">
        <div class="text">
          <p>
            <span class="blue">Цветочные татуировки</span> являются символом красоты, природы и
            женственности. Они варьируются от нежных и изящных изображений роз и лилий до ярких и
            экзотических орхидей и лотосов. Подойдук больше для женской аудитории!
          </p>
        </div>
        <div class="photo">
          <img src="/src/assets/img/flow1.jpg" alt="" />
          <img src="/src/assets/img/flow2.jpg" alt="" />
          <img src="/src/assets/img/flow3.jpg" alt="" />
          <img src="/src/assets/img/flow4.jpg" alt="" />
        </div>
      </div>
    </div>

    <div class="popular__block">
      <div class="teg"><p>Животные</p></div>
      <div class="photo__block">
        <div class="photo">
          <img src="/src/assets/img/animal1.jpg" alt="" />
          <img src="/src/assets/img/animal2.jpg" alt="" />
          <img src="/src/assets/img/animal3.jpg" alt="" />
          <img src="/src/assets/img/animal4.jpg" alt="" />
        </div>
        <div class="text">
          <p>
            <span class="blue">Татуировки с изображением животных</span> символизируют силу,
            мудрость и связь с природой. Каждый вид животного несет в себе уникальное значение: львы
            олицетворяют власть и храбрость, волки – верность и свободу, птицы – свободу и
            стремление к высотам. Потходит как к Женской так и мужской аудитории
          </p>
        </div>
      </div>
    </div>

    <div class="popular__block rever">
      <div class="teg"><p>Абстракции</p></div>
      <div class="photo__block">
        <div class="text">
          <p>
            <span class="blue">Абстрактные татуировки</span> представляют собой искусство без
            границ, где фантазия и креативность художника воплощаются в необычных формах и узорах.
            Эти татуировки часто состоят из сочетания линий, точек, геометрических фигур и
            асимметричных композиций, создающих уникальные и загадочные образы
          </p>
        </div>
        <div class="photo">
          <img src="/src/assets/img/abstract1.jpg" alt="" />
          <img src="/src/assets/img/abstract2.jpg" alt="" />
          <img src="/src/assets/img/abstract3.jpg" alt="" />
          <img src="/src/assets/img/abstract4.jpg" alt="" />
        </div>
      </div>
    </div>

    <div class="popular__block">
      <div class="teg"><p>Портреы</p></div>
      <div class="photo__block">
        <div class="photo">
          <img src="/src/assets/img/portrer1.jpg" alt="" />
          <img src="/src/assets/img/portrer2.jpg" alt="" />
          <img src="/src/assets/img/portrer3.jpg" alt="" />
          <img
            src="https://i.pinimg.com/736x/67/05/a1/6705a1f82ccad25380fb955760c4177a.jpg"
            alt=""
          />
        </div>
        <div class="text">
          <p>
            <span class="blue">Портретные татуировки</span> — это реалистичные изображения людей,
            животных или вымышленных персонажей, как угодно, они выполненные с высокой точностью и
            детализацией. Такие татуировки часто имеют глубокое личное значение и являются способом
            увековечить память о близких, кумирах или любимых питомцах.
          </p>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
.teg {
  background-color: var(--teg-color);
  padding: 10px;
  border-radius: 15px;
  font-weight: bold;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 30px;
}
.photo img {
  width: 450px;
  height: 400px;
  border-radius: 10px;
}
.title {
  font-weight: bold;
  font-size: 25px;
  margin-bottom: 100px;
}
.popular__block {
  display: flex;
  flex-direction: column;
  margin-bottom: 170px;
  align-items: start;
}
.rever {
  align-items: end;
}

.photo__block {
  display: flex;
  align-items: start;
  column-gap: 30px;
}
.all {
  background-color: transparent;
  border: 1px black solid;
  padding: 10px;
  border-radius: 15px;
  cursor: pointer;
  font-size: 17px;
  font-weight: bold;
}
.all:hover {
  background-color: #0000001c;
}
.photo {
  display: flex;
  flex-wrap: wrap;
  width: 920px;
  gap: 20px;
}
.text {
  width: 250px;
  font-size: 21px;
  font-weight: bold;
  letter-spacing: 1.5px;
}
@media (max-width: 1615px) {
  .photo {
    width: 670px;
    gap: 20px;
  }
  .photo img {
    width: 325px;
    height: 295px;
  }
  .text {
    width: 220px;
    font-size: 17px;
  }
}
@media (max-width: 1340px) {
  .photo {
    width: 450px;
  }
  .photo img {
    width: 215px;
    height: 210px;
  }
}
@media (max-width: 1240px) {
  .photo {
    width: 320px;
  }
  .photo img {
    width: 150px;
    height: 140px;
  }
}
@media (max-width: 1024px) {
  .photo {
    width: 240px;
  }
  .photo img {
    width: 110px;
    height: 116px;
  }
  .text{
    font-size: 13px;
  }
  .teg{
    font-size: 12px;
    padding: 8px;
  }
}
@media (max-width: 875px) {
  .photo {
    width: 180px;
    gap: 10px;
  }
  .photo img {
    width: 85px;
    height: 90px;
  }
  .text{
    width: 160px;
    font-size: 11px;
    letter-spacing: normal;
  }
  .photo__block{
    column-gap: 10px;
  }
}
@media (max-width: 670px) {
  .photo {
    width: 134px;
  }
  .photo img {
    width: 62px;
    height: 70px;
  }
  .text{
    width: 130px;
    font-size: 10px;
  }
  .teg{
    font-size: 10px;
    padding: 8px;
    margin-bottom: 10px;
  }
}
</style>
