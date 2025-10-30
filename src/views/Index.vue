<template>
  <div>
    <!-- header -->
    <div class="portfolio-header flex items-c" :class="{ 'is-show': mobileGnbShow }">
      <div class="hd-inner-grp flex items-c justify-b">
        <div class="hd-title f-b f-pop f-ws-n p-cursor" @click="scrollToSection('.intro-sec', true)">
          HYEONJI FORTFOLIO
        </div>

        <div class="gnb-list-grp flex tab-hide">
          <div class="gnb" @click="scrollToSection('.intro-sec')">Intro</div>
          <div class="gnb" @click="scrollToSection('.about-sec')">About Me</div>
          <div class="gnb" @click="scrollToSection('.work-sec')">Work</div>
          <div class="gnb" @click="scrollToSection('.skills-sec')">Skills</div>
        </div>

        <button class="btn btn-hd-contact f-pop f-m f-ws-n tab-hide" @click="scrollToSection('.contact-sec')">
          Contact <i class="icon icon-arrow-right"></i>
        </button>

        <button
          class="btn hamburger tab-show-flex"
          :class="{ 'is-active': mobileGnbShow }"
          @click="toggleMobileGnb"
          aria-label="모바일 메뉴"
          :aria-expanded="mobileGnbShow"
        >
          <span class="bar bar-top"></span>
          <span class="bar bar-mid"></span>
          <span class="bar bar-bot"></span>
        </button>
      </div>

      <!-- 모바일 메뉴 -->
      <div class="mo-hd-grp">
        <div class="mo-gnb-list-grp">
          <div class="mo-gnb" @click="scrollToSection('.intro-sec', true)">Intro</div>
          <div class="mo-gnb" @click="scrollToSection('.about-sec', true)">About Me</div>
          <div class="mo-gnb" @click="scrollToSection('.work-sec', true)">Work</div>
          <div class="mo-gnb" @click="scrollToSection('.skills-sec', true)">Skills</div>
        </div>

        <button class="btn btn-hd-contact f-pop f-m f-ws-n" @click="scrollToSection('.contact-sec', true)">
          Contact <i class="icon icon-arrow-right"></i>
        </button>
      </div>
    </div>
    <!-- END header -->

    <div class="page main-page">
      <div class="intro-sec pos-r">
        <div class="intro-bg img img-con">
          <video
            class="intro-video img-cov"
            src="@/assets/images/video/video_intro_bg.mp4"
            autoplay
            muted
            loop
            playsinline
          ></video>
        </div>
        <div class="intro-txt-grp">
          <p class="intro-title f-wh" data-aos="fade-up">
            완성도를 책임지는 <br class="tab-show" /><span class="highlight">웹 퍼블리셔 김현지</span>입니다.
          </p>

          <div class="intro-sub-txt-grp flex">
            <p class="intro-sub-txt">${Flexible Thinking}</p>
            <p class="intro-sub-txt">${Creative thinking}</p>
            <p class="intro-sub-txt">${Communication skills}</p>
            <p class="intro-sub-txt">${roblem-solving skills}</p>
          </div>
        </div>
      </div>

      <!-- About me -->
      <div class="about-sec">
        <div class="about-inner-grp l-center">
          <p class="top-title f-bk f-b f-pop f-center" data-aos="fade-up">About Me</p>
          <div class="emoticon-img-grp" data-aos="fade-up" data-aos-delay="50">
            <img src="@/assets/images/img_emoticon_01.png" alt="이모티콘 이미지" class="emoticon-img" />
          </div>
          <p class="sub-txt f-bk f-r f-center" data-aos="fade-up" data-aos-delay="100">
            안녕하세요! 저는 <span class="highlight type-2">변화하는 웹 퍼블리셔 김현지</span>입니다.<br />
            현실에 안주하지 않고, <br class="mb-show" />모두가 함께 함께 성장하는 것을 지양합니다. <br />
            친절함과 즐거움 속에서 함께 성장해 나가고 싶습니다.
          </p>

          <div class="about-list-grp flex" data-aos="fade-up">
            <div class="list-card hover-effect">
              <p class="point-txt f-b">point 01</p>
              <p class="card-title f-b">멈추지 않는 열정 보유</p>
              <p class="card-txt f-r">
                뭐든 즐겁게 열정적으로 해내는<br />
                글정 마인드를 가졌습니다!
              </p>
            </div>
            <div class="list-card hover-effect type-point">
              <p class="point-txt f-b">point 02</p>
              <p class="card-title f-b">탁월한 협업 능력</p>
              <p class="card-txt f-r">
                어느 누구와도 소통을 잘 해내는<br />
                뛰어난 협업 능력 보유
              </p>
            </div>
            <div class="list-card hover-effect">
              <p class="point-txt f-b">point 03</p>
              <p class="card-title f-b">꼼꼼함과 세심함</p>
              <p class="card-txt f-r">
                특유의 책임감으로<br />
                꼼꼼함과 세심함을 가졌습니다.
              </p>
            </div>
          </div>
        </div>
      </div>

      <!-- WORK -->
      <div class="work-sec">
        <div class="work-inner-grp l-center">
          <p class="top-title f-bk f-b f-pop f-center" data-aos="fade-up">Work</p>
          <div class="work-list-grp" data-aos="fade-up">
            <div class="work-card pos-r" v-for="item in projects" :key="item.title">
              <div class="work-thumb">
                <img :src="item.thumb" :alt="item.title" />
              </div>
              <div class="work-content">
                <h3 class="work-title">{{ item.title }}</h3>
                <p class="work-stack">{{ item.stack }}</p>
                <ul class="work-desc">
                  <li v-for="desc in item.desc" :key="desc">{{ desc }}</li>
                </ul>
                <div class="work-links">
                  <a v-if="item.url" :href="item.url" target="_blank" class="btn btn-link hover-effect"
                    >Website <i class="icon icon-arrow-diagonal"></i
                  ></a>
                  <a v-if="item.sub1" :href="item.sub1" target="_blank" class="btn btn-link hover-effect"
                    >Sub1 <i class="icon icon-arrow-diagonal"></i
                  ></a>
                  <a v-if="item.sub2" :href="item.sub2" target="_blank" class="btn btn-link hover-effect"
                    >Sub2 <i class="icon icon-arrow-diagonal"></i
                  ></a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- MY SKILLS -->
      <div class="skills-sec">
        <div class="l-center">
          <p class="top-title f-wh f-b f-pop f-center" data-aos="fade-up">Skills</p>
          <div class="skills-list-grp">
            <div class="skills-list" data-aos="fade-up">
              <!-- 아이콘 그룹 -->
              <div class="skill-icon-grp flex">
                <div class="skill">
                  <img src="@/assets/images/icon/icon_html5.svg" alt="skill" class="skill-img" />
                </div>
                <div class="skill">
                  <img src="@/assets/images/icon/icon_css3.svg" alt="skill" class="skill-img" />
                </div>
                <div class="skill">
                  <img src="@/assets/images/icon/icon_sass.svg" alt="skill" class="skill-img" />
                </div>
                <div class="skill">
                  <img src="@/assets/images/icon/icon_javascript.svg" alt="skill" class="skill-img" />
                </div>
              </div>

              <p class="skill-title f-wh f-b">언어</p>
              <p class="skill-txt f-r f-pop">HTML5, CSS3, SCSS, JavaScript</p>
            </div>

            <div class="skills-list" data-aos="fade-up">
              <!-- 아이콘 그룹 -->
              <div class="skill-icon-grp flex">
                <div class="skill">
                  <img src="@/assets/images/icon/icon_vue.svg" alt="skill" class="skill-img" />
                </div>
                <div class="skill">
                  <img src="@/assets/images/icon/icon_nextjs.svg" alt="skill" class="skill-img" />
                </div>
              </div>

              <p class="skill-title f-wh f-b">프레임워크</p>
              <p class="skill-txt f-r f-pop">Vue.js (Vue 2, Vue 3), Nuxt</p>
            </div>

            <div class="skills-list" data-aos="fade-up">
              <!-- 아이콘 그룹 -->
              <div class="skill-icon-grp flex">
                <div class="skill">
                  <img src="@/assets/images/icon/icon_tailwindcss.svg" alt="skill" class="skill-img" />
                </div>
                <div class="skill">
                  <img src="@/assets/images/icon/icon_jquery.svg" alt="skill" class="skill-img" />
                </div>
                <div class="skill">
                  <img src="@/assets/images/icon/icon_gsap.svg" alt="skill" class="skill-img" />
                </div>
              </div>

              <p class="skill-title f-wh f-b">라이브러리</p>
              <p class="skill-txt f-r f-pop">Tailwind CSS, jQuery, GSAP</p>
            </div>

            <div class="skills-list" data-aos="fade-up">
              <!-- 아이콘 그룹 -->
              <div class="skill-icon-grp flex">
                <div class="skill">
                  <img src="@/assets/images/icon/icon_vscode.svg" alt="skill" class="skill-img" />
                </div>
                <div class="skill">
                  <img src="@/assets/images/icon/icon_git.svg" alt="skill" class="skill-img" />
                </div>
                <div class="skill">
                  <img src="@/assets/images/icon/icon_github.svg" alt="skill" class="skill-img" />
                </div>
              </div>

              <p class="skill-title f-wh f-b">개발 환경</p>
              <p class="skill-txt f-r f-pop">VS Code, GitLab, Github</p>
            </div>

            <div class="skills-list" data-aos="fade-up">
              <!-- 아이콘 그룹 -->
              <div class="skill-icon-grp flex">
                <div class="skill">
                  <img src="@/assets/images/icon/icon_figma.svg" alt="skill" class="skill-img" />
                </div>
                <div class="skill">
                  <img src="@/assets/images/icon/icon_xd.svg" alt="skill" class="skill-img" />
                </div>
                <div class="skill">
                  <img src="@/assets/images/icon/icon_ps.svg" alt="skill" class="skill-img" />
                </div>
                <div class="skill">
                  <img src="@/assets/images/icon/icon_ai.svg" alt="skill" class="skill-img" />
                </div>
              </div>

              <p class="skill-title f-wh f-b">디자인 툴</p>
              <p class="skill-txt f-r f-pop">Figma, Adobe XD, Photoshop, Illustrator</p>
            </div>
          </div>
        </div>
      </div>

      <!-- CONTACT -->
      <div class="contact-sec">
        <div class="xl-center">
          <p class="top-title f-bk f-b f-pop" data-aos="fade-up">Contact</p>
          <p class="sub-txt f-bk f-r" data-aos="fade-up" data-aos-delay="100">
            끝까지 저의 포트폴리오를 관심있게 봐주셔서 감사합니다.<br />
            저와 나누고 싶으신 말씀이 있으시다면 언제든 연락 주세요!
          </p>
          <div class="resume-grp">
            <div class="line"></div>
            <a
              :href="resumeUrl"
              download="김현지_웹퍼블리셔_이력서.pdf"
              class="btn btn-resume f-wh f-s ani-dongdong hover-effect tab-hide"
              >이력서 다운로드</a
            >
          </div>
          <div class="contact-list-grp flex items-c">
            <div class="contact-list" data-aos="fade-up">
              <p class="label f-pop">Email:</p>
              <p class="contact f-pop">hji0530kim@gmail.com</p>
            </div>
            <div class="contact-list" data-aos="fade-up" data-aos-delay="100">
              <p class="label f-pop">Phone</p>
              <p class="contact f-pop">010-8388-9721</p>
            </div>
          </div>
        </div>
      </div>

      <div class="resume-sec tab-show pos-r">
        <a :href="resumeUrl" download="김현지_웹퍼블리셔_이력서.pdf" class="resume-download-grp">
          <div class="xl-center">
            <p class="resume-sub-txt f-wh f-r f-pop">RESUME DOWNLOAD</p>
            <p class="resume-title f-wh f-b">이력서 다운로드</p>
            <div class="btn btn-resume-arrow">
              <i class="icon icon-arrow-right-big scroll-horizontal-img"></i>
            </div>
          </div>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
import thumbAmber from '@/assets/images/work/amber_road.png';
import thumbPossol from '@/assets/images/work/possol.png';
import thumbPrabbit from '@/assets/images/work/prabbit.png';
import thumbPocket from '@/assets/images/work/pocket.png';
import thumbPortfolio from '@/assets/images/work/portfolio.png';
import thumbCrm from '@/assets/images/work/crm.png';

export default {
  name: 'Index',
  props: {
    hdColorType: {
      type: Boolean,
      default: false, // 기본 헤더 컬러 흰색, true 회색
    },
  },
  data() {
    return {
      mobileGnbShow: false,
      scrolled: false,

      projects: [
        {
          title: '자사 Website (Vue3 + Nuxt 전환)',
          stack: 'Vue3, Nuxt, SCSS, HTML',
          desc: [
            'Vue2 기반 홈페이지를 Vue3 + Nuxt로 마이그레이션하며 SCSS 퍼블 구조 세팅 및 컴포넌트 정리 담당',
            '신규 페이지 추가 및 리뉴얼 퍼블리싱 전담',
          ],
          url: 'https://xn--9i1b674cwc38r6pa.com/',
          thumb: thumbPocket,
        },
        {
          title: '프래빗 반응형 웹 퍼블리싱',
          stack: 'HTML5, SCSS, GSAP',
          desc: ['국문/영문 반응형 웹사이트를 2주 내 단독 완성', '다양한 Swiper/GSAP 인터랙션 구현'],
          url: 'https://prabbit.co.kr/',
          thumb: thumbPrabbit,
        },
        {
          title: '앰버로드 반응형 웹 퍼블리싱',
          stack: 'Vue2, SCSS',
          desc: [
            '초기 70% 담당, 리뉴얼 100% 단독 진행',
            '반응형 및 주요 인터랙션 구현',
            '높은 완성도로 동일 계열사 추가 의뢰(포솔이노텍)',
          ],
          url: 'https://amberroad.ai/',
          thumb: thumbAmber,
        },
        {
          title: '포솔이노텍 반응형 웹 퍼블리싱',
          stack: 'Vue2, SCSS',
          desc: [
            '한국어 80%, 영문 100% 퍼블리싱 담당',
            'PC/Mobile 반응형 구현',
            '앰버로드 완성도로 동일 계열사 추가 진행',
          ],
          url: 'https://www.possol.kr/',
          thumb: thumbPossol,
        },
        {
          title: '자사 포트폴리오 랜딩페이지 퍼블리싱',
          stack: 'HTML5, SCSS',
          desc: ['포트폴리오 내 일부 프로젝트 퍼블리싱 참여', 'PC/Mobile 반응형 구현'],
          sub1: 'https://portfolio.xn--9i1b674cwc38r6pa.com/golerobotics',
          sub2: 'https://portfolio.xn--9i1b674cwc38r6pa.com/amberroad',
          thumb: thumbPortfolio,
        },
        {
          title: '자사 CRM (업무 중심형 UI)',
          stack: 'Vue2, SCSS, Tailwind',
          desc: [
            '기존 비반응형 페이지를 반응형으로 전환',
            '자료실, 단체 메일 전송, 웨비나 등 신규 페이지 퍼블리싱',
            '프론트엔드 개발자와 GitLab 협업 진행',
          ],
          thumb: thumbCrm,
        },
      ],
    };
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  computed: {
    resumeUrl() {
      const file = 'resume/김현지_웹퍼블리셔_이력서.pdf';
      return encodeURI(process.env.BASE_URL + file);
    },
  },
  methods: {
    handleScroll() {
      const header = document.querySelector('.portfolio-header');
      const scrollTop = window.scrollY;
      if (scrollTop !== 0) header.classList.add('is-active');
      else header.classList.remove('is-active');
    },

    // 햄버거 토글
    toggleMobileGnb() {
      this.mobileGnbShow = !this.mobileGnbShow;
      // 바디 스크롤 잠금/해제 (선택적)
      document.body.classList.toggle('is-show', this.mobileGnbShow);
    },

    // 모바일 GNB 닫기(외부에서 호출)
    closeMobileGnb() {
      this.mobileGnbShow = false;
      document.body.classList.remove('is-show');
    },

    // 공용 스크롤 (모바일에서 호출 시 메뉴 닫기)
    scrollToSection(selector, isMobile = false) {
      const target = document.querySelector(selector);
      if (!target) return;

      const header = document.querySelector('.portfolio-header');
      const headerH = header ? header.offsetHeight : 0;
      const top = target.getBoundingClientRect().top + window.pageYOffset - headerH;

      window.scrollTo({ top, behavior: 'smooth' });

      if (isMobile) this.closeMobileGnb();
    },

    // 이력서 다운로드
    downloadResume() {
      const a = document.createElement('a');
      a.href = this.resumeUrl;
      a.setAttribute('download', '김현지_웹퍼블리셔_이력서.pdf'); // 저장 파일명
      a.style.display = 'none';
      document.body.appendChild(a);
      a.click();
      a.remove();
    },
  },
};
</script>
