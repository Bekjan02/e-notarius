<template>
    <section class="gg">
        <button @click="store.state.registryClientBigModal = true" class="gg-btn">Добавить нового
            пользователя</button>
        <div class="gg-head">
            <div class="gg-info">
                <div class="gg-search">
                    <input type="text" placeholder="Поиск по ключевому слову" class="gg-input">
                    <Search />
                </div>
                <button class="gg-excel">Экспортировать в Exсel
                    <ExcelIcon />
                </button>
            </div>
            <div class="gg-info another">
                <div class="gg-content">
                    <div class="gg-label">
                        <p class="gg-another">Период регистрации</p>
                        <div class="gg-wrapper">
                            <input type="number" placeholder="__/__/____">
                            по
                            <input type="number" placeholder="__/__/____">
                        </div>
                    </div>
                </div>
                <div class="gg-content">
                    <p>Роль пользователя</p>
                    <Accordeon style="border:unset; width:320px;"
                        :options="['Пользователь', 'Нотариус', 'Должностное лицо ОМСУ', 'Стажер']" />
                </div>
                <div class="gg-content">
                    <p>Кем зарегистрировано</p>
                    <Accordeon style="border:unset; width:320px;"
                        :options="['Алименты', 'Заработная плата', 'Пенсии', 'Стажер']" />
                </div>
            </div>
            <div class="gg-info">
                <button class="gg-filter">
                    <svg width="25" height="24" viewBox="0 0 25 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path
                            d="M13.5002 21.0031L21.8002 12.7031C22.8002 11.8031 22.8002 10.3031 21.8002 9.30313L16.2002 3.70312C15.3002 2.70312 13.8002 2.70312 12.8002 3.70312L3.2002 13.3031C2.2002 14.2031 2.2002 15.7031 3.2002 16.7031L7.5002 21.0031H22.5002M5.5002 11.0031L14.5002 20.0031"
                            stroke="#F6F6F6" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
                    </svg>
                    Очистить фильтр
                </button>
            </div>
        </div>
        <div class="gg__adaptive">
            <div class="gg__left">
                <label class="tooltip">
                    <svg width="22" height="22" viewBox="0 0 22 22" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path
                            d="M11 21C16.5228 21 21 16.5228 21 11C21 5.47715 16.5228 1 11 1C5.47715 1 1 5.47715 1 11C1 16.5228 5.47715 21 11 21Z"
                            stroke="#1BAA75" stroke-width="2" />
                        <path
                            d="M10.9998 16.9996C11.6625 16.9996 12.1998 16.4624 12.1998 15.7996C12.1998 15.1369 11.6625 14.5996 10.9998 14.5996C10.3371 14.5996 9.7998 15.1369 9.7998 15.7996C9.7998 16.4624 10.3371 16.9996 10.9998 16.9996Z"
                            fill="#1BAA75" />
                        <path
                            d="M8.75 7.2497C8.75005 6.85567 8.85358 6.46856 9.05023 6.1271C9.24688 5.78565 9.52975 5.50183 9.87054 5.30403C10.2113 5.10623 10.5981 5.0014 10.9921 5.00001C11.3861 4.99863 11.7736 5.10075 12.1158 5.29616C12.458 5.49156 12.7428 5.77339 12.9418 6.11346C13.1409 6.45353 13.2471 6.8399 13.2499 7.23392C13.2528 7.62794 13.152 8.0158 12.9579 8.35867C12.7637 8.70155 12.4829 8.98743 12.1436 9.1877C11.5736 9.5249 11 10.0373 11 10.6997V12.1997"
                            stroke="#1BAA75" stroke-width="2" stroke-linecap="round" />
                    </svg><input type="checkbox" /><span>Таблицу можно скролить по<br />
                        горизонтали либо Вы можете<br />
                        использовать кнопки для<br />
                        перемещения по таблице<svg width="24" height="24" viewBox="0 0 24 24" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path d="M6.64645 6.35355L17.9602 17.6673" stroke="#1BAA75" stroke-width="2"
                                stroke-linecap="round" stroke-linejoin="round" />
                            <path d="M6.35355 17.3536L17.6673 6.03985" stroke="#1BAA75" stroke-width="2"
                                stroke-linecap="round" stroke-linejoin="round" />
                        </svg></span>
                </label>
            </div>
            <div class="gg__right">
                <svg @click="handleScrollLeft" width="40" height="40" viewBox="0 0 40 40" fill="none"
                    xmlns="http://www.w3.org/2000/svg">
                    <rect x="0.5" y="0.5" width="39" height="39" fill="white" />
                    <g clip-path="url(#clip0_2412_22742)">
                        <path d="M22 16L18 20L22 24" stroke="#1BAA75" stroke-width="2" stroke-linejoin="round" />
                    </g>
                    <rect x="0.5" y="0.5" width="39" height="39" stroke="#EFEFEF" />
                    <defs>
                        <clipPath id="clip0_2412_22742">
                            <rect width="16" height="16" fill="white" transform="translate(28 12) rotate(90)" />
                        </clipPath>
                    </defs>
                </svg>
                <svg @click="handleScrollRight" width="40" height="40" viewBox="0 0 40 40" fill="none"
                    xmlns="http://www.w3.org/2000/svg">
                    <rect x="0.5" y="0.5" width="39" height="39" fill="white" />
                    <g clip-path="url(#clip0_2412_22746)">
                        <path d="M18 24L22 20L18 16" stroke="#1BAA75" stroke-width="2" stroke-linejoin="round" />
                    </g>
                    <rect x="0.5" y="0.5" width="39" height="39" stroke="#EFEFEF" />
                    <defs>
                        <clipPath id="clip0_2412_22746">
                            <rect width="16" height="16" fill="white" transform="matrix(0 -1 1 0 12 28)" />
                        </clipPath>
                    </defs>
                </svg>
            </div>
        </div>
        <div ref="container" class="gg-table">
            <table>
                <thead>
                    <tr>
                        <th>
                            <Sort title="ФИО пользователя" style="white-space: nowrap" />
                        </th>
                        <th>
                            <Sort title="Роль пользователя" style="white-space: nowrap; gap: 80px;" />
                        </th>
                        <th>
                            <Sort title="Логин" style="white-space: nowrap;" />
                        </th>
                        <th>
                            <Sort title="Пин" style="white-space: nowrap;" />
                        </th>
                        <th>
                            <Sort title="Мобильный телефон" style="white-space: nowrap;" />
                        </th>
                        <th>
                            <Sort title="E-mail" style="white-space: nowrap;" />
                        </th>
                        <th>
                            <Sort title="Дата и время регистрации" style="white-space: nowrap;" />
                        </th>
                        <th>
                            <Sort title="Кем зарегистрировано" style="white-space: nowrap;" />
                        </th>
                        <th>
                            Действие
                        </th>
                    </tr>
                </thead>

                <tbody>
                    <tr v-for="(_, i) in paginatedItems" :key="i">
                        <td style="white-space: nowrap"> Биримкулов Нурамир Тагдырович </td>
                        <td>Должностное лицо ОМСУ</td>
                        <td>login_example</td>
                        <td style="white-space: nowrap">20102199000001</td>
                        <td>0555 26 29 30</td>
                        <td>nuramir@example.org</td>
                        <td>01.01.2022 00:00:00</td>
                        <td>nuramir@example.org</td>
                        <td>
                            <div class="gg-table_icons">
                                <svg style="cursor:pointer;" width="44" height="44" viewBox="0 0 44 44" fill="none"
                                    xmlns="http://www.w3.org/2000/svg">
                                    <path
                                        d="M13.0583 20.8694C12.9865 21.417 13.3722 21.9191 13.9198 21.9908C14.4674 22.0626 14.9695 21.6769 15.0413 21.1293L13.0583 20.8694ZM15.4788 24.6293C15.2745 24.1162 14.6929 23.8659 14.1798 24.0703C13.6667 24.2747 13.4164 24.8563 13.6208 25.3694L15.4788 24.6293ZM13.0498 29.9993C13.0498 30.5516 13.4975 30.9993 14.0498 30.9993C14.6021 30.9993 15.0498 30.5516 15.0498 29.9993H13.0498ZM14.0498 24.9993V23.9993C13.4975 23.9993 13.0498 24.447 13.0498 24.9993H14.0498ZM19.0498 25.9993C19.6021 25.9993 20.0498 25.5516 20.0498 24.9993C20.0498 24.447 19.6021 23.9993 19.0498 23.9993V25.9993ZM15.0413 21.1293C15.4991 17.6369 18.4806 15.0286 22.0029 15.0391L22.0089 13.0391C17.4802 13.0256 13.6469 16.3791 13.0583 20.8694L15.0413 21.1293ZM22.0029 15.0391C25.5252 15.0496 28.491 17.6757 28.9279 21.1708L30.9125 20.9228C30.3507 16.4291 26.5375 13.0526 22.0089 13.0391L22.0029 15.0391ZM28.9279 21.1708C29.3648 24.6659 27.1366 27.9413 23.7253 28.8185L24.2234 30.7555C28.6094 29.6276 31.4742 25.4164 30.9125 20.9228L28.9279 21.1708ZM23.7253 28.8185C20.314 29.6957 16.7822 27.9016 15.4788 24.6293L13.6208 25.3694C15.2965 29.5766 19.8374 31.8833 24.2234 30.7555L23.7253 28.8185ZM15.0498 29.9993V24.9993H13.0498V29.9993H15.0498ZM14.0498 25.9993H19.0498V23.9993H14.0498V25.9993Z"
                                        fill="#24334B" />
                                </svg>
                                <svg style="cursor:pointer;" width="44" height="44" viewBox="0 0 44 44" fill="none"
                                    xmlns="http://www.w3.org/2000/svg">
                                    <path
                                        d="M31 15.5014H26V13.8314C25.9765 13.1912 25.7002 12.5864 25.2316 12.1497C24.7629 11.7129 24.1402 11.4798 23.5 11.5014H20.5C19.8598 11.4798 19.2371 11.7129 18.7684 12.1497C18.2998 12.5864 18.0235 13.1912 18 13.8314V15.5014H13C12.7348 15.5014 12.4804 15.6067 12.2929 15.7943C12.1054 15.9818 12 16.2362 12 16.5014C12 16.7666 12.1054 17.0209 12.2929 17.2085C12.4804 17.396 12.7348 17.5014 13 17.5014H14V28.5014C14 29.297 14.3161 30.0601 14.8787 30.6227C15.4413 31.1853 16.2044 31.5014 17 31.5014H27C27.7956 31.5014 28.5587 31.1853 29.1213 30.6227C29.6839 30.0601 30 29.297 30 28.5014V17.5014H31C31.2652 17.5014 31.5196 17.396 31.7071 17.2085C31.8946 17.0209 32 16.7666 32 16.5014C32 16.2362 31.8946 15.9818 31.7071 15.7943C31.5196 15.6067 31.2652 15.5014 31 15.5014ZM20 13.8314C20 13.6714 20.21 13.5014 20.5 13.5014H23.5C23.79 13.5014 24 13.6714 24 13.8314V15.5014H20V13.8314ZM28 28.5014C28 28.7666 27.8946 29.021 27.7071 29.2085C27.5196 29.396 27.2652 29.5014 27 29.5014H17C16.7348 29.5014 16.4804 29.396 16.2929 29.2085C16.1054 29.021 16 28.7666 16 28.5014V17.5014H28V28.5014Z"
                                        fill="#24334B" />
                                    <path
                                        d="M19 26.5C19.2652 26.5 19.5196 26.3946 19.7071 26.2071C19.8946 26.0196 20 25.7652 20 25.5V21.5C20 21.2348 19.8946 20.9804 19.7071 20.7929C19.5196 20.6054 19.2652 20.5 19 20.5C18.7348 20.5 18.4804 20.6054 18.2929 20.7929C18.1054 20.9804 18 21.2348 18 21.5V25.5C18 25.7652 18.1054 26.0196 18.2929 26.2071C18.4804 26.3946 18.7348 26.5 19 26.5ZM25 26.5C25.2652 26.5 25.5196 26.3946 25.7071 26.2071C25.8946 26.0196 26 25.7652 26 25.5V21.5C26 21.2348 25.8946 20.9804 25.7071 20.7929C25.5196 20.6054 25.2652 20.5 25 20.5C24.7348 20.5 24.4804 20.6054 24.2929 20.7929C24.1054 20.9804 24 21.2348 24 21.5V25.5C24 25.7652 24.1054 26.0196 24.2929 26.2071C24.4804 26.3946 24.7348 26.5 25 26.5Z"
                                        fill="#24334B" />
                                </svg>
                            </div>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div> 
        <button class="gg-excel another">Экспортировать в Exсel
            <ExcelIcon />
        </button>
        <BigModal v-show="store.state.registryClientBigModal" />
        <MiniModal v-show="store.state.registryClientMiniModal" />
    </section>
</template>

<script setup>
import { onMounted, ref } from "vue"
import Search from "@/components/icons/Exemple/Search.vue";
import ExcelIcon from '@/views/Icons/ExcelIcon.vue'
import Accordeon from '@/components/global/UI/Info/Accordeon.vue'
import Sort from "@/components/global/Tables/OfferTable/Sort.vue";
import Pagination from "@/components/Pagination/Pagination.vue";
import { useStore } from "vuex";
import BigModal from "@/components/global/modal/RegistryClient/BigModal.vue";
import MiniModal from "@/components/global/modal/RegistryClient/MiniModal.vue";
const store = useStore()
const emits = defineEmits(['islam'])
onMounted(() => {
    (() => emits('islam', 'Реестр пользователей'))()
})

const files = ref(new Array(6));

const paginatedItems = ref(files.value);

const paginate = (data) => {
    paginatedItems.value = data.value; // paginatedItems.push(data)
};

const container = ref(null);

const handleScrollRight = () => {
    container.value.scrollBy({
        left: 200,
        behavior: "smooth",
    });
};

const handleScrollLeft = () => {
    container.value.scrollBy({
        left: -200,
        behavior: "smooth",
    });
};

</script>

<style lang="scss">
.gg {
    margin-top: 60px;

    &-btn {
        background: #1BAA75;
        font-weight: 600;
        font-size: 16px;
        color: #FFFFFF;
        padding: 14px 24px;
    }

    &-info {
        display: flex;
        align-items: start;
        justify-content: space-between;
        margin-top: 40px;
    }

    &-search {
        display: flex;
        align-items: center;
        width: 78%;
    }

    &-input {
        width: 90%;
        padding: 15px;
        background: #FFFFFF;
        border-width: 1px 0px 1px 1px;
        border-style: solid;
        border-color: #CDCDCD;
    }

    &-excel {
        padding: 14px 24px;
        display: flex;
        align-items: center;
        font-size: 14px;
        color: #1BAA75;
        gap: 10px;
        border: 1px solid #1BAA75;
    }

    &-excel.another {
        display: none;
        padding: 14px 24px; 
        align-items: center;
        font-size: 14px;
        color: #1BAA75;
        gap: 10px;
        border: 1px solid #1BAA75;
        margin-top: 30px;
    }

    &-content {
        display: flex;
        flex-direction: column;
        max-width: 320px;

        p {
            font-weight: 500;
            font-size: 14px;
            color: #24334B;
            margin: 0;
            margin-bottom: 5px;
        }

        .gg-another {
            margin-bottom: 10px;
        }
    }

    &-wrapper {
        display: flex;
        align-items: center;
        gap: 8px;

        input {
            width: 143px;
            height: 50px;
            padding: 12px 10px;
            box-sizing: border-box;

            &[type="number"]::-webkit-inner-spin-button,
            &[type="number"]::-webkit-outer-spin-button {
                -webkit-appearance: none;
                margin: 0;
            }
        }
    }

    &-filter {
        display: flex;
        gap: 10px;
        align-items: center;
        background: #3F5984;
        font-weight: 600;
        font-size: 16px;
        color: #F6F6F6;
        padding: 10px 68px;
    }

    &-table {
        margin-top: 40px;
    }

    &-pagination {
        display: flex;
        margin: 30px auto 0;
    }

    &-table_icons {
        display: flex;
        align-items: center;
    }


    &__adaptive {
        display: none;
        justify-content: space-between;
        margin-top: 30px;

        @media screen and (max-width: 1138px) {
            display: flex;
        }
    }

    &__left svg {
        cursor: pointer;
    }

    &__right svg {
        margin-left: 10px;
        cursor: pointer;
    }

}

.gg-table {
    max-width: 1115px;
    overflow-x: auto;

    table {
        border-collapse: collapse;

        thead {
            border: 1px solid #cdcdcd;
            border-bottom: 2px solid #cdcdcd;
            height: 64px;

            th {
                padding: 22px 13px;
                background: #ffffff;
                font-weight: 600;
                font-size: 16px;
                text-align: center;
                color: #24334b;
                gap: 20px;
            }
        }

        tbody {
            tr {
                border: 1px solid transparent;

                .order-list__name {
                    color: #1baa75;
                }

                .gg-hover_active {
                    display: none;
                }

                &:hover {
                    background: #ffffff;
                    border-color: #cdcdcd;

                    .gg-hover_active {
                        display: block;
                    }

                    .gg-hover_none {
                        display: none;
                    }
                }

                td {
                    padding: 12px;
                    box-sizing: border-box;
                    font-weight: 500;
                    font-size: 14px;
                    color: #24334b;
                    text-align: left;
                }

            }
        }
    }
}


.tooltip {
    position: relative;
}

.tooltip span {
    visibility: hidden;
    width: 320px;
    background: #ffffff;
    color: #000;
    text-align: start;
    border-radius: 6px;
    padding: 16px 16px;
    box-sizing: border-box;
    position: absolute;
    z-index: 9;
    top: -1em;
    left: 100%;
    margin-left: 1em;
    opacity: 0;
    transition: opacity 1s;
    display: flex;
    justify-content: space-between;
}

.tooltip span::after {
    content: "";
    position: absolute;
    top: 1.5em;
    right: 100%;
    margin-top: -5px;
    border-width: 5px;
    border-style: solid;
    border-color: transparent white transparent transparent;
}

.tooltip input {
    display: none;
}

.tooltip input:checked+span {
    visibility: visible;
    opacity: 1;
}

@media screen and (max-width:1300px) {
    .gg {
        &-excel {
            display: none;
        }

        &-search {
            width: 100%;
        }

        &-table {
            max-width: 100%;
        }

        table {
            width: 100%;

            tr {
                width: 100%;
            }
        }

        &-excel.another {
            display: block;
        }
    }
}
@media screen and (max-width:1200px) {
    .gg {
        &-info.another {
            flex-direction: column;
        }

        &-content {
            max-width: unset;
            width: 100%;
        }

        &-wrapper {
            input {
                width: 100%;
            }
        }
    }

    .accordeon {
        width: 100% !important;
    }
}
@media screen and (max-width:530px) {
    .gg {
        &-filter {
            display: none;
        }
    } 
}
@media screen and (max-width:400px) {
    .gg {
        &-wrapper {
            justify-content: space-between;
            input {
                width: 140px;
            }
        }
        &-btn {
            padding: 15px 0;
            width: 100%;
        }
        &-input {
            width: 65%;
        }
    } 
}

</style>