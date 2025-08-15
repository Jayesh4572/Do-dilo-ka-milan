# Do-dilo-ka-milan
Do dilo ka milan ek asi website hai jo relationship ke bare me aapko batati hai
import { useState } from "react";
import { motion } from "framer-motion";
import { Menu, X, Heart, Sparkles, Shield, Mail, Phone, MapPin, ArrowRight } from "lucide-react";

export default function DoDilKaMilan() {
  const [open, setOpen] = useState(false);

  const nav = [
    { label: "Home", href: "#home" },
    { label: "Inspiration", href: "#inspiration" },
    { label: "About", href: "#about" },
    { label: "Contact", href: "#contact" },
  ];

  return (
    <div className="min-h-screen bg-gradient-to-br from-pink-50 to-white text-gray-900">
      {/* Navbar */}
      <header className="sticky top-0 z-50 backdrop-blur supports-[backdrop-filter]:bg-white/70 bg-white/60 border-b">
        <div className="mx-auto max-w-6xl px-4">
          <div className="flex items-center justify-between h-16">
            <a href="#home" className="flex items-center gap-2 font-semibold text-xl">
              <span className="inline-flex h-9 w-9 items-center justify-center rounded-2xl bg-pink-600 text-white">❤️</span>
              <span>Do Dil Ka Milan</span>
            </a>
            <nav className="hidden md:flex items-center gap-8">
              {nav.map((n) => (
                <a key={n.href} href={n.href} className="text-sm font-medium hover:text-gray-900/80">
                  {n.label}
                </a>
              ))}
              <a href="#contact" className="inline-flex items-center gap-2 rounded-2xl px-4 py-2 text-sm font-semibold bg-pink-600 text-white shadow-sm hover:shadow md:active:scale-[.98]">
                Get Inspired <ArrowRight className="h-4 w-4" />
              </a>
            </nav>
            <button
              className="md:hidden inline-flex h-10 w-10 items-center justify-center rounded-xl border"
              onClick={() => setOpen((o) => !o)}
              aria-label="Toggle menu"
            >
              {open ? <X className="h-5 w-5" /> : <Menu className="h-5 w-5" />}
            </button>
          </div>
        </div>
        {open && (
          <div className="md:hidden border-t bg-white">
            <div className="mx-auto max-w-6xl px-4 py-3 flex flex-col gap-2">
              {nav.map((n) => (
                <a key={n.href} href={n.href} className="py-2" onClick={() => setOpen(false)}>
                  {n.label}
                </a>
              ))}
              <a href="#contact" className="mt-2 inline-flex items-center gap-2 rounded-xl px-3 py-2 text-sm font-semibold bg-pink-600 text-white w-max" onClick={() => setOpen(false)}>
                Get Inspired <ArrowRight className="h-4 w-4" />
              </a>
            </div>
          </div>
        )}
      </header>

      {/* Hero */}
      <section id="home" className="relative overflow-hidden">
        <div className="absolute inset-0 -z-10 bg-[radial-gradient(40%_60%_at_70%_0%,rgba(236,72,153,.15),transparent_60%)]" />
        <div className="mx-auto max-w-6xl px-4 py-20 md:py-28">
          <div className="grid md:grid-cols-2 gap-10 items-center">
            <motion.div
              initial={{ opacity: 0, y: 12 }}
              animate={{ opacity: 1, y: 0 }}
              transition={{ duration: 0.6 }}
              className="space-y-6"
            >
              <h1 className="text-4xl md:text-6xl font-extrabold tracking-tight leading-tight">
                Inspire hearts with <span className="bg-clip-text text-transparent bg-gradient-to-r from-pink-600 to-red-500">Do Dil Ka Milan</span>
              </h1>
              <p className="text-base md:text-lg text-gray-600">
                A motivational space where two hearts connect through positivity, hope, and inspiration.
              </p>
              <div className="flex flex-wrap gap-3 pt-2">
                <a href="#inspiration" className="inline-flex items-center gap-2 rounded-2xl px-5 py-3 text-sm font-semibold bg-pink-600 text-white shadow-sm hover:shadow">
                  Read Stories <Heart className="h-4 w-4" />
                </a>
                <a href="#contact" className="inline-flex items-center gap-2 rounded-2xl px-5 py-3 text-sm font-semibold border border-pink-600 text-pink-600">
                  Share Your Story <ArrowRight className="h-4 w-4" />
                </a>
              </div>
              <div className="flex items-center gap-6 text-sm text-gray-500 pt-2">
                <div className="flex items-center gap-2"><Shield className="h-4 w-4"/> Positive Vibes</div>
                <div className="flex items-center gap-2"><Sparkles className="h-4 w-4"/> Heartwarming Stories</div>
              </div>
            </motion.div>
            <motion.div
              initial={{ opacity: 0, y: 20 }}
              animate={{ opacity: 1, y: 0 }}
              transition={{ duration: 0.6, delay: 0.1 }}
              className="relative"
            >
              <div className="aspect-[4/3] w-full rounded-2xl border shadow-sm bg-white p-4 grid place-items-center">
                <div className="w-full h-full rounded-xl bg-gradient-to-br from-pink-100 to-pink-50 grid place-items-center">
                  <span className="text-pink-600">Your inspiring image here</span>
                </div>
              </div>
            </motion.div>
          </div>
        </div>
      </section>

      {/* Inspiration Section */}
      <section id="inspiration" className="py-20 border-t">
        <div className="mx-auto max-w-6xl px-4">
          <div className="max-w-2xl mb-12">
            <h2 className="text-3xl md:text-4xl font-bold">Stories that touch hearts</h2>
            <p className="text-gray-600 mt-3">Read motivational tales and positive journeys that bring smiles and courage.</p>
          </div>
          <div className="grid md:grid-cols-3 gap-6">
            {[
              { icon: <Heart className="h-6 w-6 text-pink-600" />, title: "Love & Support", desc: "Stories of unconditional love and trust." },
              { icon: <Sparkles className="h-6 w-6 text-pink-600" />, title: "Daily Motivation", desc: "Short reads to boost your mood." },
              { icon: <Shield className="h-6 w-6 text-pink-600" />, title: "Emotional Strength", desc: "Real journeys of overcoming hardships." },
            ].map((f) => (
              <div key={f.title} className="rounded-2xl border p-6 shadow-sm bg-white">
                <div className="inline-flex h-10 w-10 items-center justify-center rounded-xl border mb-4 bg-pink-50">{f.icon}</div>
                <h3 className="font-semibold text-lg">{f.title}</h3>
                <p className="text-gray-600 text-sm mt-1">{f.desc}</p>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* About */}
      <section id="about" className="py-20 border-t bg-pink-50">
        <div className="mx-auto max-w-6xl px-4">
          <div className="grid md:grid-cols-2 gap-10 items-center">
            <div>
              <h2 className="text-3xl md:text-4xl font-bold">About Do Dil Ka Milan</h2>
              <p className="text-gray-600 mt-4">
                This is a place where we celebrate human connection, kindness, and motivation. Share your stories, inspire others, and create a ripple of positivity.
              </p>
              <ul className="mt-6 space-y-2 text-gray-700 list-disc list-inside">
                <li>Uplifting stories from real people</li>
                <li>Motivational quotes and thoughts</li>
                <li>Community of positive thinkers</li>
              </ul>
            </div>
            <div className="aspect-[4/3] w-full rounded-2xl border shadow-sm bg-white p-4 grid place-items-center">
              <div className="w-full h-full rounded-xl bg-gradient-to-br from-pink-100 to-pink-50 grid place-items-center">
                <span className="text-pink-600">Add an inspiring group photo</span>
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Contact */}
      <section id="contact" className="py-20 border-t">
        <div className="mx-auto max-w-6xl px-4">
          <div className="max-w-2xl mb-10">
            <h2 className="text-3xl md:text-4xl font-bold">Share your story</h2>
            <p className="text-gray-600 mt-3">Got an inspiring journey? Send it to us and motivate others.</p>
          </div>
          <div className="grid md:grid-cols-3 gap-6">
            <div className="md:col-span-2 rounded-2xl border p-6 bg-white shadow-sm">
              <form onSubmit={(e) => e.preventDefault()} className="grid gap-4">
                <div className="grid md:grid-cols-2 gap-4">
                  <div>
                    <label className="text-sm font-medium">Name</label>
                    <input className="mt-1 w-full rounded-xl border px-3 py-2" placeholder="Your name" />
                  </div>
                  <div>
                    <label className="text-sm font-medium">Email</label>
                    <input type="email" className="mt-1 w-full rounded-xl border px-3 py-2" placeholder="you@example.com" />
                  </div>
                </div>
                <div>
                  <label className="text-sm font-medium">Your Story</label>
                  <textarea className="mt-1 w-full rounded-xl border px-3 py-2 min-h-[120px]" placeholder="Write your inspiring story here..." />
                </div>
                <button className="inline-flex items-center gap-2 rounded-2xl px-5 py-3 text-sm font-semibold bg-pink-600 text-white shadow-sm w-max">
                  Send Story <Mail className="h-4 w-4" />
                </button>
              </form>
            </div>
            <div className="rounded-2xl border p-6 bg-white shadow-sm space-y-4">
              <div className="flex items-start gap-3"><MapPin className="h-5 w-5 mt-0.5 text-pink-600"/> <div>Ahmedabad, India</div></div>
              <div className="flex items-start gap-3"><Phone className="h-5 w-5 mt-0.5 text-pink-600"/> <div>+91 90000 00000</div></div>
              <div className="flex items-start gap-3"><Mail className="h-5 w-5 mt-0.5 text-pink-600"/> <div>hello@dodilkamilan.com</div></div>
            </div>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="border-t bg-pink-50">
        <div className="mx-auto max-w-6xl px-4 py-10 flex flex-col md:flex-row items-center justify-between gap-4">
          <p className="text-sm text-gray-600">© {new Date().getFullYear()} Do Dil Ka Milan. All rights reserved.</p>
          <div className="flex items-center gap-4 text-sm">
            <a href="#" className="hover:underline">Privacy</a>
            <a href="#" className="hover:underline">Terms</a>
          </div>
        </div>
      </footer>
    </div>
  );
}
