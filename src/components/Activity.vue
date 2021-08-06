<template>
    <div class="activity">
        <h1 class="btitle">Appointment Activity</h1>
        <div class="activity__chart"> 
            <div class="activity__row info row" v-for="(item, index) in clients" :key="index">
                <span class="activity__name row">
                    <img :src="item.img" class="activity__img" alt="">
                    <span>{{item.name}}</span>
                </span>
                <span class="activity__email">{{item.email}}</span>
                <span class="activity__date">{{item.date}}</span>
                <span class="activity__time">{{item.time}}</span>
                <span class="activity__doctor">{{item.doctor}}</span>
                <span class="activity__condition">{{item.condition}}</span>
                <span class="activity__buttons row">
                    <svg @click="openModal()" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M0 15.3664C0.4448 13.84 0.888 12.3136 1.3328 10.7872C1.368 10.6656 1.4048 10.544 1.4368 10.4224C1.488 10.2384 1.584 10.0896 1.7312 9.9664C1.8688 9.8528 1.9904 9.7168 2.1168 9.5904C4.2016 7.5248 6.2864 5.45921 8.3696 3.39201C8.4176 3.34401 8.4592 3.28961 8.4928 3.24801C8.776 3.53281 9.0416 3.80001 9.3376 4.09761C9.3056 4.12001 9.2432 4.15201 9.1952 4.20001C7.0352 6.35521 4.8768 8.5104 2.7216 10.6704C2.6448 10.7488 2.5808 10.856 2.5504 10.9616C2.2912 11.8176 2.0448 12.6784 1.7888 13.5376C1.7568 13.6448 1.7728 13.712 1.8544 13.7856C1.9872 13.9056 2.104 14.0432 2.2384 14.1616C2.2848 14.2016 2.3728 14.232 2.4288 14.2176C3.2896 13.9712 4.1488 13.72 5.0064 13.4608C5.08 13.4384 5.1488 13.376 5.2064 13.3168C7.3968 11.1328 9.584 8.9456 11.7712 6.76001C11.8128 6.71841 11.848 6.67201 11.872 6.64481C12.1824 6.95521 12.4832 7.256 12.8128 7.5856C12.7984 7.5952 12.7408 7.6192 12.7008 7.6592C10.544 9.7952 8.384 11.9264 6.2384 14.0736C5.9392 14.3744 5.6144 14.56 5.2128 14.6736C3.7888 15.0768 2.3712 15.5024 0.9504 15.92C0.856 15.9472 0.76 15.9728 0.6656 16H0.5376C0.4688 15.9696 0.3984 15.9424 0.3296 15.9104C0.1376 15.8208 0.072 15.6384 0 15.4608V15.3664ZM4.3024 12.7152C4.2608 12.4496 4.216 12.2064 4.1872 11.9632C4.1728 11.848 4.1264 11.8016 4.0144 11.7808C3.7408 11.728 3.4704 11.6592 3.2176 11.6032C5.4864 9.3296 7.7552 7.05441 10.0096 4.79361C10.3696 5.15361 10.7456 5.52801 11.1088 5.88961C8.8624 8.1424 6.5952 10.416 4.3024 12.7152ZM10.8368 1.02562C11.0416 0.825621 11.2464 0.612821 11.4656 0.414422C12.0944 -0.151977 12.9136 -0.139177 13.5264 0.459222C14.2032 1.11842 14.8704 1.78562 15.5296 2.46242C16.1536 3.10082 16.144 3.95521 15.5216 4.59201C15.3344 4.78401 15.1408 4.97121 14.9616 5.14721C13.592 3.77921 12.224 2.41282 10.8368 1.02562ZM9.168 2.53602C9.4784 2.24482 9.7968 1.94562 10.0992 1.66082C11.5328 3.09442 12.9584 4.52161 14.3968 5.96001C14.0976 6.24001 13.776 6.54241 13.4656 6.83361L9.168 2.53602Z" fill="#A0A4A8"/>
                    </svg>
                    <svg @click="removeItem(item)" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M4.00952 14.3248C4.02552 14.7024 4.33592 15 4.71352 15H11.2911C11.6687 15 11.9807 14.7024 11.9951 14.3248L12.4655 4.408H3.53912L4.00952 14.3248ZM9.48952 6.872C9.48952 6.7136 9.61752 6.5856 9.77592 6.5856H10.2335C10.3919 6.5856 10.5199 6.7152 10.5199 6.872V12.5376C10.5199 12.696 10.3903 12.824 10.2335 12.824H9.77592C9.61752 12.824 9.48952 12.696 9.48952 12.5376V6.872ZM7.48792 6.872C7.48792 6.7136 7.61592 6.5856 7.77432 6.5856H8.23192C8.39032 6.5856 8.51832 6.7152 8.51832 6.872V12.5376C8.51832 12.696 8.39032 12.824 8.23192 12.824H7.77432C7.61592 12.824 7.48792 12.696 7.48792 12.5376V6.872ZM5.48472 6.872C5.48472 6.7136 5.61272 6.5856 5.76952 6.5856H6.22712C6.38552 6.5856 6.51352 6.7152 6.51352 6.872V12.5376C6.51352 12.696 6.38392 12.824 6.22712 12.824H5.76952C5.61112 12.824 5.48472 12.696 5.48472 12.5376V6.872ZM12.7775 1.7216H9.74392V1.1472C9.74392 1.0656 9.67832 1 9.59672 1H6.40952C6.32792 1 6.26232 1.0656 6.26232 1.1472V1.7216H3.22712C2.98392 1.7216 2.78552 1.9184 2.78552 2.1632V3.552H13.2191V2.1632C13.2191 1.92 13.0223 1.7216 12.7775 1.7216Z" fill="#FF6760"/>
                    </svg>
                </span>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name : "Activity",
    data(){
        return{
            clients : [
                {
                    id : 0,
                    name : "Name",
                    email :"Email",
                    date : "Date",
                    time : "Visit Time",
                    doctor : "Doctor",
                    condition : "Conditions",
                },
                {
                    id : 1,
                    img : "https://picsum.photos/100/100",
                    name : "Leslie Alexander",
                    email :"lesie.alexander@example.com",
                    date : "10/10/2020",
                    time : "09:15-09:45am",
                    doctor : "Dr. Jacob Jones",
                    condition : "Mumps Stage II",
                },
                {
                    id : 2,
                    img : "https://picsum.photos/100/101",
                    name : "Ronald Richards",
                    email :"ronald.richards@example.com",
                    date : "10/12/2020",
                    time : "12:00-12:45pm",
                    doctor : "Dr. Theresa Webb",
                    condition : "Depression",
                },
                {
                    id : 3,
                    img : "https://picsum.photos/100/102",
                    name : "Jane Cooper",
                    email :"jane.cooper@example.com",
                    date : "10/13/2020",
                    time : "01:15-01:45pm",
                    doctor : "Dr. Jacob Jones",
                    condition : "Arthritis",
                },
                {
                    id : 4,
                    img : "https://picsum.photos/100/103",
                    name : "Robert Fox",
                    email :"robert.fox@gmail.com",
                    date : "10/14/2020",
                    time : "02:00-02:45pm",
                    doctor : "Dr. Arlene McCoy",
                    condition : "Fracture",
                },
                {
                    id : 5,
                    img : "https://picsum.photos/100/104",
                    name : "Jenny Wilson",
                    email :"jenny.wilson@example.com",
                    date : "10/15/2020",
                    time : "12:00-12:45pm",
                    doctor : "Dr. Esther Howard",
                    condition : "Depression",
                }
            ]
        }
    },
    methods : {
        removeItem(d){
            var id = d.id
            let index = this.clients.findIndex(rank => rank.id === id);
            this.clients.splice(index, 1)
        },
    }
}
</script>

<style lang="scss">
.activity{
    width: 100%;
    background: #FFFFFF;
    box-shadow: 0px 12px 26px rgba(16, 30, 115, 0.06);
    border-radius: 8px;
    &__change{
        position: absolute;
        top: 50%;
        background: #b3a1a1;
        width: 200px;
        height: 200px;
        display: none;
    }
    .btitle{
        margin-bottom: 18px;
        padding: 24px;
    }
    &__row{
        padding: 18px 24px;
        border-bottom: 1px solid #DBDDE0;
        &:first-child{
            font-weight: bold !important;
            color: #25282B !important;
            background: #FAFAFA;
            .activity__buttons{
                visibility: hidden;
            }
            .activity__img{
                display: none;
            }
        }
    }
    &__name{
        flex-basis: 23%;
        gap: 12px;
    }
    &__email{
        flex-basis: 23%;
    }
    &__date{
        flex-basis: 10%;
    }
    &__time{
        flex-basis: 15%;
    }
    &__doctor{
        flex-basis: 12%;
    }
    &__condition{
        flex-basis: 12%;
    }
    &__buttons{
        flex-basis: 5%;
        justify-content: center;
        gap: 16px;
    }
    &__img{
        width: 32px;
        height: 32px;
        object-fit: cover;
        border-radius: 50%;
    }
}

@media (max-width:776px) {
    .activity{
        &__email, &__date, &__time, &__doctor, &__condition{
            display: none;
        }
        &__row{
            justify-content: space-between;

        }
        &__name{
            flex-basis: 50%;
        }
    }
}
</style>