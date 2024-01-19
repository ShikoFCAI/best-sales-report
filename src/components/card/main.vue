<template>
    <div class="container">
        <div class="card-main">
            <img src="/pfp.png" />
            <div class="sub">
                <span>Report for</span>
                <h1>Best Sales</h1>
            </div>
        </div>
        <div class="tab">
            <span>Daily</span>
            <span style="color: white;">Weekly</span>
            <span>Monthly</span>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@import '@/assets/style.scss';

.container{
    @include max-card-width;
}

.card-main {
    @include card-generic($card-secondary);
    @include flex-row(1.25rem);
    padding: 30px 20px 20px;
    align-items: center;

    @include lg {
        @include flex-col(2rem);
        max-width: 215px;
    }

    img {
        border-radius: 9999px;
        border: white 2.5px solid;
    }

    .sub {
        @include flex-col(0.25rem);

        h1 {
            width: fit-content;
            font-size: 24px;
            margin: 0;
            font-weight: 300;

            @include lg{
                font-size: 40px;
                letter-spacing: 12px;
            }
        }

        span {
            font-size: 15px;
            color: $secondary-text;
        }

        @include lg {
            @include flex-col(10px);
        }
    }
}

.tab {
    @include flex-row;
    @include card-generic;
    justify-content: space-between;
    padding: 40px 20px 33px;
    font-size: 18px;
    color: #7078C9;

    margin-top: -20px;
    z-index: -10;
    position: relative;

    @include lg {
        min-width: 215px;
        @include flex-col(21px);
    }
}
</style>