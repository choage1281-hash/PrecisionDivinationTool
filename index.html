<!DOCTYPE html>
<html lang="zh-TW">
<head>
<meta charset="UTF-8">
<title>🔮 精準占卜工具 V1-10 (網頁版)</title>
<style>
    body { font-family: Arial, sans-serif; line-height: 1.6; padding: 20px; background-color: #f7f7f7; color: #333; }
    h1 { color: #6226d4; text-align: center; }
    .keywords { max-height: 200px; overflow-y: auto; background: #fff; padding: 10px; border: 1px solid #ccc; margin-bottom: 20px; }
    .question { margin-bottom: 10px; }
    .controls { margin-bottom: 15px; }
    .result { font-size: 1.4em; margin-top: 10px; font-weight: bold; }
    .history { max-height: 200px; overflow-y: auto; background: #fff; padding: 10px; border: 1px solid #ccc; margin-top: 15px; white-space: pre-wrap; }
    label { display: inline-block; margin-right: 10px; }
    .voice-controls { display: flex; flex-direction: row; align-items: center; gap: 10px; margin-top: 5px; flex-wrap: wrap; }
    .keyword-add { margin-top: 10px; }
    input[type="text"] { width: 60%; padding: 5px; margin-right: 5px; }
    input[type="range"] { vertical-align: middle; }
    button { padding: 8px 12px; background-color: #4CAF50; color: white; border: none; cursor: pointer; border-radius: 4px; }
    button:hover { background-color: #45a049; }
    @media (max-width: 600px) {
        input[type="text"] { width: 100%; margin-right: 0; margin-top: 5px; }
        .voice-controls { flex-direction: column; align-items: flex-start; }
    }
</style>
</head>
<body>
<h1>🔮 精準占卜工具 V1-10 (網頁版)</h1>

<div class="keywords">
  <p><strong>正向關鍵字：</strong><span id="goodKeywords"></span></p>
  <p><strong>負向關鍵字：</strong><span id="badKeywords"></span></p>
</div>

<div class="keyword-add">
  <label for="newGood">添加正向關鍵字：</label>
  <input type="text" id="newGood" placeholder="例如：幸福">
  <button onclick="addGoodKeyword()">添加</button>
</div>
<div class="keyword-add">
  <label for="newBad">添加負向關鍵字：</label>
  <input type="text" id="newBad" placeholder="例如：失敗">
  <button onclick="addBadKeyword()">添加</button>
</div>

<div class="question">
  <label for="questionInput">請輸入你的問題：</label>
  <input type="text" id="questionInput" placeholder="我今天會發財嗎？">
</div>

<div class="voice-controls">
  <label><input type="checkbox" id="voiceToggle" checked>啟用語音</label>
  <label for="speedRange">語音速度</label>
  <input type="range" id="speedRange" min="0.5" max="2" step="0.1" value="1">
  <label for="volumeRange">音量</label>
  <input type="range" id="volumeRange" min="0" max="1" step="0.1" value="0.8">
  <button onclick="askFortune()">🔮 問卜！</button>
</div>

<div id="result" class="result">占卜結果：</div>

<h3>📜 占卜歷史</h3>
<div id="history" class="history"></div>

<script>
    // 基本關鍵字列表（與 Python 腳本一致）
    const goodKeywords = [
        '升遷', '加薪', '成功', '戀愛', '求婚', '結婚', '合作', '突破', '改善', '中獎', '學習', '通過', '考上', '獲利', '賺錢',
        '旅遊', '投資', '復合', '創業', '展覽', '運動', '健康', '恢復', '順利', '發財', '買房', '搬家', '新開始', '交友',
        '和解', '晉升', '穩定', '收穫', '中標', '機會', '努力', '喜訊', '發展', '表現', '貴人', '明朗', '好轉', '和氣',
        '喜事', '利好', '好運', '旺運', '轉佳', '目標達成', '回報', '欣慰', '支持', '鼓勵', '順遂', '富貴', '幸福', '開朗',
        '陽光', '甜蜜', '溫暖', '和諧', '感恩', '收成', '充實', '團圓', '圓滿', '活力', '創造', '正能量', '信任', '機緣',
        '財運', '人氣', '理想', '美夢成真', '合作成功', '互助', '展望', '進展', '表揚', '掌聲', '長進', '旺盛', '福氣',
        '恩典', '成就感', '順心', '貴人相助', '善緣', '興旺', '提升', '升級', '豐收', '圓夢', '吉日', '合約', '迎接',
        '光明', '勝利', '肯定', '順風', '發跡', '發展順利', '綠燈', '進財', '簽約成功', '熱絡', '戀情升溫', '表現優異'
        // 可以自行擴充更多關鍵字
    ];

    const badKeywords = [
        '分手', '離婚', '吵架', '失敗', '病', '癌', '痛苦', '糾紛', '損失', '風險', '失業', '離職', '困難', '誤會', '遲到',
        '錯過', '壓力', '焦慮', '破財', '下滑', '問題', '阻礙', '疲勞', '倒閉', '拖延', '裁員', '疫情', '災難', '意外',
        '挫折', '卡關', '灰心', '混亂', '消極', '內耗', '絕望', '失戀', '欺騙', '背叛', '暴躁', '官司', '衰退', '遺憾',
        '危機', '破局', '下跌', '糟糕', '難熬', '拒絕', '鬱悶', '失衡', '中傷', '衝突', '危險', '悲觀', '疑惑', '失控',
        '崩潰', '淚水', '悲傷', '孤獨', '怨恨', '失望', '損害', '走下坡', '煩惱', '阻擋', '失血', '失利', '退步', '後悔',
        '冷淡', '煎熬', '破裂', '惡化', '不安', '封鎖', '黑暗', '潰散', '厄運', '封閉', '放棄', '焦頭爛額', '赤字', '折磨'
        // 可以自行擴充更多關鍵字
    ];

    const customGoodKeywords = [];
    const customBadKeywords = [];

    // 更新畫面上的關鍵字列表
    function updateKeywords() {
        const allGood = goodKeywords.concat(customGoodKeywords);
        const allBad = badKeywords.concat(customBadKeywords);
        document.getElementById('goodKeywords').textContent = allGood.join(', ');
        document.getElementById('badKeywords').textContent = allBad.join(', ');
    }

    // 新增正向關鍵字
    function addGoodKeyword() {
        const input = document.getElementById('newGood');
        const newKw = input.value.trim();
        if (newKw) {
            customGoodKeywords.push(newKw);
            updateKeywords();
            input.value = '';
        }
    }

    // 新增負向關鍵字
    function addBadKeyword() {
        const input = document.getElementById('newBad');
        const newKw = input.value.trim();
        if (newKw) {
            customBadKeywords.push(newKw);
            updateKeywords();
            input.value = '';
        }
    }

    // 根據問題預測運勢
    function predictFortune(question) {
        const lowerQ = question.toLowerCase();
        const allGood = goodKeywords.concat(customGoodKeywords);
        const allBad = badKeywords.concat(customBadKeywords);
        let goodHits = 0;
        let badHits = 0;
        allGood.forEach(kw => {
            if (lowerQ.includes(kw.toLowerCase())) {
                goodHits++;
            }
        });
        allBad.forEach(kw => {
            if (lowerQ.includes(kw.toLowerCase())) {
                badHits++;
            }
        });
        const total = goodHits + badHits;
        if (total === 0) {
            return '🤔 問題未命中任何關鍵字，請再具體一點';
        }
        const ratio = (goodHits - badHits) / total;
        // 正向評級
        if (ratio >= 0.9 && goodHits >= 4) {
            return '🟢 大吉';
        } else if (ratio >= 0.7 && goodHits >= 3) {
            return '🟢 吉';
        } else if (ratio >= 0.5 && goodHits >= 2) {
            return '🟡 中吉';
        } else if (ratio >= 0.3 && goodHits >= 2) {
            return '🟡 小吉';
        } else if (ratio >= 0.15 && goodHits >= 1) {
            return '🟡 半吉';
        } else if (ratio >= 0.05 && goodHits >= 1) {
            return '🟡 末吉';
        } else if (ratio > 0 && goodHits >= 1) {
            return '🟡 末小吉';
        }
        // 負向評級
        // 依負向程度分級（含「凶」分類）
        if (ratio <= -0.5 && badHits >= 3) {
            // 極度負面且命中較多關鍵字
            return '🔴 大凶';
        } else if (ratio <= -0.3 && badHits >= 2) {
            // 非常負面
            return '🔴 末凶';
        } else if (ratio <= -0.15 && badHits >= 2) {
            // 負面傾向
            return '🔸 半凶';
        } else if (ratio <= -0.05 && badHits >= 1) {
            // 略帶負面
            return '🔸 小凶';
        } else if (ratio < 0 && badHits >= 1) {
            // 略為不利，但未達小凶標準
            return '🟠 凶';
        }
        // 未能明顯歸類時
        return '⚖️ 情勢混合，需多方考量';
    }

    // 處理問卜按鈕
    function askFortune() {
        const question = document.getElementById('questionInput').value;
        if (!question.trim()) {
            document.getElementById('result').textContent = '占卜結果：請先輸入問題';
            return;
        }
        const result = predictFortune(question);
        document.getElementById('result').textContent = '占卜結果： ' + result;
        // 如果啟用語音且瀏覽器支援 speechSynthesis
        if (document.getElementById('voiceToggle').checked && 'speechSynthesis' in window) {
            // 移除表情符號以免語音朗讀時出現停頓
            const plainText = result.replace(/[🟢🟡🟠🔸🔴]/g, '');
            const utter = new SpeechSynthesisUtterance('占卜結果：' + plainText);
            utter.rate = parseFloat(document.getElementById('speedRange').value);
            utter.volume = parseFloat(document.getElementById('volumeRange').value);
            speechSynthesis.speak(utter);
        }
        // 將問題與結果加入歷史紀錄
        const historyDiv = document.getElementById('history');
        const entry = document.createElement('div');
        entry.textContent = '📝 問題：' + question + '\n🔮 結果：' + result + '\n';
        historyDiv.appendChild(entry);
        historyDiv.scrollTop = historyDiv.scrollHeight;
    }

    // 初始化關鍵字顯示
    updateKeywords();
</script>

</body>
</html>
