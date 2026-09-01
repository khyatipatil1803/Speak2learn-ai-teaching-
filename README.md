javascript 
const startBtn = document.getElementById("startBtn");
const voiceText = document.getElementById("voiceText");
const topic = document.getElementById("topic");
const diagram = document.getElementById("diagram");

startBtn.addEventListener("click", function () {

    const teacherTopic = prompt(
        "👩‍🏫 Teacher काय शिकवत आहेत?\n\nउदा.:\nHuman Heart\nLens\nDigestive System"
    );

    if (!teacherTopic) {
        return;
    }

    voiceText.innerText =
        "👩‍🏫 Teacher: " + teacherTopic;

    const text = teacherTopic.toLowerCase();

    if (
        text.includes("heart") ||
        text.includes("हृदय")
    ) {

        topic.innerText = "❤️ HUMAN HEART";

        diagram.innerHTML = `
            <div>
                ❤️
                <h2>Human Heart</h2>
                <p>हृदय रक्त संपूर्ण शरीरात पंप करते.</p>
                <p>🔵 Deoxygenated Blood</p>
                <p>🔴 Oxygenated Blood</p>
            </div>
        `;

    }

    else if (
        text.includes("lens") ||
        text.includes("भिंग")
    ) {

        topic.innerText = "🔬 CONVEX LENS";

        diagram.innerHTML = `
            <div>
                🔵 → 🔍 → 🔵
                <h2>Convex Lens</h2>
                <p>Convex lens प्रकाशकिरणांना एका बिंदूकडे वळवते.</p>
            </div>
        `;

    }

    else if (
        text.includes("digestive") ||
        text.includes("पचन")
    ) {

        topic.innerText = "🧑‍🔬 DIGESTIVE SYSTEM";

        diagram.innerHTML = `
            <div>
                🧑‍🔬
                <h2>Digestive System</h2>
                <p>अन्नाचे पचन आणि पोषकद्रव्यांचे शोषण करणारी प्रणाली.</p>
                <p>👄 → 🫃 → 🧻</p>
            </div>
        `;

    }

    else {

        topic.innerText = "📚 " + teacherTopic;

        diagram.innerHTML = `
            <div>
                🤖
                <h2>Topic Detected</h2>
                <p>AI ने "${teacherTopic}" topic ओळखला.</p>
                <p>या topic साठी पुढे visualization जोडता येईल.</p>
            </div>
        `;
    }

});