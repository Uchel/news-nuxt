<template>
  <div>
    <div class="option">
      <label for="news-category">Pilih Kategori Berita:</label>
      <select id="news-category" v-model="selectedNewsCategory">
        <option value="" disabled>Pilih Kategori</option>
        <option
          v-for="(news, category) in newsCategories"
          :key="category"
          :value="category"
        >
          {{ category }}
        </option>
      </select>
    </div>

    <div v-if="!selectedNewsCategory">
      <div class="card-all">
        <h2>Semua Berita</h2>
        <div
          v-for="(newsCategory, categoryName) in newsCategories"
          :key="categoryName"
        >
          <h3>{{ categoryName }}</h3>
          <div v-for="newsItem in newsCategory" :key="newsItem.id">
            <div class="news-item">
              <img :src="newsItem.image" alt="Gambar Berita" />
              <h4>{{ newsItem.title }}</h4>
              <p>{{ newsItem.artikel }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div v-else>
      <div class="card-category">
        <h2>Berita Kategori {{ selectedNewsCategory }}</h2>
        <div
          v-for="newsItem in newsCategories[selectedNewsCategory]"
          :key="newsItem.id"
        >
          <div class="news-item">
            <img :src="newsItem.image" alt="Gambar Berita" />
            <h4>{{ newsItem.title }}</h4>
            <p>{{ newsItem.artikel }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newsCategories: {
        Olahraga: [
          {
            id: 1,
            title:
              'Pemain Bulu tangkis asal Kamboja terkena cedera, Ini penyebabnya !!!',
            image: '../assets/images/olahraga.jpeg',
            artikel:
              'Lorem ipsum dolor sit amet consectetur adipisicing elit. Nisi beatae quibusdam quae cum illo, fugit ut nemo id possimus obcaecati autem ea, doloremque exercitationem deserunt ratione, iure reprehenderit. Vitae, dignissimos?',
          },
          {
            id: 2,
            title:
              'Pebasket Profesional asal Laos terkena lemparan penonton!!!',
            image: '../assets/images/olahraga.jpeg',
            artikel:
              'Lorem ipsum dolor sit amet consectetur adipisicing elit. Nisi beatae quibusdam quae cum illo, fugit ut nemo id possimus obcaecati autem ea, doloremque exercitationem deserunt ratione, iure reprehenderit. Vitae, dignissimos?',
          },
          {
            id: 3,
            title:
              'Pemain Bulu tangkis asal Jamaica Salto depan untuk taunting lawan',
            image: '../assets/images/olahraga.jpeg',
            artikel:
              'Lorem ipsum dolor sit amet consectetur adipisicing elit. Nisi beatae quibusdam quae cum illo, fugit ut nemo id possimus obcaecati autem ea, doloremque exercitationem deserunt ratione, iure reprehenderit. Vitae, dignissimos?',
          },
        ],
        Bisnis: [
          {
            id: 1,
            title: 'Pengamen yang sukses menjadi pengusaha kedai bakso',
            image: '../assets/images/bisnis.jpeg',
            artikel:
              'Lorem ipsum dolor sit amet consectetur adipisicing elit. Nisi beatae quibusdam quae cum illo, fugit ut nemo id possimus obcaecati autem ea, doloremque exercitationem deserunt ratione, iure reprehenderit. Vitae, dignissimos?',
          },
          {
            id: 2,
            title: 'Pemulung yang sukses menjadi pengusaha Gerai Es Coklat',
            image: '../assets/images/bisnis.jpeg',
            artikel:
              'Lorem ipsum dolor sit amet consectetur adipisicing elit. Nisi beatae quibusdam quae cum illo, fugit ut nemo id possimus obcaecati autem ea, doloremque exercitationem deserunt ratione, iure reprehenderit. Vitae, dignissimos?',
          },
        ],
        Kuliner: [
          {
            id: 1,
            title: 'Wisata kuliner teramai dan terenak di Ibukota',
            image: '../assets/images/kuliner.jpeg',
            artikel:
              'Lorem ipsum dolor sit amet consectetur adipisicing elit. Nisi beatae quibusdam quae cum illo, fugit ut nemo id possimus obcaecati autem ea, doloremque exercitationem deserunt ratione, iure reprehenderit. Vitae, dignissimos?',
          },
          {
            id: 1,
            title:
              'Wisata kuliner teramai dan terenak di Kota Bandung Saat ini',
            image: '../assets/images/kuliner.jpeg',
            artikel:
              'Lorem ipsum dolor sit amet consectetur adipisicing elit. Nisi beatae quibusdam quae cum illo, fugit ut nemo id possimus obcaecati autem ea, doloremque exercitationem deserunt ratione, iure reprehenderit. Vitae, dignissimos?',
          },
        ],
      },
      selectedNewsCategory: null,
    }
  },
}
</script>
<style src="../assets/css/newsCategories.scss" lang="scss"></style>
