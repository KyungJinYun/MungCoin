<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>뭉구코인 계산기</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Jua&family=Noto+Sans+KR:wght@400;500;700;800&display=swap');

*{box-sizing:border-box}

body{
    margin:0;
    background:#eaf8ff;
    color:#263238;
    font-family:'Noto Sans KR',sans-serif;
}

.container{
    width:min(1100px,100%);
    margin:auto;
    padding:14px 12px 50px;
}

.header{
    background:#fff;
    border:3px solid #bce8ff;
    border-radius:30px;
    padding:18px;
    text-align:center;
    box-shadow:0 8px 25px rgba(50,150,210,.15);
}

.pochacco{
    width:110px;
    height:95px;
    margin:auto;
    position:relative;
}

.head{
    position:absolute;
    left:17px;
    top:17px;
    width:76px;
    height:68px;
    background:#fff;
    border:3px solid #222;
    border-radius:48%;
}

.ear{
    position:absolute;
    width:35px;
    height:65px;
    background:#222;
    border-radius:50%;
    top:8px;
}

.ear.l{left:2px;transform:rotate(25deg)}
.ear.r{right:2px;transform:rotate(-25deg)}

.eye{
    position:absolute;
    top:24px;
    width:6px;
    height:9px;
    background:#222;
    border-radius:50%;
}

.eye.l{left:25px}
.eye.r{right:25px}

.nose{
    position:absolute;
    top:37px;
    left:50%;
    transform:translateX(-50%);
    width:9px;
    height:7px;
    background:#222;
    border-radius:50%;
}

.mouth{
    position:absolute;
    top:43px;
    left:50%;
    transform:translateX(-50%);
    width:15px;
    height:8px;
    border-bottom:2px solid #222;
    border-radius:50%;
}

.header h1{
    margin:0;
    font:32px 'Jua',sans-serif;
    color:#222;
}

.header p{
    margin:6px 0 0;
    color:#78909c;
    font-size:13px;
}

.promise{
    margin:13px auto 0;
    padding:11px 15px;
    max-width:680px;
    background:#f0faff;
    border:2px dashed #9cddfa;
    border-radius:16px;
    font:15px/1.6 'Jua',sans-serif;
}

.tabs{
    display:flex;
    gap:10px;
    margin:15px 0;
}

.tab{
    flex:1;
    border:0;
    padding:14px;
    border-radius:17px;
    background:#cfefff;
    font:17px 'Jua',sans-serif;
    color:#455a64;
    cursor:pointer;
}

.tab.active{
    background:#222;
    color:#fff;
    box-shadow:0 5px 0 #9ddcff;
}

.page{display:none}
.page.active{display:block}

.api-info{
    padding:11px;
    margin-bottom:14px;
    border-radius:14px;
    background:#fff;
    border:2px solid #d5edf8;
    text-align:center;
    font-size:12px;
    color:#607d8b;
}

.dot{
    display:inline-block;
    width:12px;
    height:12px;
    border:2px solid #d8eee8;
    border-top-color:#09a875;
    border-right-color:#09a875;
    border-radius:50%;
    margin-right:6px;
    vertical-align:-2px;
    animation:fxSpin .8s linear infinite;
}

@keyframes fxSpin{
    to{
        transform:rotate(360deg);
    }
}

.card{
    background:#fff;
    border:2px solid #d2edf8;
    border-radius:24px;
    padding:17px;
    margin-bottom:16px;
    box-shadow:0 7px 20px rgba(40,140,190,.10);
}

.card-head{
    display:flex;
    justify-content:space-between;
    align-items:flex-start;
    gap:10px;
    margin-bottom:16px;
    position:relative;
}

.card-head h2{
    margin:0;
    font:22px 'Jua',sans-serif;
}

.controls{
    display:flex;
    gap:8px;
    flex-wrap:nowrap;
    align-items:center;
}

.controls select{
    min-width:120px;
}

select{
    border:2px solid #bde5f6;
    border-radius:11px;
    background:#f8fdff;
    padding:8px 10px;
    font-weight:800;
    color:#37474f;
}

select:disabled{opacity:.8}

.market{
    width:100%;
    text-align:right;
    color:#78909c;
    font-size:11px;
    margin-top:3px;
}

.status{
    width:100%;
    text-align:right;
    color:#07845e;
    font-size:11px;
    font-weight:800;
}

.status.error{color:#d8435f}

.grid{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:11px;
}

.grid.four{
    grid-template-columns:repeat(4,1fr);
}

.field label{
    display:block;
    margin-bottom:5px;
    font-size:12px;
    font-weight:800;
    color:#546e7a;
}

input{
    width:100%;
    padding:12px;
    border:2px solid #dcebf1;
    border-radius:12px;
    outline:none;
    font-size:15px;
    background:#fff;
}

input:focus{border-color:#87d2f2}

.auto{
    background:#edf7fb!important;
    color:#546e7a;
}

.divider{
    border-top:1px dashed #d8eaf1;
    margin:16px 0;
}

.result{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:9px;
    margin-top:15px;
}

.result.five{
    grid-template-columns:repeat(5,1fr);
}

.result-box{
    background:#f7fafb;
    border-radius:14px;
    padding:13px;
}

.result-box small{
    display:block;
    color:#78909c;
    margin-bottom:5px;
    font-size:11px;
}

.result-box strong{font-size:17px}

.result-box.main{
    background:#eaf8ff;
    border:2px solid #c4eaff;
}

.result-box.main strong{font-size:20px}

.plus{color:#07845e!important}
.minus{color:#d8435f!important}

.buttons{
    display:flex;
    gap:8px;
    margin-top:14px;
    align-items:center;
}

.btn{
    border:0;
    border-radius:12px;
    padding:10px 14px;
    font-weight:800;
    cursor:pointer;
}

.save{background:#222;color:#fff}
.reset{background:#ffe9ed;color:#d8435f}

.saved{
    margin-left:auto;
    color:#07845e;
    font-size:11px;
}

.help{
    margin-top:11px;
    background:#f5fbfd;
    border-radius:12px;
    padding:10px;
    font-size:11px;
    line-height:1.7;
    color:#78909c;
}

.card-head > div:first-child{
    flex:1;
}

.fx-title{
    display:flex;
    align-items:center;
    gap:8px;
    font:22px 'Jua',sans-serif;
    line-height:1.15;
    white-space:nowrap;
}

.fx-flag{
    font-size:25px;
    line-height:1;
}

.fx-rate{
    position:absolute;
    left:50%;
    top:7px;
    transform:translateX(-50%);
    margin:0;
    font-size:13px;
    line-height:1;
    color:#07845e;
    font-weight:800;
    white-space:nowrap;
    z-index:2;
}

.fx-converter-grid{
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:12px;
}

.fx-current{
    background:#edf7fb!important;
    font-weight:800;
}

.fx-profit{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:9px;
    margin-top:12px;
}

.fx-note{
    margin-top:8px;
    color:#78909c;
    font-size:11px;
}

.fx-save-area{
    display:flex;
    gap:8px;
    margin-top:14px;
    align-items:center;
}

.fx-saved{
    margin-left:auto;
    color:#07845e;
    font-size:11px;
}


/* =========================
   통합 요약
========================= */

.summary{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:8px;
    margin:-5px 0 14px;
}

.summary-box{
    background:#fff;
    border:2px solid #d2edf8;
    border-radius:14px;
    padding:10px 12px;
    text-align:center;
}

.summary-box small{
    display:block;
    color:#78909c;
    font-size:10px;
    margin-bottom:3px;
}

.summary-box strong{
    font-size:15px;
    white-space:nowrap;
}

.summary-box.highlight{
    background:#eaf8ff;
    border-color:#c4eaff;
}

.summary-title{
    font:16px 'Jua',sans-serif;
    margin:0 0 7px;
    color:#263238;
}

@media(max-width:850px){
    .grid.four{grid-template-columns:repeat(2,1fr)}
    .result.five{grid-template-columns:repeat(3,1fr)}
    .fx-converter-grid{grid-template-columns:1fr}
}

@media(max-width:750px){
    .grid{grid-template-columns:1fr 1fr}
    .card-head{flex-direction:column}
    .controls{
        width:100%;
        display:flex;
        flex-wrap:nowrap;
        overflow-x:auto;
        gap:6px;
    }
    .controls select{
        min-width:110px;
        flex-shrink:0;
    }
    .market,.status{text-align:left}

    .summary{
        grid-template-columns:repeat(2,1fr);
    }
}

@media(max-width:500px){
    .grid,.grid.four{grid-template-columns:1fr}
    .result,.result.five{grid-template-columns:1fr 1fr}
    .result-box.main{grid-column:span 2}
    .header h1{font-size:27px}
    .fx-profit{grid-template-columns:1fr}

    .summary{
        grid-template-columns:1fr 1fr;
    }

    .summary-box strong{
        font-size:13px;
    }
}
</style>
</head>

<body>

<div class="container">

<header class="header">
<div class="pochacco">
    <div class="ear l"></div>
    <div class="ear r"></div>
    <div class="head">
        <div class="eye l"></div>
        <div class="eye r"></div>
        <div class="nose"></div>
        <div class="mouth"></div>
    </div>
</div>

<h1>뭉구코인 계산기</h1>
<p>욕심내지 말고 원칙대로!! 집중하자! 🐶💙</p>

<div class="promise">
🐶 뭉구야 꼭 성공하자.<br>
그래서 밍구랑 행복하게 살자.♥
</div>
</header>

<div class="tabs">
<button class="tab active" data-page="average">📊 평단가 계산기</button>
<button class="tab" data-page="profit">💰 수익률 계산기</button>
<button class="tab" data-page="fx">🌏 환율 계산기</button>
</div>


<!-- =========================
     평단가
========================= -->

<section id="average" class="page active">

<div class="api-info">
<span class="dot"></span>
OKX 선물 = USD / 업비트 = KRW · 현재가는 실시간 API · 5초마다 갱신
</div>

<div id="averageContainer"></div>

</section>


<!-- =========================
     수익률
========================= -->

<section id="profit" class="page">

<div class="api-info">
<span class="dot"></span>
현재가는 거래소 API로 자동 입력되며 5초마다 갱신됩니다.
</div>

<div class="summary">

    <div class="summary-box">
        <small>총매매금액</small>
        <strong id="profitSummaryBuy">-</strong>
    </div>

    <div class="summary-box">
        <small>현재금액</small>
        <strong id="profitSummaryCurrent">-</strong>
    </div>

    <div class="summary-box highlight">
        <small>손익금액</small>
        <strong id="profitSummaryProfit">-</strong>
    </div>

    <div class="summary-box highlight">
        <small>손익률</small>
        <strong id="profitSummaryRate">-</strong>
    </div>

</div>

<div id="profitContainer"></div>

</section>


<!-- =========================
     환율
========================= -->

<section id="fx" class="page">

<div class="api-info">
<span class="dot"></span>
USD · VND · JPY · EUR · THB 환율 API · 1분마다 자동 갱신
</div>

<div class="summary">

    <div class="summary-box">
        <small>총 환전금액</small>
        <strong id="fxSummaryBuy">-</strong>
    </div>

    <div class="summary-box">
        <small>현재금액</small>
        <strong id="fxSummaryCurrent">-</strong>
    </div>

    <div class="summary-box highlight">
        <small>손익금액</small>
        <strong id="fxSummaryProfit">-</strong>
    </div>

    <div class="summary-box highlight">
        <small>손익률</small>
        <strong id="fxSummaryRate">-</strong>
    </div>

</div>

<div id="fxContainer"></div>


<section class="card">

    <div class="card-head">

        <div>
            <div class="fx-title">💱 환전 평단가 계산기</div>

            <div class="fx-note">
                1차~3차로 나누어 환전한 금액을 입력하면 최종 환전 평단가를 계산합니다.
            </div>
        </div>

        <div class="controls">

            <select id="fxAvgCurrency">

                <option value="USD">
                    🇺🇸 USD 미국 달러
                </option>

                <option value="VND">
                    🇻🇳 VND 베트남 동
                </option>

                <option value="JPY">
                    🇯🇵 JPY 일본 엔
                </option>

                <option value="EUR">
                    🇪🇺 EUR 유로
                </option>

                <option value="THB">
                    🇹🇭 THB 태국 바트
                </option>

            </select>

        </div>

    </div>

    <div id="fxAverageRows"></div>

    <div class="result">

        <div class="result-box">
            <small>총 외화</small>
            <strong id="fxAvgTotalForeign">-</strong>
        </div>

        <div class="result-box">
            <small>총 원화 환전금액</small>
            <strong id="fxAvgTotalKRW">-</strong>
        </div>

        <div class="result-box main">
            <small>⭐ 최종 환전 평단가</small>
            <strong id="fxAvgPrice">-</strong>
        </div>

        <div class="result-box">
            <small>현재 환율</small>
            <strong id="fxAvgCurrent">-</strong>
        </div>

        <div class="result-box">
            <small>현재가 대비 손익</small>
            <strong id="fxAvgProfit">-</strong>
        </div>

        <div class="result-box">
            <small>손익률</small>
            <strong id="fxAvgRate">-</strong>
        </div>

    </div>

    <div class="buttons">

        <button class="btn save" id="fxAvgSave">
            💾 저장
        </button>

        <button class="btn reset" id="fxAvgReset">
            ↻ 초기화
        </button>

        <span class="saved" id="fxAvgSaved"></span>

    </div>

</section>

</section>

</div>


<script>

const COUNT=3;

const COINS={
    BTC:{
        okx:"BTC-USDT-SWAP",
        upbit:"KRW-BTC"
    },
    ETH:{
        okx:"ETH-USDT-SWAP",
        upbit:"KRW-ETH"
    },
    SOL:{
        okx:"SOL-USDT-SWAP",
        upbit:"KRW-SOL"
    }
};

const FX={

    USD:{
        flag:"🇺🇸",
        name:"미국 달러",
        symbol:"$",
        unit:1,
        decimals:2
    },

    VND:{
        flag:"🇻🇳",
        name:"베트남 동",
        symbol:"₫",
        unit:100,
        decimals:2
    },

    JPY:{
        flag:"🇯🇵",
        name:"일본 엔",
        symbol:"¥",
        unit:100,
        decimals:2
    },

    EUR:{
        flag:"🇪🇺",
        name:"유럽 유로",
        symbol:"€",
        unit:1,
        decimals:2
    },

    THB:{
        flag:"🇹🇭",
        name:"태국 바트",
        symbol:"฿",
        unit:1,
        decimals:2
    }

};

const state={
    fxRates:{},
    fxLastUpdate:null
};


/* =========================
   기본 함수
========================= */

function currencyOf(exchange){

    return exchange==="OKX"
        ?"USD"
        :"KRW";

}

function parseValue(id){

    const el=document.getElementById(id);

    if(!el)return 0;

    const value=parseFloat(
        String(el.value).replace(/,/g,"")
    );

    return Number.isFinite(value)
        ?value
        :0;

}

function formatMoney(value,currency){

    if(!Number.isFinite(value))
        return "-";

    if(currency==="USD"){

        return "$"+
            value.toLocaleString(
                "en-US",
                {
                    minimumFractionDigits:2,
                    maximumFractionDigits:2
                }
            );

    }

    return Math.round(value)
        .toLocaleString("ko-KR")+"원";

}

function formatKRW(value){

    if(!Number.isFinite(value))
        return "-";

    return Math.round(value)
        .toLocaleString("ko-KR")+"원";

}

function formatInputMoney(value,currency){

    if(!Number.isFinite(value)||value===0)
        return "";

    if(currency==="USD"){

        return value.toLocaleString(
            "en-US",
            {
                minimumFractionDigits:2,
                maximumFractionDigits:2
            }
        );

    }

    return Math.round(value)
        .toLocaleString("ko-KR");

}

function formatQuantity(value){

    if(!Number.isFinite(value))
        return "-";

    return value.toLocaleString(
        "ko-KR",
        {
            maximumFractionDigits:8
        }
    );

}

function setClass(el,value){

    el.classList.remove(
        "plus",
        "minus"
    );

    if(value>0)
        el.classList.add("plus");

    if(value<0)
        el.classList.add("minus");

}

function formatFx(value,currency){

    if(!Number.isFinite(value))
        return "-";

    const d=
        FX[currency].decimals;

    return value.toLocaleString(
        "en-US",
        {
            minimumFractionDigits:d,
            maximumFractionDigits:d
        }
    )+"원";

}

function formatForeign(value,currency){

    if(!Number.isFinite(value))
        return "-";

    return value.toLocaleString(
        "en-US",
        {
            maximumFractionDigits:4
        }
    )+" "+currency;

}


/* =========================
   탭
========================= */

document.querySelectorAll(".tab")
.forEach(tab=>{

    tab.addEventListener(
        "click",
        ()=>{

            document.querySelectorAll(".tab")
            .forEach(x=>
                x.classList.remove("active")
            );

            document.querySelectorAll(".page")
            .forEach(x=>
                x.classList.remove("active")
            );

            tab.classList.add("active");

            document
                .getElementById(
                    tab.dataset.page
                )
                .classList.add("active");

        }
    );

});


/* =========================
   거래소 / 코인
========================= */

function controls(type,i){

    return `

    <select id="${type}${i}_exchange">

        <option value="UPBIT">
            🇰🇷 업비트
        </option>

        <option value="OKX">
            🌎 OKX 선물
        </option>

    </select>

    <select id="${type}${i}_coin">

        <option value="BTC">BTC</option>
        <option value="ETH">ETH</option>
        <option value="SOL">SOL</option>

    </select>

    <select id="${type}${i}_currency" disabled>

        <option value="KRW">
            ₩ KRW
        </option>

        <option value="USD">
            $ USD
        </option>

    </select>

    `;

}

function updateMarket(type,i){

    const exchange=
        document.getElementById(
            `${type}${i}_exchange`
        ).value;

    const coin=
        document.getElementById(
            `${type}${i}_coin`
        ).value;

    const currency=
        currencyOf(exchange);

    document.getElementById(
        `${type}${i}_currency`
    ).value=currency;

    document.getElementById(
        `${type}${i}_market`
    ).textContent=

        exchange==="OKX"

        ?`OKX 선물 · ${COINS[coin].okx}`

        :`업비트 · ${COINS[coin].upbit}`;

}


/* =========================
   평단가
========================= */

function makeAverageCards(){

    let html="";

    for(let i=1;i<=COUNT;i++){

        html+=`

        <div class="card">

            <div class="card-head">

                <h2>🐶</h2>

                <div class="controls">
                    ${controls("a",i)}
                </div>

                <div id="a${i}_market"
                     class="market"></div>

                <div id="a${i}_status"
                     class="status">

                    <span class="dot"></span>
                    현재가 대기중

                </div>

            </div>

            ${averageRow(i,1)}

            <div class="divider"></div>

            ${averageRow(i,2)}

            <div class="divider"></div>

            ${averageRow(i,3)}

            <div class="result">

                <div class="result-box">

                    <small>총 보유수량</small>

                    <strong id="a${i}_totalQ">
                        -
                    </strong>

                </div>

                <div class="result-box">

                    <small>총 매매금액</small>

                    <strong id="a${i}_totalM">
                        -
                    </strong>

                </div>

                <div class="result-box main">

                    <small>⭐ 최종 평단가</small>

                    <strong id="a${i}_avg">
                        -
                    </strong>

                </div>

            </div>

            <div class="buttons">

                <button
                    class="btn save"
                    id="a${i}_save">
                    💾 저장
                </button>

                <button
                    class="btn reset"
                    id="a${i}_reset">
                    ↻ 초기화
                </button>

                <span
                    class="saved"
                    id="a${i}_saved">
                </span>

            </div>

        </div>

        `;

    }

    document.getElementById(
        "averageContainer"
    ).innerHTML=html;

}

function averageRow(i,n){

    return `

    <div class="grid four">

        <div class="field">

            <label>${n}차 매매수량</label>

            <input
                id="a${i}_q${n}"
                type="number"
                step="any"
                placeholder="예: 8.44250330"
            >

        </div>

        <div class="field">

            <label>${n}차 매매가격</label>

            <input
                id="a${i}_p${n}"
                type="number"
                step="any"
                placeholder="예: 144600"
            >

        </div>

        <div class="field">

            <label>${n}차 매매금액</label>

            <input
                id="a${i}_m${n}"
                class="auto"
                readonly
                placeholder="자동 계산"
            >

        </div>

        <div class="field">

            <label>${n}차 평단가</label>

            <input
                id="a${i}_avg${n}"
                class="auto"
                readonly
                placeholder="자동 계산"
            >

        </div>

    </div>

    `;

}

function averageCalc(i){

    const currency=
        document.getElementById(
            `a${i}_currency`
        ).value;

    let totalQ=0;
    let totalM=0;

    for(let n=1;n<=3;n++){

        const q=
            parseValue(`a${i}_q${n}`);

        const p=
            parseValue(`a${i}_p${n}`);

        const amount=q*p;

        totalQ+=q;
        totalM+=amount;

        document.getElementById(
            `a${i}_m${n}`
        ).value=

            amount>0
            ?formatInputMoney(
                amount,
                currency
            )
            :"";

        document.getElementById(
            `a${i}_avg${n}`
        ).value=

            q>0&&p>0
            ?formatInputMoney(
                amount/q,
                currency
            )
            :"";

    }

    document.getElementById(
        `a${i}_totalQ`
    ).textContent=

        totalQ>0
        ?formatQuantity(totalQ)
        :"-";

    document.getElementById(
        `a${i}_totalM`
    ).textContent=

        totalM>0
        ?formatMoney(
            totalM,
            currency
        )
        :"-";

    const average=
        totalQ>0
        ?totalM/totalQ
        :0;

    document.getElementById(
        `a${i}_avg`
    ).textContent=

        average>0
        ?formatMoney(
            average,
            currency
        )
        :"-";

}


/* =========================
   수익률 카드
========================= */

function makeProfitCards(){

    let html="";

    for(let i=1;i<=COUNT;i++){

        html+=`

        <div class="card">

            <div class="card-head">

                <h2>🐶</h2>

                <div class="controls">
                    ${controls("p",i)}
                </div>

                <div id="p${i}_market"
                     class="market"></div>

                <div id="p${i}_status"
                     class="status">

                    <span class="dot"></span>
                    현재가 대기중

                </div>

            </div>

            <div class="grid">

                <div class="field">

                    <label>매매수량</label>

                    <input
                        id="p${i}_q"
                        type="number"
                        step="any"
                        placeholder="예: 10"
                    >

                </div>

                <div class="field">

                    <label>매매가격</label>

                    <input
                        id="p${i}_buy"
                        type="number"
                        step="any"
                        placeholder="예: 150000"
                    >

                </div>

                <div class="field">

                    <label>매매금액</label>

                    <input
                        id="p${i}_money"
                        class="auto"
                        readonly
                        placeholder="자동 계산"
                    >

                </div>

                <div class="field">

                    <label>현재 가격</label>

                    <input
                        id="p${i}_current"
                        type="number"
                        step="any"
                        placeholder="API 자동 / 직접 입력"
                    >

                </div>

                <div class="field">

                    <label>매도 가격</label>

                    <input
                        id="p${i}_sell"
                        type="number"
                        step="any"
                        placeholder="예상 매도가"
                    >

                </div>

            </div>

            <div class="result">

                <div class="result-box">

                    <small>매매금액</small>

                    <strong id="p${i}_total">
                        -
                    </strong>

                </div>

                <div class="result-box">

                    <small>현재가 손익</small>

                    <strong id="p${i}_currentProfit">
                        -
                    </strong>

                </div>

                <div class="result-box">

                    <small>현재가 수익률</small>

                    <strong id="p${i}_currentRate">
                        -
                    </strong>

                </div>

                <div class="result-box main">

                    <small>⭐ 매도가 예상 손익</small>

                    <strong id="p${i}_sellProfit">
                        -
                    </strong>

                </div>

                <div class="result-box main">

                    <small>⭐ 매도가 예상 수익률</small>

                    <strong id="p${i}_sellRate">
                        -
                    </strong>

                </div>

            </div>

            <div class="help">

                현재 가격 = 지금 가격으로 매도했을 때 예상 손익<br>

                매도 가격 = 내가 원하는 가격에 매도했을 때 예상 손익

            </div>

            <div class="buttons">

                <button
                    class="btn save"
                    id="p${i}_save">
                    💾 저장
                </button>

                <button
                    class="btn reset"
                    id="p${i}_reset">
                    ↻ 초기화
                </button>

                <span
                    class="saved"
                    id="p${i}_saved">
                </span>

            </div>

        </div>

        `;

    }

    document.getElementById(
        "profitContainer"
    ).innerHTML=html;

}

function profitCalc(i){

    const currency=
        document.getElementById(
            `p${i}_currency`
        ).value;

    const q=
        parseValue(`p${i}_q`);

    const buy=
        parseValue(`p${i}_buy`);

    const current=
        parseValue(`p${i}_current`);

    const sell=
        parseValue(`p${i}_sell`);

    const total=q*buy;

    document.getElementById(
        `p${i}_money`
    ).value=

        total>0
        ?formatInputMoney(
            total,
            currency
        )
        :"";

    document.getElementById(
        `p${i}_total`
    ).textContent=

        total>0
        ?formatMoney(
            total,
            currency
        )
        :"-";


    const cp=
        document.getElementById(
            `p${i}_currentProfit`
        );

    const cr=
        document.getElementById(
            `p${i}_currentRate`
        );


    if(q>0&&buy>0&&current>0){

        const profit=
            (current-buy)*q;

        const rate=
            ((current-buy)/buy)*100;

        cp.textContent=
            (profit>=0?"+":"")+
            formatMoney(
                profit,
                currency
            );

        cr.textContent=
            (rate>=0?"+":"")+
            rate.toFixed(2)+"%";

        setClass(cp,profit);
        setClass(cr,rate);

    }else{

        cp.textContent="-";
        cr.textContent="-";

        setClass(cp,0);
        setClass(cr,0);

    }


    const sp=
        document.getElementById(
            `p${i}_sellProfit`
        );

    const sr=
        document.getElementById(
            `p${i}_sellRate`
        );


    if(q>0&&buy>0&&sell>0){

        const profit=
            (sell-buy)*q;

        const rate=
            ((sell-buy)/buy)*100;

        sp.textContent=
            (profit>=0?"+":"")+
            formatMoney(
                profit,
                currency
            );

        sr.textContent=
            (rate>=0?"+":"")+
            rate.toFixed(2)+"%";

        setClass(sp,profit);
        setClass(sr,rate);

    }else{

        sp.textContent="-";
        sr.textContent="-";

        setClass(sp,0);
        setClass(sr,0);

    }


    updateProfitSummary();

}


/* =========================
   수익률 통합 원화 요약
========================= */

function getUsdKrw(){

    return state.fxRates.USD||0;

}

function convertToKRW(value,currency){

    if(!Number.isFinite(value))
        return 0;

    if(currency==="KRW")
        return value;

    const usdKrw=
        getUsdKrw();

    if(usdKrw<=0)
        return 0;

    return value*usdKrw;

}

function updateProfitSummary(){

    let totalBuyKRW=0;
    let totalCurrentKRW=0;

    for(let i=1;i<=COUNT;i++){

        const exchange=
            document.getElementById(
                `p${i}_exchange`
            ).value;

        const currency=
            currencyOf(exchange);

        const q=
            parseValue(`p${i}_q`);

        const buy=
            parseValue(`p${i}_buy`);

        const current=
            parseValue(`p${i}_current`);

        if(q>0&&buy>0){

            const buyAmount=q*buy;

            totalBuyKRW+=
                convertToKRW(
                    buyAmount,
                    currency
                );

        }

        if(q>0&&current>0){

            const currentAmount=q*current;

            totalCurrentKRW+=
                convertToKRW(
                    currentAmount,
                    currency
                );

        }

    }

    const profit=
        totalCurrentKRW-totalBuyKRW;

    const rate=
        totalBuyKRW>0
        ?(profit/totalBuyKRW)*100
        :0;


    document.getElementById(
        "profitSummaryBuy"
    ).textContent=
        totalBuyKRW>0
        ?formatKRW(totalBuyKRW)
        :"-";

    document.getElementById(
        "profitSummaryCurrent"
    ).textContent=
        totalCurrentKRW>0
        ?formatKRW(totalCurrentKRW)
        :"-";

    const profitEl=
        document.getElementById(
            "profitSummaryProfit"
        );

    const rateEl=
        document.getElementById(
            "profitSummaryRate"
        );

    if(totalBuyKRW>0){

        profitEl.textContent=
            (profit>=0?"+":"")+
            formatKRW(profit);

        rateEl.textContent=
            (rate>=0?"+":"")+
            rate.toFixed(2)+"%";

        setClass(profitEl,profit);
        setClass(rateEl,rate);

    }else{

        profitEl.textContent="-";
        rateEl.textContent="-";

        setClass(profitEl,0);
        setClass(rateEl,0);

    }

}


/* =========================
   저장
========================= */

function saveAverage(i){

    const data={

        exchange:
            document.getElementById(
                `a${i}_exchange`
            ).value,

        coin:
            document.getElementById(
                `a${i}_coin`
            ).value,

        q:[],
        p:[]

    };

    for(let n=1;n<=3;n++){

        data.q.push(
            document.getElementById(
                `a${i}_q${n}`
            ).value
        );

        data.p.push(
            document.getElementById(
                `a${i}_p${n}`
            ).value
        );

    }

    localStorage.setItem(
        `munggu_average_${i}`,
        JSON.stringify(data)
    );

    document.getElementById(
        `a${i}_saved`
    ).textContent=
        "✓ 저장 완료";

}

function loadAverage(i){

    const raw=
        localStorage.getItem(
            `munggu_average_${i}`
        );

    if(!raw)return;

    try{

        const data=JSON.parse(raw);

        document.getElementById(
            `a${i}_exchange`
        ).value=
            data.exchange||"UPBIT";

        document.getElementById(
            `a${i}_coin`
        ).value=
            data.coin||"BTC";

        for(let n=1;n<=3;n++){

            document.getElementById(
                `a${i}_q${n}`
            ).value=
                data.q?.[n-1]||"";

            document.getElementById(
                `a${i}_p${n}`
            ).value=
                data.p?.[n-1]||"";

        }

        updateMarket("a",i);
        averageCalc(i);

    }catch(e){

        console.error(e);

    }

}


function saveProfit(i){

    const data={

        exchange:
            document.getElementById(
                `p${i}_exchange`
            ).value,

        coin:
            document.getElementById(
                `p${i}_coin`
            ).value,

        q:
            document.getElementById(
                `p${i}_q`
            ).value,

        buy:
            document.getElementById(
                `p${i}_buy`
            ).value,

        current:
            document.getElementById(
                `p${i}_current`
            ).value,

        sell:
            document.getElementById(
                `p${i}_sell`
            ).value

    };

    localStorage.setItem(
        `munggu_profit_${i}`,
        JSON.stringify(data)
    );

    document.getElementById(
        `p${i}_saved`
    ).textContent=
        "✓ 저장 완료";

}

function loadProfit(i){

    const raw=
        localStorage.getItem(
            `munggu_profit_${i}`
        );

    if(!raw)return;

    try{

        const data=JSON.parse(raw);

        document.getElementById(
            `p${i}_exchange`
        ).value=
            data.exchange||"UPBIT";

        document.getElementById(
            `p${i}_coin`
        ).value=
            data.coin||"BTC";

        document.getElementById(
            `p${i}_q`
        ).value=
            data.q||"";

        document.getElementById(
            `p${i}_buy`
        ).value=
            data.buy||"";

        document.getElementById(
            `p${i}_current`
        ).value=
            data.current||"";

        document.getElementById(
            `p${i}_sell`
        ).value=
            data.sell||"";

        updateMarket("p",i);
        profitCalc(i);

    }catch(e){

        console.error(e);

    }

}


/* =========================
   초기화
========================= */

function resetAverage(i){

    if(!confirm(
        `종목 ${i} 평단가 계산기를 초기화할까요?`
    ))
        return;

    for(let n=1;n<=3;n++){

        document.getElementById(
            `a${i}_q${n}`
        ).value="";

        document.getElementById(
            `a${i}_p${n}`
        ).value="";

        document.getElementById(
            `a${i}_m${n}`
        ).value="";

        document.getElementById(
            `a${i}_avg${n}`
        ).value="";

    }

    localStorage.removeItem(
        `munggu_average_${i}`
    );

    averageCalc(i);

    document.getElementById(
        `a${i}_saved`
    ).textContent="";

}

function resetProfit(i){

    if(!confirm(
        `종목 ${i} 수익률 계산기를 초기화할까요?`
    ))
        return;

    ["q","buy","current","sell"]
    .forEach(k=>{

        document.getElementById(
            `p${i}_${k}`
        ).value="";

    });

    localStorage.removeItem(
        `munggu_profit_${i}`
    );

    profitCalc(i);

    document.getElementById(
        `p${i}_saved`
    ).textContent="";

}


/* =========================
   OKX
========================= */

async function getOKX(coin){

    try{

        const response=await fetch(

            "https://www.okx.com/api/v5/market/ticker?instId="+
            encodeURIComponent(
                COINS[coin].okx
            ),

            {
                cache:"no-store"
            }

        );

        if(!response.ok)
            throw new Error(
                "OKX HTTP error"
            );

        const data=
            await response.json();

        if(
            data.code!=="0"||
            !data.data?.length
        )
            throw new Error(
                "OKX data error"
            );

        return Number(
            data.data[0].last
        );

    }catch(error){

        console.error(error);

        return null;

    }

}


/* =========================
   업비트
========================= */

async function getUpbit(coin){

    try{

        const response=await fetch(

            "https://api.upbit.com/v1/ticker?markets="+
            encodeURIComponent(
                COINS[coin].upbit
            ),

            {
                cache:"no-store"
            }

        );

        if(!response.ok)
            throw new Error(
                "Upbit HTTP error"
            );

        const data=
            await response.json();

        if(!data?.length)
            throw new Error(
                "Upbit data error"
            );

        return Number(
            data[0].trade_price
        );

    }catch(error){

        console.error(error);

        return null;

    }

}


/* =========================
   코인 현재가
========================= */

async function getPrice(type,i){

    const exchange=
        document.getElementById(
            `${type}${i}_exchange`
        ).value;

    const coin=
        document.getElementById(
            `${type}${i}_coin`
        ).value;

    const status=
        document.getElementById(
            `${type}${i}_status`
        );

    status.innerHTML=
        '<span class="dot"></span>현재가 조회중...';

    status.classList.remove(
        "error"
    );

    const price=
        exchange==="OKX"
        ?await getOKX(coin)
        :await getUpbit(coin);

    if(price===null){

        status.innerHTML=
            '<span class="dot"></span>API 조회 실패 · 직접 입력 가능';

        status.classList.add(
            "error"
        );

        return;

    }

    const currency=
        currencyOf(exchange);

    status.innerHTML=
        '<span class="dot"></span>현재가 '+
        formatMoney(
            price,
            currency
        );

    if(type==="p"){

        document.getElementById(
            `p${i}_current`
        ).value=price;

        profitCalc(i);

    }

}


/* =========================
   환율 카드
========================= */

function makeFxCards(){

    let html="";

    Object.keys(FX)
    .forEach(code=>{

        const f=FX[code];

        const unitText=
            f.unit===100
            ?`100 ${code}`
            :`1 ${code}`;

        html+=`

        <div class="card">

            <div class="card-head">

                <div>

                    <div class="fx-title">

                        <span class="fx-flag">
                            ${f.flag}
                        </span>

                        ${f.name} (${code})

                    </div>

                    <div
                        id="fx${code}_rateText"
                        class="fx-rate"
                    >
                        현재 환율 조회중...
                    </div>

                </div>

                <div
                    id="fx${code}_status"
                    class="status"
                >

                    <span class="dot"></span>
                    대기중

                </div>

            </div>

            <div class="fx-converter-grid">

                <div class="field">

                    <label>
                        보유/입력 ${code} 금액
                    </label>

                    <input
                        id="fx${code}_amount"
                        type="number"
                        step="any"
                        placeholder="${code} 숫자 입력"
                    >

                </div>

                <div class="field">

                    <label>
                        내 환전 평단가 (${unitText} = 원)
                    </label>

                    <input
                        id="fx${code}_avg"
                        type="number"
                        step="any"
                        placeholder="예: 환전 당시 환율"
                    >

                </div>

                <div class="field">

                    <label>
                        원화 환산금액
                    </label>

                    <input
                        id="fx${code}_krw"
                        class="auto"
                        readonly
                        placeholder="자동 계산"
                    >

                </div>

                <div class="field">

                    <label>
                        현재 환율
                    </label>

                    <input
                        id="fx${code}_current"
                        class="auto fx-current"
                        readonly
                        placeholder="API 자동"
                    >

                </div>

            </div>

            <div class="fx-profit">

                <div class="result-box">

                    <small>
                        현재 환율 대비 손익가격
                    </small>

                    <strong
                        id="fx${code}_profit">
                        -
                    </strong>

                </div>

                <div class="result-box">

                    <small>
                        현재 환율 대비 손익률
                    </small>

                    <strong
                        id="fx${code}_rate">
                        -
                    </strong>

                </div>

            </div>

            <div class="help">

                ${code} 금액을 입력하면 현재 환율 기준
                원화로 자동 계산됩니다.<br>

                내 환전 평단가를 입력하면 현재 환율과 비교해
                손익금액·손익률을 보여줍니다.

            </div>

            <div class="fx-save-area">

                <button
                    class="btn save"
                    id="fx${code}_save">
                    💾 저장
                </button>

                <button
                    class="btn reset"
                    id="fx${code}_reset">
                    ↻ 초기화
                </button>

                <span
                    class="fx-saved"
                    id="fx${code}_saved">
                </span>

            </div>

        </div>

        `;

    });

    document.getElementById(
        "fxContainer"
    ).innerHTML=html;

}


/* =========================
   환율 계산
========================= */

function fxCalc(code){

    const amount=
        parseValue(
            `fx${code}_amount`
        );

    const avg=
        parseValue(
            `fx${code}_avg`
        );

    const current=
        state.fxRates[code]||0;

    const unit=
        FX[code].unit;


    const krwEl=
        document.getElementById(
            `fx${code}_krw`
        );


    krwEl.value=

        amount>0&&current>0

        ?Math.round(
            (amount/unit)*current
        ).toLocaleString(
            "ko-KR"
        )+"원"

        :"";


    document.getElementById(
        `fx${code}_current`
    ).value=

        current>0
        ?current.toFixed(
            FX[code].decimals
        )
        :"";


    if(
        amount>0&&
        avg>0&&
        current>0
    ){

        const foreignUnits=
            amount/unit;

        const profit=
            (current-avg)*
            foreignUnits;

        const rate=
            ((current-avg)/avg)*
            100;

        const pe=
            document.getElementById(
                `fx${code}_profit`
            );

        const re=
            document.getElementById(
                `fx${code}_rate`
            );

        pe.textContent=
            (profit>=0?"+":"")+
            Math.round(profit)
                .toLocaleString(
                    "ko-KR"
                )+"원";

        re.textContent=
            (rate>=0?"+":"")+
            rate.toFixed(2)+"%";

        setClass(pe,profit);
        setClass(re,rate);

    }else{

        document.getElementById(
            `fx${code}_profit`
        ).textContent="-";

        document.getElementById(
            `fx${code}_rate`
        ).textContent="-";

        setClass(
            document.getElementById(
                `fx${code}_profit`
            ),
            0
        );

        setClass(
            document.getElementById(
                `fx${code}_rate`
            ),
            0
        );

    }

    updateFxSummary();

}


/* =========================
   환율 저장
========================= */

function saveFx(code){

    const data={

        amount:
            document.getElementById(
                `fx${code}_amount`
            ).value,

        avg:
            document.getElementById(
                `fx${code}_avg`
            ).value

    };

    localStorage.setItem(
        `munggu_fx_${code}`,
        JSON.stringify(data)
    );

    document.getElementById(
        `fx${code}_saved`
    ).textContent=
        "✓ 저장 완료";

}

function loadFx(code){

    const raw=
        localStorage.getItem(
            `munggu_fx_${code}`
        );

    if(!raw)return;

    try{

        const data=
            JSON.parse(raw);

        document.getElementById(
            `fx${code}_amount`
        ).value=
            data.amount||"";

        document.getElementById(
            `fx${code}_avg`
        ).value=
            data.avg||"";

        fxCalc(code);

    }catch(e){

        console.error(e);

    }

}

function resetFx(code){

    if(!confirm(
        `${FX[code].name} 환율 계산기를 초기화할까요?`
    ))
        return;

    document.getElementById(
        `fx${code}_amount`
    ).value="";

    document.getElementById(
        `fx${code}_avg`
    ).value="";

    localStorage.removeItem(
        `munggu_fx_${code}`
    );

    fxCalc(code);

    document.getElementById(
        `fx${code}_saved`
    ).textContent="";

}


/* =========================
   Frankfurter 환율 API
========================= */

async function getFxRates(){

    const statusCodes=
        Object.keys(FX);


    statusCodes.forEach(code=>{

        const el=
            document.getElementById(
                `fx${code}_status`
            );

        if(el){

            el.innerHTML=
                '<span class="dot"></span>환율 조회중...';

            el.classList.remove(
                "error"
            );

        }

    });


    let rates=null;


    try{

        const response=
            await fetch(

                "https://api.frankfurter.dev/v2/rates?base=USD&quotes=KRW,VND,JPY,EUR,THB",

                {
                    cache:"no-store"
                }

            );


        if(!response.ok)
            throw new Error(
                "Frankfurter HTTP error"
            );


        const data=
            await response.json();


        if(
            !Array.isArray(data)||
            !data.length
        )
            throw new Error(
                "Frankfurter data error"
            );


        const raw={};


        data.forEach(item=>{

            if(
                item &&
                item.quote &&
                Number.isFinite(
                    Number(item.rate)
                )
            ){

                raw[item.quote]=
                    Number(item.rate);

            }

        });


        const usdKrw=raw.KRW;
        const vnd=raw.VND;
        const jpy=raw.JPY;
        const eur=raw.EUR;
        const thb=raw.THB;


        if(
            Number.isFinite(usdKrw)&&
            vnd>0&&
            jpy>0&&
            eur>0&&
            thb>0
        ){

            rates={

                USD:
                    usdKrw,

                VND:
                    usdKrw*100/vnd,

                JPY:
                    usdKrw*100/jpy,

                EUR:
                    usdKrw/eur,

                THB:
                    usdKrw/thb

            };

        }

    }catch(error){

        console.warn(
            "Frankfurter 환율 API 실패",
            error
        );

    }


    if(!rates){

        statusCodes.forEach(code=>{

            const el=
                document.getElementById(
                    `fx${code}_status`
                );

            if(el){

                el.innerHTML=
                    '<span class="dot"></span>API 조회 실패';

                el.classList.add(
                    "error"
                );

            }

        });

        return;

    }


    state.fxRates=rates;

    state.fxLastUpdate=
        new Date();


    statusCodes.forEach(code=>{

        const rate=
            rates[code];

        const unit=
            FX[code].unit;

        const rateText=
            unit===100

            ?`현재 환율 · 100 ${code} = `

            :`현재 환율 · 1 ${code} = `;


        document.getElementById(
            `fx${code}_rateText`
        ).textContent=

            rateText+
            rate.toLocaleString(
                "ko-KR",
                {
                    minimumFractionDigits:
                        FX[code].decimals,

                    maximumFractionDigits:
                        FX[code].decimals
                }
            )+"원";


        document.getElementById(
            `fx${code}_status`
        ).innerHTML=
            '<span class="dot"></span>실시간 환율 반영';


        fxCalc(code);

    });


    updateProfitSummary();
    updateFxSummary();
    fxAverageCalc();

}


/* =========================
   환율 통합 원화 요약
========================= */

function updateFxSummary(){

    let totalBuyKRW=0;
    let totalCurrentKRW=0;


    Object.keys(FX)
    .forEach(code=>{

        const amount=
            parseValue(
                `fx${code}_amount`
            );

        const avg=
            parseValue(
                `fx${code}_avg`
            );

        const current=
            state.fxRates[code]||0;

        const unit=
            FX[code].unit;


        if(
            amount>0&&
            avg>0
        ){

            totalBuyKRW+=
                (amount/unit)*avg;

        }


        if(
            amount>0&&
            current>0
        ){

            totalCurrentKRW+=
                (amount/unit)*current;

        }

    });


    const profit=
        totalCurrentKRW-
        totalBuyKRW;

    const rate=
        totalBuyKRW>0
        ?profit/totalBuyKRW*100
        :0;


    document.getElementById(
        "fxSummaryBuy"
    ).textContent=

        totalBuyKRW>0
        ?formatKRW(totalBuyKRW)
        :"-";


    document.getElementById(
        "fxSummaryCurrent"
    ).textContent=

        totalCurrentKRW>0
        ?formatKRW(totalCurrentKRW)
        :"-";


    const profitEl=
        document.getElementById(
            "fxSummaryProfit"
        );

    const rateEl=
        document.getElementById(
            "fxSummaryRate"
        );


    if(totalBuyKRW>0){

        profitEl.textContent=
            (profit>=0?"+":"")+
            formatKRW(profit);

        rateEl.textContent=
            (rate>=0?"+":"")+
            rate.toFixed(2)+"%";

        setClass(
            profitEl,
            profit
        );

        setClass(
            rateEl,
            rate
        );

    }else{

        profitEl.textContent="-";
        rateEl.textContent="-";

        setClass(
            profitEl,
            0
        );

        setClass(
            rateEl,
            0
        );

    }

}


/* =========================
   환전 평단가
========================= */

function makeFxAverageRows(){

    let html="";


    for(let n=1;n<=3;n++){

        html+=`

        <div class="grid four">

            <div class="field">

                <label>
                    ${n}차 환전 외화금액
                </label>

                <input
                    id="fxAvg_q${n}"
                    type="number"
                    step="any"
                    placeholder="예: 1000"
                >

            </div>

            <div class="field">

                <label id="fxAvg_pLabel${n}">
                    ${n}차 환전 환율
                </label>

                <input
                    id="fxAvg_p${n}"
                    type="number"
                    step="any"
                    placeholder="예: 1390"
                >

            </div>

            <div class="field">

                <label>
                    ${n}차 환전금액
                </label>

                <input
                    id="fxAvg_m${n}"
                    class="auto"
                    readonly
                    placeholder="자동 계산"
                >

            </div>

            <div class="field">

                <label>
                    ${n}차 평단가
                </label>

                <input
                    id="fxAvg_each${n}"
                    class="auto"
                    readonly
                    placeholder="자동 계산"
                >

            </div>

        </div>

        ${n<3?
            '<div class="divider"></div>':
            ''}

        `;

    }


    document.getElementById(
        "fxAverageRows"
    ).innerHTML=html;


    updateFxAverageLabels();

}

function updateFxAverageLabels(){

    const code=
        document.getElementById(
            "fxAvgCurrency"
        ).value;

    const unit=
        FX[code].unit;


    for(let n=1;n<=3;n++){

        document.getElementById(
            `fxAvg_pLabel${n}`
        ).textContent=

            `${n}차 환전 환율 (${unit} ${code} = 원)`;

    }

}


function fxAverageCalc(){

    const code=
        document.getElementById(
            "fxAvgCurrency"
        ).value;

    const unit=
        FX[code].unit;


    updateFxAverageLabels();


    let totalQ=0;
    let totalM=0;


    for(let n=1;n<=3;n++){

        const q=
            parseValue(
                `fxAvg_q${n}`
            );

        const p=
            parseValue(
                `fxAvg_p${n}`
            );


        const amount=
            (q/unit)*p;


        totalQ+=q;
        totalM+=amount;


        document.getElementById(
            `fxAvg_m${n}`
        ).value=

            amount>0
            ?Math.round(amount)
                .toLocaleString(
                    "ko-KR"
                )+"원"
            :"";


        document.getElementById(
            `fxAvg_each${n}`
        ).value=

            q>0&&p>0
            ?p.toFixed(
                FX[code].decimals
            )
            :"";

    }


    document.getElementById(
        "fxAvgTotalForeign"
    ).textContent=

        totalQ>0
        ?formatForeign(
            totalQ,
            code
        )
        :"-";


    document.getElementById(
        "fxAvgTotalKRW"
    ).textContent=

        totalM>0
        ?Math.round(totalM)
            .toLocaleString(
                "ko-KR"
            )+"원"
        :"-";


    const average=
        totalQ>0
        ?totalM/(totalQ/unit)
        :0;


    document.getElementById(
        "fxAvgPrice"
    ).textContent=

        average>0
        ?formatFx(
            average,
            code
        )
        :"-";


    const current=
        state.fxRates[code]||0;


    document.getElementById(
        "fxAvgCurrent"
    ).textContent=

        current>0
        ?formatFx(
            current,
            code
        )
        :"-";


    const profitEl=
        document.getElementById(
            "fxAvgProfit"
        );

    const rateEl=
        document.getElementById(
            "fxAvgRate"
        );


    if(
        totalQ>0&&
        average>0&&
        current>0
    ){

        const foreignUnits=
            totalQ/unit;

        const profit=
            (current-average)*
            foreignUnits;

        const rate=
            ((current-average)/
            average)*100;


        profitEl.textContent=

            (profit>=0?"+":"")+
            Math.round(profit)
                .toLocaleString(
                    "ko-KR"
                )+"원";


        rateEl.textContent=

            (rate>=0?"+":"")+
            rate.toFixed(2)+"%";


        setClass(
            profitEl,
            profit
        );

        setClass(
            rateEl,
            rate
        );

    }else{

        profitEl.textContent="-";
        rateEl.textContent="-";

        setClass(
            profitEl,
            0
        );

        setClass(
            rateEl,
            0
        );

    }

}


/* =========================
   환전 평단가 저장
========================= */

function saveFxAverage(){

    const data={

        currency:
            document.getElementById(
                "fxAvgCurrency"
            ).value,

        q:[],
        p:[]

    };


    for(let n=1;n<=3;n++){

        data.q.push(
            document.getElementById(
                `fxAvg_q${n}`
            ).value
        );

        data.p.push(
            document.getElementById(
                `fxAvg_p${n}`
            ).value
        );

    }


    localStorage.setItem(
        "munggu_fx_average",
        JSON.stringify(data)
    );


    document.getElementById(
        "fxAvgSaved"
    ).textContent=
        "✓ 저장 완료";

}


function loadFxAverage(){

    const raw=
        localStorage.getItem(
            "munggu_fx_average"
        );

    if(!raw)return;


    try{

        const data=
            JSON.parse(raw);


        document.getElementById(
            "fxAvgCurrency"
        ).value=
            data.currency||"USD";


        for(let n=1;n<=3;n++){

            document.getElementById(
                `fxAvg_q${n}`
            ).value=
                data.q?.[n-1]||"";

            document.getElementById(
                `fxAvg_p${n}`
            ).value=
                data.p?.[n-1]||"";

        }


        fxAverageCalc();

    }catch(e){

        console.error(e);

    }

}


function resetFxAverage(){

    if(!confirm(
        "환전 평단가 계산기를 초기화할까요?"
    ))
        return;


    for(let n=1;n<=3;n++){

        document.getElementById(
            `fxAvg_q${n}`
        ).value="";

        document.getElementById(
            `fxAvg_p${n}`
        ).value="";

        document.getElementById(
            `fxAvg_m${n}`
        ).value="";

        document.getElementById(
            `fxAvg_each${n}`
        ).value="";

    }


    localStorage.removeItem(
        "munggu_fx_average"
    );


    fxAverageCalc();


    document.getElementById(
        "fxAvgSaved"
    ).textContent="";

}


/* =========================
   이벤트
========================= */

function bindEvents(){

    for(let i=1;i<=COUNT;i++){

        for(let n=1;n<=3;n++){

            document.getElementById(
                `a${i}_q${n}`
            ).addEventListener(
                "input",
                ()=>averageCalc(i)
            );

            document.getElementById(
                `a${i}_p${n}`
            ).addEventListener(
                "input",
                ()=>averageCalc(i)
            );

        }


        document.getElementById(
            `a${i}_exchange`
        ).addEventListener(
            "change",
            async()=>{

                updateMarket("a",i);

                averageCalc(i);

                await getPrice(
                    "a",
                    i
                );

            }
        );


        document.getElementById(
            `a${i}_coin`
        ).addEventListener(
            "change",
            async()=>{

                updateMarket("a",i);

                await getPrice(
                    "a",
                    i
                );

            }
        );


        document.getElementById(
            `a${i}_save`
        ).addEventListener(
            "click",
            ()=>saveAverage(i)
        );


        document.getElementById(
            `a${i}_reset`
        ).addEventListener(
            "click",
            ()=>resetAverage(i)
        );


        ["q","buy","current","sell"]
        .forEach(key=>{

            document.getElementById(
                `p${i}_${key}`
            ).addEventListener(
                "input",
                ()=>profitCalc(i)
            );

        });


        document.getElementById(
            `p${i}_exchange`
        ).addEventListener(
            "change",
            async()=>{

                updateMarket("p",i);

                profitCalc(i);

                await getPrice(
                    "p",
                    i
                );

            }
        );


        document.getElementById(
            `p${i}_coin`
        ).addEventListener(
            "change",
            async()=>{

                updateMarket("p",i);

                await getPrice(
                    "p",
                    i
                );

            }
        );


        document.getElementById(
            `p${i}_save`
        ).addEventListener(
            "click",
            ()=>saveProfit(i)
        );


        document.getElementById(
            `p${i}_reset`
        ).addEventListener(
            "click",
            ()=>resetProfit(i)
        );

    }


    Object.keys(FX)
    .forEach(code=>{

        document.getElementById(
            `fx${code}_amount`
        ).addEventListener(
            "input",
            ()=>fxCalc(code)
        );

        document.getElementById(
            `fx${code}_avg`
        ).addEventListener(
            "input",
            ()=>fxCalc(code)
        );

        document.getElementById(
            `fx${code}_save`
        ).addEventListener(
            "click",
            ()=>saveFx(code)
        );

        document.getElementById(
            `fx${code}_reset`
        ).addEventListener(
            "click",
            ()=>resetFx(code)
        );

    });


    document.getElementById(
        "fxAvgCurrency"
    ).addEventListener(
        "change",
        fxAverageCalc
    );


    for(let n=1;n<=3;n++){

        document.getElementById(
            `fxAvg_q${n}`
        ).addEventListener(
            "input",
            fxAverageCalc
        );

        document.getElementById(
            `fxAvg_p${n}`
        ).addEventListener(
            "input",
            fxAverageCalc
        );

    }


    document.getElementById(
        "fxAvgSave"
    ).addEventListener(
        "click",
        saveFxAverage
    );


    document.getElementById(
        "fxAvgReset"
    ).addEventListener(
        "click",
        resetFxAverage
    );

}


/* =========================
   시작
========================= */

makeAverageCards();

makeProfitCards();

makeFxCards();

makeFxAverageRows();

bindEvents();


for(let i=1;i<=COUNT;i++){

    updateMarket("a",i);

    updateMarket("p",i);

    loadAverage(i);

    loadProfit(i);

}


/* 환율 저장값 */

Object.keys(FX)
.forEach(code=>{

    loadFx(code);

});


loadFxAverage();


/* 초기 API 조회 */

setTimeout(()=>{

    for(let i=1;i<=COUNT;i++){

        getPrice(
            "a",
            i
        );

        getPrice(
            "p",
            i
        );

    }

    getFxRates();

},500);


/* 코인 가격 5초 */

setInterval(()=>{

    for(let i=1;i<=COUNT;i++){

        getPrice(
            "a",
            i
        );

        getPrice(
            "p",
            i
        );

    }

},5000);


/* 환율 1분 */

setInterval(()=>{

    getFxRates();

},60000);

</script>

</body>
</html>
