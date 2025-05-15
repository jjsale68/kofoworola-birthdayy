// Fade-in animations
document.addEventListener('DOMContentLoaded', () => {
    const elements = document.querySelectorAll('.fade-in');
    elements.forEach((el, index) => {
        setTimeout(() => {
            el.style.animationDelay = `${index * 0.2}s`;
        }, 0);
    });
});

// Memory Jar
function showMemoryNote() {
    const notes = [
        'Happy Birthday, Kofoworola! E.K Fashion Fusion’s taking over! ????',
        'Your dancing and singing make June 5 the hottest party! ??',
        'Ziba Beach awaits, my love—shine like Burna Boy at Chunz! ??'
    ];
    const note = notes[Math.floor(Math.random() * notes.length)];
    const noteElement = document.getElementById('memory-note');
    noteElement.textContent = note;
    noteElement.style.display = 'block';
}

// Guestbook Form (stores messages locally)
document.getElementById('guestbook-form')?.addEventListener('submit', (e) => {
    e.preventDefault();
    const message = e.target.querySelector('textarea').value;
    const messagesDiv = document.getElementById('guestbook-messages');
    const p = document.createElement('p');
    p.textContent = message;
    messagesDiv.appendChild(p);
    e.target.reset();
    localStorage.setItem('guestbook', messagesDiv.innerHTML);
});

// Load guestbook messages
if (document.getElementById('guestbook-messages')) {
    document.getElementById('guestbook-messages').innerHTML = localStorage.getItem('guestbook') || '';
}

// Countdown Timer (June 5, 2025)
const countdownDate = new Date('2025-06-05T19:00:00').getTime();
const countdownElement = document.getElementById('countdown');
if (countdownElement) {
    const countdown = setInterval(() => {
        const now = new Date().getTime();
        const distance = countdownDate - now;
        const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
        const seconds = Math.floor((distance % (1000 * 60)) / 1000);
        countdownElement.textContent = `Ziba Beach Bash in ${hours}h ${minutes}m ${seconds}s! ??`;
        if (distance < 0) {
            clearInterval(countdown);
            countdownElement.textContent = 'Happy Birthday, Kofoworola! Party Time at Ziba! ??';
        }
    }, 1000);
};

// Confetti Animation (CSS Canvas)
document.addEventListener('DOMContentLoaded', () => {
    const canvas = document.createElement('canvas');
    canvas.style.position = 'fixed';
    canvas.style.top = '0';
    canvas.style.left = '0';
    canvas.style.width = '100%';
    canvas.style.height = '100%';
    canvas.style.pointerEvents = 'none';
    canvas.style.zIndex = '5';
    document.body.appendChild(canvas);
    const ctx = canvas.getContext('2d');
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

    const confetti = [];
    for (let i = 0; i < 150; i++) {
        confetti.push({
            x: Math.random() * canvas.width,
            y: Math.random() * canvas.height - canvas.height,
            r: Math.random() * 6 + 2,
            d: Math.random() * 100,
            color: ['#FFD700', '#FF69B4', '#40E0D0'][Math.floor(Math.random() * 3)],
            tilt: Math.random() * 20 - 10,
            speed: Math.random() * 3 + 1
        });
    }

    function drawConfetti() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        confetti.forEach((p, i) => {
            p.y += p.speed;
            p.tilt += 0.05;
            if (p.y > canvas.height) p.y = -10;
            ctx.beginPath();
            ctx.rect(p.x, p.y, p.r, p.r);
            ctx.fillStyle = p.color;
            ctx.fill();
            ctx.rotate((p.tilt * Math.PI) / 180);
        });
        requestAnimationFrame(drawConfetti);
    }
    drawConfetti();
});
