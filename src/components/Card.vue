<template>
  <div class="card-wrapper">
      <div class="my-carousel">
        <div class="btn-wrap top"><i class="material-icons">expand_less</i></div>
        <div class="my-carousel-items">
          <div class="item-wrap" v-bind:key="pic" v-for="pic in productPics" ><img :src="require(`@/assets/carousel/${pic}`)"></div>
        </div>
        <div class="btn-wrap bottom"><i class="material-icons">expand_more</i></div>
      </div>

      <div class="main-img">
        <img src="@/assets/02.png" alt="">
      </div>

      <div class="product-info">

        <div class="product-title">
          {{title}}
        </div>

        <div class="product-rating">
          <div class="raitings">
            <div class="raitings-star"><img src="../assets/full_star.png" alt=""></div>
            <div class="raitings-num">{{ratingsNum}}</div>
          </div>
          <div class="orders-count">Количество заказов: {{ordersCount}}</div>
        </div>

        <hr>

        <div class="product-price">
          <div class="dicount-price">{{discountPrice}} сум</div>
          <div class="real-price">
            <div class="price">{{price}} сум</div>
            <div class="dicount">{{discount}}%</div>
          </div>
        </div>

        <div class="product-payment">
          <p>Метод оплаты:</p>
          <div>
            <img src="../assets/payme.png" alt="">
            <img src="../assets/humo.png" alt="">
            <img src="../assets/click.png" alt="">
          </div>
        </div>

        <div class="product-delivery">
          <p>Метод доставки:</p>
          <div>
            <div><img src="../assets/delivery.png" alt=""><span>Доставка продавца</span></div>
            <div><img src="../assets/ad-product.png" alt=""><span>Самовызов</span></div>
          </div>
        </div>

        <hr>

        <div class="product-amount">
          <p>Количество</p>
          <div class="amount-wrapper">
            <div class="counter-wrap">
              <div class="decrease"><i class="material-icons">remove</i></div>
              <input class="counter" value="123">
              <div class="increase"><i class="material-icons">add</i></div>
            </div>
            <div class="amount"><i class="material-icons">done</i><span>в наличии {{amount}} шт.</span></div>
          </div>
        </div>

        <div>
          <div class="buttons">
              <button class="buy-btn buttons-item">Купить в один клик</button>
              <button class="contact-btn buttons-item">Связаться с продавцом</button>
          </div>
          <hr>
          <div class="delivery-cost">
              <p>
                <span>* Стоимость доставки заказов до 40 000 сум  - договорная</span>
                <span>** Бесплатная доставка при заказе от 40 000 сум</span>
              </p>
          </div>
        </div>
      </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: () => 'This is the product title'
    },
    rating: {
      type: Number,
      default: () => 0
    },
    ratingsNum: {
      type: Number,
      default: () => 0
    },
    ordersCount: {
      type: Number,
      default: () => 0
    },
    price: {
      type: Number,
      default: () => 0
    },
    discount: {
      type: Number,
      default: () => 0
    },
    amount: {
      type: Number,
      default: () => 0
    },
    productPics: {
      type: Array,
      default: () => []
    },
  },
  computed: {
    discountPrice() {
      return this.price - ((this.price/100) * this.discount)
    }
  }
}
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Rubik:wght@400;500&display=swap');
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.card-wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-height: 664px;
  max-width: 1239px;
  margin: 0 auto;
  padding: 16px 56px 63px;
  gap: 16px;
}
.my-carousel {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  max-height: 541px;
  position: relative;

  .btn-wrap {
    width: 36px;
    height: 36px;
    border: 1px solid #E0E0E0;
    position: absolute;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #fff;
    border-radius: 4px;
    cursor: pointer;
  }

  .top {
    top: 0;
  }

  .bottom {
    bottom: 0;
  }

  .my-carousel-items {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  overflow: hidden;

  .item-wrap {
    cursor: pointer;
    width: 65px;
    height: 65px;
    border: 1px solid #E0E0E0;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 6px 0;
    border-radius: 4px;
    }

    img {
      width: 30px;
    }
  }
}

.main-img {
  border: 1px solid #E0E0E0;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 4px;

  img {
    margin: 95px;
  }
}
.product-info {
  max-width: 541px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  
  .product-title {
    font-family: 'Rubik', sans-serif;
    font-style: normal;
    font-weight: 500;
    font-size: 20px;
    line-height: 24px;
    color: #2F323D;
  }
}
.product-rating {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 322px;
  height: 42px;
  margin-bottom: 14px;

  .raitings {
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 32px;
    width: 140px;
    
    .raitings-star {
      display: flex;
    }
    
    .raitings-num {
      font-family: 'Rubik', sans-serif;
      font-style: normal;
      font-weight: normal;
      font-size: 11px;
      line-height: 15px;
      color: #596178;
      text-align: center;
    }
  }
  .orders-count {
    font-family: 'Rubik', sans-serif;
    font-style: normal;
    font-weight: normal;
    font-size: 11px;
    line-height: 15px;
    color: #596178;
    text-align: center;
  } 
}
.product-price {
  margin-top: 24px;
  margin-bottom: 16px;
}
.dicount-price {
  font-family: 'Rubik', sans-serif;
  font-style: normal;
  font-weight: 500;
  font-size: 24px;
  line-height: 30px;
  color: #2F323D;
  margin-bottom: 8px;
}
.real-price {
  display: flex;
  width: 163px;
  justify-content: space-between;
  .price {
    font-family: 'Rubik', sans-serif;
    font-style: normal;
    font-weight: normal;
    font-size: 13px;
    line-height: 15px;
    color: #596178;
    text-decoration: line-through;
  }
  .dicount{
    width: 42px;
    height: 23px;
    background: #FF5530;
    border-radius: 6px;
    font-family: Rubik;
    font-style: normal;
    font-weight: normal;
    font-size: 13px;
    line-height: 18px;
    text-align: center;
    display: flex;
    align-items: center;
    justify-content: center;
    color: #FFFFFF;
  }
}
.product-payment {
  font-family: 'Rubik', sans-serif;
  font-style: normal;
  font-weight: normal;
  font-size: 13px;
  line-height: 15px;
  color: #596178;
  display: flex;
  width: 295px;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 16px;
  div {
    display: flex;
    justify-content: space-between;
    align-items: center;
    img {
      width: 50px;
      margin: 0 8px;
    };
  }
}
.product-delivery {
  font-family: 'Rubik', sans-serif;
  font-style: normal;
  font-weight: normal;
  font-size: 13px;
  line-height: 15px;
  color: #596178;
  display: flex;
  width: 416px;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 16px;
  div {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 0 10px;
    img {
      margin-right: 5px;
    };
    span {
      color: #2F323D;;
    }
  }
}
.product-amount {
  font-family: Rubik;
  font-style: normal;
  font-weight: normal;
  font-size: 13px;
  line-height: 15px;
  color: #2F323D;
  margin: 16px 0 38px;
  
  .amount-wrapper {
    display: flex;
    margin-top: 14px;
    
    .counter-wrap {
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: 42px;
      .increase, .decrease {
        width: 42px;
        height: 100%;
        background-color: #fff;
        border: 1px solid #E0E0E0;
        border-radius: 4px;
        display: flex;
        justify-content: center;
        align-items: center;
        cursor: pointer;
        transition: 0.3s;
        &:hover {
          i {
            color: #000;
          }
        }
        i {
          color: #ccc;
        }
      } 
      .counter {
        width: 60px;
        height: 100%;
        background-color: #F6F6F6;
        text-align: center;
        border: 1px solid #E0E0E0;
        border-radius: 4px;
        padding: 0;
        margin: 0 8px;
      }
    }
    .amount {
      background: #EFEEB4;
      border-radius: 4px;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 0px 8px;
      margin-left: 20px;
      i {
        color: #309975;
        margin-right: 15px;
      }
    }
  }
}
.buttons {
  margin-bottom: 24px;
}
.buttons-item {
  border-radius: 4px;
  font-family: Rubik;
  font-style: normal;
  font-weight: normal;
  font-size: 17px;
  line-height: 24px;
  padding: 8px 32px;
}
.buy-btn {
  background-color: #309975;
  border: 1px solid #309975;
  color: #fff;
  margin-right: 16px;
  cursor: pointer;
  transition: 0.3s;
  &:hover {
    background-color: #fff;
    border: 1px solid #E0E0E0;;
    color: #2F323D;
  }
}
.contact-btn {
  background-color: #fff;
  border: 1px solid #E0E0E0;;
  color: #2F323D;
  cursor: pointer;
  transition: 0.3s;
  &:hover {
    background-color: #309975;
    border: 1px solid #309975;
    color: #fff;
  }
}
.delivery-cost {
  margin-top: 16px;
  p {
    font-family: Rubik;
    font-style: normal;
    font-weight: normal;
    font-size: 15px;
    line-height: 21px;
    color: #596178;
    span {
      display: block;
    }
  }
}



</style>