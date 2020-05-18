<template>
  <v-content>
    <!-- top banner -->
    <banner :person.sync="persons"></banner>
    <!-- add section -->
    <add-component></add-component>
    <!-- persons sections -->
    <section id="previous-rulings">
      <v-container>
        <h2>Votes</h2>
        <div class="persons-wrapper">
          <v-row>
            <v-col cols="12" :xs="12" :sm="12" :md="6" v-for="person in persons" :key="person.name">
              <person-component :person="person" @hola="saveVotes"></person-component>
            </v-col>
          </v-row>
        </div>
      </v-container>
    </section>
    <!-- add person section -->
    <add-person-component></add-person-component>
  </v-content>
</template>

<script>
import banner from '../components/main-banner'
import addComponent from '../components/add-component'
import personComponent from '../components/person-component'
import addPersonComponent from '../components/add-person-component'
export default {
  name: 'Home',
  components: {
    banner,
    'add-component':addComponent,
    'person-component':personComponent,
    'add-person-component':addPersonComponent
  },
  data(){
    return{
      //persons dummy data
      persons:{
        0:{
          id:1,
          name: 'Kanye West',
          category:'Entertainment',
          description:'Vestibulum diam ante, porttitor a odio eget, rhoncus neque. Aenean Su velit libero.',
          votes:{
            up:3,
            down:1,
            total:4
          },
          date:1,
          backgroundImg:'https://lh3.googleusercontent.com/Gzlo_0P8fcsumMKMkMIMj0mq0Qy_-R-Szw_dbhjsI1RUXCQW53hBaIH8Q5qRoTJkPuMebLT0AQaSZUKuOcmULUGAIE4sfiWjZkpsJuek-AaVwhseQl9kWfKU_f2-iZ3FhsLII9QgIEOKD7Cz617SQkpeKlxKSkMheiip0S6QFW7Q9RllVtY1hdqrV4VZ5LxgRYwIPXUAnSC30vj0UhFylG9xAbutvWlXhIVRrWTDzMu6al-qyv7x_8cv-rGZULIVzNHxyMx3bwarYm9mhtftxO6rYtq_8xL6VL2hk7d3QEUOVIOSwhYEN4vxet4kOrmWVtcJMisFV4C-NXIRuqCvpQeUbkBJILTAvFYpjny5ddWkC3kYTUAplGJl0uyqR3btLqXSX_i-fsG-CtK73M8vR1lgqYybAuCGVS681GZy-SFnqhziA_irH7c4AJSKEoxh-O8g9UwcqlNDeozXqT94Dg88M6ZsoB8PpvsiLmWO3G74z3htobLxvFAs0rX4hnnBxYWblr5wzaYTkFVm0a_KL_RAxd1i8EVyAJcYxErWFF7x6VGlTyUpKsG1bPDFyXlsxJLoGn738NFr1SDjEZGNJzmDHl7v0eqcqzQNz7L59q3nu7tGMAKWd8IX-SSgMDe0fNNW2r-v8pWSt1ogEF_1a1zAx7csrhOG9gqdEJm4C1oYuZJqFjx6Mx6yF_fT=w491-h549-no?authuser=0'
        },
        1:{
          id:2,
          name: 'Mark Zuckerberg',
          category:'Business',
          description:'Vestibulum diam ante, porttitor a odio eget, rhoncus neque. Aenean Su velit libero.',
          votes:{
            up:1,
            down:3,
            total:4
          },
          date:1,
          backgroundImg:'https://lh3.googleusercontent.com/P9tTcyEXRqN0jw_mMSRkv5x2RZ9-2wdQPk7HDdAjpR20jKuvgqLo1yGINLW05xQfKylp2GubY5ugd51MTWLQdnP_Os7z9khr-SmUd3OpbGgjGs2kF3HWMAMYKHiT1DOO_969unGIKHl41PaPcLUHTTQ5WGscnqjUCxAA8SWXslN4B4lU9a_KSe_PrPyJZjQwRWP5a5n7PpYTiJoD_egojikhmPAj35MV9u-VMVGI0zra6KV4J7BDRpADANOjPG2L5Hz_8ZkqWJm1zDZKc7cL7En-R963Mq9QqjxnHKZdiUjTb_iIy7w3vf__d8t7sJwuVuoefGmIAYRo184UlMQAVavhXeArPT7OqyRLJwd1mxPWewyGRS2zCRON8q6qMtM5CewyHPkNNOvNzdAKuU-hjNzId1Vu-kttGyr8lgXAN2lhlMqSP8S9_ksE_bIrppWIKK2KyffyL4CTZm9_EbU7QBMvOMnG2mmh9jOpfWrjZnQJAMHtIU0lAfW6ToeCxSFUpKnJW1U9i6SrG-gv2qLFfoeOYSqDB3q8F6kANce1U-Pl4jw6OBVBS5J4f5-E6ynb6UDwzpnZNo9M-G0zoY_rpSoBTdLDqG8q4d15HnZvjWJrxgQ9o3z-_WS_E_XsVlRJ8qHlR7Nm_TUudKX_afvsqWNbJiA0TGqWz9Jt_ROGKCtlVhbbbq6ObuQYi2TQ=w491-h549-no?authuser=0'
        },
        2:{
          id:3,
          name: "Cristina Fernández de Kirchner",
          category:'Politics',
          description:'Vestibulum diam ante, porttitor a odio eget, rhoncus neque. Aenean Su velit libero.',
          votes:{
            up:1,
            down:3,
            total:4
          },
          date:1,
          backgroundImg:'https://lh3.googleusercontent.com/noLEBKrwbPquFY307BY4zVhTwOIaP5hhDGasWPeQwytMAv7CWVkvyGQ9yPjJEP-AI3aRip-34zpqIus6LGEb_-GsskcCwg5vtarSC3pWzY_rCXMMrfVzn1yallndlL80W4uRWptriKP1uo4EBvYLyACpp7jctNsbFj7GJiWuvl2l678ZbGsqk2HqKPW913PByUmXNVo9zgmqEtyZMGWx4Tus_a0zzE115MUntlj33lndkDEkbb2LtJT2mB76_vQ0kLKDLuJYRZZmxP6zdCg3MLbf3Ch-_xw5P0rwocigy5s6f8rEFobun_eXFGaANpKgFUfGaw1N1RKLLeLOdtPVQ914Apq4F035OMe4BKGv0HtzmgWdfohI9ynwiAs8mWS0-KD5-Kads8jTMhfqHJP705XI_Y3_rk2pCzuNRsSpAwGjW9eS7eizUpKMMPnCoE1XKJ1Hfr9ERW1Ack3r3Khihh4IcfS0XXx-CN7hA6LUyMe0gmS8kOmRb_BJKYLiTsSVhCOvAjz1k58hA21coA6fSdsFXTY_LljQSzbg4GlkUzwmsJjE9zdYbCzs3a0T6QtTWuyEXI4XcbbSTpHwvm26jzLpfk02ADUB2NOGaG09Q1fC8mfcVpdBhRwE2YJwqXWp3KMSkPUsajSibWEbYGrFWk0XSoUWNonU9rnF_hEXJoDENZgSkITikhynkccd=w491-h549-no?authuser=0'
        },
        3:{
          id:4,
          name: 'Malala Yousafzai',
          category:'Entertainment',
          description:'Vestibulum diam ante, porttitor a odio eget, rhoncus neque. Aenean Su velit libero.',
          votes:{
            up:3,
            down:1,
            total:4
          },
          date:1,
          backgroundImg:'https://lh3.googleusercontent.com/V75qTWA0FZNGvZybOarDNno77OiaUqBf1vSSVQTzvlAOOk84GvQSlmbaodayG7KqdFQ_h-LInUXGtWBjeIGk8k2w0LDxeJD8grj2oEgDViF6JMIGfWypB8bVZa6Z3QK6_W02MJaDt1m5hhJDiHbT4XaAbhgPC7-mR8IebqzEdDFtTb5ckTqe7_irKoFMsJEOr-SX9TxTUKQFzhEGJSJF2uf3vX8ZnsTOQ4tF5ddULy-XbnHQ2gatjDfUdX5R-49OyEwNttetQxF2vOxIMl_uHasNMBhRqEbPs_yqbmuzPSqxH6eKOte2mVzHF5C7xGsd5dypqI7G5dmt5qafqvhuBgY4P8G_Qtv_MhvtzNp2eaIpA342aK5yrdlsmtgXG5diG6cLXBadDtLJtI76ZoAxZQCoor8Eq-axc_-TlsUMyJeaCysUqwRqSjj2iCefTaL7_He-6B8E74-bWjAXYIptHcp9vcQepfN2t8qOBT1CSUQep34fQQDDEO_pe8RNkSo6YouzJyEEL0lGrX_JP_PmkWtrihvxCL2RACQNOdapMT1wrbbun3lUu7UL5JNlWqNh5PCAJGbZ8gx7oGMO4OePMt2qbx4tXZIdvQF-Mnvh_96MRsXnFZbEuyCfwM-8VQjQ5R8oazFOD51XOBaf4udbn7cJgu6946r9s3ZcDRNfic3SChTzBxR60hktjUEw=w491-h549-no?authuser=0'
        },
        4:{
          id:5,
          name: 'Pope Francis',
          category:'Religion',
          description:"He's talking tough on clergy sexual abuse,<br> but is he just another papal pervert protector? (thumbs down)<br> or a true pedophile punishing pontiff? (thumbs up)",
          votes:{
            up:3,
            down:3,
            total:6
          },
          date:1,
          backgroundImg:'https://lh3.googleusercontent.com/NqnQq4pqrbfPZv8S0WVzBwBZ2-T2w8Ko9lzaMbwcjK5SGVg_0MovRA4kL-h0OfxyDNZ_eo8wuY8UxxabhDQr2h-HfnWeleWgjCeG2aiI5liaZulBjJ_qv0fcCHc7N7RrSmw_8DgG-Nx89X8JtcGVN8r2zf81M-KVm1bDeO_Lr3OYC2lbexOoWLsXmGWuZjPdlNdn9XD2CPF6vvTIytSddnuVs6aIQbeZwEgW4NyxlP0nhxS2EbMNRicikgukJEJLlAiWAC34YhMc-5HVNro1j3CK3oNgn-DCMjFE-EokDzFoDcFgvWLLAhFBlNoPhqwudIlP4QkgZW0_5_zHB07Kdwqrj56vYsMuPP_EwRadKvrdXiKdaJ8feyYSa9ygFuAmu0o9bZo6fGTJMQmE9nOvZGxmr78B4Cm8xrfNgsE-ye50L3uy6SBy_Q3kkAFwskVxyisSG_i8Pvb5SnurYB3mdDkUlsmOWmOfTTphLhetUoTVpwIHzzuIV9FmGpinnL1XjcSAJz2GNxWHOzs-qkw0Hof5L0EX52jwNDZD-9v0Sd1oQ_5VvwNXcbHIMbZOz_fkVEDvCcLBiZV9n_TyzCVDkatxNOVB2er8RgMac9TQhAF0Xz6Sh01ZmjNsY4YKTDW9XmLDwSn4fzhyUAHLw1C9KWiox_E_zRJdA_ScDVRP02rLfd18-j6WohST06sG=w491-h549-no?authuser=0'
        },
      }
    }
  },
  mounted() {
    this.getVotes();
  },
  methods:{
    saveVotes(){
      console.log('hola mundo');
      localStorage.setItem('persons', JSON.stringify(this.persons));
    },
    getVotes(){
      const votes = JSON.parse(localStorage.getItem('persons'));//getting the saved votes
      votes ? this.persons = votes : console.log('no storage');//checking for existing votes
    }
  }
}
</script>
