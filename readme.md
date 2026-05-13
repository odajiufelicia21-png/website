import React, { useState } from 'react';
import { 
  Play, 
  BookOpen, 
  Music, 
  Star, 
  Zap, 
  Award, 
  Smartphone, 
  Globe, 
  Mic, 
  Disc, 
  Users, 
  Camera, 
  Heart,
  ChevronRight,
  CheckCircle2,
  ArrowRight,
  Layers,
  TrendingUp,
  Layout,
  Radio
} from 'lucide-react';

const App = () => {
  const [activeTab, setActiveTab] = useState('home');
  const [activeModule, setActiveModule] = useState(0);

  const modules = [
    {
      id: 1,
      title: "M1: Introducere în Simbioza Artistică",
      subtitle: "Creierul, Ritmul și Mișcarea",
      image: "https://images.unsplash.com/photo-1514525253361-bee8a18744ad?q=80&w=1964&auto=format&fit=crop",
      content: "Descoperă cum reacționează creierul la frecvențe și cum se transformă sunetul în impuls muscular. Explicația științifică a legăturii dintre sunet și mișcare.",
      exercises: ["Ascultare activă: Identificarea instrumentelor", "Coordonare 4/4 cu palmele", "Jurnal de expresie emoțională"],
      lessons: ["Ce este muzica?", "Evoluția dansului", "Neuroștiința ritmului", "Legătura sunet-corp"]
    },
    {
      id: 2,
      title: "M2: Arhitectura Muzicală",
      subtitle: "De la Notă la Emoție",
      image: "https://images.unsplash.com/photo-1507838153414-b4b713384a76?q=80&w=2070&auto=format&fit=crop",
      content: "Învață alfabetul muzical: note, game, acorduri, tempo și structuri compoziționale moderne. Diferența dintre genuri și BPM.",
      lessons: ["Note și Gamă", "BPM și Ritm", "Armonie și Emoție", "Structura unei piese Pop/EDM"]
    },
    {
      id: 3,
      title: "M3: Templul Mișcării",
      subtitle: "Postură, Echilibru și Control",
      image: "https://images.unsplash.com/photo-1508700115892-45ecd05ae2ad?q=80&w=2069&auto=format&fit=crop",
      content: "Pregătirea fizică a artistului. Tehnici de stretching, izolare corporală și prevenirea accidentărilor pentru o carieră lungă.",
      lessons: ["Postura Corectă", "Centre de Echilibru", "Mobilitate Articulară", "Izolări: Gât, Umeri, Șolduri"]
    },
    {
      id: 4,
      title: "M4: Enciclopedia Stilurilor",
      subtitle: "Genuri Muzicale & Dansuri Urbane",
      image: "https://images.unsplash.com/photo-1535525153412-5a42439a210d?q=80&w=2070&auto=format&fit=crop",
      content: "O incursiune în Hip-Hop, Contemporary, K-Pop, Salsa și Afrobeat. Istorie, ritm specific și artiști celebri.",
      details: [
        { name: "Hip-Hop", music: "Rap/Beats", dance: "Breaking/Popping", icon: <Disc className="w-4 h-4" /> },
        { name: "K-Pop", music: "Hybrid Pop", dance: "Choreographed Performance", icon: <Star className="w-4 h-4" /> },
        { name: "Contemporary", music: "Ambient/Experimental", dance: "Lyrical Flow", icon: <Heart className="w-4 h-4" /> }
      ]
    },
    {
      id: 5,
      title: "M5: Laboratorul de Producție",
      subtitle: "Crearea Primului Tău Beat",
      image: "https://images.unsplash.com/photo-1598488035139-bdbb2231ce04?q=80&w=2070&auto=format&fit=crop",
      content: "Introducere în DAW-uri: FL Studio, Ableton, Logic. Beat making, sample-uri, mixaj și efecte audio de bază.",
      lessons: ["Alegerea DAW-ului", "Sound Design & Sample-uri", "Mixajul Vocilor", "Efecte: Reverb, Delay, Distortion"]
    },
    {
      id: 6,
      title: "M6: Arta Coregrafică",
      subtitle: "Vizualizarea Muzicii",
      image: "https://images.unsplash.com/photo-1547153760-18fc86324498?q=80&w=1887&auto=format&fit=crop",
      content: "Cum să construiești o poveste prin mișcare. Sincronizare pe beat, tranziții fluide și energie scenică impunătoare.",
      lessons: ["Conceptul Coregrafic", "Tranziții Fluide", "Sincronizarea pe Beat", "Freestyle & Improvisation"]
    },
    {
      id: 7,
      title: "M7: Business & Branding",
      subtitle: "Industria Muzicală Modernă",
      image: "https://images.unsplash.com/photo-1559136555-9303baea8ebd?q=80&w=2070&auto=format&fit=crop",
      content: "Navigarea pe platformele Spotify, YouTube și Instagram. Cum devii un artist independent și cum îți lansezi muzica.",
      lessons: ["Distribuție Digitală", "Branding de Artist", "Monetizare & Drepturi de Autor", "Networking"]
    },
    {
      id: 8,
      title: "M8: Viralitate pe Social Media",
      subtitle: "Strategii TikTok & Instagram",
      image: "https://images.unsplash.com/photo-1611162617213-7d7a39e9b1d7?q=80&w=1974&auto=format&fit=crop",
      content: "Crearea de conținut care atrage atenția. Algoritmi, estetică vizuală și storytelling artistic pentru reels și shorts.",
      lessons: ["Algoritmul TikTok", "Estetică Visuală", "Strategii de Reels", "Comunitatea de Fani"]
    },
    {
      id: 9,
      title: "M9: Psihologia Scenică",
      subtitle: "Mentalitate de Învingător",
      image: "https://images.unsplash.com/photo-1516280440614-37939bbacd81?q=80&w=2070&auto=format&fit=crop",
      content: "Emoția ca instrument de lucru. Depășirea fricii de scenă, disciplina creativă și menținerea încrederii în viziunea ta.",
      lessons: ["Încrederea pe Scenă", "Depășirea Blocajelor", "Disciplina vs Motivație", "Emoția ca Instrument"]
    },
    {
      id: 10,
      title: "M10: Marea Lansare",
      subtitle: "De la Dormitor la Scenă",
      image: "https://images.unsplash.com/photo-1470225620780-dba8ba36b745?q=80&w=2070&auto=format&fit=crop",
      content: "Ghid complet de lansare a primei melodii și a primului videoclip. Plan de promovare și analiză a rezultatelor.",
      lessons: ["Planul de Lansare", "Producția Video", "Campania de PR", "Analiza Rezultatelor"]
    }
  ];

  const packages = [
    { name: "Explorer", price: "49€", features: ["Modulele 1-4", "Acces 6 luni", "Glosar Termeni"], color: "bg-gray-800" },
    { name: "Artist PRO", price: "129€", features: ["Toate cele 10 Module", "Plan de 30/90 zile", "Acces Comunitate", "Checklist-uri"], color: "bg-purple-900 border-2 border-purple-400 scale-105" },
    { name: "Elite Masterclass", price: "299€", features: ["Tot din PRO", "Feedback Personalizat", "1-on-1 Mentoring", "Certificat de Absolvire"], color: "bg-gray-900" }
  ];

  return (
    <div className="min-h-screen bg-[#0a0a0c] text-white font-sans selection:bg-purple-500 selection:text-white pb-20">
      {/* Navigation */}
      <nav className="fixed top-0 w-full z-50 bg-[#0a0a0c]/80 backdrop-blur-md border-b border-white/10 px-6 py-4 flex justify-between items-center">
        <div className="flex items-center gap-2 cursor-pointer" onClick={() => setActiveTab('home')}>
          <div className="w-10 h-10 bg-gradient-to-tr from-purple-600 to-cyan-400 rounded-lg flex items-center justify-center font-bold text-xl italic shadow-lg shadow-purple-500/20">B</div>
          <span className="text-xl font-black tracking-tighter uppercase hidden sm:inline">Beat & Flow <span className="text-purple-400 font-normal">Academy</span></span>
        </div>
        <div className="flex gap-4 md:gap-8 text-xs md:text-sm font-medium uppercase tracking-widest text-gray-400">
          <button onClick={() => setActiveTab('home')} className={`hover:text-purple-400 transition ${activeTab === 'home' ? 'text-white border-b-2 border-purple-500 pb-1' : ''}`}>Acasă</button>
          <button onClick={() => setActiveTab('curriculum')} className={`hover:text-purple-400 transition ${activeTab === 'curriculum' ? 'text-white border-b-2 border-purple-500 pb-1' : ''}`}>Curs</button>
          <button onClick={() => setActiveTab('pricing')} className={`hover:text-purple-400 transition ${activeTab === 'pricing' ? 'text-white border-b-2 border-purple-500 pb-1' : ''}`}>Preț</button>
        </div>
        <button className="bg-purple-600 hover:bg-purple-500 px-4 md:px-6 py-2 rounded-full text-xs md:text-sm font-bold transition transform hover:scale-105 active:scale-95 shadow-lg shadow-purple-500/20">
          Acces Premium
        </button>
      </nav>

      {/* Hero Section */}
      {activeTab === 'home' && (
        <>
          <section className="pt-32 pb-20 px-6 max-w-7xl mx-auto">
            <div className="grid md:grid-cols-2 gap-12 items-center">
              <div>
                <div className="inline-flex items-center gap-2 px-3 py-1 bg-white/5 border border-white/10 rounded-full text-xs font-bold text-purple-400 mb-6 uppercase tracking-widest">
                  <Zap className="w-3 h-3" /> Revoluția Artistică Digitală
                </div>
                <h1 className="text-5xl md:text-8xl font-black leading-none mb-6 italic tracking-tighter">
                  MUZICA <span className="text-transparent bg-clip-text bg-gradient-to-r from-purple-400 to-cyan-400">ESTE</span> MIȘCARE.
                </h1>
                <p className="text-xl text-gray-400 mb-8 max-w-lg leading-relaxed font-light">
                  Singura platformă care te învață să produci propriul sunet și să-l transformi în mișcare scenică. Devino un artist complet 360°.
                </p>
                <div className="flex flex-col sm:flex-row gap-4">
                  <button onClick={() => setActiveTab('curriculum')} className="flex items-center justify-center gap-2 bg-white text-black px-8 py-4 rounded-xl font-bold text-lg hover:bg-gray-200 transition">
                    Explorează Modulele <ArrowRight className="w-5 h-5" />
                  </button>
                </div>
              </div>
              <div className="relative group">
                <div className="absolute inset-0 bg-gradient-to-r from-purple-500/20 to-cyan-500/20 blur-3xl group-hover:from-purple-500/30 group-hover:to-cyan-500/30 transition"></div>
                <div className="relative aspect-[4/5] rounded-3xl overflow-hidden border border-white/10 shadow-2xl">
                  <img 
                    src="https://images.unsplash.com/photo-1547153760-18fc86324498?q=80&w=1887&auto=format&fit=crop" 
                    alt="Coregrafie modernă" 
                    className="w-full h-full object-cover grayscale brightness-75 group-hover:grayscale-0 group-hover:brightness-100 transition duration-1000 scale-105 group-hover:scale-100"
                  />
                  <div className="absolute inset-0 bg-gradient-to-t from-[#0a0a0c] via-transparent to-transparent opacity-60" />
                  <div className="absolute bottom-8 left-8 right-8">
                    <div className="bg-black/60 backdrop-blur-xl p-6 rounded-2xl border border-white/10">
                      <div className="flex items-center gap-4 mb-3">
                         <div className="w-2 h-2 bg-red-500 rounded-full animate-ping" />
                         <span className="text-[10px] font-bold uppercase tracking-widest text-gray-300">Sesiune Live Acum</span>
                      </div>
                      <p className="font-bold italic text-lg leading-tight uppercase">Masterclass: Tehnici de Freestyle & Beat-making</p>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </section>

          {/* Featured Images / Gallery - REDUCED TO 3 IMAGES */}
          <section className="px-6 max-w-7xl mx-auto py-20">
            <h2 className="text-sm font-bold uppercase tracking-[0.4em] text-center mb-12 text-gray-500">Vizualizarea Artei</h2>
            <div className="grid grid-cols-1 md:grid-cols-3 gap-6 h-[400px]">
              <div className="rounded-2xl overflow-hidden border border-white/10 relative group shadow-2xl">
                <img src="https://images.unsplash.com/photo-1516280440614-37939bbacd81?q=80&w=2070&auto=format&fit=crop" className="w-full h-full object-cover transition duration-500 group-hover:scale-110" alt="Concert" />
                <div className="absolute inset-0 bg-purple-600/20 opacity-0 group-hover:opacity-100 transition" />
                <div className="absolute bottom-4 left-4 font-black italic uppercase text-xs tracking-widest">Performance</div>
              </div>
              <div className="rounded-2xl overflow-hidden border border-white/10 relative group md:translate-y-8 shadow-2xl">
                <img src="https://images.unsplash.com/photo-1535525153412-5a42439a210d?q=80&w=2070&auto=format&fit=crop" className="w-full h-full object-cover transition duration-500 group-hover:scale-110" alt="Dansator" />
                <div className="absolute inset-0 bg-cyan-600/20 opacity-0 group-hover:opacity-100 transition" />
                <div className="absolute bottom-4 left-4 font-black italic uppercase text-xs tracking-widest">Movement</div>
              </div>
              <div className="rounded-2xl overflow-hidden border border-white/10 relative group shadow-2xl">
                <img src="https://images.unsplash.com/photo-1598488035139-bdbb2231ce04?q=80&w=2070&auto=format&fit=crop" className="w-full h-full object-cover transition duration-500 group-hover:scale-110" alt="Studio" />
                <div className="absolute inset-0 bg-purple-600/20 opacity-0 group-hover:opacity-100 transition" />
                <div className="absolute bottom-4 left-4 font-black italic uppercase text-xs tracking-widest">Production</div>
              </div>
            </div>
          </section>
        </>
      )}

      {/* Curriculum Section */}
      {activeTab === 'curriculum' && (
        <section className="pt-32 pb-20 px-6 max-w-7xl mx-auto">
          <div className="flex flex-col md:flex-row justify-between items-end mb-16 gap-6">
            <div>
              <h2 className="text-4xl md:text-6xl font-black italic mb-2 uppercase tracking-tighter">Plan de <span className="text-purple-400">Carieră</span></h2>
              <p className="text-gray-400 text-lg">10 pași spre măiestria artistică totală.</p>
            </div>
            <div className="flex gap-4 bg-white/5 p-2 rounded-2xl border border-white/10">
               <div className="px-4 py-2 bg-purple-600 rounded-xl font-bold text-xs uppercase tracking-widest">Studenți: 12.4k</div>
               <div className="px-4 py-2 border border-white/10 rounded-xl font-bold text-xs uppercase tracking-widest">Update: 2026</div>
            </div>
          </div>

          <div className="grid lg:grid-cols-12 gap-10">
            {/* Sidebar Navigation */}
            <div className="lg:col-span-4 space-y-3 h-[700px] overflow-y-auto pr-4 custom-scrollbar">
              {modules.map((m, idx) => (
                <button
                  key={m.id}
                  onClick={() => setActiveModule(idx)}
                  className={`w-full text-left p-6 rounded-2xl transition-all duration-300 border group ${activeModule === idx ? 'bg-gradient-to-r from-purple-600 to-purple-800 border-purple-400 shadow-xl shadow-purple-900/20' : 'bg-white/5 border-white/10 hover:bg-white/10 hover:border-white/20'}`}
                >
                  <div className="flex justify-between items-start mb-2">
                    <span className={`text-[10px] font-black uppercase tracking-[0.2em] ${activeModule === idx ? 'text-white/70' : 'text-purple-400'}`}>Modulul 0{m.id}</span>
                    {activeModule === idx && <Play className="w-3 h-3 fill-white" />}
                  </div>
                  <span className="text-lg font-black italic uppercase leading-none block group-hover:translate-x-1 transition-transform">{m.title.split(': ')[1]}</span>
                </button>
              ))}
            </div>

            {/* Content Display */}
            <div className="lg:col-span-8">
              <div className="bg-white/5 rounded-[2.5rem] border border-white/10 overflow-hidden shadow-2xl">
                {/* Header Image for Module */}
                <div className="h-64 w-full relative">
                  <img src={modules[activeModule].image} className="w-full h-full object-cover" alt="Modul Image" />
                  <div className="absolute inset-0 bg-gradient-to-t from-[#121214] via-black/20 to-transparent" />
                  <div className="absolute bottom-6 left-8">
                    <h3 className="text-3xl font-black italic uppercase tracking-tighter text-white drop-shadow-lg">{modules[activeModule].title}</h3>
                    <p className="text-purple-400 font-bold uppercase text-xs tracking-widest">{modules[activeModule].subtitle}</p>
                  </div>
                </div>

                <div className="p-8 md:p-12">
                  <div className="grid md:grid-cols-3 gap-12">
                    <div className="md:col-span-2">
                      <h4 className="text-xs font-bold text-gray-500 uppercase tracking-[0.3em] mb-6">Obiective de învățare</h4>
                      <p className="text-xl text-gray-300 leading-relaxed italic mb-10">"{modules[activeModule].content}"</p>
                      
                      <div className="grid sm:grid-cols-2 gap-8">
                        <div>
                          <h5 className="text-[10px] font-bold text-white uppercase tracking-widest mb-4 flex items-center gap-2">
                            <Layers className="w-3 h-3 text-cyan-400" /> Programa Detaliată
                          </h5>
                          <ul className="space-y-4">
                            {modules[activeModule].lessons.map((lesson, i) => (
                              <li key={i} className="flex items-center gap-3 text-sm text-gray-400">
                                <div className="w-1 h-1 bg-purple-500 rounded-full" />
                                {lesson}
                              </li>
                            ))}
                          </ul>
                        </div>
                        {modules[activeModule].exercises && (
                          <div className="bg-purple-900/10 p-6 rounded-2xl border border-purple-500/20">
                            <h5 className="text-[10px] font-bold text-purple-400 uppercase tracking-widest mb-4 flex items-center gap-2">
                              <Zap className="w-3 h-3" /> Workshop Practic
                            </h5>
                            <ul className="space-y-3">
                              {modules[activeModule].exercises.map((ex, i) => (
                                <li key={i} className="text-xs font-medium text-gray-300 italic border-l-2 border-purple-500/40 pl-3">
                                  {ex}
                                </li>
                              ))}
                            </ul>
                          </div>
                        )}
                      </div>
                    </div>

                    <div className="space-y-6">
                      <div className="bg-black/40 p-6 rounded-2xl border border-white/5">
                        <h4 className="text-[10px] font-bold uppercase text-gray-500 mb-4 tracking-widest">Resurse Modul</h4>
                        <div className="space-y-3">
                          <button className="w-full flex items-center gap-3 p-3 rounded-lg bg-white/5 hover:bg-white/10 transition text-xs font-bold uppercase tracking-widest">
                            <BookOpen className="w-4 h-4 text-purple-400" /> Ghid PDF
                          </button>
                          <button className="w-full flex items-center gap-3 p-3 rounded-lg bg-white/5 hover:bg-white/10 transition text-xs font-bold uppercase tracking-widest">
                            <Music className="w-4 h-4 text-cyan-400" /> Playlist
                          </button>
                          <button className="w-full flex items-center gap-3 p-3 rounded-lg bg-white/5 hover:bg-white/10 transition text-xs font-bold uppercase tracking-widest">
                            <Camera className="w-4 h-4 text-white" /> Live Replay
                          </button>
                        </div>
                      </div>
                      
                      <div className="p-6 bg-gradient-to-br from-purple-600/20 to-transparent rounded-2xl border border-purple-500/20">
                        <TrendingUp className="w-8 h-8 text-purple-400 mb-4" />
                        <p className="text-xs text-gray-400 font-medium">Acest modul îți va crește coordonarea cu <span className="text-white font-bold">40%</span> în prima săptămână de practică.</p>
                      </div>
                    </div>
                  </div>

                  <div className="mt-12 pt-10 border-t border-white/5 flex flex-col sm:row justify-between items-center gap-6">
                    <div className="flex items-center gap-4">
                      <div className="w-12 h-12 rounded-full border border-white/10 overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1539571696357-5a69c17a67c6?q=80&w=1887&auto=format&fit=crop" className="w-full h-full object-cover" alt="Expert" />
                      </div>
                      <div>
                        <span className="block text-xs font-bold uppercase tracking-widest text-purple-400">Expert Instructor</span>
                        <span className="text-sm font-black italic uppercase">Alex Voinea</span>
                      </div>
                    </div>
                    <button className="bg-white text-black px-10 py-4 rounded-xl font-black uppercase tracking-[0.2em] text-sm hover:bg-purple-500 hover:text-white transition transform active:scale-95 flex items-center gap-3 shadow-xl">
                      Începe Învățarea <Play className="w-4 h-4 fill-current" />
                    </button>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>
      )}

      {/* Pricing Section */}
      {activeTab === 'pricing' && (
        <section className="pt-32 pb-20 px-6 max-w-7xl mx-auto text-center">
          <h2 className="text-5xl md:text-7xl font-black italic mb-4 uppercase tracking-tighter">Investiția în <span className="text-purple-400">Arta</span> Ta</h2>
          <p className="text-gray-400 max-w-2xl mx-auto text-lg mb-16 font-light leading-relaxed">
            Pachete create pentru orice nivel de experiență. De la explorator curios la artist de scenă.
          </p>

          <div className="grid md:grid-cols-3 gap-8 items-center">
            {packages.map((pkg, i) => (
              <div key={i} className={`${pkg.color} p-10 rounded-[2.5rem] border border-white/10 flex flex-col items-center text-left relative overflow-hidden group hover:shadow-2xl hover:shadow-purple-500/20 transition-all duration-500`}>
                {i === 1 && (
                  <div className="absolute top-6 right-6 bg-cyan-400 text-black px-3 py-1 rounded-full text-[10px] font-black uppercase italic animate-pulse">
                    Cel Mai Popular
                  </div>
                )}
                <h3 className="text-2xl font-black italic uppercase mb-2">{pkg.name}</h3>
                <div className="text-5xl font-black mb-8 italic tracking-tighter">{pkg.price} <span className="text-sm font-normal text-gray-500 uppercase tracking-widest">/ total</span></div>
                
                <div className="w-full h-px bg-white/10 mb-8" />

                <ul className="space-y-4 mb-10 w-full">
                  {pkg.features.map((feat, j) => (
                    <li key={j} className="flex items-center gap-3 text-gray-300 text-sm font-medium">
                      <CheckCircle2 className="w-5 h-5 text-purple-400 shrink-0" />
                      {feat}
                    </li>
                  ))}
                </ul>

                <button className={`w-full py-5 rounded-2xl font-black uppercase tracking-[0.2em] text-xs transition-all ${i === 1 ? 'bg-white text-black hover:bg-purple-500 hover:text-white shadow-xl shadow-white/5' : 'bg-white/5 text-white hover:bg-white/10'}`}>
                  Cumpără Acum
                </button>
              </div>
            ))}
          </div>
        </section>
      )}

      {/* Stats Section */}
      <section className="bg-white/5 py-20 border-y border-white/10 px-6">
        <div className="max-w-7xl mx-auto grid grid-cols-2 md:grid-cols-4 gap-12 text-center">
          <div>
            <span className="block text-4xl md:text-5xl font-black italic text-purple-400 mb-2 uppercase tracking-tighter">150+</span>
            <span className="text-xs font-bold uppercase tracking-widest text-gray-500">Video Lecții</span>
          </div>
          <div>
            <span className="block text-4xl md:text-5xl font-black italic text-white mb-2 uppercase tracking-tighter">45GB</span>
            <span className="text-xs font-bold uppercase tracking-widest text-gray-500">Resurse Audio</span>
          </div>
          <div>
            <span className="block text-4xl md:text-5xl font-black italic text-cyan-400 mb-2 uppercase tracking-tighter">24/7</span>
            <span className="text-xs font-bold uppercase tracking-widest text-gray-500">Suport Comunitate</span>
          </div>
          <div>
            <span className="block text-4xl md:text-5xl font-black italic text-white mb-2 uppercase tracking-tighter">LIFETIME</span>
            <span className="text-xs font-bold uppercase tracking-widest text-gray-500">Acces Conținut</span>
          </div>
        </div>
      </section>

      {/* Footer - UPDATED YEAR TO 2026 */}
      <footer className="mt-20 border-t border-white/10 py-16 px-6 bg-black">
        <div className="max-w-7xl mx-auto">
          <div className="grid md:grid-cols-4 gap-12 mb-16">
            <div className="col-span-2">
               <div className="flex items-center gap-2 mb-6">
                <div className="w-10 h-10 bg-purple-600 rounded flex items-center justify-center font-bold italic shadow-lg shadow-purple-500/20">B</div>
                <span className="text-xl font-black italic uppercase tracking-tighter">Beat & Flow <span className="text-purple-400">Academy</span></span>
              </div>
              <p className="text-gray-500 max-w-sm leading-relaxed italic">Transformăm pasiunea în profesie. O metodologie unică ce unește sunetul cu mișcare corporală.</p>
            </div>
            <div>
              <h5 className="font-bold uppercase tracking-widest text-xs mb-6 text-white">Comunitate</h5>
              <ul className="space-y-4 text-sm text-gray-500 font-medium">
                <li className="hover:text-purple-400 cursor-pointer transition">Grup de Discord</li>
                <li className="hover:text-purple-400 cursor-pointer transition">Evenimente Live</li>
                <li className="hover:text-purple-400 cursor-pointer transition">Showcase-ul Elevilor</li>
              </ul>
            </div>
            <div>
              <h5 className="font-bold uppercase tracking-widest text-xs mb-6 text-white">Legal</h5>
              <ul className="space-y-4 text-sm text-gray-500 font-medium">
                <li className="hover:text-purple-400 cursor-pointer transition">Termeni și Condiții</li>
                <li className="hover:text-purple-400 cursor-pointer transition">Politică de Confidențialitate</li>
                <li className="hover:text-purple-400 cursor-pointer transition">Contact Media</li>
              </ul>
            </div>
          </div>
          <div className="pt-8 border-t border-white/5 flex flex-col md:flex-row justify-between items-center gap-8">
            <p className="text-gray-600 text-[10px] uppercase tracking-[0.3em] font-bold italic">© 2026 Beat & Flow Academy — Premium Arts Education</p>
            <div className="flex gap-8">
              <Smartphone className="w-5 h-5 text-gray-600 hover:text-white cursor-pointer transition-colors" />
              <Radio className="w-5 h-5 text-gray-600 hover:text-white cursor-pointer transition-colors" />
              <Layout className="w-5 h-5 text-gray-600 hover:text-white cursor-pointer transition-colors" />
            </div>
          </div>
        </div>
      </footer>

      <style jsx>{`
        .custom-scrollbar::-webkit-scrollbar {
          width: 5px;
        }
        .custom-scrollbar::-webkit-scrollbar-track {
          background: rgba(255, 255, 255, 0.02);
          border-radius: 10px;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb {
          background: rgba(168, 85, 247, 0.3);
          border-radius: 10px;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb:hover {
          background: rgba(168, 85, 247, 0.6);
        }
        
        @keyframes fade-in {
          from { opacity: 0; transform: translateY(10px); }
          to { opacity: 1; transform: translateY(0); }
        }
        
        .animate-fade-in {
          animation: fade-in 0.6s ease-out forwards;
        }
      `}</style>
    </div>
  );
};
export default App;
