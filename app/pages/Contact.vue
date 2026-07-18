<template>
  <div class="bg-black text-white min-h-screen overflow-hidden">
    
    <!-- Hero Header -->
    <section class="h-[50vh] flex items-center justify-center relative select-none">
      <div class="absolute inset-0 z-0">
        <img
          :src="bg"
          class="w-full h-full object-cover opacity-40 filter contrast-125 transition-all duration-1000 transform hover:scale-105"
          alt="SabAli Contact Header Background"
        />
        <div class="absolute inset-0 bg-gradient-to-b from-black/80 via-black/40 to-black"></div>
      </div>

      <div class="relative z-10 text-center px-6 max-w-4xl">
        <span class="text-xs uppercase tracking-[0.5em] text-white/50 block mb-6 animate-fade-in">
          Konsyerj xizmati
        </span>
        <h1 class="text-4xl md:text-7xl font-light tracking-[0.15em] text-white uppercase leading-none mb-4">
          BIZ BILAN BOG‘LANISH
        </h1>
        <p class="text-sm font-serif italic text-white/60 tracking-[0.2em] leading-relaxed max-w-md mx-auto">
          Shaxsiy buyurtmalar, individual atir yaratish va konsyerj xizmatiga doir barcha savollaringiz uchun.
        </p>
      </div>
    </section>

    <!-- Contact & Form Section -->
    <section class="py-24 px-6 sm:px-12 md:px-24 bg-black border-t border-white/5 relative">
      <div class="max-w-7xl mx-auto grid lg:grid-cols-12 gap-16">
        
        <!-- Left: Boutique Coordinates -->
        <div class="lg:col-span-5 flex flex-col space-y-12">
          
          <div class="space-y-4">
            <h2 class="text-xs uppercase tracking-[0.4em] text-white/40">
              Markaziy Atelyelarimiz
            </h2>
            <div class="h-[1px] w-12 bg-white/20"></div>
          </div>

          <!-- Locations -->
          <div class="space-y-8">
            <!-- Paris -->
            <div class="flex flex-col space-y-2">
              <span class="text-sm font-semibold tracking-widest text-white uppercase">Parij Atelyesi</span>
              <p class="text-sm text-white/60 font-light leading-relaxed">
                14 Rue de la Paix, 75002 Paris, France
              </p>
              <p class="text-xs text-white/40 font-mono tracking-wider">
                paris@sabaliparfume.com
              </p>
            </div>

            <!-- Tashkent -->
            <div class="flex flex-col space-y-2">
              <span class="text-sm font-semibold tracking-widest text-white uppercase">Toshkent Shourumi</span>
              <p class="text-sm text-white/60 font-light leading-relaxed">
                Amir Temur ko'chasi, 10-uy, Toshkent, O‘zbekiston
              </p>
              <p class="text-xs text-white/40 font-mono tracking-wider">
                tashkent@sabaliparfume.com
              </p>
            </div>
          </div>

          <!-- Working Hours -->
          <div class="flex flex-col space-y-4 pt-4 border-t border-white/5">
            <span class="text-xs uppercase tracking-[0.3em] text-white/40">Ish vaqti</span>
            <div class="space-y-1 text-sm font-light text-white/60">
              <p class="flex justify-between max-w-xs">
                <span>Dushanba — Shanba</span>
                <span class="font-mono">11:00 — 20:00</span>
              </p>
              <p class="flex justify-between max-w-xs text-white/30">
                <span>Yakshanba</span>
                <span>Faqat buyurtma bo‘yicha</span>
              </p>
            </div>
          </div>

          <!-- Global Hotline -->
          <div class="flex flex-col space-y-2 pt-4 border-t border-white/5">
            <span class="text-xs uppercase tracking-[0.3em] text-white/40">Konsyerj stoli</span>
            <p class="text-lg font-light text-white tracking-wider font-mono">
              +998 (99) 123-45-67
            </p>
            <p class="text-xs text-white/30 font-light">
              Dushanba – Shanba, soat 10:00 – 19:00 gacha faol (GMT+5)
            </p>
          </div>

        </div>

        <!-- Right: Bespoke Inquiry Form -->
        <div class="lg:col-span-7 bg-zinc-950/40 border border-white/5 rounded-2xl p-8 sm:p-10 relative">
          
          <div class="mb-8">
            <h3 class="text-xl font-light tracking-[0.1em] uppercase text-white">
              Savollaringizni yo‘llang
            </h3>
            <p class="text-xs text-white/40 mt-2">
              Quyidagi so‘rovnomani to‘ldiring. Bizning konsyerj jamoamiz siz bilan 24 soat ichida bog‘lanadi.
            </p>
          </div>

          <!-- Inquiry Form -->
          <form @submit.prevent="submitForm" class="space-y-8">
            
            <!-- Dual inputs row (Name and Email) -->
            <div class="grid md:grid-cols-2 gap-8">
              <div class="relative flex flex-col space-y-2">
                <label for="name" class="text-[10px] uppercase tracking-[0.2em] text-white/40">To‘liq ismingiz</label>
                <input 
                  type="text" 
                  id="name" 
                  v-model="form.name"
                  required
                  class="bg-transparent border-b border-white/15 focus:border-white py-3 text-sm font-light outline-none transition-colors duration-300"
                  placeholder="Masalan: Iskandar Mercer"
                />
              </div>

              <div class="relative flex flex-col space-y-2">
                <label for="email" class="text-[10px] uppercase tracking-[0.2em] text-white/40">Elektron pochta manzilingiz</label>
                <input 
                  type="email" 
                  id="email" 
                  v-model="form.email"
                  required
                  class="bg-transparent border-b border-white/15 focus:border-white py-3 text-sm font-light outline-none transition-colors duration-300"
                  placeholder="Masalan: iskandar@example.com"
                />
              </div>
            </div>

            <!-- Subject Dropdown -->
            <div class="relative flex flex-col space-y-2">
              <label for="subject" class="text-[10px] uppercase tracking-[0.2em] text-white/40">Bog‘lanishdan maqsad</label>
              <select 
                id="subject" 
                v-model="form.subject"
                required
                class="bg-zinc-950 text-white border-b border-white/15 focus:border-white py-3 text-sm font-light outline-none transition-colors duration-300 cursor-pointer appearance-none"
              >
                <option value="" disabled selected>Mavzuni tanlang...</option>
                <option value="consultation">Shaxsiy parfyumeriya konsultatsiyasi</option>
                <option value="bespoke">Individual atir yaratish buyurtmasi</option>
                <option value="order">Maxsus / Katta miqdordagi buyurtma</option>
                <option value="general">Umumiy brend bo‘yicha savollar</option>
              </select>
            </div>

            <!-- Message Box -->
            <div class="relative flex flex-col space-y-2">
              <label for="message" class="text-[10px] uppercase tracking-[0.2em] text-white/40">Sizning xabaringiz</label>
              <textarea 
                id="message" 
                v-model="form.message"
                rows="4"
                required
                class="bg-transparent border-b border-white/15 focus:border-white py-3 text-sm font-light outline-none transition-colors duration-300 resize-none"
                placeholder="O‘z ifor xohishlaringiz yoki savollaringizni yozib qoldiring..."
              ></textarea>
            </div>

            <!-- Submit Button / States -->
            <div class="pt-4">
              <button 
                type="submit" 
                :disabled="isSubmitting"
                class="w-full py-4 bg-white text-black text-xs uppercase tracking-[0.3em] font-medium hover:bg-zinc-200 transition duration-300 select-none flex items-center justify-center gap-3 disabled:opacity-50 disabled:cursor-not-allowed"
              >
                <span v-if="isSubmitting" class="w-4 h-4 border-2 border-black border-t-transparent rounded-full animate-spin"></span>
                <span>{{ isSubmitting ? 'Yuborilmoqda...' : 'Xabarni yuborish' }}</span>
              </button>
            </div>

            <!-- Toast Success / Error Message -->
            <transition name="fade">
              <div 
                v-if="submitStatus === 'success'" 
                class="p-4 bg-white/5 border border-white/10 rounded-xl text-center"
              >
                <p class="text-xs uppercase tracking-[0.25em] text-emerald-400 font-medium">
                  Xabar muvaffaqiyatli yuborildi
                </p>
                <p class="text-xs text-white/50 mt-1 font-light">
                  Sizning so‘rovingiz konsyerj jamoamizga yetib bordi. Tez orada siz bilan aloqaga chiqamiz.
                </p>
              </div>
            </transition>

          </form>

        </div>

      </div>
    </section>

    <!-- Consultation Cards -->
    <section class="py-32 px-6 sm:px-12 md:px-24 bg-zinc-950 border-t border-white/5 relative">
      <div class="max-w-6xl mx-auto">
        <div class="text-center mb-20">
          <h2 class="text-xs uppercase tracking-[0.4em] text-white/40 mb-4">
            Shaxsiy atelye
          </h2>
          <p class="text-2xl font-light tracking-wide text-white/80">
            Ifor kashfiyotlari
          </p>
        </div>

        <div class="grid md:grid-cols-3 gap-12">
          
          <!-- Experience 1 -->
          <div class="flex flex-col space-y-4 p-8 bg-black/40 border border-white/5 rounded-2xl hover:border-white/10 transition-colors duration-300">
            <span class="text-[10px] font-mono tracking-widest text-white/30 uppercase">I-Kashfiyot</span>
            <h3 class="text-lg font-light tracking-widest text-white uppercase">
              Ifor tanlash konsultatsiyasi
            </h3>
            <p class="text-xs font-light text-white/50 leading-relaxed">
              Bosh parfyumerimiz bilan yakkama-yakka uchrashib, ifor xohishlaringizni tahlil qiling va o‘zingizga eng mos keladigan ifor formulasini aniqlang.
            </p>
          </div>

          <!-- Experience 2 -->
          <div class="flex flex-col space-y-4 p-8 bg-black/40 border border-white/5 rounded-2xl hover:border-white/10 transition-colors duration-300">
            <span class="text-[10px] font-mono tracking-widest text-white/30 uppercase">II-Kashfiyot</span>
            <h3 class="text-lg font-light tracking-widest text-white uppercase">
              Shaxsiy atir formulasi
            </h3>
            <p class="text-xs font-light text-white/50 leading-relaxed">
              O‘zingiz uchun takrorlanmas, shaxsiy iforni loyihalashtiring. Shaxsiy retseptingiz maxsus arxiv omborimizda saqlanadi va kelajakda uni istalgan vaqtda qayta buyurtma berishingiz mumkin.
            </p>
          </div>

          <!-- Experience 3 -->
          <div class="flex flex-col space-y-4 p-8 bg-black/40 border border-white/5 rounded-2xl hover:border-white/10 transition-colors duration-300">
            <span class="text-[10px] font-mono tracking-widest text-white/30 uppercase">III-Kashfiyot</span>
            <h3 class="text-lg font-light tracking-widest text-white uppercase">
              Atelye masterklassi

            </h3>
            <p class="text-xs font-light text-white/50 leading-relaxed">
              Noyob va hashamatli atirlarning yaratilish kimyosi, o‘simliklar terimi va ifor yig‘ish formulalarini o‘rganuvchi kichik guruh (4 kishigacha) uchun shaxsiy masterklass.
            </p>
          </div>

        </div>
      </div>
    </section>

  </div>
</template>

<script setup>
import { ref } from 'vue'
import bg from '~/assets/images/mobile-banner/13.jpg'
const isSubmitting = ref(false)
const submitStatus = ref(null)

const form = ref({
  name: '',
  email: '',
  subject: '',
  message: ''
})

const submitForm = () => {
  isSubmitting.value = true
  submitStatus.value = null

  // Simulate premium concierge API submit latency
  setTimeout(() => {
    isSubmitting.value = false
    submitStatus.value = 'success'
    
    // Reset form fields
    form.value = {
      name: '',
      email: '',
      subject: '',
      message: ''
    }
  }, 2000)
}
</script>

<style scoped>
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in {
  animation: fadeIn 1.2s cubic-bezier(0.4, 0, 0.2, 1) forwards;
}

/* Custom fade animations */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
