const questions = [
  {
    question: "Your bestie is crying over something dumb. You...",
    options: [
      { text: "Send them 47 relatable memes.", type: "Meme Archivist" },
      { text: "Drop everything and call them.", type: "Therapist" },
      { text: "Bring snacks and a blanket.", type: "Snack Parent" },
      { text: "Accidentally make it about you.", type: "Main Character" },
      { text: "React '😭' and reply 4 hours later.", type: "Flaker" }
    ]
  },
  {
    question: "It’s group hangout time. You’re the one who...",
    options: [
      { text: "Plans everything and brings food.", type: "Snack Parent" },
      { text: "Agrees but never shows up.", type: "Flaker" },
      { text: "Brings surprise drama and chaos.", type: "Agent of Chaos" },
      { text: "Captures aesthetic pics for everyone’s stories.", type: "Main Character" },
      { text: "Makes a playlist and emotional pep talk.", type: "Therapist" }
    ]
  },
  {
    question: "How do you show love?",
    options: [
      { text: "Memes. Always memes.", type: "Meme Archivist" },
      { text: "Random deep convos at 2AM.", type: "Therapist" },
      { text: "Acts of service & snacks.", type: "Snack Parent" },
      { text: "Emotional detachment with heart emojis.", type: "Flaker" },
      { text: "Over-the-top main character energy.", type: "Main Character" }
    ]
  },
  {
    question: "Group chat is dry. What do you do?",
    options: [
      { text: "Drop a cursed meme.", type: "Meme Archivist" },
      { text: "Type 'GUYS I HAVE TEA'", type: "Agent of Chaos" },
      { text: "'Y’all wanna hangout this weekend?'", type: "Snack Parent" },
      { text: "'is everyone mad at me or am i projecting again'", type: "Therapist" },
      { text: "See the messages. Say nothing.", type: "Flaker" }
    ]
  },
  {
    question: "Someone says 'you’re such a good friend.' You:",
    options: [
      { text: "Cry.", type: "Therapist" },
      { text: "Blame astrology.", type: "Main Character" },
      { text: "'stop or i’ll send a TikTok of a frog in a hat.'", type: "Meme Archivist" },
      { text: "Say 'thanks' and disappear.", type: "Flaker" },
      { text: "'Want samosas?'", type: "Snack Parent" }
    ]
  },
  {
    question: "Your energy in any friendship dynamic is:",
    options: [
      { text: "Protective mom.", type: "Snack Parent" },
      { text: "Therapist unpaid intern.", type: "Therapist" },
      { text: "Meme pipeline.", type: "Meme Archivist" },
      { text: "Chaos goblin.", type: "Agent of Chaos" },
      { text: "MIA with love.", type: "Flaker" }
    ]
  }
];

const results = {
  "Therapist": {
    title: "You're the Therapist ✨",
    description: "You’re emotionally intelligent, always ready to listen, and probably a little emotionally tired. Everyone comes to you with their mess — but you handle it like a pro (with a hint of burnout).",
    image: "images/therapist.png"
  },
  "Agent of Chaos": {
    title: "You're the Agent of Chaos 💥",
    description: "You bring the drama, the fun, the 'did-they-just-say-that?!' energy. You're unpredictable and unforgettable. Maybe tone it down? Or don’t. We love the chaos.",
    image: "images/chaos.png"
  },
  "Meme Archivist": {
    title: "You're the Meme Archivist 😂",
    description: "Memes are your love language. You’ve got folders of TikToks, screenshots, and unhinged GIFs ready to go. You communicate exclusively in Gen Z hieroglyphics.",
    image: "images/meme.png"
  },
  "Flaker": {
    title: "You're the Flaker 💤",
    description: "You love your friends deeply… from a distance. Social battery is low, your love is high, and you'll probably reply to that text tomorrow. Or next week.",
    image: "images/flaker.png"
  },
  "Main Character": {
    title: "You're the Main Character 🎬",
    description: "You carry the plot. You show up with outfits, energy, and emotional arcs. You’re inspiring, iconic, and possibly exhausting — but in the best way.",
    image: "images/main.png"
  },
  "Snack Parent": {
    title: "You're the Snack Parent 🍱",
    description: "You show love with action — food, rides, tissues, vibes. You're the glue of your group. A+ friend. Would hug again.",
    image: "images/snack.png"
  }
};

let currentQuestion = 0;
let scores = {};

function startQuiz() {
  document.getElementById("start-screen").classList.add("hidden");
  document.getElementById("quiz-screen").classList.remove("hidden");
  scores = {};
  currentQuestion = 0;
  showQuestion();
}

function showQuestion() {
  const q = questions[currentQuestion];
  document.getElementById("question-text").innerText = q.question;
  const answerBox = document.getElementById("answer-buttons");
  answerBox.innerHTML = "";
  q.options.forEach((opt) => {
    const btn = document.createElement("button");
    btn.innerText = opt.text;
    btn.onclick = () => selectAnswer(opt.type);
    answerBox.appendChild(btn);
  });
}

function selectAnswer(type) {
  scores[type] = (scores[type] || 0) + 1;
  currentQuestion++;
  if (currentQuestion < questions.length) {
    showQuestion();
  } else {
    showResult();
  }
}

function showResult() {
  document.getElementById("quiz-screen").classList.add("hidden");
  document.getElementById("result-screen").classList.remove("hidden");

  const topType = Object.keys(scores).reduce((a, b) => scores[a] > scores[b] ? a : b);
  const result = results[topType];
  
  document.getElementById("result-title").innerText = result.title;
  document.getElementById("result-description").innerText = result.description;
  const image = document.getElementById("result-image");
  if (result.image) {
    image.src = result.image;
    image.classList.remove("hidden");
  } else {
    image.classList.add("hidden");
  }
}

function restartQuiz() {
  document.getElementById("result-screen").classList.add("hidden");
  document.getElementById("start-screen").classList.remove("hidden");
}
