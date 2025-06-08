# personal_homepages
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>孙杭瑜的个人主页</title>
    <link rel="stylesheet" href="css/style.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <header>
        <div class="container">
            <div class="profile">
                < img src="images/profile.jpg" alt="孙杭瑜的照片" class="profile-img">
                <h1>孙杭瑜</h1>
                <p class="signature">你当像鸟飞往你的山</p >
            </div>
            <nav>
                <ul>
                    <li>基本信息</li>
                    <li>我的学校</li>
                    <li>我的爱好</li>
                    <li>我的相册</li>
                </ul>
            </nav>
        </div>
    </header>

    <main>
        <section id="about" class="section">
            <div class="container">
                <h2>基本信息</h2>
                <div class="info-grid">
                    <div class="info-item">
                        <i class="fas fa-user"></i>
                        <span>姓名：孙杭瑜</span>
                    </div>
                    <div class="info-item">
                        <i class="fas fa-venus"></i>
                        <span>性别：女</span>
                    </div>
                    <div class="info-item">
                        <i class="fas fa-birthday-cake"></i>
                        <span>出生年月：2006年1月</span>
                    </div>
                    <div class="info-item">
                        <i class="fas fa-calendar-alt"></i>
                        <span>年龄：19岁</span>
                    </div>
                    <div class="info-item">
                        <i class="fas fa-phone"></i>
                        <span>电话：13819314622</span>
                    </div>
                    <div class="info-item">
                        <i class="fas fa-envelope"></i>
                        <span>邮箱：hangyu_sun@126.com</span>
                    </div>
                    <div class="info-item">
                        <i class="fas fa-graduation-cap"></i>
                        <span>专业：会计学</span>
                    </div>
                    <div class="info-item">
                        <i class="fas fa-book"></i>
                        <span>学历：本科</span>
                    </div>
                </div>
            </div>
        </section>

        <section id="education" class="section">
            <div class="container">
                <h2>我的学校</h2>
                <div class="school-info">
                    < img src="images/school.jpg" alt="嘉兴大学" class="school-img">
                    <div class="school-text">
                        <h3>嘉兴大学</h3>
                        <p>嘉兴大学是一所位于浙江嘉兴的综合性大学，校园环境优美，学风浓厚，给我提供了丰富的学习与成长机会。</p >
                    </div>
                </div>
            </div>
        </section>

        <section id="hobbies" class="section">
            <div class="container">
                <h2>我的爱好</h2>
                <div class="hobbies-grid">
                    <div class="hobby-card">
                        <div class="hobby-icon">
                            <i class="fas fa-camera"></i>
                        </div>
                        <h3>摄影</h3>
                        <p>我喜欢用镜头记录生活中的美好瞬间，无论是风景、人物还是日常的小物，都能成为我镜头下的故事。</p >
                    </div>
                    <div class="hobby-card">
                        <div class="hobby-icon">
                            <i class="fas fa-plane"></i>
                        </div>
                        <h3>旅行</h3>
                        <p>旅行让我认识不同的人、风土与文化。走出去，世界变得更广阔，心也更自由。</p >
                    </div>
                    <div class="hobby-card">
                        <div class="hobby-icon">
                            <i class="fas fa-book"></i>
                        </div>
                        <h3>阅读</h3>
                        <p>读书是我生活的一部分，尤其喜欢悬疑、人文类的书籍。阅读让我沉静下来，也让我不断思考与成长。</p >
                    </div>
                </div>
            </div>
        </section>

        <section id="gallery" class="section">
            <div class="container">
                <h2>我的相册</h2>
                <div class="gallery-grid">
                    <div class="gallery-item">
                        < img src="images/hobby1.jpg" alt="摄影">
                        <div class="gallery-caption">摄影作品</div>
                    </div>
                    <div class="gallery-item">
                        < img src="images/hobby2.jpg" alt="旅行">
                        <div class="gallery-caption">旅行记忆</div>
                    </div>
                    <div class="gallery-item">
                        < img src="images/hobby3.jpg" alt="阅读">
                        <div class="gallery-caption">阅读时光</div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <footer>
        <div class="container">
            <p>&copy; 2024 孙杭瑜的个人主页</p >
            <div class="social-links">
                <i class="fab fa-weixin"></i>
                <i class="fab fa-weibo"></i>
                
            </div>
        </div>
    </footer>

    <script src="js/script.js"></script>
</body>
</html>
// 平滑滚动效果
document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function (e) {
        e.preventDefault();
        
        document.querySelector(this.getAttribute('href')).scrollIntoView({
            behavior: 'smooth'
        });
    });
});

// 导航栏高亮效果
const sections = document.querySelectorAll('section');
const navItems = document.querySelectorAll('nav ul li a');

window.addEventListener('scroll', () => {
    let current = '';
    
    sections.forEach(section => {
        const sectionTop = section.offsetTop;
        const sectionHeight = section.clientHeight;
        
        if (pageYOffset >= (sectionTop - 300)) {
            current = section.getAttribute('id');
        }
    });
    
    navItems.forEach(item => {
        item.classList.remove('active');
        if (item.getAttribute('href') === `#${current}`) {
            item.classList.add('active');
        }
    });
});

// 图片懒加载
const images = document.querySelectorAll('img[data-src]');

const imgOptions = {
    threshold: 0,
    rootMargin: '0px 0px 50px 0px'
};

const imgObserver = new IntersectionObserver((entries, imgObserver) => {
    entries.forEach(entry => {
        if (!entry.isIntersecting) {
            return;
        } else {
            preloadImage(entry.target);
            imgObserver.unobserve(entry.target);
        }
    });
}, imgOptions);

images.forEach(image => {
    imgObserver.observe(image);
});

function preloadImage(img) {
    const src = img.getAttribute('data-src');
    if (!src) {
        return;
    }
    img.src = src;
}
