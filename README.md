<html lang="ar">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Present Perfect vs Simple Past Quiz</title>
<style>
body {
  margin:0;
  font-family:system-ui,-apple-system,"Segoe UI",Roboto,"Noto Sans Arabic";
  background:#eef2f7;
  direction:ltr;
}
.container {
  max-width:900px;
  margin:30px auto;
  padding:20px;
}
h1 {
  font-size:2rem;
  color:#34495e;
  margin-bottom:12px;
  text-align:center;
}
.lead {
  text-align:center;
  margin-bottom:20px;
  color:#2c3e50;
  font-size:1.2rem;
}
.info {
  text-align:center;
  margin-bottom:25px;
  color:#2c3e50;
  font-weight:600;
  line-height:1.6;
  font-size:1.1rem;
}
.card {
  background:#fff;
  padding:22px;
  border-radius:18px;
  box-shadow:0 8px 26px rgba(0,0,0,.08);
  margin-bottom:20px;
  position:relative;
  transition:transform .25s;
}
.card:hover {transform:translateY(-3px);}
.q-head {
  display:flex;
  align-items:center;
  gap:14px;
}
.q-num {
  background:linear-gradient(135deg,#81ecec,#74b9ff);
  color:#fff;
  padding:8px 18px;
  border-radius:14px;
  font-weight:700;
  font-size:1rem;
}
.sentence {
  margin:14px 0 16px;
  font-size:1.3rem;
  color:#2c3e50;
}
.choices {
  display:flex;
  gap:12px;
  flex-wrap:wrap;
}
.choice {
  flex:1 1 240px;
  padding:14px 16px;
  border-radius:12px;
  border:1px solid #dce6f1;
  background:#dfe6e9;
  cursor:pointer;
  transition:.3s all;
  user-select:none;
  font-size:1.1rem;
  text-align:center;
}
.choice:hover {transform:translateY(-4px) scale(1.02); box-shadow:0 6px 18px rgba(0,0,0,.08);}
.choice.correct {
  background:linear-gradient(90deg,#2ecc71,#27ae60);
  color:#fff;
  font-weight:700;
  animation: glow 1s ease-in-out;
}
.choice.wrong {
  background:linear-gradient(90deg,#e74c3c,#c0392b);
  color:#fff;
  font-weight:700;
  animation: shake 0.5s;
}
.choice.disabled {cursor:default; opacity:.85; box-shadow:none; transform:none;}
@keyframes shake {
  0%,100%{transform:translateX(0);}
  25%{transform:translateX(-6px);}
  50%{transform:translateX(6px);}
  75%{transform:translateX(-4px);}
}
@keyframes glow {
  0%,100%{box-shadow:0 0 8px rgba(0,0,0,.2);}
  50%{box-shadow:0 0 18px rgba(255,255,255,.6);}
}
.popover {
  position:relative;
  background:#fff;
  border:1px solid #cfd8dc;
  border-radius:14px;
  padding:16px 18px;
  margin-top:12px;
  font-size:1.05rem;
  color:#2c3e50;
  box-shadow:0 8px 26px rgba(0,0,0,.08);
  width:100%;
  line-height:1.6;
  direction:rtl;
  text-align:right;
  opacity:0;
  transform:translateY(-10px);
  animation: popfade 0.5s forwards;
}
@keyframes popfade {
  to {opacity:1; transform:translateY(0);}
}
.popover .eng-example {
  margin-top:8px;
  padding-top:6px;
  border-top:1px solid #ddd;
  font-family:"Segoe UI",sans-serif;
  direction:ltr;
  text-align:left;
  font-weight:600;
}
.credit {
  text-align:center;
  margin-top:30px;
  font-size:1rem;
  color:#555;
  padding:12px 0;
}
</style>
</head>
<body>
<div class="container">

<div class="info">
تنفيذ معلم مادة اللغة الإنجليزية: الأستاذ / فهد نغيمش الخالدي<br>
مدرسة: سعيد بن العاص المتوسطة<br>
الصف: الثالث المتوسط
</div>

<h1>Present Perfect vs Simple Past Quiz</h1>
<p class="lead">اختر الإجابة الصحيحة. إذا كانت إجابتك خاطئة، سيظهر الشرح باللغة العربية مع مثال.</p>

<div id="quiz"></div>
<div class="credit">إعداد: المعلم فهد نغيمش الخالدي</div>
</div>

<script>
const questions = [
  { sentence:"I _____ (visit) London three times in my life.", choices:["visited","have visited"], correct:1,
    explanation:"نستخدم Present Perfect للتجارب الحياتية بدون ذكر وقت محدد.",
    example:"I have visited London three times." },
  { sentence:"She _____ (finish) her homework yesterday.", choices:["has finished","finished"], correct:1,
    explanation:"كلمة yesterday تحدد وقتًا منتهيًا → Simple Past.",
    example:"She finished her homework yesterday." },
  { sentence:"We _____ (live) here since 2018.", choices:["lived","have lived"], correct:1,
    explanation:"استخدام since يدل على فعل بدأ في الماضي ومازال مستمرًا.",
    example:"We have lived here since 2018." },
  { sentence:"He _____ (break) his leg last winter.", choices:["broke","has broken"], correct:0,
    explanation:"last winter يحدد وقتًا من الماضي فقط → Simple Past.",
    example:"He broke his leg last winter." },
  { sentence:"She _____ gone to the store.", choices:["have","has"], correct:1,
    explanation:"في Present Perfect نستخدم has مع She/He/It لأن الفاعل مفرد.",
    example:"She has gone to the store." },
  { sentence:"They _____ already finished the project.", choices:["have","has"], correct:0,
    explanation:"مع they نستخدم have لأن الفاعل جمع.",
    example:"They have already finished the project." },
  { sentence:"He _____ not done his work yet.", choices:["have","has"], correct:1,
    explanation:"الفعل المفرد He يأخذ has في Present Perfect.",
    example:"He has not done his work yet." },
  { sentence:"I _____ ate sushi before.", choices:["have eaten","ate"], correct:0,
    explanation:"عند الحديث عن تجربة بدون وقت محدد نستخدم Present Perfect.",
    example:"I have eaten sushi before." },
  { sentence:"She _____ never seen snow.", choices:["has","have"], correct:0,
    explanation:"الفاعل She مفرد → has + التصريف الثالث للفعل.",
    example:"She has never seen snow." },
  { sentence:"We _____ finished the exam two hours ago.", choices:["have finished","finished"], correct:1,
    explanation:"وجود 'two hours ago' يدل على وقت من الماضي المنتهي → Simple Past.",
    example:"We finished the exam two hours ago." },
  { sentence:"I _____ (meet) him in 2020.", choices:["met","have met"], correct:0,
    explanation:"2020 وقت محدد في الماضي → Simple Past.",
    example:"I met him in 2020." },
  { sentence:"I _____ (meet) him before.", choices:["met","have met"], correct:1,
    explanation:"before يدل على تجربة بدون وقت → Present Perfect.",
    example:"I have met him before." },
  { sentence:"They _____ (be) friends since childhood.", choices:["have been","were"], correct:0,
    explanation:"العلاقة مستمرة حتى الآن → Present Perfect.",
    example:"They have been friends since childhood." },
  { sentence:"She _____ (go) to Paris last month.", choices:["went","has gone"], correct:0,
    explanation:"last month وقت منتهي → Simple Past.",
    example:"She went to Paris last month." },
  { sentence:"He _____ (lose) his keys — he can’t find them.", choices:["lost","has lost"], correct:1,
    explanation:"النتيجة مازالت مستمرة → Present Perfect.",
    example:"He has lost his keys." },
  { sentence:"I _____ just finished my homework.", choices:["have","has"], correct:0,
    explanation:"مع I نستخدم have + التصريف الثالث → Present Perfect.",
    example:"I have just finished my homework." },
  { sentence:"They _____ (see) that movie yesterday.", choices:["have seen","saw"], correct:1,
    explanation:"yesterday يدل على زمن محدد → Simple Past.",
    example:"They saw that movie yesterday." },
  { sentence:"She _____ (write) three emails so far.", choices:["has written","wrote"], correct:0,
    explanation:"so far تشير إلى تجربة مستمرة → Present Perfect.",
    example:"She has written three emails so far." },
  { sentence:"We _____ (eat) lunch an hour ago.", choices:["have eaten","ate"], correct:1,
    explanation:"an hour ago يدل على وقت محدد → Simple Past.",
    example:"We ate lunch an hour ago." },
  { sentence:"He _____ (never/try) sushi before.", choices:["has never tried","never tried"], correct:0,
    explanation:"قبل الآن → Present Perfect للتجربة.",
    example:"He has never tried sushi before." },
  { sentence:"I _____ (finish) reading the book.", choices:["finished","have finished"], correct:1,
    explanation:"التجربة مستمرة أو انتهت للتو → Present Perfect.",
    example:"I have finished reading the book." },
  { sentence:"They _____ (visit) their grandparents last weekend.", choices:["visited","have visited"], correct:0,
    explanation:"last weekend زمن محدد → Simple Past.",
    example:"They visited their grandparents last weekend." },
  { sentence:"She _____ (be) ill since Monday.", choices:["has been","was"], correct:0,
    explanation:"since Monday → مستمرة → Present Perfect.",
    example:"She has been ill since Monday." },
  { sentence:"He _____ (start) his new job yesterday.", choices:["has started","started"], correct:1,
    explanation:"yesterday زمن محدد → Simple Past.",
    example:"He started his new job yesterday." },
  { sentence:"We _____ (know) each other for ten years.", choices:["have known","knew"], correct:0,
    explanation:"for ten years → مستمرة → Present Perfect.",
    example:"We have known each other for ten years." },
  { sentence:"I _____ (lose) my wallet yesterday.", choices:["lost","have lost"], correct:0,
    explanation:"yesterday → Simple Past.",
    example:"I lost my wallet yesterday." }
];

const quiz=document.getElementById("quiz");

function createCard(q,i){
  const card=document.createElement("div");
  card.className="card";
  card.innerHTML=`<div class="q-head"><div class="q-num">Q${i+1}</div></div>
  <div class="sentence">${q.sentence}</div><div class="choices"></div>`;
  const choicesDiv=card.querySelector(".choices");
  q.choices.forEach((choice,idx)=>{
    const btn=document.createElement("button");
    btn.className="choice"; btn.textContent=choice;
    btn.addEventListener("click",()=>{
      if(btn.classList.contains("disabled")) return;
      Array.from(choicesDiv.children).forEach(c=>c.classList.add("disabled"));
      if(idx === q.correct){ 
        btn.classList.add("correct"); 
      } else {
        btn.classList.add("wrong");
        choicesDiv.children[q.correct].classList.add("correct"); 
        showPopover(card,q.explanation,q.example);
      }
    });
    choicesDiv.appendChild(btn);
  });
  return card;
}

function showPopover(card,arabic,example){
  const old=card.querySelector(".popover"); if(old) old.remove();
  const pop=document.createElement("div");
  pop.className="popover";
  pop.innerHTML=`<div><strong>الشرح:</strong> ${arabic}</div>
                 <div class="eng-example">${example}</div>`;
  card.appendChild(pop);
}

questions.forEach((q,i)=>quiz.appendChild(createCard(q,i)));
</script>
</body>
</html>
