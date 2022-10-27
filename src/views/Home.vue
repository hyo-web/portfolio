<template>
    <section>
        <article id="visual" class="visual-wrap">
            <h1><span>Hyo</span>Portfolio</h1>
        </article>
        <article id="about" class="about-wrap">
            <div class="inner-box">
                <div class="about-box">
                    <div class="img-box">
                        <div class="img"></div>
                        <div class="desc">
                            김효영 33세
                            
                        </div>
                        <div class="btn-box">
                            <a href="https://velog.io/@kimhyo" target="_blank">
                                <img src="~@/assets/images/icon_velog.svg" alt="">
                            </a>
                             <a href="https://github.com/kimhyoyeong/" target="_blank">
                                <img src="~@/assets/images/icon_git.svg" alt="">
                            </a>
                        </div>
                    </div>
                    <div class="info-box">
                        <div class="detail-box">
                            <div class="box">
                                <div class="title-wrap">
                                    <h2 class="title-type">career</h2>

                                    <span class="career">{{ career }}년차</span>
                                </div>
                                <p>
                                    디지털다임 UI개발팀 매니저
                                    <span>2019.01 ~ 재직중</span><br />
                                    해커스교육그룹 웹퍼블리셔팀 사원
                                    <span>2015.09 - 2018.12</span><br />
                                    모노라움 웹퍼블리셔과정
                                    <span>2015.06 – 2015.08</span><br />
                                    숭실대학교 글로벌미디어학부 졸업
                                    <span>2012.03 - 2015.02</span><br />
                                </p>
                            </div>
                            <div class="box">
                                <div class="title-wrap">
                                    <h2 class="title-type">skill</h2>
                                </div>
                                <p>
                                    HTML5, 웹표준, 크로스브라우징, 반응형 웹,
                                    시멘틱마크업<br />
                                    CSS3, Sass<br />
                                    Git, SVN, Redmine<br />
                                    JavaScript, Vuejs, jQuery, TweenMax<br />
                                    npm, Gulp, Webpack, Bootstrap<br />
                                    Photoshop, Zeplin, WebStorm, Visual Studio
                                    Code<br />
                                </p>
                            </div>
                            <div class="box">
                                <div class="title-wrap">
                                    <h2 class="title-type">license</h2>
                                </div>
                                <p>
                                    정보처리기사 <span>2014.08</span><br />
                                    사무자동화산업기사 <span>2011.06</span
                                    ><br />
                                    컴퓨터활용능력 2급 <span>2011.06</span
                                    ><br />
                                    멀티미디어콘텐츠제작전문가
                                    <span>2009.10</span><br />
                                    웹디자인기능사 <span>2007.05</span><br />
                                </p>
                            </div>
                        </div>
                        <ul class="list-about">
                            <li>
                                <div class="icon-box">&lt;/&gt;</div>
                                <p>
                                    2015년 웹퍼블리셔 직군으로 시작하여 현재
                                    웹에이전시에서 UI 개발팀 매니저 일하고
                                    있습니다. <br />고등학생 때 웹디자인
                                    기능대회에 학교 대표로 참가한 경험으로 나모
                                    웹에디터, 드림위버, 플래시, 테이블 코딩하던
                                    시절을 겪으며 빠르게 변화하는 웹을 가까이
                                    느끼고 있습니다. <br />HTML5 시맨틱 구조로
                                    작업을 진행하며 다양한 브라우저와 환경에
                                    일관적인 페이지가 노출될 수 있도록 노력하고
                                    있습니다.<br />
                                    제 자리에 머무르는 것이 아닌 항상 웹
                                    트렌드에 신경 쓰고 배우는 자세로 업무에
                                    임하고 있습니다.
                                </p>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </article>
        <article id="portfolio" class="portfolio-wrap">
            <div class="title-wrap">
                <h2 class="title-type">portfolio</h2>
                <div class="side-box">
                    <span class="percent-line"></span>기여도
                </div>
            </div>

            <ul class="list-portfolio">
                <li v-for="(portfolio, index) in portfolioList" :key="index">
                    <a
                        href="#"
                        @click.prevent="modalOpen(portfolio)"
                        style="background-"
                    >
                        <div class="img-box">
                            <div class="summary-box">
                                <percent-box
                                    :percent="portfolio.percent"
                                ></percent-box>
                                <div class="text-box">
                                    {{ portfolio.type }}
                                </div>
                            </div>
                        </div>
                        <div class="info-box">
                            <strong>{{ portfolio.name }}</strong>
                        </div>
                    </a>
                </li>
            </ul>
        </article>
        <portfolio-modal
            :visible="modalVsible"
            :portfolioItem="portfolioItem"
            @modalClose="modalClose"
        />
    </section>
</template>

<script>
import PercentBox from "@/components/PercentBox";
import PortfolioModal from "@/components/PortfolioModal";
const now = new Date();

export default {
    name: "Home",
    components: {
        PercentBox,
        PortfolioModal,
    },
    data() {
        return {
            modalVsible: false,
            portfolioItem: {},
            portfolioList: [
                {
                    name: "대한전선",
                    type: "반응형",
                    term: "2022.07 - 2022.10",
                    percent: 100,
                    skill: "html,css,jQuery",
                    guide: "https://aws-code.d2.co.kr/2022/taihan/guide/color.html",
                    index: "https://aws-code.d2.co.kr/2022/taihan/list/",
                    site: "https://taihan.com/",
                    desc: `반응형으로 작업 진행하였습니다.`,
                },
                {
                    name: "CJ프레시밀",
                    type: "MO [vuejs]",
                    term: "2021.11 - 2021.12",
                    percent: 30,
                    skill: "html,css,vuejs",
                    index: "",
                    desc: `vue로 작업한 프로젝트로 기본 레이아웃 구조와 공통 컴포넌트 가이드 작업진행하였습니다. 메뉴별 나눠서 작업하였으며, 메인,점포관리,공통컴포넌트 위주로 작업진행하였습니다.`,
                },
                {
                    name: "SK텔레콤 T Factory Manager",
                    type: "TABLET",
                    term: "2021.08",
                    percent: 90,
                    skill: "html, css, jQuery",
                    index: "https://aws-code.d2.co.kr/2022/rms/list/",
                    desc: ``,
                },
                {
                    name: "아우디폭스바겐코리아 VW 리드매니지먼트",
                    type: "MO [vuejs]",
                    term: "2021.07",
                    percent: 30,
                    skill: "html,css,vuejs",
                    index: "",
                    desc: `vue로 작업한 프로젝트로 기본 레이아웃 구조와 공통 컴포넌트 가이드 작업진행하였습니다. API를 처음으로 다뤄보는 실무 프로젝트 였습니다.`,
                },
                {
                    name: "SK텔레콤 T Place",
                    type: "KIOSK / TABLET / 반응형",
                    term: "2019.12 - 2020.02",
                    percent: 80,
                    skill: "html,css,jQuery",
                    guide:"http://aws-code.d2.co.kr/2020/skt_tplace/guide/chart.html",
                    index:"http://aws-code.d2.co.kr/2020/skt_tplace/list/plan_tablet.html",
                    desc: `고객사가 요구하는 다양한 차트들을 서치하여 최대한 요건에 맞게 커스텀 진행해서 적용하였고 다양한 모션 작업과 반응형인 특성을 고려하여 SVG로 모션을 연구해서 반영하였습니다. 1년 가까이 진행했던 프로젝트로서 제가 주축으로 공통 가이드를 잡고 일정에 맞추기 위해 인원이 투입이 되었던 큰 규모의 프로젝트이며, 제일 많이 성장했던 프로젝트입니다`,
                },
                {
                    name: "SK네트웍스 Nshop",
                    type: "MO",
                    term: "2019.12 - 2020.02",
                    percent: 100,
                    skill: "html,css,jQuery",
                    index: "http://aws-code.d2.co.kr/2019/Nshop/list/B2B.html",
                    site: "https://m.sknshop.co.kr/web/mo/index.htmlx",
                    desc: ``,
                },
                {
                    name: "(주)카버코리아 AHC 국문 쇼핑몰",
                    type: "PC",
                    term: "2019.07 - 2019.10",
                    percent: 80,
                    skill: "html,css,jQuery",
                    guide: "https://aws-code.d2.co.kr/2019/ahc/pc/shop/html/guide/color.html",
                    index: "http://aws-code.d2.co.kr/2019/ahc/list/",
                    site: "https://www.ahc.co.kr/shop/main",
                    desc: `쇼핑몰이랑 특성에 맞게 페이지가 많고 조건별로 노출되는 부분이 상이한 부분이 많은 작업이었습니다. 일정에 맞추기 위해 3명이 투입되었으며, 제가 주축으로 공통 가이드를 잡고 가이드 기준으로 페이지 작업이 진행할 수 있도록 하였습니다.`,
                },
                {
                    name: "신세계조선호텔 레스케이프",
                    type: "MO",
                    term: "2019.02 - 2019.04",
                    percent: 100,
                    skill: "html,css,jQuery",
                    site: "https://www.lescapehotel.com/",
                    desc: ``,
                },
                {
                    name: "해커스교육그룹 영문사이트",
                    type: "PC",
                    term: "2018.09 - 2018.10",
                    percent: 100,
                    skill: "html,css,jQuery",
                    site: "http://www.hackerseducation.com/",
                    desc: `기존에 오래된 해커스닷컴 영문사이트를 새로 구축하는 작업을 하였습니다.
CSS3와 jQuery를 활용해 다양한 효과를 주어, 기존에 텍스트 위주였던 페이지와 차별화가 느껴지도록 작업하였습니다.
애니메이션의 각각 컨텐츠별로 간단하게 클래스를 추가하여 가져다 쓸수 있도록 분리 하였으며,
Sass모듈화를 통해 유지관리가 용이하도록 작업하였습니다`,
                },
                {
                    name: "해커스경영아카데미",
                    type: "PC / MO",
                    term: "2018.09 - 2018.10",
                    percent: 40,
                    skill: "html,css,jQuery",
                    site: "https://ecpa.hackers.com/",
                    desc: `해커스교육그룹 템플릿 작업하였습니다.
공통된 디자인 요소들을 Sass모듈화 작업 가이드화 하여 쉽게 유지보수와 코드의 재활용이 가능하도록 진행하였습니다.
템플릿 작업으로써 CSS 사용하는 대표컬러와 Sprite 이미지 URL 변수로 사용하여 추후 간단하게 변경 가능하도록 작업 하였습니다.
웹퍼블리셔 3명 투입 2번째 포지션으로 작업하였으며, 여러사람과 함께 작업하면서 모듈화의 중요성을 깨달았던 작업이었습니다.`,
                },
                {
                    name: "해커스 통합회원",
                    type: "PC / MO",
                    term: "2018.06 - 2018.07",
                    percent: 40,
                    skill: "html,css,jQuery",
                    url: "",
                    desc: `해커스 회원 통합 관리하는 사이트이며, 모바일 구축에 참여하였습니다.
해커스에서 처음으로 Sass를 도입한 프로젝트이며 Sass를 통한 코드 재사용, 변수선언, 모듈화등 배울 수 있어서 의미 있었던 프로젝트였습니다.
웹퍼블리셔 3명이 투입되었으며, 나의정보 페이지를 작업진행하였습니다.
그 외 단순한 아이콘을 CSS3로만 작업하여 컬러나 사이즈만 수정하여 재사용 가능하도록 가이드에 참여하였습니다.`,
                },
                {
                    name: "위더스&한울 이러닝 템플릿",
                    type: "PC",
                    term: "2018.02 - 2018.03",
                    percent: 100,
                    skill: "html,css,jQuery",
                    url: "",
                    desc: `기존에 플래시로 되어있던 이러닝 컨텐츠를 HTML로 변환하는 프로젝트에 참여하였습니다.
템플릿을 만드는 작업이기에 테마 변경이 효율적으로 가능하도록 대표컬러가 있는 모든이미지를 Sprite하여 한번에 수정가능하도록 작업하였습니다.`,
                },
                {
                    name: "해커스 HRD 2017",
                    type: "PC",
                    term: "2017.10 - 2017.12",
                    percent: 100,
                    skill: "html,css,jQuery",
                    index: "http://hackershrd.com/worksheet/guide/table.php",
                    desc: `해커스 교육 서비스(b2b) 템플릿 사이트 구축에 참여하였습니다.
타이틀, 테이블, 버튼, 아이콘 등 유사한 디자인을 가이드페이지로 정리한 후 작업을 진행하였습니다.
유사한 부분은 공통으로 선언하고 타입별로 재선언하여 재사용과 유지보수에 용이하도록 하였습니다.`,
                },
                {
                    name: "해커스 중국어 인강 리뉴얼",
                    type: "PC",
                    term: "2018.03 - 2018.06",
                    percent: 100,
                    skill: "html,css,jQuery",
                    site: "https://china.hackers.com/",
                    desc: `해커스인강 템플릿 기반으로 적용하였으며, 추가된 페이지 작업, 이미지 레이지로드 적용
이벤트 페이지 이전업무와 관리, 기존 운영 충돌을 피하기 위해 Git  브랜치관리 작업등을 하였습니다. `,
                },
                {
                    name: "해커스잡 공기업 리뉴얼",
                    type: "PC / MO",
                    term: "2017.12 - 2018.01",
                    percent: 100,
                    skill: "html,css,jQuery",
                    site: "https://public.hackers.com/",
                    desc: `해커스인강 템플릿 기반으로 적용하였으며, 추가된 페이지 작업, 이미지 레이지로드 적용
이벤트 페이지 이전업무와 관리, 기존 운영 충돌을 피하기 위해 Git  브랜치관리 작업등을 하였습니다. `,
                },
                {
                    name: "해커스 PREP 리뉴얼",
                    type: "PC / MO",
                    term: "2017.09 - 2017.10",
                    percent: 100,
                    skill: "html,css,jQuery",
                    site: "https://mprep.hackers.com/",
                    desc: `해커스인강 템플릿 기반으로 적용하였으며, 추가된 페이지 작업, 이미지 레이지로드 적용
이벤트 페이지 이전업무와 관리, 기존 운영 충돌을 피하기 위해 Git  브랜치관리 작업등을 하였습니다. `,
                },
                {
                    name: "해커스 인강 리뉴얼",
                    type: "PC / MO",
                    term: "2016.03 - 2016.10",
                    percent: 30,
                    skill: "html,css,jQuery",
                    site: "https://champ.hackers.com/",
                    desc: `모든 페이지 검수 후 오류 수정 맡아 진행하였으며,
해커스에 중요 유입 페이지인 모든 이벤트 페이지를 이전 진행하고,
이벤트 페이지 효율적인 작업을 위해 관리자단에서 관리해야 할 부분을 정리하여 전달 후 가이드 진행, 이벤트 페이지 최적화를 진행하였습니다.
메인 페이지 레이지 로드를 적용하였습니다.`,
                },
                {
                    name: "해커스 HRD 2016",
                    type: "PC",
                    term: "2016.01 ~ 2016.02",
                    percent: 100,
                    skill: "html,css,jQuery",
                    index: "http://hackershrd.com/worksheet/guide/table.php",
                    desc: `해커스 교육 서비스(b2b) 템플릿 사이트 구축에 참여하였습니다.
사수 도움 아래 진행하였고, 그 과정에서 CSS 작성 순서와 방법, 네이밍룰을 배울 수 있었습니다.
또한 개발자에게 전달해야할 이슈사항을 주석을 남기고, 기획자/디자이너/개발자와 원할하게 커뮤니케이션 하는 방법 등 기본 능력을 익힐 수 있었습니다.`,
                },
            ],
        };
    },
    computed: {
        career: function() {
            return now.getFullYear() - 2015 + 1;
        },
    },
    mounted() {
        console.log(this.orderPortfolio);
    },
    methods: {
        modalOpen(item) {
            this.modalVsible = true;
            this.portfolioItem = item;
        },
        modalClose(state) {
            this.modalVsible = state;
        },
    },
};
</script>

<style lang="scss" scoped></style>
