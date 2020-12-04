<template>
    <section class="converter">
        <div class="row justify-content-center">
            <div class="col-12">
                <h3>Converter</h3>
            </div>
            <div class="col-6">
                <div class="row">
                    <div class="form-group col-6">
                        <label for="celsius" class="col-12 col-form-label text-left">Celsius</label>
                        <input
                            id="celsius"
                            type="number"
                            class="form-control"
                            name="celsius"
                            value
                            required
                            autofocus
                            v-model="celsius"
                            v-on:input="convert($event, 1)"
                        />
                    </div>
                    <div class="form-group col-6">
                        <label for="fahrenheit" class="col-12 col-form-label text-left">Fahrenheit</label>
                        <input
                            id="fahrenheit"
                            type="number"
                            class="form-control"
                            name="fahrenheit"
                            value
                            required
                            autofocus
                            v-model="fahrenheit"
                            v-on:input="convert($event, 2)"
                        />
                    </div>
                </div>
            </div>
        </div>
        
    </section>
</template>

<script>
export default {
    name: "Converter",
    data() {
        return {
            temperature: 0,
            celsius: 0,
            fahrenheit: 0
        }
    },
    methods: {
        addCounter() {
            this.counter++
        },
        convert(ev, type) {
            if (type === 1) {
                if (!isNaN(this.celsius)) {
                    this.fahrenheit = this.celsius * (9/5) + 32
                    this.fahrenheit = this.fahrenheit.toFixed(4)
                }
            } else if (type === 2) {
                if (!isNaN(this.fahrenheit)) {
                    this.celsius = (this.fahrenheit - 32) * (5/9)
                    this.celsius = this.celsius.toFixed(4)
                }
            }
        }
    }
}
</script>

<style scoped>
.btn-primary {
    color: #fff;
    background-color: #6542f4;
    border-color: #6542f4;
}
.counter-number {
    font-size: 5rem;
}
</style>