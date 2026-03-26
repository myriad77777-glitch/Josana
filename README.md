# Josana
intel.html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Josana Day Academy</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">

<style>
body { margin:0; font-family:'Poppins',sans-serif; background:#f5f7fa; }

/* NAV */
nav {
  display:flex;
  justify-content:space-between;
  padding:15px 30px;
  background:white;
  position:sticky;
  top:0;
}
nav a { margin:0 10px; text-decoration:none; color:#333; }

/* SLIDER */
.slider { position:relative; height:80vh; overflow:hidden; }
.slide {
  position:absolute;
  width:100%;
  height:100%;
  opacity:0;
  transition:1s;
}
.slide img { width:100%; height:100%; object-fit:cover; }
.slide.active { opacity:1; }

/* CAPTION */
.caption {
  position:absolute;
  top:50%;
  left:50%;
  transform:translate(-50%,-50%);
  color:white;
  text-align:center;
  background:rgba(0,0,0,0.4);
  padding:20px;
  border-radius:10px;
}

/* ARROWS */
.prev,.next {
  position:absolute;
  top:50%;
  transform:translateY(-50%);
  background:rgba(0,0,0,0.5);
  color:white;
  border:none;
  padding:10px;
}
.prev { left:20px; }
.next { right:20px; }

/* SECTION */
.section {
  padding:60px 20px;
  text-align:center;
}

/* GALLERY GRID */
.gallery {
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
  gap:15px;
  padding:20px;
}
.gallery img {
  width:100%;
  height:200px;
  object-fit:cover;
  border-radius:10px;
  cursor:pointer;
  transition:0.3s;
}
.gallery img:hover {
  transform:scale(1.05);
}

/* MODAL (CLICK IMAGE FULLSCREEN) */
.modal {
  display:none;
  position:fixed;
  top:0;
  left:0;
  width:100%;
  height:100%;
  background:rgba(0,0,0,0.9);
  justify-content:center;
  align-items:center;
}
.modal img {
  max-width:90%;
  max-height:90%;
}

/* FOOTER */
footer {
  background:#001a33;
  color:white;
  text-align:center;
  padding:20px;
}
</style>
</head>

<body>

<nav>
  <h2>Josana Academy</h2>
  <div>
    <a href="#">Home</a>
    <a href="#gallery">Gallery</a>
  </div>
</nav>

<!-- SLIDER -->
<div class="slider">

<div class="slide active">
<img src="IMAGE1.jpg">
<div class="caption">
<h1>Welcome to Josana Academy</h1>
</div>
</div>

<div class="slide">
<img src="IMAGE2.jpg">
<div class="caption">
<h1>Quality Education</h1>
</div>
</div>

<button class="prev">❮</button>
<button class="next">❯</button>

</div>

<!-- GALLERY -->
<div class="section" id="gallery">
<h2>Our School Life</h2>

<div class="gallery">
<img src="IMAGE1.jpg">
<img src="IMAGE2.jpg">
<img src="IMAGE3.jpg">
<img src="IMAGE4.jpg">
<img src="IMAGE5.jpg">
<img src="IMAGE6.jpg">
</div>

</div>

<!-- MODAL -->
<div class="modal" id="modal">
<img id="modalImg">
</div>

<footer>
<p>© 2026 Josana Day Academy</p>
</footer>

<!-- WHATSAPP -->
<a href="https://wa.me/254XXXXXXXXX"
style="position:fixed;bottom:20px;right:20px;
background:#25D366;color:white;padding:15px;
border-radius:50%;">💬</a>

<script>
let slides=document.querySelectorAll('.slide');
let index=0;

document.querySelector('.next').onclick=()=>{
 index=(index+1)%slides.length;
 show();
};
document.querySelector('.prev').onclick=()=>{
 index=(index-1+slides.length)%slides.length;
 show();
};

function show(){
 slides.forEach(s=>s.classList.remove('active'));
 slides[index].classList.add('active');
}
setInterval(()=>{index=(index+1)%slides.length;show();},4000);

/* GALLERY CLICK */
let modal=document.getElementById('modal');
let modalImg=document.getElementById('modalImg');

document.querySelectorAll('.gallery img').forEach(img=>{
 img.onclick=()=>{
  modal.style.display='flex';
  modalImg.src=img.src;
 };
});

modal.onclick=()=>{modal.style.display='none';};
</script>

</body>
</html>
