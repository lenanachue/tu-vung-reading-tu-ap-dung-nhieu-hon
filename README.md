<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Từ Vựng Ôn Tập - Đọc Hiểu</title>
<style>
:root{
  --purple-1:#f3e8ff;
  --purple-2:#e9d5ff;
  --purple-3:#c084fc;
  --purple-4:#a855f7;
  --purple-5:#7e22ce;
  --purple-dark:#581c87;
  --pink:#f0abfc;
  --card-bg:#ffffff;
  --correct:#22c55e;
  --wrong:#ef4444;
}
*{box-sizing:border-box;}
body{
  margin:0;
  font-family:'Segoe UI', 'Roboto', Arial, sans-serif;
  background:linear-gradient(135deg,var(--purple-1) 0%, var(--purple-2) 40%, #fdf4ff 100%);
  color:#3b0764;
  min-height:100vh;
  position:relative;
  overflow-x:hidden;
}
.floaty{
  position:fixed;
  font-size:34px;
  opacity:0.18;
  z-index:0;
  animation:float 8s ease-in-out infinite;
  pointer-events:none;
}
@keyframes float{
  0%,100%{transform:translateY(0px) rotate(0deg);}
  50%{transform:translateY(-22px) rotate(8deg);}
}
.f1{top:6%;left:4%;animation-delay:0s;}
.f2{top:16%;right:6%;animation-delay:1.5s;}
.f3{bottom:14%;left:8%;animation-delay:3s;}
.f4{bottom:6%;right:10%;animation-delay:2s;}
.f5{top:45%;left:2%;animation-delay:4s;}
.f6{top:60%;right:3%;animation-delay:2.5s;}

.wrap{
  max-width:920px;
  margin:0 auto;
  padding:28px 18px 60px;
  position:relative;
  z-index:1;
}
header{
  text-align:center;
  margin-bottom:26px;
}
header h1{
  font-size:clamp(22px,4vw,32px);
  background:linear-gradient(90deg,var(--purple-5),var(--pink));
  -webkit-background-clip:text;
  background-clip:text;
  color:transparent;
  margin:0 0 6px;
}
header p{
  color:#6b21a8;
  font-size:15px;
  margin:0;
}

.tabs{
  display:flex;
  flex-wrap:wrap;
  gap:8px;
  justify-content:center;
  margin-bottom:22px;
}
.tab-btn{
  border:2px solid var(--purple-3);
  background:#ffffffaa;
  color:var(--purple-5);
  padding:10px 16px;
  border-radius:14px;
  cursor:pointer;
  font-weight:600;
  font-size:14px;
  transition:all .2s;
}
.tab-btn:hover{background:var(--purple-1);}
.tab-btn.active{
  background:linear-gradient(90deg,var(--purple-4),var(--pink));
  color:#fff;
  border-color:transparent;
  box-shadow:0 4px 14px rgba(168,85,247,0.35);
}

.panel{display:none;}
.panel.active{display:block; animation:fadein .35s ease;}
@keyframes fadein{from{opacity:0;transform:translateY(8px);}to{opacity:1;transform:translateY(0);}}

.section-title{
  font-size:18px;
  color:var(--purple-dark);
  margin:6px 0 16px;
  padding-left:10px;
  border-left:5px solid var(--purple-4);
}

.card{
  background:var(--card-bg);
  border:2px solid var(--purple-2);
  border-left:6px solid var(--purple-4);
  border-radius:16px;
  padding:16px 18px;
  margin-bottom:14px;
  box-shadow:0 3px 10px rgba(168,85,247,0.08);
}
.word-row{
  display:flex;
  align-items:baseline;
  gap:10px;
  flex-wrap:wrap;
  margin-bottom:4px;
}
.word{
  font-size:19px;
  font-weight:700;
  color:var(--purple-5);
}
.ipa{color:#a855f7; font-size:14px;}
.pos{
  background:var(--purple-1);
  color:var(--purple-5);
  font-size:12px;
  padding:2px 8px;
  border-radius:8px;
  font-style:italic;
}
.meaning{
  font-size:15px;
  color:#3b0764;
  margin:4px 0 8px;
  font-weight:600;
}
.mnemonic{
  background:#fdf4ff;
  border:1px dashed var(--purple-3);
  border-radius:10px;
  padding:8px 10px;
  font-size:13.5px;
  color:#6b21a8;
  margin-bottom:6px;
}
.mnemonic b{color:var(--purple-5);}
.example{
  font-size:13.5px;
  color:#555;
  font-style:italic;
}

.practice-intro{
  background:#fff;
  border:2px solid var(--purple-2);
  border-radius:16px;
  padding:14px 18px;
  margin-bottom:18px;
}
.word-bank{
  display:flex;
  flex-wrap:wrap;
  gap:8px;
  margin-top:8px;
}
.chip{
  background:linear-gradient(90deg,var(--purple-1),#fdf4ff);
  border:1.5px solid var(--purple-3);
  color:var(--purple-5);
  padding:5px 12px;
  border-radius:20px;
  font-size:13px;
  font-weight:600;
}

.sentence-card{
  background:var(--card-bg);
  border:2px solid var(--purple-2);
  border-radius:14px;
  padding:14px 16px;
  margin-bottom:12px;
  line-height:2.1;
  font-size:15px;
}
.sentence-card .num{
  color:var(--purple-4);
  font-weight:700;
  margin-right:4px;
}
.blank-input{
  border:none;
  border-bottom:2.5px solid var(--purple-4);
  background:var(--purple-1);
  padding:3px 8px;
  font-size:15px;
  font-family:inherit;
  width:130px;
  text-align:center;
  border-radius:6px 6px 0 0;
  color:var(--purple-dark);
  font-weight:600;
}
.blank-input:focus{outline:none; background:#fff; border-bottom-color:var(--pink);}
.blank-input.correct{background:#dcfce7; border-bottom-color:var(--correct); color:#15803d;}
.blank-input.wrong{background:#fee2e2; border-bottom-color:var(--wrong); color:#b91c1c;}

.check-row{
  display:flex;
  gap:10px;
  justify-content:center;
  margin:20px 0 10px;
  flex-wrap:wrap;
}
.btn{
  border:none;
  padding:11px 22px;
  border-radius:12px;
  font-weight:700;
  font-size:14.5px;
  cursor:pointer;
  transition:transform .15s;
}
.btn:hover{transform:translateY(-2px);}
.btn-primary{
  background:linear-gradient(90deg,var(--purple-4),var(--pink));
  color:#fff;
  box-shadow:0 4px 12px rgba(168,85,247,0.35);
}
.btn-secondary{
  background:#fff;
  color:var(--purple-5);
  border:2px solid var(--purple-3);
}
.result-box{
  text-align:center;
  font-size:16px;
  font-weight:700;
  padding:12px;
  border-radius:12px;
  margin-top:14px;
  display:none;
}
.result-good{background:#dcfce7; color:#15803d; display:block;}
.result-mid{background:#fef9c3; color:#854d0e; display:block;}
.result-low{background:#fee2e2; color:#b91c1c; display:block;}

.footer-note{
  text-align:center;
  color:#9333ea;
  font-size:12.5px;
  margin-top:30px;
  opacity:0.8;
}
</style>
</head>
<body>

<div class="floaty f1">📚</div>
<div class="floaty f2">✏️</div>
<div class="floaty f3">🎓</div>
<div class="floaty f4">📖</div>
<div class="floaty f5">💜</div>
<div class="floaty f6">🔤</div>

<div class="wrap">
  <header>
    <h1>🌸 Từ Vựng Ôn Tập Đọc Hiểu 🌸</h1>
    <p>20 từ vựng quan trọng trích từ 2 bài đọc — Học trước, luyện tập sau!</p>
  </header>

  <div class="tabs">
    <button class="tab-btn active" onclick="showTab('vocab1')">📖 Từ vựng - Bài 1</button>
    <button class="tab-btn" onclick="showTab('vocab2')">📖 Từ vựng - Bài 2</button>
    <button class="tab-btn" onclick="showTab('practice1')">✍️ Luyện tập - Bài 1</button>
    <button class="tab-btn" onclick="showTab('practice2')">✍️ Luyện tập - Bài 2</button>
  </div>

  <!-- ===================== VOCAB 1 ===================== -->
  <div id="vocab1" class="panel active">
    <div class="section-title">10 từ vựng — Bài đọc "Living in the country"</div>

    <div class="card">
      <div class="word-row"><span class="word">advantage</span><span class="ipa">/ədˈvæn.tɪdʒ/</span><span class="pos">n</span></div>
      <div class="meaning">lợi thế, điểm thuận lợi</div>
      <div class="mnemonic">💡 Mẹo: liên tưởng đến chiếc xe <b>VAN</b> trong "ad-VAN-tage" — xe VAN chở đầy "lợi thế" cho bạn.</div>
      <div class="example">"There are certainly many <b>advantages</b> to living in the country."</div>
    </div>

    <div class="card">
      <div class="word-row"><span class="word">disadvantage</span><span class="ipa">/ˌdɪs.ədˈvæn.tɪdʒ/</span><span class="pos">n</span></div>
      <div class="meaning">bất lợi, điểm không thuận lợi</div>
      <div class="mnemonic">💡 Mẹo: <b>dis-</b> là phủ định (như trong "disagree"), nên disadvantage = KHÔNG có advantage.</div>
      <div class="example">"There are certain <b>disadvantages</b> or drawbacks to life outside the city."</div>
    </div>

    <div class="card">
      <div class="word-row"><span class="word">quietness</span><span class="ipa">/ˈkwaɪ.ət.nəs/</span><span class="pos">n</span></div>
      <div class="meaning">sự yên tĩnh</div>
      <div class="mnemonic">💡 Mẹo: em đã biết <b>quiet</b> (yên tĩnh) rồi, thêm "-ness" biến tính từ thành danh từ.</div>
      <div class="example">"You can enjoy peace and <b>quietness</b>."</div>
    </div>

    <div class="card">
      <div class="word-row"><span class="word">friendly</span><span class="ipa">/ˈfrend.li/</span><span class="pos">adj</span></div>
      <div class="meaning">thân thiện</div>
      <div class="mnemonic">💡 Mẹo: <b>friend</b> (bạn) + "-ly" → có tính cách như một người bạn.</div>
      <div class="example">"People tend to be <b>friendlier</b>."</div>
    </div>

    <div class="card">
      <div class="word-row"><span class="word">traffic</span><span class="ipa">/ˈtræf.ɪk/</span><span class="pos">n</span></div>
      <div class="meaning">giao thông, xe cộ</div>
      <div class="mnemonic">💡 Mẹo: liên tưởng cụm quen thuộc "traffic jam" = kẹt xe.</div>
      <div class="example">"There is less <b>traffic</b>, so it is safer for young children."</div>
    </div>

    <div class="card">
      <div class="word-row"><span class="word">entertainment</span><span class="ipa">/ˌen.təˈteɪn.mənt/</span><span class="pos">n</span></div>
      <div class="meaning">sự giải trí</div>
      <div class="mnemonic">💡 Mẹo: nghĩ đến "TV entertainment" — chương trình giải trí trên TV.</div>
      <div class="example">"<b>Entertainment</b> is difficult to find, particularly in the evening."</div>
    </div>

    <div class="card">
      <div class="word-row"><span class="word">particularly</span><span class="ipa">/pəˈtɪk.jə.lə.li/</span><span class="pos">adv</span></div>
      <div class="meaning">đặc biệt là</div>
      <div class="mnemonic">💡 Mẹo: gốc từ <b>particular</b> (cụ thể, riêng biệt) + "-ly".</div>
      <div class="example">"...particularly in the evening."</div>
    </div>

    <div class="card">
      <div class="word-row"><span class="word">suitable</span><span class="ipa">/ˈsuː.tə.bəl/</span><span class="pos">adj</span></div>
      <div class="meaning">phù hợp</div>
      <div class="mnemonic">💡 Mẹo: <b>suit</b> (bộ vest / vừa vặn) + "-able" → mặc "suit" vừa vặn = phù hợp.</div>
      <div class="example">"The country is more <b>suitable</b> for some people than others."</div>
    </div>

    <div class="card">
      <div class="word-row"><span class="word">retired</span><span class="ipa">/rɪˈtaɪəd/</span><span class="pos">adj</span></div>
      <div class="meaning">đã nghỉ hưu</div>
      <div class="mnemonic">💡 Mẹo: <b>re-</b> + <b>tired</b> (mệt) → làm việc mệt nhiều lần rồi nên nghỉ hưu.</div>
      <div class="example">"It is often the best for those who are <b>retired</b>."</div>
    </div>

    <div class="card">
      <div class="word-row"><span class="word">career</span><span class="ipa">/kəˈrɪər/</span><span class="pos">n</span></div>
      <div class="meaning">sự nghiệp, nghề nghiệp lâu dài</div>
      <div class="mnemonic">💡 Mẹo: đọc gần giống "carrier" — người "mang" cả sự nghiệp suốt đời.</div>
      <div class="example">"Young people who have a <b>career</b> are better provided in the city."</div>
    </div>
  </div>

  <!-- ===================== VOCAB 2 ===================== -->
  <div id="vocab2" class="panel">
    <div class="section-title">10 từ vựng — Bài đọc điền từ về nước Anh</div>

    <div class="card">
      <div class="word-row"><span class="word">rapidly</span><span class="ipa">/ˈræp.ɪd.li/</span><span class="pos">adv</span></div>
      <div class="meaning">một cách nhanh chóng</div>
      <div class="mnemonic">💡 Mẹo: liên tưởng "rapid fire" trong game bắn súng — bắn cực nhanh.</div>
      <div class="example">"Life is changing <b>rapidly</b> in the large cities of England."</div>
    </div>

    <div class="card">
      <div class="word-row"><span class="word">remain</span><span class="ipa">/rɪˈmeɪn/</span><span class="pos">v</span></div>
      <div class="meaning">vẫn còn, duy trì như cũ</div>
      <div class="mnemonic">💡 Mẹo: <b>re-</b> + <b>main</b> (chính) → phần chính vẫn còn nguyên đó.</div>
      <div class="example">"Life in other areas <b>remains</b> much the same as it has been for centuries."</div>
    </div>

    <div class="card">
      <div class="word-row"><span class="word">population</span><span class="ipa">/ˌpɒp.jəˈleɪ.ʃən/</span><span class="pos">n</span></div>
      <div class="meaning">dân số</div>
      <div class="mnemonic">💡 Mẹo: gốc giống <b>popular</b> (được nhiều người biết đến) → population = số lượng người (dân số).</div>
      <div class="example">"Factories have brought huge <b>population</b> increases to the cities."</div>
    </div>

    <div class="card">
      <div class="word-row"><span class="word">boom</span><span class="ipa">/buːm/</span><span class="pos">v/n</span></div>
      <div class="meaning">bùng nổ, phát triển mạnh</div>
      <div class="mnemonic">💡 Mẹo: âm thanh "boom" giống tiếng nổ lớn — bùng nổ nhanh và mạnh.</div>
      <div class="example">"City life <b>boomed</b>."</div>
    </div>

    <div class="card">
      <div class="word-row"><span class="word">traditional</span><span class="ipa">/trəˈdɪʃ.ən.əl/</span><span class="pos">adj</span></div>
      <div class="meaning">thuộc về truyền thống</div>
      <div class="mnemonic">💡 Mẹo: gốc <b>tradition</b> (truyền thống) + "-al", từ vay mượn tiếng Việt "truyền thống" khá quen.</div>
      <div class="example">"The <b>traditional</b> lifestyle has remained nearly unchanged."</div>
    </div>

    <div class="card">
      <div class="word-row"><span class="word">unchanged</span><span class="ipa">/ʌnˈtʃeɪndʒd/</span><span class="pos">adj</span></div>
      <div class="meaning">không thay đổi</div>
      <div class="mnemonic">💡 Mẹo: <b>un-</b> (không) + <b>changed</b> (đã thay đổi) — em đã biết cả hai phần rồi.</div>
      <div class="example">"The traditional lifestyle has remained nearly <b>unchanged</b>."</div>
    </div>

    <div class="card">
      <div class="word-row"><span class="word">efficient</span><span class="ipa">/ɪˈfɪʃ.ənt/</span><span class="pos">adj</span></div>
      <div class="meaning">hiệu quả</div>
      <div class="mnemonic">💡 Mẹo: từ "hiệu quả/efficient" hay được dùng khi nói về máy móc, công nghệ.</div>
      <div class="example">"It made farm production more <b>efficient</b>."</div>
    </div>

    <div class="card">
      <div class="word-row"><span class="word">industrial</span><span class="ipa">/ɪnˈdʌs.tri.əl/</span><span class="pos">adj</span></div>
      <div class="meaning">thuộc về công nghiệp</div>
      <div class="mnemonic">💡 Mẹo: gốc <b>industry</b> (công nghiệp) + "-al", liên tưởng "khu công nghiệp".</div>
      <div class="example">"The <b>Industrial</b> Revolution."</div>
    </div>

    <div class="card">
      <div class="word-row"><span class="word">agriculture</span><span class="ipa">/ˈæɡ.rɪ.kʌl.tʃər/</span><span class="pos">n</span></div>
      <div class="meaning">nông nghiệp</div>
      <div class="mnemonic">💡 Mẹo: <b>agri-</b> (đất, nông) + <b>culture</b> (văn hóa) → "văn hóa của đất đai" = nông nghiệp.</div>
      <div class="example">"Workers is still employed in <b>agriculture</b> or in domestic service."</div>
    </div>

    <div class="card">
      <div class="word-row"><span class="word">profession</span><span class="ipa">/prəˈfeʃ.ən/</span><span class="pos">n</span></div>
      <div class="meaning">nghề nghiệp chuyên môn</div>
      <div class="mnemonic">💡 Mẹo: em đã biết <b>professional</b> (cầu thủ chuyên nghiệp) — profession chính là gốc của từ đó.</div>
      <div class="example">"A smaller number of people work in the <b>professions</b>."</div>
    </div>
  </div>

  <!-- ===================== PRACTICE 1 ===================== -->
  <div id="practice1" class="panel">
    <div class="section-title">Luyện tập — Điền từ vào câu (Bài 1)</div>
    <div class="practice-intro">
      Điền từ đúng vào chỗ trống. Mỗi câu chỉ dùng <b>một từ</b> trong ngân hàng từ bên dưới (chia động từ/thêm hậu tố nếu cần).
      <div class="word-bank">
        <span class="chip">advantage</span><span class="chip">disadvantage</span><span class="chip">quietness</span>
        <span class="chip">friendly</span><span class="chip">traffic</span><span class="chip">entertainment</span>
        <span class="chip">particularly</span><span class="chip">suitable</span><span class="chip">retired</span><span class="chip">career</span>
      </div>
    </div>

    <div class="sentence-card"><span class="num">1.</span>My grandparents are <input class="blank-input" data-answer="retired" placeholder="......."> now, so they moved to a quiet village to relax.</div>
    <div class="sentence-card"><span class="num">2.</span>One big <input class="blank-input" data-answer="advantage" placeholder="......."> of living near the sea is the fresh air every morning.</div>
    <div class="sentence-card"><span class="num">3.</span>In our neighborhood, the streets are so busy that <input class="blank-input" data-answer="traffic" placeholder="......."> jams happen almost every afternoon.</div>
    <div class="sentence-card"><span class="num">4.</span>After a long week at work, I really enjoy the <input class="blank-input" data-answer="quietness" placeholder="......."> of the countryside on weekends.</div>
    <div class="sentence-card"><span class="num">5.</span>My new neighbors are very <input class="blank-input" data-answer="friendly" placeholder="......."> — they always say hello and offer to help.</div>
    <div class="sentence-card"><span class="num">6.</span>One <input class="blank-input" data-answer="disadvantage" placeholder="......."> of living far from the city is that it takes longer to get to school.</div>
    <div class="sentence-card"><span class="num">7.</span>There isn't much <input class="blank-input" data-answer="entertainment" placeholder="......."> in small towns, so people often go to bed early.</div>
    <div class="sentence-card"><span class="num">8.</span>This apartment is very <input class="blank-input" data-answer="suitable" placeholder="......."> for a small family with young children.</div>
    <div class="sentence-card"><span class="num">9.</span>She wants to build a successful <input class="blank-input" data-answer="career" placeholder="......."> as a doctor, so she studies very hard.</div>
    <div class="sentence-card"><span class="num">10.</span>It is hard to find a job in the countryside, <input class="blank-input" data-answer="particularly" placeholder="......."> in winter when farms need fewer workers.</div>

    <div class="check-row">
      <button class="btn btn-primary" onclick="checkAnswers('practice1')">✅ Kiểm tra</button>
      <button class="btn btn-secondary" onclick="resetPanel('practice1')">🔄 Làm lại</button>
    </div>
    <div id="result-practice1" class="result-box"></div>
  </div>

  <!-- ===================== PRACTICE 2 ===================== -->
  <div id="practice2" class="panel">
    <div class="section-title">Luyện tập — Điền từ vào câu (Bài 2)</div>
    <div class="practice-intro">
      Điền từ đúng vào chỗ trống. Mỗi câu chỉ dùng <b>một từ</b> trong ngân hàng từ bên dưới (chia động từ/thêm hậu tố nếu cần).
      <div class="word-bank">
        <span class="chip">rapidly</span><span class="chip">remain</span><span class="chip">population</span>
        <span class="chip">boom</span><span class="chip">traditional</span><span class="chip">unchanged</span>
        <span class="chip">efficient</span><span class="chip">industrial</span><span class="chip">agriculture</span><span class="chip">profession</span>
      </div>
    </div>

    <div class="sentence-card"><span class="num">1.</span>New technology is developing so <input class="blank-input" data-answer="rapidly" placeholder="......."> that phones become outdated within a year.</div>
    <div class="sentence-card"><span class="num">2.</span>Even after moving to the city, she decided to <input class="blank-input" data-answer="remain" placeholder="......."> close to her family in the village.</div>
    <div class="sentence-card"><span class="num">3.</span>The <input class="blank-input" data-answer="population" placeholder="......."> of the city has doubled since the new factories opened.</div>
    <div class="sentence-card"><span class="num">4.</span>Tourism <input class="blank-input" data-answer="boomed" placeholder="......."> in the coastal town after the new airport was built.</div>
    <div class="sentence-card"><span class="num">5.</span>My grandmother still cooks <input class="blank-input" data-answer="traditional" placeholder="......."> dishes that her mother taught her.</div>
    <div class="sentence-card"><span class="num">6.</span>Despite all the new buildings, the old market has stayed almost <input class="blank-input" data-answer="unchanged" placeholder="......."> for fifty years.</div>
    <div class="sentence-card"><span class="num">7.</span>The new machine is much more <input class="blank-input" data-answer="efficient" placeholder="......."> than the old one, so farmers finish work faster.</div>
    <div class="sentence-card"><span class="num">8.</span>This area used to be full of farms, but now it is an <input class="blank-input" data-answer="industrial" placeholder="......."> zone with many factories.</div>
    <div class="sentence-card"><span class="num">9.</span>Most families in the village still depend on <input class="blank-input" data-answer="agriculture" placeholder="......."> to earn a living.</div>
    <div class="sentence-card"><span class="num">10.</span>Being a doctor is a <input class="blank-input" data-answer="profession" placeholder="......."> that requires many years of study.</div>

    <div class="check-row">
      <button class="btn btn-primary" onclick="checkAnswers('practice2')">✅ Kiểm tra</button>
      <button class="btn btn-secondary" onclick="resetPanel('practice2')">🔄 Làm lại</button>
    </div>
    <div id="result-practice2" class="result-box"></div>
  </div>

  <div class="footer-note">💜 Học từ vựng trước, sau đó luyện tập để ghi nhớ lâu hơn nhé! 💜</div>
</div>

<script>
function showTab(id){
  document.querySelectorAll('.panel').forEach(p=>p.classList.remove('active'));
  document.querySelectorAll('.tab-btn').forEach(b=>b.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  const idx = ['vocab1','vocab2','practice1','practice2'].indexOf(id);
  document.querySelectorAll('.tab-btn')[idx].classList.add('active');
}

function normalize(str){
  return str.trim().toLowerCase().replace(/\s+/g,'');
}

function checkAnswers(panelId){
  const panel = document.getElementById(panelId);
  const inputs = panel.querySelectorAll('.blank-input');
  let correct = 0;
  inputs.forEach(inp=>{
    const answer = normalize(inp.getAttribute('data-answer'));
    const given = normalize(inp.value);
    inp.classList.remove('correct','wrong');
    if(given === answer){
      inp.classList.add('correct');
      correct++;
    } else if(given.length>0){
      inp.classList.add('wrong');
    }
  });
  const total = inputs.length;
  const resultBox = document.getElementById('result-' + panelId);
  resultBox.classList.remove('result-good','result-mid','result-low');
  let emoji, cls, msg;
  const ratio = correct/total;
  if(ratio === 1){ emoji='🎉🌟'; cls='result-good'; msg='Xuất sắc! Em đã nắm vững toàn bộ từ vựng!'; }
  else if(ratio >= 0.7){ emoji='👏😊'; cls='result-mid'; msg='Khá tốt! Xem lại vài từ sai rồi thử lại nhé!'; }
  else { emoji='💪📖'; cls='result-low'; msg='Hãy quay lại phần Từ vựng để ôn thêm rồi thử lại nha!'; }
  resultBox.classList.add(cls);
  resultBox.innerHTML = `${emoji} Đúng ${correct}/${total} câu — ${msg}`;

  try{
    localStorage.setItem('vocab_score_'+panelId, JSON.stringify({correct, total, date:new Date().toISOString()}));
  }catch(e){}
}

function resetPanel(panelId){
  const panel = document.getElementById(panelId);
  panel.querySelectorAll('.blank-input').forEach(inp=>{
    inp.value='';
    inp.classList.remove('correct','wrong');
  });
  document.getElementById('result-' + panelId).classList.remove('result-good','result-mid','result-low');
  document.getElementById('result-' + panelId).innerHTML='';
}

// restore draft inputs from localStorage (draft persistence)
document.querySelectorAll('.blank-input').forEach(inp=>{
  inp.addEventListener('input', ()=>{
    try{
      const key = 'vocab_draft_' + inp.closest('.panel').id + '_' + Array.from(inp.parentElement.parentElement.children).indexOf(inp.closest('.sentence-card'));
    }catch(e){}
  });
});
</script>

</body>
</html>
