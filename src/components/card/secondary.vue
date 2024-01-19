<script setup>
import { ref, computed } from 'vue';
import IconMore from '@/components/icon/more.vue'

const props = defineProps({
    color: String,
    entry: Object,
})

console.log(props.entry);
const frameClass = ref("frame-" + props.color)

</script>

<template>
    <div :class="frameClass"></div>
    <div class="card-secondary">
        <div class="cont">
            <div class="title">
                <div>{{ entry.category }}</div>
                <IconMore />
            </div>
            <div class="sub-cont">
                <div class="price">{{ entry.price }}$</div>
                <div class="desc">
                    <div class="two-line-text" style="width: fit-content;">{{ entry.description }}</div>
                    <div class="stock">
                        <span>InStore</span>
                        <span>{{ entry.rating.count }}</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@import '@/assets/style.scss';

$margin-offset: -20px;
$sm-frame-height: 38px - $margin-offset;
$lg-frame-height: 42px - $margin-offset;

@each $key, $val in $frame-colors {
    .frame-#{$key} {
        width: 100%;
        height: $sm-frame-height;
        margin-bottom: $margin-offset;
        z-index: -10;
        position: relative;

        @include card-generic($val);

        @include lg {
            height: $lg-frame-height;
        }
    }
}

.card-secondary {
    padding: 37px 14px 28px 30px;
    @include card-generic;

    .cont {
        @include flex-col(7px);

        @include lg {
            @include flex-col(33px);
        }
    }

    .sub-cont {
        @include flex-row(24px);
        align-items: center;

        @include lg {
            @include flex-col(8px);
        }
    }

    .title {
        @include flex-row(47px);
        justify-content: space-between;
        align-items: center;
        font-weight: 500;
    }

    .price {
        font-size: 40px;
        font-weight: 300;
        width: 100%;
    }

    .desc {
        @include flex-row(8px);

        @include lg {
            @include flex-row(8px);
            font-size: 12px;
        }
        font-size: 10px;
        color: $secondary-text;
    }

    .stock {
        color: white;
        font-size: 12px;
        font-weight: 500;
        display: none;

        @include lg {
            display: block;
            text-align: center;
            justify-content: center;
            @include flex-col;
        }
    }
}
</style>