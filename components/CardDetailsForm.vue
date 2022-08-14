<template>
    <div>
        <form @submit.prevent="submitCard">
            <InputBoxField
            inputType="text"
            label="CARDHOLDER NAME"
            placeholder="Enter cardholder name"
            required="false"
            @changeInput="updateCardHolderName"
            />

            <InputBoxField
            inputType="number"
            label="CARD NUMBER"
            placeholder="Enter card number"
            required="required"
            @changeInput="updateCardNumber"
            />

            EXP. DATE(MM/YY)
            <InputBoxField
            inputType="number"
            label="MM"
            placeholder="MM"
            required="required"
            @changeInput="updateExpMM"
            />
            <InputBoxField
            inputType="number"
            label="YY"
            placeholder="YY"
            required="required"
            @changeInput="updateExpYY"
            />
            
            <InputBoxField
            inputType="number"
            label="CVC"
            placeholder="123"
            required="required"
            @changeInput="updateCVC"
            />

            <button>Confirm</button>
        </form>

        <div v-if="submitted">
            <h2>Output</h2>

            {{ cardHolderName }}

            {{ cardNumber }}

            {{ expMM }}

            {{ expYY }}

            {{ cvc }}
        </div>

        {{ validationMessage }}
    </div>
</template>

<script>
import InputBoxField from './InputBoxField';

export default ({
    name: 'CardDetailsForm',
    components: {
        InputBoxField,
    },
    data() {
        return {
            cardHolderName: '',
            cardNumber: 0,
            cvc: 0,
            expMM: 0,
            expYY: 0,
            validationMessage: '',
            submitted: false
        }
    },
    methods: {
        submitCard() {
            console.log('submit clicked');
            this.submitted = true;
            if(this.cardHolderName = '') {
                this.validationMessage = 'Enter in a card name';
            }
        },
        updateCardHolderName(value) {
            console.log(value, 'value updated');
            this.cardHolderName = value;
        },
        updateCardNumber(value) {
            console.log(value, 'value updated');
            this.cardNumber = value;
        },
        updateCVC(value) {
            console.log(value, 'value updated');
            this.cvc = value;
        },
        updateExpMM(value) {
            console.log(value, 'value updated');
            this.expMM = value;
        },
        updateExpYY(value) {
            console.log(value, 'value updated');
            this.expYY = value;
        }
    }

})
</script>