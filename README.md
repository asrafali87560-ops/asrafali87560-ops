## Hi there 👋```react
import React, { useState, useEffect } from 'react';

// --- ROBUST INLINE SVG ICONS (Guarantees zero dependency compile issues) ---
const IconUtensils = () => (
  <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2.5" strokeLinecap="round" strokeLinejoin="round">
    <path d="M3 2v7c0 1.1.9 2 2 2h4a2 2 0 0 0 2-2V2" />
    <path d="M7 2v20" />
    <path d="M21 15V2v0a5 5 0 0 0-5 5v6c0 1.1.9 2 2 2h3Zm0 0v7" />
  </svg>
);

const IconPhone = () => (
  <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round">
    <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z" />
  </svg>
);

const IconMapPin = () => (
  <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round">
    <path d="M20 10c0 6-8 12-8 12s-8-6-8-12a8 8 0 0 1 16 0Z" />
    <circle cx="12" cy="10" r="3" />
  </svg>
);

const IconStar = ({ fill = false }) => (
  <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill={fill ? "currentColor" : "none"} stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round">
    <polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2" />
  </svg>
);

const IconInstagram = () => (
  <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round">
    <rect width="20" height="20" x="2" y="2" rx="5" ry="5" />
    <path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z" />
    <line x1="17.5" x2="17.51" y1="6.5" y2="6.5" />
  </svg>
);

const IconFacebook = () => (
  <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round">
    <path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z" />
  </svg>
);

const IconArrowRight = () => (
  <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round">
    <path d="M5 12h14" />
    <path d="m12 5 7 7-7 7" />
  </svg>
);

const IconQuote = () => (
  <svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" viewBox="0 0 24 24" fill="currentColor" className="opacity-25">
    <path d="M3 21c3 0 7-1 7-8V5H3v8h4c0 3-2 5-4 5v3zm11 0c3 0 7-1 7-8V5h-7v8h4c0 3-2 5-4 5v3z" />
  </svg>
);

const IconMenu = () => (
  <svg xmlns="http://www.w3.org/2000/svg" width="30" height="30" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round">
    <line x1="4" x2="20" y1="12" y2="12" />
    <line x1="4" x2="20" y1="6" y2="6" />
    <line x1="4" x2="20" y1="18" y2="18" />
  </svg>
);

const IconX = () => (
  <svg xmlns="http://www.w3.org/2000/svg" width="30" height="30" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round">
    <line x1="18" x2="6" y1="6" y2="18" />
    <line x1="6" x2="18" y1="6" y2="18" />
  </svg>
);

export default function App() {
  const [isScrolled, setIsScrolled] = useState(false);
  const [mobileMenuOpen, setMobileMenuOpen] = useState(false);

  useEffect(() => {
    const handleScroll = () => {
      setIsScrolled(window.scrollY > 20);
    };
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  }, []);

  const scrollTo = (id) => {
    const element = document.getElementById(id);
    if (element) {
      element.scrollIntoView({ behavior: 'smooth' });
      setMobileMenuOpen(false);
    }
  };

  const navLinks = [
    { name: 'Home', id: 'home' },
    { name: 'Our Vibe', id: 'about' },
    { name: 'The Menu', id: 'menu' },
    { name: 'Testimonials', id: 'reviews' },
    { name: 'Contact', id: 'contact' },
  ];

  return (
    <div className="min-h-screen bg-[#1A0E0A] font-sans text-[#FFF8E7] scroll-smooth antialiased">
      
      {/* Navigation */}
      <nav
        className={`fixed w-full z-50 transition-all duration-300 ${
          isScrolled 
            ? 'bg-[#150A07] shadow-lg shadow-black/50 py-3 border-b border-[#3A241A]' 
            : 'bg-gradient-to-b from-black/80 to-transparent py-5'
        }`}
      >
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex justify-between items-center">
            
            {/* Logo */}
            <div 
              className="flex items-center space-x-3 cursor-pointer group"
              onClick={() => scrollTo('home')}
            >
              <div className="bg-[#D4AF37] p-2.5 rounded-sm text-[#1A0E0A] group-hover:bg-[#F3CE5E] transition-colors">
                <IconUtensils />
              </div>
              <div className="flex flex-col">
                <h1 className="text-2xl md:text-3xl font-black text-[#D4AF37] tracking-widest uppercase leading-none font-serif">
                  Food Verge
                </h1>
                <p className="text-[10px] md:text-xs font-bold text-[#FFF8E7]/70 tracking-[0.3em] uppercase mt-1">
                  Authentic • Premium
                </p>
              </div>
            </div>

            {/* Desktop Nav */}
            <div className="hidden md:flex items-center space-x-8">
              {navLinks.map((link) => (
                <button
                  key={link.id}
                  onClick={() => scrollTo(link.id)}
                  className="text-sm font-semibold text-[#FFF8E7]/80 hover:text-[#D4AF37] transition-colors uppercase tracking-wider"
                >
                  {link.name}
                </button>
              ))}
              <a 
                href="tel:07007424613" 
                className="flex items-center space-x-2 bg-[#D4AF37] text-[#1A0E0A] px-6 py-2.5 rounded-sm hover:bg-[#F3CE5E] transition-colors font-bold text-sm tracking-wide uppercase shadow-[0_0_15px_rgba(212,175,55,0.3)]"
              >
                <IconPhone />
                <span>Order Now</span>
              </a>
            </div>

            {/* Mobile Menu Button */}
            <div className="md:hidden flex items-center">
              <button
                onClick={() => setMobileMenuOpen(!mobileMenuOpen)}
                className="text-[#D4AF37] hover:text-[#F3CE5E] focus:outline-none"
              >
                {mobileMenuOpen ? <IconX /> : <IconMenu />}
              </button>
            </div>
          </div>
        </div>

        {/* Mobile Nav Menu */}
        {mobileMenuOpen && (
          <div className="md:hidden absolute top-full left-0 w-full bg-[#1A0E0A] shadow-2xl border-b border-[#3A241A]">
            <div className="px-4 pt-2 pb-6 space-y-1 flex flex-col">
              {navLinks.map((link) => (
                <button
                  key={link.id}
                  onClick={() => scrollTo(link.id)}
                  className="w-full text-left px-3 py-4 text-sm font-bold text-[#FFF8E7] border-b border-[#3A241A] hover:text-[#D4AF37] transition-colors uppercase tracking-widest"
                >
                  {link.name}
                </button>
              ))}
              <a 
                href="tel:07007424613" 
                className="w-full mt-6 flex items-center justify-center space-x-2 bg-[#D4AF37] text-[#1A0E0A] px-4 py-3.5 rounded-sm font-bold uppercase tracking-widest"
              >
                <IconPhone />
                <span>Call 070074 24613</span>
              </a>
            </div>
          </div>
        )}
      </nav>

      {/* Hero Section */}
      <section 
        id="home" 
        className="relative min-h-[90vh] flex items-center justify-center overflow-hidden pt-20"
      >
        <div className="absolute inset-0 z-0">
          <img 
            src="https://images.unsplash.com/photo-1606491956689-2ea866880c84?auto=format&fit=crop&w=1920&q=80" 
            alt="Premium Indian Food" 
            className="w-full h-full object-cover object-center"
          />
          <div className="absolute inset-0 bg-gradient-to-r from-[#1A0E0A] via-[#1A0E0A]/95 to-[#1A0E0A]/50"></div>
        </div>

        <div className="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 w-full">
          <div className="max-w-3xl">
            <div className="inline-flex items-center space-x-2 mb-6">
              <div className="h-[1px] w-12 bg-[#D4AF37]"></div>
              <span className="text-[#D4AF37] font-bold tracking-[0.2em] text-sm uppercase">
                Welcome to Food Verge
              </span>
            </div>
            
            <h2 className="text-5xl md:text-7xl font-black text-[#FFF8E7] leading-[1.1] mb-6 font-serif">
              The Finest <br />
              <span className="text-[#D4AF37] italic">Vada Pav & Chaap</span><br />
              in Delhi.
            </h2>
            
            <p className="text-lg md:text-xl text-[#FFF8E7]/70 mb-10 font-light leading-relaxed max-w-2xl border-l-2 border-[#D4AF37] pl-6">
              Immerse yourself in authentic South Indian flavors and the richest North Indian street food. Crafted with passion, served with elegance.
            </p>
            
            <div className="flex flex-col sm:flex-row space-y-4 sm:space-y-0 sm:space-x-6">
              <button 
                onClick={() => scrollTo('menu')}
                className="bg-[#D4AF37] text-[#1A0E0A] px-8 py-4 rounded-sm font-bold text-sm tracking-widest uppercase hover:bg-[#F3CE5E] transition-all flex items-center justify-center space-x-3 shadow-[0_0_20px_rgba(212,175,55,0.2)]"
              >
                <span>View The Menu</span>
                <IconArrowRight />
              </button>
              <a 
                href="tel:07007424613"
                className="bg-transparent border border-[#D4AF37] text-[#D4AF37] px-8 py-4 rounded-sm font-bold text-sm tracking-widest uppercase hover:bg-[#D4AF37] hover:text-[#1A0E0A] transition-all flex items-center justify-center space-x-3"
              >
                <IconPhone />
                <span>Reserve / Call</span>
              </a>
            </div>
          </div>
        </div>
      </section>

      {/* About Section */}
      <section id="about" className="py-24 md:py-32 bg-[#21120D] relative border-t border-[#3A241A]">
        <div className="absolute inset-0 opacity-[0.03] bg-[url('https://www.transparenttextures.com/patterns/cubes.png')]"></div>
        
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
          <div className="text-center max-w-3xl mx-auto mb-20">
            <span className="text-[#D4AF37] font-bold tracking-[0.2em] text-sm uppercase block mb-4">Our Philosophy</span>
            <h2 className="text-4xl md:text-5xl font-black text-[#FFF8E7] mb-6 font-serif">A Symphony of Spices</h2>
            <div className="w-16 h-1 bg-[#D4AF37] mx-auto mb-8"></div>
            <p className="text-lg text-[#FFF8E7]/70 leading-relaxed font-light">
              Nestled in the vibrant heart of Mayur Vihar, Food Verge elevates traditional street food into a gourmet experience. We pride ourselves on authentic recipes, meticulous preparation, and a warm, welcoming atmosphere.
            </p>
          </div>

          <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
            {/* Feature 1 */}
            <div className="bg-[#1A0E0A] p-10 border border-[#3A241A] group hover:border-[#D4AF37] transition-colors duration-500 rounded-sm">
              <div className="w-14 h-14 bg-[#2A1610] text-[#D4AF37] flex items-center justify-center mb-8 group-hover:scale-110 transition-transform duration-500">
                <IconStar fill={true} />
              </div>
              <h3 className="text-xl font-bold text-[#FFF8E7] mb-4 font-serif uppercase tracking-wide">Authentic Heritage</h3>
              <p className="text-[#FFF8E7]/60 font-light leading-relaxed">
                From perfectly spiced South Indian delicacies to rich, creamy North Indian Chaap, our flavors remain true to their ancestral roots.
              </p>
            </div>
            
            {/* Feature 2 */}
            <div className="bg-[#1A0E0A] p-10 border border-[#3A241A] group hover:border-[#D4AF37] transition-colors duration-500 rounded-sm">
              <div className="w-14 h-14 bg-[#2A1610] text-[#D4AF37] flex items-center justify-center mb-8 group-hover:scale-110 transition-transform duration-500">
                <IconUtensils />
              </div>
              <h3 className="text-xl font-bold text-[#FFF8E7] mb-4 font-serif uppercase tracking-wide">Exquisite Service</h3>
              <p className="text-[#FFF8E7]/60 font-light leading-relaxed">
                Our highly-trained staff is dedicated to providing an impeccable dining experience, ensuring every visit leaves you delighted.
              </p>
            </div>

            {/* Feature 3 */}
            <div className="bg-[#1A0E0A] p-10 border border-[#3A241A] group hover:border-[#D4AF37] transition-colors duration-500 rounded-sm">
              <div className="w-14 h-14 bg-[#2A1610] text-[#D4AF37] flex items-center justify-center mb-8 group-hover:scale-110 transition-transform duration-500">
                <IconMapPin />
              </div>
              <h3 className="text-xl font-bold text-[#FFF8E7] mb-4 font-serif uppercase tracking-wide">Prime Location</h3>
              <p className="text-[#FFF8E7]/60 font-light leading-relaxed">
                Situated perfectly by the Sai Mandir Market, we offer a luxurious escape right in the bustling heart of Delhi.
              </p>
            </div>
          </div>
        </div>
      </section>

      {/* Menu Section */}
      <section id="menu" className="py-24 md:py-32 bg-[#1A0E0A] relative border-t border-[#3A241A]">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="text-center max-w-3xl mx-auto mb-20">
            <span className="text-[#D4AF37] font-bold tracking-[0.2em] text-sm uppercase block mb-4">Culinary Excellence</span>
            <h2 className="text-4xl md:text-5xl font-black text-[#FFF8E7] mb-6 font-serif">Curated Menu</h2>
            <div className="w-16 h-1 bg-[#D4AF37] mx-auto mb-8"></div>
          </div>

          <div className="grid grid-cols-1 lg:grid-cols-2 gap-16 lg:gap-24">
            {/* Category 1 */}
            <div>
              <div className="flex items-center space-x-4 mb-10">
                <h3 className="text-2xl font-serif text-[#D4AF37] uppercase tracking-widest">Signatures & Street</h3>
                <div className="flex-1 h-[1px] bg-[#3A241A]"></div>
              </div>
              
              <div className="space-y-10">
                {/* Menu Item */}
                <div className="group flex flex-col sm:flex-row items-start sm:items-center space-y-4 sm:space-y-0 sm:space-x-6">
                  <div className="overflow-hidden border border-[#3A241A] shrink-0">
                    <img src="https://images.unsplash.com/photo-1606491956689-2ea866880c84?auto=format&fit=crop&w=200&q=80" alt="Vada Pav" className="w-24 h-24 sm:w-28 sm:h-28 object-cover group-hover:scale-110 transition-transform duration-700" />
                  </div>
                  <div className="flex-1 w-full">
                    <div className="flex justify-between items-baseline mb-2 border-b border-[#3A241A] pb-2 border-dashed">
                      <h4 className="text-lg font-bold text-[#FFF8E7] uppercase tracking-wide">Food Verge Special Vada Pav</h4>
                      <span className="text-[#D4AF37] font-serif text-xl ml-4">₹50</span>
                    </div>
                    <p className="text-sm text-[#FFF8E7]/60 font-light leading-relaxed">Our signature spiced potato dumpling, golden-fried, encased in a butter-toasted bun with artisan garlic chutney.</p>
                  </div>
                </div>
                
                {/* Menu Item */}
                <div className="group flex flex-col sm:flex-row items-start sm:items-center space-y-4 sm:space-y-0 sm:space-x-6">
                  <div className="overflow-hidden border border-[#3A241A] shrink-0">
                    <img src="https://images.unsplash.com/photo-1599487405270-8174382c2a04?auto=format&fit=crop&w=200&q=80" alt="Malai Chaap" className="w-24 h-24 sm:w-28 sm:h-28 object-cover group-hover:scale-110 transition-transform duration-700" />
                  </div>
                  <div className="flex-1 w-full">
                    <div className="flex justify-between items-baseline mb-2 border-b border-[#3A241A] pb-2 border-dashed">
                      <h4 className="text-lg font-bold text-[#FFF8E7] uppercase tracking-wide">Creamy Malai Chaap</h4>
                      <span className="text-[#D4AF37] font-serif text-xl ml-4">₹180</span>
                    </div>
                    <p className="text-sm text-[#FFF8E7]/60 font-light leading-relaxed">Premium soya chaap marinated overnight in rich cashew cream and yogurt, perfectly char-grilled.</p>
                  </div>
                </div>
              </div>
            </div>

            {/* Column 2 */}
            <div className="space-y-16">
              {/* Category 2 */}
              <div>
                <div className="flex items-center space-x-4 mb-10">
                  <h3 className="text-2xl font-serif text-[#D4AF37] uppercase tracking-widest">South Indian Classics</h3>
                  <div className="flex-1 h-[1px] bg-[#3A241A]"></div>
                </div>
                <div className="space-y-10">
                  {/* Menu Item */}
                  <div className="flex flex-col w-full">
                    <div className="flex justify-between items-baseline mb-2 border-b border-[#3A241A] pb-2 border-dashed">
                      <h4 className="text-lg font-bold text-[#FFF8E7] uppercase tracking-wide">Classic Masala Dosa</h4>
                      <span className="text-[#D4AF37] font-serif text-xl ml-4">₹120</span>
                    </div>
                    <p className="text-sm text-[#FFF8E7]/60 font-light leading-relaxed">Crispy, golden rice crepe filled with an aromatic spiced potato mash, accompanied by traditional sambar.</p>
                  </div>
                  {/* Menu Item */}
                  <div className="flex flex-col w-full">
                    <div className="flex justify-between items-baseline mb-2 border-b border-[#3A241A] pb-2 border-dashed">
                      <h4 className="text-lg font-bold text-[#FFF8E7] uppercase tracking-wide">Authentic Idli Sambar</h4>
                      <span className="text-[#D4AF37] font-serif text-xl ml-4">₹80</span>
                    </div>
                    <p className="text-sm text-[#FFF8E7]/60 font-light leading-relaxed">Delicately steamed, fluffy rice cakes submerged in our deeply flavorful, slow-cooked sambar.</p>
                  </div>
                </div>
              </div>

              {/* Category 3 */}
              <div>
                <div className="flex items-center space-x-4 mb-10">
                  <h3 className="text-2xl font-serif text-[#D4AF37] uppercase tracking-widest">Beverages</h3>
                  <div className="flex-1 h-[1px] bg-[#3A241A]"></div>
                </div>
                <div className="space-y-6">
   

<!--
**asrafali87560-ops/asrafali87560-ops** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
