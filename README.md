# dante-portfolio 
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { PlayIcon, MailIcon } from "lucide-react";
import { motion } from "framer-motion";

export default function DantePortfolio() {
  return (
    <div className="p-4 md:p-10 space-y-16">
      {/* Hero Section */}
      <div className="relative h-[80vh] flex flex-col justify-center items-center text-center bg-black text-white">
        <img
          src="/image.png"
          alt="Hero"
          className="absolute inset-0 w-full h-full object-cover opacity-30"
        />
        <div className="relative z-10 space-y-4">
          <h1 className="text-4xl md:text-6xl font-bold">
            Fueling Sports. Creating Moments.
          </h1>
          <p className="text-lg md:text-2xl">
            Sports Marketing | Editing | Fan Experience Architect
          </p>
          <div className="space-x-4">
            <Button size="lg">Watch My Work</Button>
            <Button variant="outline" size="lg">Resume</Button>
          </div>
        </div>
      </div>

      {/* Featured Projects */}
      <section className="space-y-6">
        <h2 className="text-3xl font-bold text-center">Featured Projects</h2>
        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          {[1, 2, 3, 4, 5, 6].map((id) => (
            <Card key={id} className="hover:scale-105 transition">
              <CardContent className="p-0">
                <div className="relative">
                  <img
                    src={`/project${id}.jpg`}
                    alt={`Project ${id}`}
                    className="w-full h-48 object-cover"
                  />
                  <Button className="absolute bottom-2 right-2" size="sm">
                    <PlayIcon className="w-4 h-4 mr-1" /> Watch
                  </Button>
                </div>
                <div className="p-4">
                  <h3 className="font-semibold">Project Title {id}</h3>
                  <p className="text-sm text-muted-foreground">
                    Description of what made this project special.
                  </p>
                </div>
              </CardContent>
            </Card>
          ))}
        </div>
      </section>

      {/* YouTube Highlight Carousel */}
      <section className="space-y-6">
        <h2 className="text-3xl font-bold text-center">Highlight Reel</h2>
        <div className="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
          {["abcd1", "abcd2", "abcd3"].map((videoId) => (
            <div key={videoId} className="aspect-video">
              <iframe
                className="w-full h-full rounded-xl"
                src={`https://www.youtube.com/embed/${videoId}`}
                title="YouTube video player"
                frameBorder="0"
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                allowFullScreen
              ></iframe>
            </div>
          ))}
        </div>
      </section>

      {/* Strengths Section */}
      <section className="space-y-6">
        <h2 className="text-3xl font-bold text-center">What I Bring to the Field</h2>
        <div className="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4">
          {[
            { icon: "🎤", label: "Crowd Engagement" },
            { icon: "🎬", label: "Hype Editing" },
            { icon: "📣", label: "Fan-First Storytelling" },
            { icon: "🧩", label: "Creative Strategy" },
            { icon: "🏟️", label: "Event Design" },
            { icon: "🎯", label: "Sports Marketing" },
          ].map(({ icon, label }, i) => (
            <Card key={i} className="text-center p-6">
              <div className="text-4xl mb-2">{icon}</div>
              <p className="font-semibold text-lg">{label}</p>
            </Card>
          ))}
        </div>
      </section>

      {/* About Section */}
      <section className="text-center max-w-2xl mx-auto space-y-4">
        <h2 className="text-3xl font-bold">About Me</h2>
        <p>
          I'm Dante – a passionate creator who thrives on the electric energy of sports. Whether it's designing halftime shows, cutting hype reels, or hyping up a crowd, I make sure fans feel part of something bigger.
        </p>
      </section>

      {/* Resume & Contact */}
      <section className="text-center space-y-4">
        <Button className="text-lg">Download Resume</Button>
        <p className="text-muted-foreground">Or get in touch directly:</p>
        <Button variant="outline">
          <MailIcon className="mr-2 w-4 h-4" /> Email Me
        </Button>
      </section>
    </div>
  );
}
