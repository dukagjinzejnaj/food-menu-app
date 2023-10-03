<script>
export default {
    methods: {
        currentDate() {
            const current = new Date();
            const date = `${current.getDate()} / ${current.getMonth()+1} / ${current.getFullYear()}`;
            return date;
        }
  }
}
</script>

<template>
    <div class="footer">
        <a class="button-modal" href="#open-modal">Aktueller Datum?</a>
        <div id="open-modal" class="modal-window">
            <div>
                <h3>{{currentDate()}}</h3>
                <a href="#" class="modal-close">X</a>
            </div>
        </div>
    </div>
</template>