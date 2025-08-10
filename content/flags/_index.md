---
title: Flag
template: flags.html
paginate_by: 0
---



<div id="progress-container" style="width:100%; min-height:400px; background:#f5f7fa; padding:20px; border-radius:10px"></div>

<script>
// 精简版JavaScript核心逻辑
const container = document.getElementById('progress-container');
const now = new Date();
const year = now.getFullYear();
const isLeap = (year % 4 === 0 && year % 100 !== 0) || year % 400 === 0;
const totalDays = isLeap ? 366 : 365;
const start = new Date(year, 0, 1);
const dayOfYear = Math.floor((now - start) / 864e5) + 1;
const percent = ((dayOfYear / totalDays) * 100).toFixed(2);

container.innerHTML = `
  <div style="background:white; border-radius:10px; padding:20px; max-width:600px; margin:0 auto">
    <h1 style="color:#2c3e50">年度进度: ${percent}%</h1>
    <div style="background:#eee; height:20px; border-radius:10px; margin:20px 0">
      <div style="background:linear-gradient(90deg,#43cea2,#185a9d); width:${percent}%; height:100%; border-radius:10px"></div>
    </div>
    <div>今天是 ${year}年${now.getMonth()+1}月${now.getDate()}日</div>
  </div>
`;
</script>
