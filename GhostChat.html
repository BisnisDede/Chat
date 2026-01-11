import React, { useState, useEffect, useRef } from 'react';
import { 
  Send, 
  Shield, 
  Clock, 
  Lock, 
  Trash2, 
  AlertTriangle, 
  User, 
  Zap,
  Globe,
  Moon,
  Sun,
  PlusCircle,
  ChevronRight,
  Info,
  ChevronDown,
  X,
  Sparkles
} from 'lucide-react';

const PACKAGES = [
  { id: 1, time: 1, label: { en: '1 Hour Stay', id: '1 Jam Kunjungan', es: '1 Hora', fr: '1 Heure', ja: '1 時間' }, price: '10.000' },
  { id: 2, time: 2, label: { en: '2 Hours Stay', id: '2 Jam Kunjungan', es: '2 Horas', fr: '2 Heures', ja: '2 時間' }, price: '20.000' },
  { id: 3, time: 3, label: { en: '3 Hours Stay', id: '3 Jam Kunjungan', es: '3 Horas', fr: '3 Heures', ja: '3 時間' }, price: '30.000' },
  { id: 4, time: 4, label: { en: '4 Hours Stay', id: '4 Jam Kunjungan', es: '4 Horas', fr: '4 Heures', ja: '4 時間' }, price: '40.000' },
  { id: 5, time: 5, label: { en: '5 Hours Stay', id: '5 Jam Kunjungan', es: '5 Horas', fr: '5 Heures', ja: '5 時間' }, price: '50.000' },
  { id: 24, time: 24, label: { en: '24 Hours Stay', id: '24 Jam Kunjungan', es: '24 Horas', fr: '24 Heures', ja: '24 時間' }, price: '100.000' },
];

const LANGUAGES = [
  { code: 'en', name: 'English', flag: '🇺🇸' },
  { code: 'id', name: 'Indonesia', flag: '🇮🇩' },
  { code: 'es', name: 'Español', flag: '🇪🇸' },
  { code: 'fr', name: 'Français', flag: '🇫🇷' },
  { code: 'ja', name: '日本語', flag: '🇯🇵' },
];

const TRANSLATIONS = {
  en: {
    heroTitle: "Niskala",
    heroSubtitle: "Pure Presence. Thoughtful Dialogue.",
    heroDesc: "A sanctuary for deep reflection and meaningful exchange. Experience a space that values your focus without distraction.",
    startButton: "Enter Space",
    extendSession: "Extend Stay",
    timeRemaining: "Presence Remaining",
    identity: "Visitor",
    warning: "This space is transient. Like a breath, the dialogue exists only while you are here, dissolving naturally as time passes.",
    placeholder: "Write your thoughts...",
    sessionEnded: "The moment has passed. Extend to stay longer.",
    stopSession: "Close Space",
    noStorage: "Transient",
    anonymous: "Anonymous Soul",
    legal: "Mindful Space",
    choosePlan: "Select your duration of presence",
    addTime: "Deepen Connection",
    safetyNote: "Niskala is a sanctuary of respect. We foster positive and constructive dialogues."
  },
  id: {
    heroTitle: "Niskala",
    heroSubtitle: "Kehadiran Murni. Dialog Bermakna.",
    heroDesc: "Tempat perlindungan untuk refleksi mendalam dan pertukaran pikiran. Rasakan ruang yang menghargai fokus Anda tanpa gangguan.",
    startButton: "Masuk Ruang",
    extendSession: "Tambah Durasi",
    timeRemaining: "Sisa Waktu",
    identity: "Pengunjung",
    warning: "Ruang ini bersifat sementara. Seperti nafas, dialog hanya ada selama Anda di sini, melarut secara alami seiring waktu.",
    placeholder: "Tuliskan pikiran Anda...",
    sessionEnded: "Momen telah berlalu. Tambah durasi untuk tinggal lebih lama.",
    stopSession: "Tutup Ruang",
    noStorage: "Fana",
    anonymous: "Jiwa Anonim",
    legal: "Ruang Tenang",
    choosePlan: "Pilih durasi kehadiran Anda",
    addTime: "Perdalam Koneksi",
    safetyNote: "Niskala adalah tempat perlindungan yang penuh hormat. Kami memupuk dialog positif dan konstruktif."
  }
};

const SYSTEM_PROMPT = `
Role: Niskala Guide. 
Tone: Calm, wise, professional, and neutral.
CORE VALUES:
1. Positivity: Always guide the user towards constructive thoughts.
2. Safety: Firmly but politely decline illegal requests, SARA, or malicious provocations.
3. Privacy: Do not ask for or repeat personal information.
Approach: If a user asks something harmful or tries to frame others, respond: "My purpose is to maintain this as a constructive and safe space for reflection. Let's discuss something that adds value or clarity instead."
`;

const App = () => {
  const [lang, setLang] = useState('en');
  const [theme, setTheme] = useState('dark');
  const [sessionActive, setSessionActive] = useState(false);
  const [remainingTime, setRemainingTime] = useState(0);
  const [messages, setMessages] = useState([]);
  const [input, setInput] = useState('');
  const [isLoading, setIsLoading] = useState(false);
  const [showPackages, setShowPackages] = useState(true);
  const [showExtendModal, setShowExtendModal] = useState(false);
  const [isLangOpen, setIsLangOpen] = useState(false);
  const [userId] = useState(() => `spirit-${Math.floor(Math.random() * 9000) + 1000}`);
  
  const scrollRef = useRef(null);
  const langRef = useRef(null);
  
  // UNTUK PENGGUNA NON-TEKNIS: 
  // Masukkan API Key Anda di sini jika hanya untuk testing sendiri.
  // Untuk publik, gunakan Environment Variable (Langkah 3 di atas).
  const apiKey = ""; 

  const t = TRANSLATIONS[lang] || TRANSLATIONS.en;

  useEffect(() => {
    const handleClickOutside = (event) => {
      if (langRef.current && !langRef.current.contains(event.target)) {
        setIsLangOpen(false);
      }
    };
    document.addEventListener('mousedown', handleClickOutside);
    return () => document.removeEventListener('mousedown', handleClickOutside);
  }, []);

  useEffect(() => {
    let interval;
    if (sessionActive && remainingTime > 0) {
      interval = setInterval(() => {
        setRemainingTime((prev) => {
          if (prev <= 1) {
            setSessionActive(false);
            return 0;
          }
          return prev - 1;
        });
      }, 1000);
    }
    return () => clearInterval(interval);
  }, [sessionActive, remainingTime]);

  useEffect(() => {
    if (scrollRef.current) {
      scrollRef.current.scrollTop = scrollRef.current.scrollHeight;
    }
  }, [messages, isLoading]);

  const formatTime = (seconds) => {
    const h = Math.floor(seconds / 3600);
    const m = Math.floor((seconds % 3600) / 60);
    const s = seconds % 60;
    return `${h.toString().padStart(2, '0')}:${m.toString().padStart(2, '0')}:${s.toString().padStart(2, '0')}`;
  };

  const startOrExtendSession = (hours) => {
    setRemainingTime(prev => prev + (hours * 3600));
    setSessionActive(true);
    setShowPackages(false);
    setShowExtendModal(false);
    if (messages.length === 0) {
      const welcomeMsgs = {
        en: "Welcome to Niskala. What is on your mind today?",
        id: "Selamat datang di Niskala. Apa yang sedang Anda pikirkan hari ini?"
      };
      setMessages([{ role: 'assistant', content: welcomeMsgs[lang] || welcomeMsgs.en }]);
    }
  };

  const handleSend = async () => {
    if (!input.trim() || !sessionActive || isLoading) return;

    const userMsg = input.trim();
    setInput('');
    setMessages(prev => [...prev, { role: 'user', content: userMsg }]);
    setIsLoading(true);

    try {
      // MENGHUBUNGKAN KE OPENAI API
      const response = await fetch("https://api.openai.com/v1/chat/completions", {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
          "Authorization": `Bearer ${apiKey}` // Pastikan API Key terisi
        },
        body: JSON.stringify({
          model: "gpt-4o-mini", // Model OpenAI yang cepat dan murah
          messages: [
            { role: "system", content: SYSTEM_PROMPT },
            ...messages.slice(-6).map(m => ({
              role: m.role === 'user' ? 'user' : 'assistant',
              content: m.content
            })),
            { role: "user", content: userMsg }
          ],
          temperature: 0.7
        })
      });

      const data = await response.json();
      
      if (data.error) {
        throw new Error(data.error.message);
      }

      const aiResponse = data.choices[0].message.content;
      setMessages(prev => [...prev, { role: 'assistant', content: aiResponse }]);
    } catch (error) {
      console.error("OpenAI Error:", error);
      setMessages(prev => [...prev, { role: 'assistant', content: "Maaf, koneksi ke pikiran semesta sedang terganggu. Pastikan API Key sudah terisi dan saldo OpenAI Anda mencukupi." }]);
    } finally {
      setIsLoading(false);
    }
  };

  const currentLang = LANGUAGES.find(l => l.code === lang);

  const PackageList = ({ onSelect, title }) => (
    <div className="space-y-6 animate-in fade-in zoom-in duration-500">
      <h2 className="text-xl font-light text-center opacity-70 tracking-widest uppercase">{title}</h2>
      <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
        {PACKAGES.map((pkg) => (
          <button
            key={pkg.id}
            onClick={() => onSelect(pkg.time)}
            className={`group flex items-center justify-between p-6 rounded-[2.5rem] border transition-all duration-300 ${
              theme === 'dark' 
                ? 'bg-slate-900 border-slate-800 hover:border-indigo-500/30 hover:bg-slate-800/50' 
                : 'bg-white border-slate-100 hover:border-indigo-300 hover:shadow-lg'
            }`}
          >
            <div className="flex flex-col items-start">
              <span className="text-[9px] opacity-40 uppercase tracking-[0.3em] font-bold">{(pkg.label[lang] || pkg.label.en)}</span>
              <span className="text-xl font-medium mt-1 tracking-tight">Rp {pkg.price}</span>
            </div>
            <div className="w-10 h-10 rounded-full bg-indigo-500/5 group-hover:bg-indigo-500 group-hover:text-white transition-all flex items-center justify-center text-indigo-400">
              <PlusCircle className="w-5 h-5" />
            </div>
          </button>
        ))}
      </div>
      <p className="text-[9px] text-center opacity-30 uppercase tracking-[0.2em] max-w-xs mx-auto leading-relaxed">
        {t.safetyNote}
      </p>
    </div>
  );

  return (
    <div className={`flex h-screen transition-colors duration-1000 ${
      theme === 'dark' ? 'bg-[#0a0a0c] text-slate-300' : 'bg-[#f8f9fa] text-slate-800'
    }`}>
      {/* Top Controls */}
      <div className="fixed top-6 right-6 z-50 flex gap-4 items-center">
        <div className="relative" ref={langRef}>
          <button 
            onClick={() => setIsLangOpen(!isLangOpen)}
            className={`flex items-center gap-3 px-4 py-2 rounded-2xl border text-xs font-bold uppercase tracking-widest transition-all ${
              theme === 'dark' ? 'bg-slate-900 border-slate-800' : 'bg-white border-slate-200'
            }`}
          >
            <span>{currentLang?.flag}</span>
            <span>{currentLang?.code}</span>
            <ChevronDown className={`w-3 h-3 opacity-40 transition-transform ${isLangOpen ? 'rotate-180' : ''}`} />
          </button>
          {isLangOpen && (
            <div className={`absolute right-0 mt-3 w-48 rounded-[1.5rem] border shadow-2xl overflow-hidden animate-in fade-in slide-in-from-top-2 duration-300 z-[100] ${
              theme === 'dark' ? 'bg-slate-900 border-slate-800' : 'bg-white border-slate-200'
            }`}>
              {LANGUAGES.map((l) => (
                <button
                  key={l.code}
                  onClick={() => { setLang(l.code); setIsLangOpen(false); }}
                  className={`flex items-center w-full gap-4 px-5 py-4 text-xs font-bold uppercase tracking-widest transition-all ${
                    lang === l.code ? 'bg-indigo-600 text-white' : 'hover:bg-indigo-500/10'
                  }`}
                >
                  <span>{l.flag}</span>
                  <span>{l.name}</span>
                </button>
              ))}
            </div>
          )}
        </div>
        <button 
          onClick={() => setTheme(theme === 'dark' ? 'light' : 'dark')}
          className={`p-3 rounded-2xl border transition-all ${
            theme === 'dark' ? 'bg-slate-900 border-slate-800' : 'bg-white border-slate-200 shadow-sm'
          }`}
        >
          {theme === 'dark' ? <Sun className="w-5 h-5 text-amber-300/60" /> : <Moon className="w-5 h-5 text-indigo-500/60" />}
        </button>
      </div>

      {/* Landing */}
      {showPackages && (
        <div className="fixed inset-0 z-40 flex flex-col items-center justify-center p-6 bg-inherit">
          <div className="max-w-2xl w-full text-center space-y-16">
            <div className="space-y-6">
              <div className="flex justify-center mb-4">
                <div className="p-3 bg-indigo-500/5 rounded-full border border-indigo-500/10">
                  <Sparkles className="w-6 h-6 text-indigo-400" />
                </div>
              </div>
              <h1 className="text-7xl font-light tracking-[0.2em] uppercase text-transparent bg-clip-text bg-gradient-to-b from-indigo-400 to-indigo-700">
                {t.heroTitle}
              </h1>
              <p className="text-lg font-light opacity-50 tracking-[0.4em] uppercase">{t.heroSubtitle}</p>
              <p className="max-w-md mx-auto opacity-40 leading-relaxed text-xs font-medium italic">{t.heroDesc}</p>
            </div>
            <PackageList title={t.choosePlan} onSelect={startOrExtendSession} />
          </div>
        </div>
      )}

      {/* Main Chat Area */}
      {!showPackages && (
        <div className="flex w-full">
          {/* Subtle Sidebar */}
          <div className={`hidden md:flex w-80 flex-col border-r transition-all duration-700 ${
            theme === 'dark' ? 'bg-black/20 border-slate-900' : 'bg-white border-slate-100 shadow-xl'
          }`}>
            <div className="p-10 border-b border-inherit">
              <h2 className="text-2xl font-light tracking-[0.2em] uppercase text-indigo-500">Niskala</h2>
            </div>
            
            <div className="flex-1 p-8 space-y-10">
              <div className="space-y-4">
                <label className="text-[10px] font-bold opacity-30 uppercase tracking-[0.3em]">{t.timeRemaining}</label>
                <div className={`p-6 rounded-[2rem] border transition-all ${
                  theme === 'dark' ? 'bg-slate-900/50 border-slate-800' : 'bg-slate-50 border-slate-100'
                }`}>
                  <div className="text-3xl font-mono font-light tracking-widest text-indigo-400 text-center">
                    {formatTime(remainingTime)}
                  </div>
                  <button 
                    onClick={() => setShowExtendModal(true)}
                    className="mt-6 flex items-center justify-center w-full py-4 gap-2 bg-indigo-600/10 text-indigo-400 border border-indigo-500/20 rounded-[1.2rem] text-[10px] font-bold uppercase tracking-widest hover:bg-indigo-600 hover:text-white transition-all active:scale-95"
                  >
                    <PlusCircle className="w-4 h-4" /> {t.extendSession}
                  </button>
                </div>
              </div>

              <div className="space-y-3">
                <label className="text-[10px] font-bold opacity-30 uppercase tracking-[0.3em]">{t.identity}</label>
                <div className="flex items-center gap-4 px-2 opacity-60">
                  <User className="w-4 h-4" />
                  <span className="text-xs font-mono tracking-tighter">{userId}</span>
                </div>
              </div>

              <div className={`p-6 rounded-[1.5rem] border flex gap-4 ${
                theme === 'dark' ? 'bg-indigo-500/5 border-indigo-500/10' : 'bg-slate-50 border-slate-100'
              }`}>
                <Info className="w-4 h-4 text-indigo-400 shrink-0" />
                <p className="text-[10px] leading-relaxed opacity-40 italic">{t.warning}</p>
              </div>
            </div>

            <div className="p-8">
              <button 
                onClick={() => window.location.reload()}
                className="flex items-center justify-center w-full p-4 gap-3 opacity-20 hover:opacity-100 hover:text-red-500 transition-all text-[9px] font-bold uppercase tracking-[0.2em]"
              >
                <Trash2 className="w-3 h-3" /> {t.stopSession}
              </button>
            </div>
          </div>

          {/* Chat Container */}
          <div className="flex-1 flex flex-col relative">
            <div ref={scrollRef} className="flex-1 overflow-y-auto p-6 md:p-16 space-y-12 scroll-smooth">
              {messages.map((msg, idx) => (
                <div key={idx} className={`flex ${msg.role === 'user' ? 'justify-end' : 'justify-start'} animate-in slide-in-from-bottom-2 duration-500`}>
                  <div className={`max-w-[85%] md:max-w-[55%] p-6 md:p-7 rounded-[2rem] leading-relaxed ${
                    msg.role === 'user' 
                      ? 'bg-indigo-600 text-white rounded-tr-none shadow-xl shadow-indigo-600/10' 
                      : `${theme === 'dark' ? 'bg-slate-900 border-slate-800' : 'bg-white border-slate-200 shadow-sm'} rounded-tl-none border`
                  }`}>
                    <p className="text-sm md:text-base font-light">{msg.content}</p>
                  </div>
                </div>
              ))}
              {isLoading && (
                <div className="flex justify-start">
                  <div className="p-4 flex gap-2 opacity-30">
                    <div className="w-1.5 h-1.5 bg-indigo-500 rounded-full animate-bounce" />
                    <div className="w-1.5 h-1.5 bg-indigo-500 rounded-full animate-bounce [animation-delay:0.2s]" />
                    <div className="w-1.5 h-1.5 bg-indigo-500 rounded-full animate-bounce [animation-delay:0.4s]" />
                  </div>
                </div>
              )}
            </div>

            <div className="p-6 md:p-16 pt-0">
              <div className="max-w-3xl mx-auto relative">
                <textarea
                  rows="1"
                  disabled={!sessionActive}
                  value={input}
                  onChange={(e) => setInput(e.target.value)}
                  onKeyDown={(e) => { if (e.key === 'Enter' && !e.shiftKey) { e.preventDefault(); handleSend(); }}}
                  placeholder={sessionActive ? t.placeholder : t.sessionEnded}
                  className={`w-full border-2 transition-all rounded-[2rem] py-5 pl-7 pr-20 text-sm md:text-base outline-none disabled:opacity-30 ${
                    theme === 'dark' 
                      ? 'bg-slate-900/50 border-slate-800 focus:border-indigo-600/50' 
                      : 'bg-white border-slate-100 focus:border-indigo-400/50'
                  }`}
                />
                <button
                  onClick={handleSend}
                  disabled={!sessionActive || !input.trim() || isLoading}
                  className="absolute right-3.5 bottom-3.5 p-3.5 bg-indigo-600 hover:bg-indigo-500 text-white rounded-2xl transition-all shadow-lg shadow-indigo-600/20 active:scale-90"
                >
                  <Send className="w-5 h-5" />
                </button>
              </div>
              <div className="flex justify-center gap-10 mt-8 opacity-10 text-[8px] font-bold uppercase tracking-[0.5em]">
                <span>{t.noStorage}</span>
                <span>{t.anonymous}</span>
                <span>{t.legal}</span>
              </div>
            </div>
          </div>
        </div>
      )}

      {/* Extend Modal */}
      {showExtendModal && (
        <div className="fixed inset-0 z-[110] flex items-center justify-center p-6 bg-black/80 backdrop-blur-xl animate-in fade-in duration-300">
          <div className={`max-w-xl w-full p-10 rounded-[3rem] relative shadow-2xl ${theme === 'dark' ? 'bg-slate-950 border border-slate-900' : 'bg-white'}`}>
            <button onClick={() => setShowExtendModal(false)} className="absolute top-8 right-8 p-2 opacity-30 hover:opacity-100"><X className="w-6 h-6" /></button>
            <PackageList title={t.addTime} onSelect={startOrExtendSession} />
          </div>
        </div>
      )}
    </div>
  );
};

export default App;