<template>
  <vuetable ref="vuetable"
    api-url="http://vuetable.ratiw.net/api/users"
    :fields="fields"
  ></vuetable>
</template>

<script>
import Vuetable from 'vuetable-2/src/components/Vuetable'
import accounting from 'accounting'
import moment from 'moment'

export default {
  components: {
    Vuetable
  },
  data () {
    return {
      fields: [
        'name', 'email',
        {
          name: 'birthdate',
          titleClass: 'text-center',
          dataClass: 'text-center',
          callback: 'formatDate|DD-MM-YYYY'
        },
        {
          name: 'nickname',
          callback: 'allcap'
        },
        {
          name: 'gender',
          titleClass: 'text-center',
          dataClass: 'text-center',
          callback: 'genderLabel'
        },
        {
          name: 'salary',
          titleClass: 'text-center',
          dataClass: 'text-right',
          callback: 'formatNumber'
        }
      ]
    }
  },
  methods: {
    allcap (value) {
      return value.toUpperCase()
    },
    genderLabel (value) {
      return value === 'M'
        ? '<span class="label label-warning"><i class="glyphicon glyphicon-star"></i> Male</span>'
        : '<span class="label label-success"><i class="glyphicon glyphicon-heart"></i> Female</span>'
    },
    formatNumber (value) {
      return accounting.formatNumber(value, 2)
    },
    formatDate (value, fmt = 'D MMM YYYY') {
      return (value == null)
        ? ''
        : moment(value, 'YYYY-MM-DD').format(fmt)
    }
  }
}
</script>
