<script lang='ts' setup>
import { useTheme } from 'vuetify'


const settings = {
    settings: {
        theme: "system",
        language: "zh_CN",

    }
}

//#region 主题

const theme = useTheme()
watch(() => settings.settings.theme, () => {
    setHtmlClass()
    console.log(`当前主题: ${settings.settings.theme}`);

}, { immediate: true })

// 监听系统主题变化
onMounted(() => {
    window.matchMedia("(prefers-color-scheme: dark)").addEventListener("change", (e) => {
        if (settings.settings.theme == "system") {
            if (e.matches) {
                setDarkTheme()
            } else {
                setLightTheme()
            }
        }
    })
})

// console.log(settings.settings.theme);

function setHtmlClass() {
    switch (settings.settings.theme) {
        case "system":
            if (window.matchMedia("(prefers-color-scheme: dark)").matches) {
                setDarkTheme()
            } else {
                setLightTheme()
            }
            break;
        case 'dark':
            setDarkTheme()
            break;
        case 'light':
            setLightTheme()
            break;
        default:
            break;
    }
}

function setDarkTheme() {
    let html = document.querySelector("html")
    html?.classList.add("dark")
    theme.global.name.value = "dark"
}

function setLightTheme() {
    let html = document.querySelector("html")
    html?.classList.remove("dark")
    theme.global.name.value = "light"
}

//#endregion


//#region 初始化语言

const { locale } = useI18n()

watch(() => settings.settings.language, () => {
    locale.value = settings.settings.language
    console.log(`当前语言: ${settings.settings.language}`);
}, { immediate: true })

//#endregion


</script>
<template>

</template>
<script lang='ts'>

export default {
    name: 'Global',
}
</script>
<style lang='less' scoped></style>
