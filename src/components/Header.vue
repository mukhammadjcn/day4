<template>
    <header class="header row">
        <form action="#" class="header__search">
            <input type="text" placeholder="Search">
            <svg width="14" height="14" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M11.2028 9.85174C11.1006 9.74954 11.0866 9.57314 11.165 9.45134C11.781 8.50354 12.1422 7.37514 12.1422 6.16274C12.1422 2.81394 9.4178 0.0909424 6.0718 0.0909424C2.723 0.0909424 0 2.81394 0 6.16274C0 9.51014 2.723 12.2331 6.0718 12.2331C7.3752 12.2331 8.582 11.8145 9.5732 11.1117C9.6894 11.0277 9.8644 11.0389 9.9666 11.1397L12.1366 13.3097C12.1506 13.3237 12.166 13.3377 12.1814 13.3489C12.2066 13.3699 12.3116 13.4679 12.4124 13.5701L12.67 13.8263C12.7722 13.9271 12.9374 13.9271 13.0382 13.8263L13.923 12.9415C14.0252 12.8393 14.0252 12.6741 13.9244 12.5719L11.2028 9.85174ZM9.744 8.99074C9.5438 9.25114 9.3184 9.48914 9.0692 9.70054C8.26 10.3879 7.2142 10.8051 6.0718 10.8051C3.5112 10.8051 1.428 8.72194 1.428 6.16274C1.428 3.60354 3.5112 1.51894 6.0718 1.51894C8.631 1.51894 10.7142 3.60214 10.7142 6.16274C10.7142 7.22674 10.3488 8.20674 9.744 8.99074Z" fill="#CACCCF"/>
            </svg>
        </form>
        <div class="user row">
            <span class="user__notification">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M20.2223 18.3815C20.1479 18.2135 20.1311 17.9687 20.1935 17.7959C20.6759 16.4279 21.1703 15.0671 21.6839 13.7087C22.2311 12.2663 22.6559 10.8143 22.4423 9.2375C22.1999 7.4471 21.4655 5.8967 20.1431 4.6727C19.4975 4.0775 18.7415 3.6095 17.9927 3.0527C18.0503 2.8943 18.1439 2.6471 18.2351 2.3999C18.3839 1.9919 18.2687 1.6727 17.9255 1.5455C17.5727 1.4159 17.2775 1.5623 17.1119 1.9583C17.0039 2.2127 16.9079 2.4695 16.8023 2.7335C15.8039 2.4887 14.8175 2.3903 13.8167 2.5343C10.8335 2.9615 8.6807 4.5263 7.5167 7.3175C6.8039 9.0335 6.2159 10.8023 5.5823 12.5495C5.5055 12.7655 5.3831 12.8927 5.1743 12.9863C4.1135 13.4615 3.0599 13.9511 1.9991 14.4335C1.7159 14.5607 1.5047 14.7407 1.5119 15.0767C1.5191 15.4247 1.7639 15.5639 2.0519 15.6671C4.0319 16.3775 6.0071 17.0951 7.9919 17.7911C8.2895 17.8967 8.3927 18.0143 8.3759 18.3431C8.2751 20.5463 10.3415 22.1879 12.4799 21.6287C13.3463 21.4031 14.0063 20.8967 14.5031 20.1431C14.6063 20.1791 14.6999 20.2127 14.7935 20.2439C16.8047 20.9639 18.8159 21.6839 20.8271 22.4087C21.1295 22.5167 21.4079 22.5623 21.6575 22.3055C21.9167 22.0367 21.8087 21.7607 21.6743 21.4775C21.1799 20.4527 20.6879 19.4231 20.2223 18.3815ZM11.1191 20.4599C10.1615 20.1839 9.5279 19.3247 9.5951 18.3455C10.8479 18.7919 12.0743 19.2311 13.3055 19.6703C12.9551 20.3423 11.9495 20.6999 11.1191 20.4599Z" fill="#CACCCF"/>
                </svg>
                <span class="user__notification-num">9</span>
                <button class="hamburgerBtn" @click="showMenu()">
                    {{isMenu ? '=' : 'x'}}
                </button>
            </span>
            <div class="user__img">
                <img src="https://media-exp1.licdn.com/dms/image/C4D03AQEE-UE_6Lf3Iw/profile-displayphoto-shrink_100_100/0/1581420997532?e=1630540800&v=beta&t=lWn-FbiWjJRjKiWsQCB4Yr2esExmFf5r-7K-0VIOSjQ" alt="">
            </div>
        </div>
    </header>
</template>

<script>
export default {
    name : "Header",
    data(){
        return{
            isMenu : true
        }
    },
    methods : {
        showMenu(){
            var nav =  document.querySelector(".sidebar")
            if(this.isMenu){
                nav.style.left = "0"
            } else{
                nav.style.left = "-100%"
            }
            this.isMenu =! this.isMenu
        }
    }
}
</script>

<style lang="scss">
.header{
    width: 100%;
    justify-content: space-between;
    &__search{
        position: relative;
        input{
            background: #FFFFFF;
            border-radius: 100px;     
            width: 350px;
            height: 40px;  
            border: none;
            padding: 12px 42px;
            font-size: 13px;
            line-height: 16px;
            color: #A0A4A8;
            outline: none;
            &::placeholder{
                font-size: 13px;
                line-height: 16px;
                color: #A0A4A8;
            }
        }
        svg{
            position: absolute;
            top: 50%;
            left: 16px;
            transform: translateY(-50%);
        }
    }
}
.user{
    gap: 24px;
    &__img{
        img{
            width: 56px;
            height: 56px;
            object-fit: cover;
            border-radius: 50%;
            border: 3px solid #E8E8E8;
        }
    }
    &__notification{
        position: relative;
        &-num{
            background: #FF6760;
            width: 20px;
            height: 20px;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            font-weight: bold;
            font-size: 10px;
            line-height: 12px;
            position: absolute;
            color: #FFFFFF;
            top: 0;
            right: 0;
            transform: translate(50%, -50%);
            border: 2px solid white;
        }
    }
}
.hamburgerBtn{
    display: none;
}

@media (max-width:776px) {
    .header{
        &__search{
            input{
                width: auto;
            }
        }
    }
}

@media(max-width:500px){
    .header{
        &__search{
            display: none;
        }
    }
    .hamburgerBtn{
        font-size: 24px;
        display: block;
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        right: -150%;
    }
    .user{
        width: 90%;
        flex-direction: row-reverse;
        justify-content: space-between;
    }
}
</style>