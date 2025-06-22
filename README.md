<!DOCTYPE html>
<html lang="ka">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>მძიმე ბაბუების კლუბი</title>
    <script src="https://cdn.tailwindcss.com/3.4.16"></script>
    <script>
      tailwind.config = {
        theme: {
          extend: {
            colors: { primary: "#c91f1f", secondary: "#333333" },
            borderRadius: {
              none: "0px",
              sm: "2px",
              DEFAULT: "4px",
              md: "8px",
              lg: "12px",
              xl: "16px",
              "2xl": "20px",
              "3xl": "24px",
              full: "9999px",
              button: "4px",
            },
          },
        },
      };
    </script>
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Pacifico&display=swap"
      rel="stylesheet"
    />
    <link
      href="https://fonts.googleapis.com/css2?family=MedievalSharp&family=Metal+Mania&display=swap"
      rel="stylesheet"
    />
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/remixicon/4.6.0/remixicon.min.css"
    />
    <style>
      :where([class^="ri-"])::before { content: "\f3c2"; }
      body {
          background-color: #0a0a0a;
          color: #e0e0e0;
          font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      }
      .gothic-font {
          font-family: 'MedievalSharp', cursive;
      }
      .metal-font {
          font-family: 'Metal Mania', cursive;
      }
      .custom-checkbox {
          appearance: none;
          width: 1.2rem;
          height: 1.2rem;
          border: 2px solid #666;
          background-color: #222;
          border-radius: 2px;
          position: relative;
      }
      .custom-checkbox:checked {
          background-color: #c91f1f;
          border-color: #c91f1f;
      }
      .custom-checkbox:checked::after {
          content: '✓';
          position: absolute;
          top: 50%;
          left: 50%;
          transform: translate(-50%, -50%);
          color: white;
          font-size: 0.8rem;
      }
      .custom-switch {
          position: relative;
          display: inline-block;
          width: 3rem;
          height: 1.5rem;
      }
      .custom-switch input {
          opacity: 0;
          width: 0;
          height: 0;
      }
      .slider {
          position: absolute;
          cursor: pointer;
          top: 0;
          left: 0;
          right: 0;
          bottom: 0;
          background-color: #333;
          transition: .4s;
          border-radius: 34px;
      }
      .slider:before {
          position: absolute;
          content: "";
          height: 1.1rem;
          width: 1.1rem;
          left: 0.2rem;
          bottom: 0.2rem;
          background-color: #777;
          transition: .4s;
          border-radius: 50%;
      }
      input:checked + .slider {
          background-color: #c91f1f;
      }
      input:checked + .slider:before {
          transform: translateX(1.5rem);
          background-color: white;
      }
      .vinyl-profile {
          transition: all 0.3s ease;
      }
      .vinyl-profile:hover {
          transform: scale(1.05);
      }
      .guitar-pick {
          clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);
      }
      .rating-badge {
          background: linear-gradient(145deg, #444, #222);
          box-shadow: 2px 2px 5px rgba(0,0,0,0.5);
      }
      .playlist-item {
          background: linear-gradient(145deg, #333, #222);
          border-left: 4px solid #c91f1f;
      }
      .news-item {
          border-bottom: 1px solid #444;
      }
      .forum-item {
          background: linear-gradient(to right, #222, #1a1a1a);
      }
      .hero-section {
          background-image: url('https://readdy.ai/api/search-image?query=vintage%20electric%20guitar%20with%20dark%20moody%20lighting%2C%20black%20background%2C%20dramatic%20shadows%2C%20heavy%20metal%20aesthetic%2C%20detailed%20guitar%20texture%2C%20cinematic%20lighting&width=1200&height=600&seq=guitar1&orientation=landscape');
          background-size: cover;
          background-position: center;
          position: relative;
      }
      .hero-section::after {
          content: '';
          position: absolute;
          top: 0;
          left: 0;
          right: 0;
          bottom: 0;
          background: linear-gradient(to right, rgba(0,0,0,0.9) 0%, rgba(0,0,0,0.7) 50%, rgba(0,0,0,0.5) 100%);
          z-index: 1;
      }
      .hero-content {
          position: relative;
          z-index: 2;
      }
      .nav-link {
          position: relative;
      }
      .nav-link::after {
          content: '';
          position: absolute;
          width: 0;
          height: 2px;
          bottom: -4px;
          left: 0;
          background-color: #c91f1f;
          transition: width 0.3s ease;
      }
      .nav-link:hover::after {
          width: 100%;
      }
      .custom-range {
          -webkit-appearance: none;
          width: 100%;
          height: 8px;
          background: #333;
          border-radius: 4px;
          outline: none;
      }
      .custom-range::-webkit-slider-thumb {
          -webkit-appearance: none;
          appearance: none;
          width: 20px;
          height: 20px;
          background: #c91f1f;
          border-radius: 50%;
          cursor: pointer;
      }
      .custom-range::-moz-range-thumb {
          width: 20px;
          height: 20px;
          background: #c91f1f;
          border-radius: 50%;
          cursor: pointer;
      }
    </style>
  </head>
  <body class="min-h-screen">
    <header
      class="bg-black bg-opacity-90 border-b border-gray-800 sticky top-0 z-50"
    >
      <div class="container mx-auto px-4 py-3">
        <div class="flex justify-between items-center">
          <div class="flex items-center">
            <div
              class="w-12 h-12 bg-primary rounded-full flex items-center justify-center mr-3"
            >
              <i class="ri-skull-2-line ri-xl text-white"></i>
            </div>
            <h1 class="metal-font text-3xl text-white">მძიმე ბაბუების კლუბი</h1>
          </div>

          <nav class="hidden md:flex space-x-8">
            <a
              href="#"
              class="nav-link text-white hover:text-primary transition-colors"
              >მთავარი</a
            >
            <a
              href="#grandfathers"
              class="nav-link text-white hover:text-primary transition-colors"
              >ბაბუები</a
            >
            <a
              href="#forum"
              class="nav-link text-white hover:text-primary transition-colors"
              >ფორუმი</a
            >
            <a
              href="#playlists"
              class="nav-link text-white hover:text-primary transition-colors"
              >პლეილისტები</a
            >
            <a
              href="#news"
              class="nav-link text-white hover:text-primary transition-colors"
              >ახალი ამბები</a
            >
          </nav>

          <div class="flex items-center space-x-4">
            <button
              class="guitar-pick bg-primary w-10 h-10 flex items-center justify-center"
            >
              <i class="ri-user-line ri-lg text-white"></i>
            </button>
            <button
              class="md:hidden w-10 h-10 flex items-center justify-center text-white"
              id="mobile-menu-button"
            >
              <i class="ri-menu-line ri-lg"></i>
            </button>
          </div>
        </div>

        <div id="mobile-menu" class="md:hidden hidden pt-4 pb-2">
          <nav class="flex flex-col space-y-3">
            <a
              href="#"
              class="text-white hover:text-primary py-2 border-b border-gray-800"
              >მთავარი</a
            >
            <a
              href="#grandfathers"
              class="text-white hover:text-primary py-2 border-b border-gray-800"
              >ბაბუები</a
            >
            <a
              href="#forum"
              class="text-white hover:text-primary py-2 border-b border-gray-800"
              >ფორუმი</a
            >
            <a
              href="#playlists"
              class="text-white hover:text-primary py-2 border-b border-gray-800"
              >პლეილისტები</a
            >
            <a
              href="#news"
              class="text-white hover:text-primary py-2 border-b border-gray-800"
              >ახალი ამბები</a
            >
          </nav>
        </div>
      </div>
    </header>

    <main>
      <!-- Hero Section -->
      <section class="hero-section min-h-[600px] flex items-center">
        <div class="container mx-auto px-4 hero-content">
          <div class="max-w-2xl">
            <h1 class="metal-font text-5xl md:text-6xl text-white mb-6">
              ლეგენდები არასოდეს ბერდებიან
            </h1>
            <p class="text-xl text-gray-300 mb-8">
              გაერთიანდით მძიმე მეტალის, მოტოციკლების და ნოსტალგიის მოყვარულ
              ბაბუებთან ერთად. ჩვენ ვაგრძელებთ როკს!
            </p>
            <div class="flex flex-wrap gap-4">
              <button
                class="bg-primary hover:bg-red-800 text-white px-6 py-3 text-lg font-bold !rounded-button whitespace-nowrap transition-colors"
              >
                შემოგვიერთდი
              </button>
              <button
                class="bg-gray-800 hover:bg-gray-700 text-white px-6 py-3 text-lg font-bold !rounded-button whitespace-nowrap transition-colors"
              >
                გაიგე მეტი
              </button>
            </div>
          </div>
        </div>
      </section>

      <!-- Black Belt Rating Section -->
      <section class="bg-gradient-to-b from-black to-gray-900 py-12">
        <div class="container mx-auto px-4">
          <div class="flex flex-col md:flex-row items-center justify-between">
            <div class="mb-8 md:mb-0 md:w-1/2">
              <h2 class="gothic-font text-3xl text-white mb-4">
                შავი ქამრის ბაბუების ლიგა
              </h2>
              <p class="text-gray-300 mb-6">
                გახდი ლეგენდა მძიმე მეტალის ცოდნით. უპასუხე კითხვებს, დააგროვე
                ქულები და მიაღწიე უმაღლეს რანგს!
              </p>
              <div class="flex items-center space-x-6">
                <div
                  class="rating-badge flex flex-col items-center p-3 rounded-lg"
                >
                  <div class="w-12 h-12 flex items-center justify-center">
                    <i class="ri-sword-line ri-2x text-yellow-500"></i>
                  </div>
                  <span class="text-yellow-500 font-bold">ოქროს ქამარი</span>
                </div>
                <div
                  class="rating-badge flex flex-col items-center p-3 rounded-lg"
                >
                  <div class="w-12 h-12 flex items-center justify-center">
                    <i class="ri-shield-line ri-2x text-gray-400"></i>
                  </div>
                  <span class="text-gray-400 font-bold">ვერცხლის ქამარი</span>
                </div>
                <div
                  class="rating-badge flex flex-col items-center p-3 rounded-lg"
                >
                  <div class="w-12 h-12 flex items-center justify-center">
                    <i class="ri-copper-coin-line ri-2x text-amber-700"></i>
                  </div>
                  <span class="text-amber-700 font-bold">ბრინჯაოს ქამარი</span>
                </div>
              </div>
            </div>
            <div class="md:w-1/2 bg-gray-800 p-6 rounded-lg">
              <h3 class="gothic-font text-2xl text-white mb-4">
                დღის მეტალ კითხვა
              </h3>
              <p class="text-gray-300 mb-4">
                რომელ წელს გამოვიდა Black Sabbath-ის დებიუტი ალბომი?
              </p>
              <div class="space-y-3 mb-6">
                <div class="flex items-center">
                  <input
                    type="radio"
                    id="answer1"
                    name="metal-question"
                    class="custom-checkbox mr-3"
                  />
                  <label for="answer1" class="text-gray-300">1968</label>
                </div>
                <div class="flex items-center">
                  <input
                    type="radio"
                    id="answer2"
                    name="metal-question"
                    class="custom-checkbox mr-3"
                  />
                  <label for="answer2" class="text-gray-300">1969</label>
                </div>
                <div class="flex items-center">
                  <input
                    type="radio"
                    id="answer3"
                    name="metal-question"
                    class="custom-checkbox mr-3"
                  />
                  <label for="answer3" class="text-gray-300">1970</label>
                </div>
                <div class="flex items-center">
                  <input
                    type="radio"
                    id="answer4"
                    name="metal-question"
                    class="custom-checkbox mr-3"
                  />
                  <label for="answer4" class="text-gray-300">1971</label>
                </div>
              </div>
              <button
                class="bg-primary hover:bg-red-800 text-white px-4 py-2 font-bold !rounded-button whitespace-nowrap transition-colors"
              >
                პასუხის გაგზავნა
              </button>
            </div>
          </div>
        </div>
      </section>

      <!-- Grandfathers Section -->
      <section id="grandfathers" class="py-16 bg-gray-900">
        <div class="container mx-auto px-4">
          <h2 class="metal-font text-4xl text-center text-white mb-12">
            ჩვენი ლეგენდარული ბაბუები
          </h2>

          <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8">
            <!-- Grandfather 1 -->
            <div
              class="vinyl-profile bg-black rounded-lg overflow-hidden shadow-lg"
            >
              <div class="h-64 overflow-hidden">
                <img
                  src="https://readdy.ai/api/search-image?query=older%20man%20with%20long%20gray%20hair%20and%20beard%20wearing%20black%20leather%20jacket%2C%20rock%20style%2C%20heavy%20metal%20fan%2C%20atmospheric%20portrait%2C%20dramatic%20lighting%2C%20serious%20expression%2C%20vintage%20motorcycle%20in%20background&width=400&height=400&seq=grandpa1&orientation=squarish"
                  alt="გიორგი"
                  class="w-full h-full object-cover object-top"
                />
              </div>
              <div class="p-4">
                <h3 class="gothic-font text-2xl text-white mb-2">
                  გიორგი "გიტარა" მაისურაძე
                </h3>
                <p class="text-gray-400 mb-3">
                  68 წლის | ოქროს ქამრის მფლობელი
                </p>
                <p class="text-gray-300 mb-4">
                  ყოფილი გიტარისტი, 40 წლიანი სტაჟით. უყვარს Black Sabbath და
                  Deep Purple. ფლობს 17 ვინტაჟურ გიტარას.
                </p>
                <div class="flex justify-between items-center">
                  <span class="text-primary font-bold">243 პოსტი</span>
                  <button
                    class="bg-gray-800 hover:bg-gray-700 text-white px-3 py-1 !rounded-button whitespace-nowrap transition-colors"
                  >
                    პროფილი
                  </button>
                </div>
              </div>
            </div>

            <!-- Grandfather 2 -->
            <div
              class="vinyl-profile bg-black rounded-lg overflow-hidden shadow-lg"
            >
              <div class="h-64 overflow-hidden">
                <img
                  src="https://readdy.ai/api/search-image?query=older%20man%20with%20bald%20head%20and%20white%20beard%20wearing%20denim%20vest%20with%20patches%2C%20heavy%20metal%20fan%2C%20atmospheric%20portrait%2C%20dramatic%20lighting%2C%20confident%20pose%2C%20vintage%20motorcycle%20in%20background&width=400&height=400&seq=grandpa2&orientation=squarish"
                  alt="ზურაბი"
                  class="w-full h-full object-cover object-top"
                />
              </div>
              <div class="p-4">
                <h3 class="gothic-font text-2xl text-white mb-2">
                  ზურაბ "ზურა" კვარაცხელია
                </h3>
                <p class="text-gray-400 mb-3">
                  72 წლის | ვერცხლის ქამრის მფლობელი
                </p>
                <p class="text-gray-300 mb-4">
                  ყოფილი მოტოციკლისტი. მეტალს უსმენს 1975 წლიდან. უყვარს Judas
                  Priest და Iron Maiden. ჯერ კიდევ დადის კონცერტებზე.
                </p>
                <div class="flex justify-between items-center">
                  <span class="text-primary font-bold">187 პოსტი</span>
                  <button
                    class="bg-gray-800 hover:bg-gray-700 text-white px-3 py-1 !rounded-button whitespace-nowrap transition-colors"
                  >
                    პროფილი
                  </button>
                </div>
              </div>
            </div>

            <!-- Grandfather 3 -->
            <div
              class="vinyl-profile bg-black rounded-lg overflow-hidden shadow-lg"
            >
              <div class="h-64 overflow-hidden">
                <img
                  src="https://readdy.ai/api/search-image?query=older%20man%20with%20gray%20ponytail%20wearing%20black%20t-shirt%20with%20metal%20band%20logo%2C%20leather%20bracelet%2C%20atmospheric%20portrait%2C%20dramatic%20lighting%2C%20rock%20hand%20gesture%2C%20vintage%20vinyl%20records%20in%20background&width=400&height=400&seq=grandpa3&orientation=squarish"
                  alt="ლევანი"
                  class="w-full h-full object-cover object-top"
                />
              </div>
              <div class="p-4">
                <h3 class="gothic-font text-2xl text-white mb-2">
                  ლევან "ბასი" ბერიძე
                </h3>
                <p class="text-gray-400 mb-3">
                  65 წლის | ოქროს ქამრის მფლობელი
                </p>
                <p class="text-gray-300 mb-4">
                  ყოფილი ბასისტი. კოლექციონერი - ფლობს 500+ ვინილს. უყვარს
                  Metallica და Megadeth. ატარებს მეტალ ფესტივალს.
                </p>
                <div class="flex justify-between items-center">
                  <span class="text-primary font-bold">312 პოსტი</span>
                  <button
                    class="bg-gray-800 hover:bg-gray-700 text-white px-3 py-1 !rounded-button whitespace-nowrap transition-colors"
                  >
                    პროფილი
                  </button>
                </div>
              </div>
            </div>

            <!-- Grandfather 4 -->
            <div
              class="vinyl-profile bg-black rounded-lg overflow-hidden shadow-lg"
            >
              <div class="h-64 overflow-hidden">
                <img
                  src="https://readdy.ai/api/search-image?query=older%20man%20with%20white%20mustache%20wearing%20bandana%20and%20leather%20vest%2C%20heavy%20metal%20fan%2C%20atmospheric%20portrait%2C%20dramatic%20lighting%2C%20sitting%20on%20vintage%20motorcycle%2C%20sunset%20background&width=400&height=400&seq=grandpa4&orientation=squarish"
                  alt="დავითი"
                  class="w-full h-full object-cover object-top"
                />
              </div>
              <div class="p-4">
                <h3 class="gothic-font text-2xl text-white mb-2">
                  დავით "დრამი" ჯაფარიძე
                </h3>
                <p class="text-gray-400 mb-3">
                  70 წლის | ბრინჯაოს ქამრის მფლობელი
                </p>
                <p class="text-gray-300 mb-4">
                  ყოფილი დრამერი. მოტოციკლების ხელოსანი. უყვარს Motörhead და
                  AC/DC. აწყობს ყოველწლიურ მოტო შეკრებებს.
                </p>
                <div class="flex justify-between items-center">
                  <span class="text-primary font-bold">156 პოსტი</span>
                  <button
                    class="bg-gray-800 hover:bg-gray-700 text-white px-3 py-1 !rounded-button whitespace-nowrap transition-colors"
                  >
                    პროფილი
                  </button>
                </div>
              </div>
            </div>
          </div>

          <div class="text-center mt-12">
            <button
              class="bg-gray-800 hover:bg-gray-700 text-white px-6 py-3 font-bold !rounded-button whitespace-nowrap transition-colors"
            >
              ყველა ბაბუას ნახვა
            </button>
          </div>
        </div>
      </section>

      <!-- Playlists Section -->
      <section id="playlists" class="py-16 bg-black">
        <div class="container mx-auto px-4">
          <h2 class="metal-font text-4xl text-center text-white mb-12">
            ბაბუების მეტალ პლეილისტები
          </h2>

          <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <!-- Playlist 1 -->
            <div class="bg-gray-900 rounded-lg overflow-hidden shadow-lg">
              <div class="flex items-center p-4 border-b border-gray-800">
                <div
                  class="w-16 h-16 bg-primary rounded-full flex items-center justify-center mr-4"
                >
                  <i class="ri-music-2-line ri-2x text-white"></i>
                </div>
                <div>
                  <h3 class="gothic-font text-2xl text-white">
                    კლასიკური მძიმე მეტალი
                  </h3>
                  <p class="text-gray-400">
                    შემდგენელი: გიორგი "გიტარა" მაისურაძე
                  </p>
                </div>
              </div>

              <div class="p-4">
                <div
                  class="playlist-item flex justify-between items-center p-3 mb-3 rounded"
                >
                  <div class="flex items-center">
                    <div
                      class="w-8 h-8 flex items-center justify-center mr-3 text-gray-400"
                    >
                      <i class="ri-play-circle-line ri-lg"></i>
                    </div>
                    <div>
                      <h4 class="text-white">Black Sabbath - Paranoid</h4>
                      <p class="text-gray-500 text-sm">1970 | 2:48</p>
                    </div>
                  </div>
                  <div class="w-8 h-8 flex items-center justify-center">
                    <i
                      class="ri-heart-line ri-lg text-gray-400 hover:text-primary cursor-pointer"
                    ></i>
                  </div>
                </div>

                <div
                  class="playlist-item flex justify-between items-center p-3 mb-3 rounded"
                >
                  <div class="flex items-center">
                    <div
                      class="w-8 h-8 flex items-center justify-center mr-3 text-gray-400"
                    >
                      <i class="ri-play-circle-line ri-lg"></i>
                    </div>
                    <div>
                      <h4 class="text-white">
                        Deep Purple - Smoke on the Water
                      </h4>
                      <p class="text-gray-500 text-sm">1972 | 5:40</p>
                    </div>
                  </div>
                  <div class="w-8 h-8 flex items-center justify-center">
                    <i
                      class="ri-heart-line ri-lg text-gray-400 hover:text-primary cursor-pointer"
                    ></i>
                  </div>
                </div>

                <div
                  class="playlist-item flex justify-between items-center p-3 mb-3 rounded"
                >
                  <div class="flex items-center">
                    <div
                      class="w-8 h-8 flex items-center justify-center mr-3 text-gray-400"
                    >
                      <i class="ri-play-circle-line ri-lg"></i>
                    </div>
                    <div>
                      <h4 class="text-white">
                        Led Zeppelin - Whole Lotta Love
                      </h4>
                      <p class="text-gray-500 text-sm">1969 | 5:34</p>
                    </div>
                  </div>
                  <div class="w-8 h-8 flex items-center justify-center">
                    <i
                      class="ri-heart-line ri-lg text-gray-400 hover:text-primary cursor-pointer"
                    ></i>
                  </div>
                </div>

                <div
                  class="playlist-item flex justify-between items-center p-3 mb-3 rounded"
                >
                  <div class="flex items-center">
                    <div
                      class="w-8 h-8 flex items-center justify-center mr-3 text-gray-400"
                    >
                      <i class="ri-play-circle-line ri-lg"></i>
                    </div>
                    <div>
                      <h4 class="text-white">
                        Judas Priest - Breaking the Law
                      </h4>
                      <p class="text-gray-500 text-sm">1980 | 2:35</p>
                    </div>
                  </div>
                  <div class="w-8 h-8 flex items-center justify-center">
                    <i
                      class="ri-heart-line ri-lg text-gray-400 hover:text-primary cursor-pointer"
                    ></i>
                  </div>
                </div>
              </div>

              <div class="p-4 border-t border-gray-800">
                <button
                  class="bg-primary hover:bg-red-800 text-white px-4 py-2 !rounded-button whitespace-nowrap transition-colors"
                >
                  სრული პლეილისტი
                </button>
              </div>
            </div>

            <!-- Playlist 2 -->
            <div class="bg-gray-900 rounded-lg overflow-hidden shadow-lg">
              <div class="flex items-center p-4 border-b border-gray-800">
                <div
                  class="w-16 h-16 bg-primary rounded-full flex items-center justify-center mr-4"
                >
                  <i class="ri-album-line ri-2x text-white"></i>
                </div>
                <div>
                  <h3 class="gothic-font text-2xl text-white">
                    80-იანების თრეში
                  </h3>
                  <p class="text-gray-400">შემდგენელი: ლევან "ბასი" ბერიძე</p>
                </div>
              </div>

              <div class="p-4">
                <div
                  class="playlist-item flex justify-between items-center p-3 mb-3 rounded"
                >
                  <div class="flex items-center">
                    <div
                      class="w-8 h-8 flex items-center justify-center mr-3 text-gray-400"
                    >
                      <i class="ri-play-circle-line ri-lg"></i>
                    </div>
                    <div>
                      <h4 class="text-white">Metallica - Master of Puppets</h4>
                      <p class="text-gray-500 text-sm">1986 | 8:35</p>
                    </div>
                  </div>
                  <div class="w-8 h-8 flex items-center justify-center">
                    <i
                      class="ri-heart-fill ri-lg text-primary cursor-pointer"
                    ></i>
                  </div>
                </div>

                <div
                  class="playlist-item flex justify-between items-center p-3 mb-3 rounded"
                >
                  <div class="flex items-center">
                    <div
                      class="w-8 h-8 flex items-center justify-center mr-3 text-gray-400"
                    >
                      <i class="ri-play-circle-line ri-lg"></i>
                    </div>
                    <div>
                      <h4 class="text-white">Slayer - Raining Blood</h4>
                      <p class="text-gray-500 text-sm">1986 | 4:17</p>
                    </div>
                  </div>
                  <div class="w-8 h-8 flex items-center justify-center">
                    <i
                      class="ri-heart-line ri-lg text-gray-400 hover:text-primary cursor-pointer"
                    ></i>
                  </div>
                </div>

                <div
                  class="playlist-item flex justify-between items-center p-3 mb-3 rounded"
                >
                  <div class="flex items-center">
                    <div
                      class="w-8 h-8 flex items-center justify-center mr-3 text-gray-400"
                    >
                      <i class="ri-play-circle-line ri-lg"></i>
                    </div>
                    <div>
                      <h4 class="text-white">Megadeth - Holy Wars</h4>
                      <p class="text-gray-500 text-sm">1990 | 6:36</p>
                    </div>
                  </div>
                  <div class="w-8 h-8 flex items-center justify-center">
                    <i
                      class="ri-heart-line ri-lg text-gray-400 hover:text-primary cursor-pointer"
                    ></i>
                  </div>
                </div>

                <div
                  class="playlist-item flex justify-between items-center p-3 mb-3 rounded"
                >
                  <div class="flex items-center">
                    <div
                      class="w-8 h-8 flex items-center justify-center mr-3 text-gray-400"
                    >
                      <i class="ri-play-circle-line ri-lg"></i>
                    </div>
                    <div>
                      <h4 class="text-white">Anthrax - Caught in a Mosh</h4>
                      <p class="text-gray-500 text-sm">1987 | 4:59</p>
                    </div>
                  </div>
                  <div class="w-8 h-8 flex items-center justify-center">
                    <i
                      class="ri-heart-line ri-lg text-gray-400 hover:text-primary cursor-pointer"
                    ></i>
                  </div>
                </div>
              </div>

              <div class="p-4 border-t border-gray-800">
                <button
                  class="bg-primary hover:bg-red-800 text-white px-4 py-2 !rounded-button whitespace-nowrap transition-colors"
                >
                  სრული პლეილისტი
                </button>
              </div>
            </div>
          </div>

          <div class="mt-12">
            <div class="bg-gray-900 rounded-lg p-6">
              <h3 class="gothic-font text-2xl text-white mb-4">
                მუსიკის მოსმენა
              </h3>
              <div class="mb-6">
                <div class="flex justify-between items-center mb-2">
                  <span class="text-white">Iron Maiden - The Trooper</span>
                  <span class="text-gray-400">2:45 / 4:12</span>
                </div>
                <input
                  type="range"
                  min="0"
                  max="100"
                  value="65"
                  class="custom-range mb-4"
                />
                <div class="flex justify-center space-x-6">
                  <button
                    class="w-12 h-12 bg-gray-800 hover:bg-gray-700 rounded-full flex items-center justify-center"
                  >
                    <i class="ri-skip-back-line ri-lg text-white"></i>
                  </button>
                  <button
                    class="w-16 h-16 bg-primary hover:bg-red-800 rounded-full flex items-center justify-center"
                  >
                    <i class="ri-pause-line ri-2x text-white"></i>
                  </button>
                  <button
                    class="w-12 h-12 bg-gray-800 hover:bg-gray-700 rounded-full flex items-center justify-center"
                  >
                    <i class="ri-skip-forward-line ri-lg text-white"></i>
                  </button>
                </div>
              </div>
              <div class="flex items-center justify-between">
                <div class="flex items-center">
                  <div class="w-10 h-10 flex items-center justify-center mr-2">
                    <i class="ri-volume-up-line ri-lg text-gray-400"></i>
                  </div>
                  <input
                    type="range"
                    min="0"
                    max="100"
                    value="80"
                    class="custom-range w-24"
                  />
                </div>
                <div class="flex space-x-4">
                  <div class="w-10 h-10 flex items-center justify-center">
                    <i class="ri-repeat-line ri-lg text-primary"></i>
                  </div>
                  <div class="w-10 h-10 flex items-center justify-center">
                    <i
                      class="ri-shuffle-line ri-lg text-gray-400 hover:text-primary cursor-pointer"
                    ></i>
                  </div>
                  <div class="w-10 h-10 flex items-center justify-center">
                    <i
                      class="ri-list-check-2 ri-lg text-gray-400 hover:text-primary cursor-pointer"
                    ></i>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Forum Section -->
      <section id="forum" class="py-16 bg-gray-900">
        <div class="container mx-auto px-4">
          <h2 class="metal-font text-4xl text-center text-white mb-12">
            ბაბუების ფორუმი
          </h2>

          <div class="bg-black rounded-lg overflow-hidden shadow-lg mb-8">
            <div class="p-6 border-b border-gray-800">
              <h3 class="gothic-font text-2xl text-white mb-2">
                დაწერე შენი ისტორია
              </h3>
              <p class="text-gray-400 mb-4">
                გაუზიარე სხვა ბაბუებს შენი მოგონებები და თავგადასავლები
              </p>
              <div class="mb-4">
                <input
                  type="text"
                  placeholder="სათაური"
                  class="w-full bg-gray-800 text-white border-none rounded p-3 mb-3"
                />
                <textarea
                  placeholder="შენი ისტორია..."
                  class="w-full bg-gray-800 text-white border-none rounded p-3 h-32"
                ></textarea>
              </div>
              <div class="flex justify-between items-center">
                <div class="flex items-center space-x-4">
                  <button
                    class="w-10 h-10 bg-gray-800 hover:bg-gray-700 rounded flex items-center justify-center"
                  >
                    <i class="ri-image-line ri-lg text-gray-400"></i>
                  </button>
                  <button
                    class="w-10 h-10 bg-gray-800 hover:bg-gray-700 rounded flex items-center justify-center"
                  >
                    <i class="ri-link ri-lg text-gray-400"></i>
                  </button>
                  <button
                    class="w-10 h-10 bg-gray-800 hover:bg-gray-700 rounded flex items-center justify-center"
                  >
                    <i class="ri-emotion-line ri-lg text-gray-400"></i>
                  </button>
                </div>
                <button
                  class="bg-primary hover:bg-red-800 text-white px-6 py-2 font-bold !rounded-button whitespace-nowrap transition-colors"
                >
                  გამოქვეყნება
                </button>
              </div>
            </div>

            <!-- Forum Post 1 -->
            <div class="forum-item p-6 border-b border-gray-800">
              <div class="flex items-start mb-4">
                <img
                  src="https://readdy.ai/api/search-image?query=older%20man%20with%20long%20gray%20hair%20and%20beard%20wearing%20black%20leather%20jacket%2C%20rock%20style%2C%20heavy%20metal%20fan%2C%20atmospheric%20portrait%2C%20dramatic%20lighting%2C%20serious%20expression%2C%20vintage%20motorcycle%20in%20background&width=100&height=100&seq=grandpa1sm&orientation=squarish"
                  alt="გიორგი"
                  class="w-12 h-12 rounded-full object-cover object-top mr-4"
                />
                <div>
                  <h4 class="text-white font-bold">
                    გიორგი "გიტარა" მაისურაძე
                  </h4>
                  <p class="text-gray-500 text-sm">2025-06-20 | 15:30</p>
                </div>
              </div>
              <h3 class="text-xl text-white mb-3">
                ჩემი პირველი კონცერტი - Deep Purple 1974
              </h3>
              <p class="text-gray-300 mb-4">
                მახსოვს როგორ ვიყავი Deep Purple-ის კონცერტზე 1974 წელს. ეს იყო
                ჩემი ცხოვრების ყველაზე დაუვიწყარი დღე. რიტჩი ბლექმორის გიტარის
                სოლო დღემდე მახსოვს. იმ დღეს გადავწყვიტე, რომ გიტარისტი უნდა
                გავმხდარიყავი. მას შემდეგ 40 წელი გავიდა და ჯერ კიდევ ვუკრავ!
              </p>
              <div class="flex justify-between items-center">
                <div class="flex space-x-4">
                  <button
                    class="flex items-center text-gray-400 hover:text-primary"
                  >
                    <i class="ri-thumb-up-line ri-lg mr-1"></i>
                    <span>42</span>
                  </button>
                  <button
                    class="flex items-center text-gray-400 hover:text-primary"
                  >
                    <i class="ri-chat-1-line ri-lg mr-1"></i>
                    <span>12</span>
                  </button>
                </div>
                <button class="text-gray-400 hover:text-primary">
                  <i class="ri-share-line ri-lg"></i>
                </button>
              </div>
            </div>

            <!-- Forum Post 2 -->
            <div class="forum-item p-6 border-b border-gray-800">
              <div class="flex items-start mb-4">
                <img
                  src="https://readdy.ai/api/search-image?query=older%20man%20with%20bald%20head%20and%20white%20beard%20wearing%20denim%20vest%20with%20patches%2C%20heavy%20metal%20fan%2C%20atmospheric%20portrait%2C%20dramatic%20lighting%2C%20confident%20pose%2C%20vintage%20motorcycle%20in%20background&width=100&height=100&seq=grandpa2sm&orientation=squarish"
                  alt="ზურაბი"
                  class="w-12 h-12 rounded-full object-cover object-top mr-4"
                />
                <div>
                  <h4 class="text-white font-bold">ზურაბ "ზურა" კვარაცხელია</h4>
                  <p class="text-gray-500 text-sm">2025-06-19 | 11:15</p>
                </div>
              </div>
              <h3 class="text-xl text-white mb-3">
                ჩემი მოტოციკლით მოგზაურობა მეტალ ფესტივალზე
              </h3>
              <p class="text-gray-300 mb-4">
                1985 წელს ჩემი Harley-Davidson-ით გავემგზავრე მეტალ ფესტივალზე.
                500 კილომეტრი გავიარე, წვიმაში და ქარში. როცა ჩავედი, Iron
                Maiden-ი უკრავდა "The Trooper"-ს. ის მომენტი არასოდეს
                დამავიწყდება. ვინმეს თუ ახსოვს ის ფესტივალი?
              </p>
              <div class="flex justify-between items-center">
                <div class="flex space-x-4">
                  <button
                    class="flex items-center text-gray-400 hover:text-primary"
                  >
                    <i class="ri-thumb-up-line ri-lg mr-1"></i>
                    <span>36</span>
                  </button>
                  <button
                    class="flex items-center text-gray-400 hover:text-primary"
                  >
                    <i class="ri-chat-1-line ri-lg mr-1"></i>
                    <span>8</span>
                  </button>
                </div>
                <button class="text-gray-400 hover:text-primary">
                  <i class="ri-share-line ri-lg"></i>
                </button>
              </div>
            </div>
          </div>

          <div class="text-center">
            <button
              class="bg-gray-800 hover:bg-gray-700 text-white px-6 py-3 font-bold !rounded-button whitespace-nowrap transition-colors"
            >
              მეტი ისტორია
            </button>
          </div>
        </div>
      </section>

      <!-- News Section -->
      <section id="news" class="py-16 bg-black">
        <div class="container mx-auto px-4">
          <h2 class="metal-font text-4xl text-center text-white mb-12">
            ბაბუების ახალი ამბები
          </h2>

          <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <!-- News 1 -->
            <div class="bg-gray-900 rounded-lg overflow-hidden shadow-lg">
              <div class="h-48 overflow-hidden">
                <img
                  src="https://readdy.ai/api/search-image?query=group%20of%20older%20men%20at%20heavy%20metal%20concert%2C%20enjoying%20music%2C%20atmospheric%20lighting%2C%20rock%20and%20roll%2C%20vintage%20style%2C%20dramatic%20scene%2C%20crowd%20of%20senior%20metalheads&width=400&height=250&seq=news1&orientation=landscape"
                  alt="კონცერტი"
                  class="w-full h-full object-cover object-top"
                />
              </div>
              <div class="p-4">
                <div class="flex justify-between items-center mb-3">
                  <span class="bg-primary text-white text-sm px-2 py-1 rounded"
                    >ღონისძიება</span
                  >
                  <span class="text-gray-500 text-sm">2025-06-15</span>
                </div>
                <h3 class="gothic-font text-xl text-white mb-3">
                  ბაბუების მეტალ ჯემი - წარმატებული შეხვედრა
                </h3>
                <p class="text-gray-300 mb-4">
                  წინა კვირას ჩატარდა ბაბუების მეტალ ჯემი, სადაც 20-ზე მეტმა
                  ბაბუამ დაუკრა თავისი საყვარელი სიმღერები. ღონისძიება 5 საათს
                  გაგრძელდა!
                </p>
                <button class="text-primary hover:text-red-400 font-bold">
                  სრულად წაკითხვა →
                </button>
              </div>
            </div>

            <!-- News 2 -->
            <div class="bg-gray-900 rounded-lg overflow-hidden shadow-lg">
              <div class="h-48 overflow-hidden">
                <img
                  src="https://readdy.ai/api/search-image?query=vintage%20motorcycle%20rally%20with%20older%20men%2C%20leather%20jackets%2C%20classic%20motorcycles%20lined%20up%2C%20atmospheric%20lighting%2C%20dramatic%20scene%2C%20senior%20bikers%20meeting&width=400&height=250&seq=news2&orientation=landscape"
                  alt="მოტოციკლები"
                  class="w-full h-full object-cover object-top"
                />
              </div>
              <div class="p-4">
                <div class="flex justify-between items-center mb-3">
                  <span class="bg-primary text-white text-sm px-2 py-1 rounded"
                    >მოგზაურობა</span
                  >
                  <span class="text-gray-500 text-sm">2025-06-10</span>
                </div>
                <h3 class="gothic-font text-xl text-white mb-3">
                  ბაბუების მოტო-ტური დაგეგმილია ივლისში
                </h3>
                <p class="text-gray-300 mb-4">
                  ივლისში იგეგმება ბაბუების მოტო-ტური მთის გზებზე. მარშრუტი 300
                  კმ-ს მოიცავს. მონაწილეობის მსურველებმა დაგვიკავშირდით.
                </p>
                <button class="text-primary hover:text-red-400 font-bold">
                  სრულად წაკითხვა →
                </button>
              </div>
            </div>

            <!-- News 3 -->
            <div class="bg-gray-900 rounded-lg overflow-hidden shadow-lg">
              <div class="h-48 overflow-hidden">
                <img
                  src="https://readdy.ai/api/search-image?query=vinyl%20record%20collection%2C%20vintage%20albums%2C%20heavy%20metal%20records%2C%20atmospheric%20lighting%2C%20dramatic%20scene%2C%20classic%20rock%20albums%2C%20record%20store&width=400&height=250&seq=news3&orientation=landscape"
                  alt="ვინილები"
                  class="w-full h-full object-cover object-top"
                />
              </div>
              <div class="p-4">
                <div class="flex justify-between items-center mb-3">
                  <span class="bg-primary text-white text-sm px-2 py-1 rounded"
                    >კოლექცია</span
                  >
                  <span class="text-gray-500 text-sm">2025-06-05</span>
                </div>
                <h3 class="gothic-font text-xl text-white mb-3">
                  ლევან "ბასი" ბერიძემ 1000 ვინილის კოლექცია შეაგროვა
                </h3>
                <p class="text-gray-300 mb-4">
                  ჩვენმა წევრმა ლევანმა მიაღწია 1000 ვინილის კოლექციას! მისი
                  უახლესი შენაძენია Black Sabbath-ის იშვიათი ჩანაწერი 1970
                  წლიდან.
                </p>
                <button class="text-primary hover:text-red-400 font-bold">
                  სრულად წაკითხვა →
                </button>
              </div>
            </div>
          </div>

          <div class="mt-12">
            <div class="bg-gray-900 rounded-lg p-6">
              <h3 class="gothic-font text-2xl text-white mb-4">
                გამოიწერე ბაბუების სიახლეები
              </h3>
              <p class="text-gray-300 mb-6">
                მიიღე უახლესი ინფორმაცია ღონისძიებების, შეხვედრების და მეტალის
                სიახლეების შესახებ
              </p>
              <div class="flex flex-col md:flex-row gap-4">
                <input
                  type="email"
                  placeholder="შენი ელ-ფოსტა"
                  class="flex-grow bg-gray-800 text-white border-none rounded p-3"
                />
                <div class="flex items-center">
                  <label class="custom-switch mr-3">
                    <input type="checkbox" checked />
                    <span class="slider"></span>
                  </label>
                  <span class="text-gray-300">კვირაში ერთხელ</span>
                </div>
                <button
                  class="bg-primary hover:bg-red-800 text-white px-6 py-3 font-bold !rounded-button whitespace-nowrap transition-colors"
                >
                  გამოწერა
                </button>
              </div>
            </div>
          </div>
        </div>
      </section>
    </main>
    <footer class="bg-black py-12 border-t border-gray-800">
      <div class="container mx-auto px-4">
        <div class="grid grid-cols-1 md:grid-cols-4 gap-8 mb-8">
          <div>
            <div class="flex items-center mb-4">
              <div
                class="w-12 h-12 bg-primary rounded-full flex items-center justify-center mr-3"
              >
                <i class="ri-skull-2-line ri-xl text-white"></i>
              </div>
              <h2 class="metal-font text-2xl text-white">
                მძიმე ბაბუების კლუბი
              </h2>
            </div>
            <p class="text-gray-400 mb-4">
              ადგილი, სადაც პენსიონერი მეტალისტები ერთიანდებიან, რათა გაიზიარონ
              თავიანთი სიყვარული მძიმე მუსიკის, მოტოციკლების და ნოსტალგიის
              მიმართ.
            </p>
            <div class="flex space-x-4">
              <a
                href="#"
                class="w-10 h-10 bg-gray-800 hover:bg-gray-700 rounded-full flex items-center justify-center"
              >
                <i class="ri-facebook-fill ri-lg text-white"></i>
              </a>
              <a
                href="#"
                class="w-10 h-10 bg-gray-800 hover:bg-gray-700 rounded-full flex items-center justify-center"
              >
                <i class="ri-instagram-line ri-lg text-white"></i>
              </a>
              <a
                href="#"
                class="w-10 h-10 bg-gray-800 hover:bg-gray-700 rounded-full flex items-center justify-center"
              >
                <i class="ri-youtube-fill ri-lg text-white"></i>
              </a>
            </div>
          </div>

          <div>
            <h3 class="gothic-font text-xl text-white mb-4">ნავიგაცია</h3>
            <ul class="space-y-2">
              <li>
                <a href="#" class="text-gray-400 hover:text-primary">მთავარი</a>
              </li>
              <li>
                <a href="#grandfathers" class="text-gray-400 hover:text-primary"
                  >ბაბუები</a
                >
              </li>
              <li>
                <a href="#forum" class="text-gray-400 hover:text-primary"
                  >ფორუმი</a
                >
              </li>
              <li>
                <a href="#playlists" class="text-gray-400 hover:text-primary"
                  >პლეილისტები</a
                >
              </li>
              <li>
                <a href="#news" class="text-gray-400 hover:text-primary"
                  >ახალი ამბები</a
                >
              </li>
            </ul>
          </div>

          <div>
            <h3 class="gothic-font text-xl text-white mb-4">
              მომავალი ღონისძიებები
            </h3>
            <ul class="space-y-4">
              <li class="flex items-start">
                <div class="w-8 h-8 flex items-center justify-center mr-2 mt-1">
                  <i class="ri-calendar-event-line ri-lg text-primary"></i>
                </div>
                <div>
                  <h4 class="text-white">ბაბუების ჯემ-სეშენი</h4>
                  <p class="text-gray-500">2025-07-15 | 18:00</p>
                </div>
              </li>
              <li class="flex items-start">
                <div class="w-8 h-8 flex items-center justify-center mr-2 mt-1">
                  <i class="ri-motorbike-line ri-lg text-primary"></i>
                </div>
                <div>
                  <h4 class="text-white">მოტო-ტური</h4>
                  <p class="text-gray-500">2025-07-20 | 10:00</p>
                </div>
              </li>
              <li class="flex items-start">
                <div class="w-8 h-8 flex items-center justify-center mr-2 mt-1">
                  <i class="ri-album-line ri-lg text-primary"></i>
                </div>
                <div>
                  <h4 class="text-white">ვინილების გაცვლა</h4>
                  <p class="text-gray-500">2025-07-25 | 16:00</p>
                </div>
              </li>
            </ul>
          </div>

          <div>
            <h3 class="gothic-font text-xl text-white mb-4">დაგვიკავშირდით</h3>
            <ul class="space-y-3">
              <li class="flex items-start">
                <div class="w-8 h-8 flex items-center justify-center mr-2 mt-1">
                  <i class="ri-map-pin-line ri-lg text-primary"></i>
                </div>
                <span class="text-gray-400">მეტალის ქუჩა 66, თბილისი</span>
              </li>
              <li class="flex items-start">
                <div class="w-8 h-8 flex items-center justify-center mr-2 mt-1">
                  <i class="ri-phone-line ri-lg text-primary"></i>
                </div>
                <span class="text-gray-400">+995 555 123 456</span>
              </li>
              <li class="flex items-start">
                <div class="w-8 h-8 flex items-center justify-center mr-2 mt-1">
                  <i class="ri-mail-line ri-lg text-primary"></i>
                </div>
                <span class="text-gray-400">info@mdzimebabu.ge</span>
              </li>
            </ul>
          </div>
        </div>

        <div
          class="border-t border-gray-800 pt-8 flex flex-col md:flex-row justify-between items-center"
        >
          <p class="text-gray-500 mb-4 md:mb-0">
            © 2025 მძიმე ბაბუების კლუბი. ყველა უფლება დაცულია.
          </p>
          <div class="flex space-x-4">
            <a href="#" class="text-gray-500 hover:text-primary">წესები</a>
            <a href="#" class="text-gray-500 hover:text-primary"
              >კონფიდენციალურობა</a
            >
            <a href="#" class="text-gray-500 hover:text-primary">დახმარება</a>
          </div>
        </div>
      </div>
    </footer>

    <script id="mobile-menu-script">
      document.addEventListener("DOMContentLoaded", function () {
        const mobileMenuButton = document.getElementById("mobile-menu-button");
        const mobileMenu = document.getElementById("mobile-menu");

        mobileMenuButton.addEventListener("click", function () {
          mobileMenu.classList.toggle("hidden");

          if (mobileMenu.classList.contains("hidden")) {
            mobileMenuButton.innerHTML = '<i class="ri-menu-line ri-lg"></i>';
          } else {
            mobileMenuButton.innerHTML = '<i class="ri-close-line ri-lg"></i>';
          }
        });
      });
    </script>

    <script id="form-interactions">
      document.addEventListener("DOMContentLoaded", function () {
        // Radio buttons
        const radioButtons = document.querySelectorAll('input[type="radio"]');
        radioButtons.forEach((radio) => {
          radio.addEventListener("click", function () {
            radioButtons.forEach((rb) => {
              if (rb !== this) {
                rb.checked = false;
              }
            });
          });
        });

        // Heart icons
        const heartIcons = document.querySelectorAll(".ri-heart-line");
        heartIcons.forEach((icon) => {
          icon.addEventListener("click", function () {
            if (this.classList.contains("ri-heart-line")) {
              this.classList.remove("ri-heart-line");
              this.classList.add("ri-heart-fill");
              this.classList.add("text-primary");
            } else {
              this.classList.remove("ri-heart-fill");
              this.classList.remove("text-primary");
              this.classList.add("ri-heart-line");
            }
          });
        });
      });
    </script>
  </body>
</html>
