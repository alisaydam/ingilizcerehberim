<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="utf-8" />
		<title>İngilizce Rehberim</title>
		<meta
			name="viewport"
			content="width=device-width, initial-scale=1, minimum-scale=1, maximum-scale=1"
		/>
		<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.css" />
		<style>
			html,
			body {
				position: relative;
				height: 100%;
				margin: 0;
				padding: 0;
			}

			body {
				background: #eee;
				font-family:
					Helvetica Neue,
					Helvetica,
					Arial,
					sans-serif;
				font-size: 14px;
				color: #000;
				margin: 0;
				padding: 0;
			}

			.swiper {
				width: 100%;
				height: 100%;
			}

			.swiper-slide {
				background-position: center;
				background-size: cover;
				background-color: black;
				color: #fffafa;
				display: flex;
				align-items: center;
				justify-content: center;
				font-size: 20px;
			}

			p {
				text-align: center;
				padding: 2rem;
			}
		</style>
	</head>

	<body>
		<!-- <div class="topics">
				<div class="head">
					<p>• PRESENT SİMPLE FORMS OF ‘TO BE’ -am,is,are</p>
					<p>˅</p>
				</div>
				<div class="summary">
					<p class="recap">
						"To be" fiilinin şimdiki basit biçimleri, şimdiki zamanda bir kişiyi, şeyi veya durumu
						tanımlamak için kullanılır. Bu formlar genellikle genel gerçekler, rutinler,
						alışkanlıklar ve şimdiki zamanda olma durumları hakkında konuşmak için kullanılır.
						Oldukça basit bir şekilde açıklamak gerekirse; eğer özne “I” ise “to be” fiili kendini
						“Am” olarak, “He / She / It” ise “Is” olarak, “You / We / They” ise kendini “Are” olarak
						gösterir.
					</p>
					<p class="link">
						<a href="www.google.com" target="_blank">
							Buraya tıklayarak detaylı konu anlatımına git
						</a>
					</p>
				</div>
			</div> -->
		<!-- Swiper -->
		<div class="swiper mySwiper">
			<div class="swiper-wrapper">
				<div class="swiper-slide">
					<p>ingilizcerehberim.org'a Hoşgeldiniz</p>
				</div>
				<div class="swiper-slide">
					<p>
						Bu site, ALKÜ İngilizce Bölümü, Topluma Hizmet dersi proje ödevi kapsamında
						hazırlanmıştır.
					</p>
				</div>
				<div class="swiper-slide">
					<p>
						Bu sitede, İngilizce öğrenmek isteyen öğrenciler için A1'den B2'ye kadar olan İngilizce
						konular, çeşitli kaynaklardan yararlanılarak derlenmeiştir.
					</p>
				</div>
				<div class="swiper-slide">
					<p>
						Sitede direkt konu anlatımı olmamakla beraber, internette bulunan kaynaklar her seviyeye
						göre uygun olarak sıralanmıştır.
					</p>
				</div>
				<div class="swiper-slide">
					<p>
						Her seviye için listenin(dinleme) yapabileceğiniz İngilizce video linkleri mevcuttur.
					</p>
				</div>
				<div class="swiper-slide">
					<p>Yönendiriliyor...</p>
				</div>
				<div class="swiper-button-next"></div>
				<div class="swiper-button-prev"></div>
				<div class="swiper-pagination"></div>
			</div>
		</div>
		<script src="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.js"></script>
		<script>
			var swiper = new Swiper('.mySwiper', {
				spaceBetween: 30,
				effect: 'fade',
				rewind: false,
				autoplay: {
					delay: 4000,
					disableOnInteraction: false,
					stopOnLastSlide: true
				},
				navigation: {
					nextEl: '.swiper-button-next',
					prevEl: '.swiper-button-prev'
				},
				pagination: {
					el: '.swiper-pagination',
					type: 'progressbar',
					clickable: true
				},
				on: {
					touchStart: function () {
						// Pause autoplay when the user starts touching the screen
						swiper.autoplay.stop();
					},
					touchEnd: function () {
						// Resume autoplay when the user releases the touch
						swiper.autoplay.start();
					},
					transitionEnd: function () {
						// Check if the current slide is the last one
						if (swiper.isEnd) {
							// You can add your redirection logic here
							setTimeout(function () {
								// You can add your redirection logic here
								redirectToNewURL();
							}, 2000);
						}
					}
				}
			});
			// Function to redirect to a new URL
			function redirectToNewURL() {
				// Replace 'YOUR_REDIRECT_URL' with the actual URL you want to redirect to
				window.location.href = 'home';
			}
		</script>
	</body>
</html>
