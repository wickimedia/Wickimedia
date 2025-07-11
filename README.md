import { Button } from "@/components/ui/button";
import { Card, CardContent, CardDescription, CardHeader, CardTitle } from "@/components/ui/card";
import { Input } from "@/components/ui/input";
import { Badge } from "@/components/ui/badge";
import { Separator } from "@/components/ui/separator";
import { Avatar, AvatarFallback, AvatarImage } from "@/components/ui/avatar";
import Image from "next/image";

export default function Home() {
  return (
    <div className="min-h-screen bg-gradient-to-br from-slate-900 via-slate-800 to-slate-900">
      {/* Navigation */}
      <nav className="sticky top-0 z-50 bg-slate-900/80 backdrop-blur-sm border-b border-slate-700">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex justify-between items-center h-16">
            <div className="flex items-center">
              {/* Temporary logo placeholder - replace with actual logo */}
              <div className="w-10 h-10 bg-orange-600 rounded-full flex items-center justify-center mr-3">
                <span className="text-white font-bold text-lg">WM</span>
              </div>
              <h1 className="text-2xl font-bold text-white">Wickimedia</h1>
            </div>
            <div className="hidden md:block">
              <div className="ml-10 flex items-baseline space-x-4">
                <a href="#services" className="text-slate-300 hover:text-white px-3 py-2 rounded-md text-sm font-medium transition-colors">Services</a>
                <a href="#our-work" className="text-slate-300 hover:text-white px-3 py-2 rounded-md text-sm font-medium transition-colors">Our Work</a>
                <a href="#about" className="text-slate-300 hover:text-white px-3 py-2 rounded-md text-sm font-medium transition-colors">About</a>
                <a href="#portfolio" className="text-slate-300 hover:text-white px-3 py-2 rounded-md text-sm font-medium transition-colors">Portfolio</a>
                <a href="#contact" className="text-slate-300 hover:text-white px-3 py-2 rounded-md text-sm font-medium transition-colors">Contact</a>
              </div>
            </div>
            <Button className="bg-orange-600 hover:bg-orange-700 text-white">Get Started</Button>
          </div>
        </div>
      </nav>

      {/* Hero Section */}
      <section className="relative min-h-screen flex items-center justify-center px-4 sm:px-6 lg:px-8">
        <div className="max-w-4xl mx-auto text-center">
          <h1 className="text-5xl md:text-7xl font-bold text-white mb-6">
            Accelerate Your
            <span className="text-transparent bg-clip-text bg-gradient-to-r from-orange-400 to-orange-600"> Digital Growth</span>
          </h1>
          <p className="text-xl md:text-2xl text-slate-300 mb-8 max-w-3xl mx-auto">
            We help businesses dominate their markets through cutting-edge digital marketing strategies,
            data-driven campaigns, and measurable results that drive real ROI.
          </p>
          <div className="flex flex-col sm:flex-row gap-4 justify-center">
            <Button size="lg" className="bg-orange-600 hover:bg-orange-700 text-white text-lg px-8 py-4">
              Start Your Journey
            </Button>
            <Button size="lg" variant="outline" className="border-slate-400 text-slate-300 hover:bg-slate-800 text-lg px-8 py-4">
              View Our Work
            </Button>
          </div>
        </div>

        {/* Floating Cards */}
        <div className="absolute top-1/2 left-10 transform -translate-y-1/2 hidden lg:block">
          <Card className="w-48 bg-slate-800/50 border-slate-600 backdrop-blur-sm">
            <CardContent className="p-4">
              <div className="text-2xl font-bold text-orange-400">300%</div>
              <div className="text-slate-300 text-sm">Average ROI Increase</div>
            </CardContent>
          </Card>
        </div>

        <div className="absolute top-1/3 right-10 transform -translate-y-1/2 hidden lg:block">
          <Card className="w-48 bg-slate-800/50 border-slate-600 backdrop-blur-sm">
            <CardContent className="p-4">
              <div className="text-2xl font-bold text-orange-400">500+</div>
              <div className="text-slate-300 text-sm">Successful Campaigns</div>
            </CardContent>
          </Card>
        </div>
      </section>

      {/* Services Section */}
      <section id="services" className="py-20 px-4 sm:px-6 lg:px-8">
        <div className="max-w-7xl mx-auto">
          <div className="text-center mb-16">
            <h2 className="text-4xl md:text-5xl font-bold text-white mb-4">Our Services</h2>
            <p className="text-xl text-slate-300 max-w-3xl mx-auto">
              Comprehensive digital marketing solutions tailored to your business goals
            </p>
          </div>

          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            {[
              {
                title: "Search Engine Optimization",
                description: "Dominate search results with our proven SEO strategies that drive organic traffic and boost visibility.",
                icon: "🎯",
                features: ["Keyword Research", "Technical SEO", "Content Optimization", "Link Building"]
              },
              {
                title: "Pay-Per-Click Advertising",
                description: "Maximize ROI with targeted PPC campaigns across Google Ads, Facebook, and other platforms.",
                icon: "💰",
                features: ["Campaign Setup", "Ad Optimization", "Bid Management", "Conversion Tracking"]
              },
              {
                title: "Social Media Marketing",
                description: "Build brand awareness and engage your audience across all major social media platforms.",
                icon: "📱",
                features: ["Content Creation", "Community Management", "Influencer Partnerships", "Social Ads"]
              },
              {
                title: "Content Marketing",
                description: "Create compelling content that resonates with your audience and drives meaningful engagement.",
                icon: "✍️",
                features: ["Blog Writing", "Video Production", "Infographics", "Email Campaigns"]
              },
              {
                title: "Website Development",
                description: "Build fast, responsive websites optimized for conversions and user experience.",
                icon: "🌐",
                features: ["Custom Design", "Mobile Responsive", "Speed Optimization", "CRO"]
              },
              {
                title: "Analytics & Reporting",
                description: "Track performance with detailed analytics and actionable insights for continuous improvement.",
                icon: "📊",
                features: ["Google Analytics", "Custom Dashboards", "Performance Reports", "ROI Analysis"]
              }
            ].map((service, index) => (
              <Card key={index} className="bg-slate-800/50 border-slate-600 hover:bg-slate-700/50 transition-all duration-300">
                <CardHeader>
                  <div className="text-4xl mb-4">{service.icon}</div>
                  <CardTitle className="text-xl text-white">{service.title}</CardTitle>
                  <CardDescription className="text-slate-300">{service.description}</CardDescription>
                </CardHeader>
                <CardContent>
                  <div className="flex flex-wrap gap-2">
                    {service.features.map((feature, idx) => (
                      <Badge key={idx} variant="secondary" className="bg-orange-600/20 text-orange-300 border-orange-600/30">
                        {feature}
                      </Badge>
                    ))}
                  </div>
                </CardContent>
              </Card>
            ))}
          </div>
        </div>
      </section>

      {/* Our Work Video Section */}
      <section id="our-work" className="py-20 px-4 sm:px-6 lg:px-8 bg-slate-800/30">
        <div className="max-w-7xl mx-auto">
          <div className="text-center mb-16">
            <h2 className="text-4xl md:text-5xl font-bold text-white mb-4">Our Work in Action</h2>
            <p className="text-xl text-slate-300 max-w-3xl mx-auto">
              See how we transform businesses through powerful digital marketing campaigns
            </p>
          </div>

          <div className="grid grid-cols-1 lg:grid-cols-2 gap-8 mb-12">
            {/* Featured Video */}
            <div className="lg:col-span-2">
              <Card className="bg-slate-800/50 border-slate-600 overflow-hidden">
                <div className="relative aspect-video bg-slate-700 flex items-center justify-center">
                  <div className="text-center">
                    <div className="w-16 h-16 bg-orange-600 rounded-full flex items-center justify-center mx-auto mb-4">
                      <svg className="w-8 h-8 text-white" fill="currentColor" viewBox="0 0 24 24">
                        <path d="M8 5v14l11-7z"/>
                      </svg>
                    </div>
                    <h3 className="text-lg font-semibold text-white mb-2">Featured Campaign Video</h3>
                    <p className="text-slate-400">Upload your main showcase video here</p>
                    <p className="text-sm text-slate-500 mt-2">Recommended: MP4 format, max 50MB</p>
                  </div>
                </div>
                <CardContent className="p-6">
                  <h3 className="text-xl font-bold text-white mb-2">Complete Digital Transformation</h3>
                  <p className="text-slate-300 mb-4">
                    Watch how we helped TechStart Solutions achieve a 400% increase in leads through our comprehensive digital marketing strategy.
                  </p>
                  <div className="flex flex-wrap gap-2">
                    <Badge className="bg-orange-600/20 text-orange-300 border-orange-600/30">SEO</Badge>
                    <Badge className="bg-orange-600/20 text-orange-300 border-orange-600/30">PPC</Badge>
                    <Badge className="bg-orange-600/20 text-orange-300 border-orange-600/30">Content Marketing</Badge>
                  </div>
                </CardContent>
              </Card>
            </div>

            {/* Video Grid */}
            {[
              {
                title: "Social Media Campaign Success",
                description: "How we boosted Urban Fitness Co's social engagement by 300%",
                category: "Social Media",
                duration: "2:45"
              },
              {
                title: "SEO Strategy Deep Dive",
                description: "Behind-the-scenes look at our SEO process and results",
                category: "SEO",
                duration: "3:20"
              },
              {
                title: "PPC Campaign Optimization",
                description: "Real-time campaign management and optimization techniques",
                category: "PPC Advertising",
                duration: "4:15"
              },
              {
                title: "Client Success Story",
                description: "GreenLeaf Organics shares their journey with Wickimedia",
                category: "Testimonial",
                duration: "1:50"
              }
            ].map((video, index) => (
              <Card key={index} className="bg-slate-800/50 border-slate-600 hover:bg-slate-700/50 transition-all duration-300 group">
                <div className="relative aspect-video bg-slate-700 overflow-hidden">
                  <div className="absolute inset-0 flex items-center justify-center group-hover:bg-black/20 transition-colors">
                    <div className="text-center">
                      <div className="w-12 h-12 bg-orange-600 rounded-full flex items-center justify-center mx-auto mb-2 group-hover:scale-110 transition-transform">
                        <svg className="w-6 h-6 text-white" fill="currentColor" viewBox="0 0 24 24">
                          <path d="M8 5v14l11-7z"/>
                        </svg>
                      </div>
                      <p className="text-slate-400 text-sm">Upload Video {index + 1}</p>
                    </div>
                  </div>
                  <div className="absolute bottom-2 right-2 bg-black/70 text-white px-2 py-1 rounded text-xs">
                    {video.duration}
                  </div>
                  <div className="absolute top-2 left-2">
                    <Badge variant="secondary" className="bg-orange-600/80 text-white text-xs">
                      {video.category}
                    </Badge>
                  </div>
                </div>
                <CardContent className="p-4">
                  <h4 className="font-semibold text-white mb-2">{video.title}</h4>
                  <p className="text-slate-400 text-sm">{video.description}</p>
                </CardContent>
              </Card>
            ))}
          </div>

          {/* Call to Action */}
          <div className="text-center">
            <Card className="bg-gradient-to-r from-orange-600/20 to-orange-700/20 border-orange-600/30 max-w-2xl mx-auto">
              <CardContent className="p-8">
                <h3 className="text-2xl font-bold text-white mb-4">Ready to See Your Business Grow?</h3>
                <p className="text-slate-300 mb-6">
                  Let's create a success story video for your business next!
                </p>
                <Button className="bg-orange-600 hover:bg-orange-700 text-white">
                  Start Your Campaign
                </Button>
              </CardContent>
            </Card>
          </div>
        </div>
      </section>

      {/* About Section */}
      <section id="about" className="py-20 px-4 sm:px-6 lg:px-8">
        <div className="max-w-7xl mx-auto">
          <div className="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
            <div>
              <h2 className="text-4xl md:text-5xl font-bold text-white mb-6">Why Choose Wickimedia?</h2>
              <p className="text-lg text-slate-300 mb-6">
                With over a decade of experience in digital marketing, we've helped hundreds of businesses
                transform their online presence and achieve unprecedented growth.
              </p>
              <div className="space-y-4">
                {[
                  "Data-driven strategies backed by real analytics",
                  "Dedicated account managers for personalized service",
                  "Transparent reporting with measurable results",
                  "Cutting-edge tools and industry best practices",
                  "Proven track record across multiple industries"
                ].map((point, index) => (
                  <div key={index} className="flex items-center space-x-3">
                    <div className="w-2 h-2 bg-orange-400 rounded-full"></div>
                    <span className="text-slate-300">{point}</span>
                  </div>
                ))}
              </div>
            </div>
            <div className="grid grid-cols-2 gap-6">
              {[
                { number: "10+", label: "Years Experience" },
                { number: "500+", label: "Projects Completed" },
                { number: "98%", label: "Client Satisfaction" },
                { number: "300%", label: "Average ROI" }
              ].map((stat, index) => (
                <Card key={index} className="bg-slate-800/70 border-slate-600 text-center p-6">
                  <div className="text-3xl font-bold text-orange-400 mb-2">{stat.number}</div>
                  <div className="text-slate-300 text-sm">{stat.label}</div>
                </Card>
              ))}
            </div>
          </div>
        </div>
      </section>

      {/* Portfolio Section */}
      <section id="portfolio" className="py-20 px-4 sm:px-6 lg:px-8">
        <div className="max-w-7xl mx-auto">
          <div className="text-center mb-16">
            <h2 className="text-4xl md:text-5xl font-bold text-white mb-4">Success Stories</h2>
            <p className="text-xl text-slate-300 max-w-3xl mx-auto">
              Real results from real businesses that trusted us with their growth
            </p>
          </div>

          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            {[
              {
                company: "TechStart Solutions",
                industry: "Technology",
                results: "400% increase in leads",
                description: "Complete digital transformation including SEO, PPC, and content marketing strategy.",
                metrics: { traffic: "+250%", conversions: "+400%", roi: "650%" }
              },
              {
                company: "Urban Fitness Co",
                industry: "Health & Fitness",
                results: "300% revenue growth",
                description: "Social media marketing and targeted advertising campaign for fitness equipment.",
                metrics: { traffic: "+180%", conversions: "+300%", roi: "480%" }
              },
              {
                company: "GreenLeaf Organics",
                industry: "Food & Beverage",
                results: "500% online sales boost",
                description: "E-commerce optimization and multi-channel marketing approach for organic products.",
                metrics: { traffic: "+320%", conversions: "+500%", roi: "720%" }
              }
            ].map((project, index) => (
              <Card key={index} className="bg-slate-800/50 border-slate-600 hover:shadow-lg hover:shadow-orange-500/20 transition-all duration-300">
                <CardHeader>
                  <div className="flex items-center justify-between mb-2">
                    <CardTitle className="text-lg text-white">{project.company}</CardTitle>
                    <Badge variant="outline" className="border-orange-600/50 text-orange-300">
                      {project.industry}
                    </Badge>
                  </div>
                  <div className="text-2xl font-bold text-orange-400 mb-2">{project.results}</div>
                  <CardDescription className="text-slate-300">{project.description}</CardDescription>
                </CardHeader>
                <CardContent>
                  <div className="grid grid-cols-3 gap-4 text-center">
                    <div>
                      <div className="text-lg font-semibold text-white">{project.metrics.traffic}</div>
                      <div className="text-xs text-slate-400">Traffic</div>
                    </div>
                    <div>
                      <div className="text-lg font-semibold text-white">{project.metrics.conversions}</div>
                      <div className="text-xs text-slate-400">Conversions</div>
                    </div>
                    <div>
                      <div className="text-lg font-semibold text-white">{project.metrics.roi}</div>
                      <div className="text-xs text-slate-400">ROI</div>
                    </div>
                  </div>
                </CardContent>
              </Card>
            ))}
          </div>
        </div>
      </section>

      {/* Testimonials Section */}
      <section className="py-20 px-4 sm:px-6 lg:px-8 bg-slate-800/30">
        <div className="max-w-7xl mx-auto">
          <div className="text-center mb-16">
            <h2 className="text-4xl md:text-5xl font-bold text-white mb-4">What Our Clients Say</h2>
            <p className="text-xl text-slate-300">Hear from businesses that have transformed their growth with us</p>
          </div>

          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            {[
              {
                quote: "Wickimedia transformed our online presence completely. Our leads increased by 400% in just 6 months!",
                author: "Sarah Johnson",
                position: "CEO, TechStart Solutions",
                avatar: "SJ"
              },
              {
                quote: "The ROI we've seen from their campaigns is incredible. They truly understand digital marketing.",
                author: "Mike Chen",
                position: "Marketing Director, Urban Fitness Co",
                avatar: "MC"
              },
              {
                quote: "Professional, results-driven, and always available. The best marketing agency we've worked with.",
                author: "Emma Rodriguez",
                position: "Founder, GreenLeaf Organics",
                avatar: "ER"
              }
            ].map((testimonial, index) => (
              <Card key={index} className="bg-slate-800/70 border-slate-600">
                <CardContent className="p-6">
                  <div className="text-slate-300 mb-4 italic">"{testimonial.quote}"</div>
                  <div className="flex items-center space-x-3">
                    <Avatar>
                      <AvatarFallback className="bg-orange-600 text-white">{testimonial.avatar}</AvatarFallback>
                    </Avatar>
                    <div>
                      <div className="text-white font-semibold">{testimonial.author}</div>
                      <div className="text-slate-400 text-sm">{testimonial.position}</div>
                    </div>
                  </div>
                </CardContent>
              </Card>
            ))}
          </div>
        </div>
      </section>

      {/* Contact Section */}
      <section id="contact" className="py-20 px-4 sm:px-6 lg:px-8">
        <div className="max-w-4xl mx-auto">
          <div className="text-center mb-16">
            <h2 className="text-4xl md:text-5xl font-bold text-white mb-4">Ready to Grow?</h2>
            <p className="text-xl text-slate-300">
              Let's discuss how we can accelerate your business growth with digital marketing
            </p>
          </div>

          <Card className="bg-slate-800/50 border-slate-600">
            <CardContent className="p-8">
              <form className="space-y-6">
                <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
                  <div>
                    <label className="block text-sm font-medium text-slate-300 mb-2">Name</label>
                    <Input placeholder="Your name" className="bg-slate-700/50 border-slate-600 text-white" />
                  </div>
                  <div>
                    <label className="block text-sm font-medium text-slate-300 mb-2">Email</label>
                    <Input type="email" placeholder="your@email.com" className="bg-slate-700/50 border-slate-600 text-white" />
                  </div>
                </div>
                <div>
                  <label className="block text-sm font-medium text-slate-300 mb-2">Company</label>
                  <Input placeholder="Your company name" className="bg-slate-700/50 border-slate-600 text-white" />
                </div>
                <div>
                  <label className="block text-sm font-medium text-slate-300 mb-2">Message</label>
                  <textarea
                    placeholder="Tell us about your project..."
                    rows={4}
                    className="w-full px-3 py-2 bg-slate-700/50 border border-slate-600 rounded-md text-white placeholder-slate-400 focus:outline-none focus:ring-2 focus:ring-orange-500"
                  />
                </div>
                <Button className="w-full bg-orange-600 hover:bg-orange-700 text-white text-lg py-3">
                  Send Message
                </Button>
              </form>
            </CardContent>
          </Card>
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-slate-900 border-t border-slate-700 py-12 px-4 sm:px-6 lg:px-8">
        <div className="max-w-7xl mx-auto">
          <div className="grid grid-cols-1 md:grid-cols-4 gap-8">
            <div className="md:col-span-2">
              <div className="flex items-center mb-4">
                <div className="w-8 h-8 bg-orange-600 rounded-full flex items-center justify-center mr-3">
                  <span className="text-white font-bold text-sm">WM</span>
                </div>
                <h3 className="text-2xl font-bold text-white">Wickimedia</h3>
              </div>
              <p className="text-slate-300 mb-4 max-w-md">
                Your trusted partner for digital marketing success. We help businesses grow through
                innovative strategies and measurable results.
              </p>
              <div className="text-slate-400 mb-6">
                <p>📧 hello@wickimedia.com</p>
                <p>📞 (555) 123-4567</p>
                <p>📍 123 Digital Avenue, Marketing City, MC 12345</p>
              </div>

              {/* Social Media Links */}
              <div className="flex space-x-4">
                <a href="#" className="text-slate-400 hover:text-orange-400 transition-colors">
                  <svg className="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"/>
                  </svg>
                </a>
                <a href="#" className="text-slate-400 hover:text-orange-400 transition-colors">
                  <svg className="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M22.46 6c-.77.35-1.6.58-2.46.69.88-.53 1.56-1.37 1.88-2.38-.83.5-1.75.85-2.72 1.05C18.37 4.5 17.26 4 16 4c-2.35 0-4.27 1.92-4.27 4.29 0 .34.04.67.11.98C8.28 9.09 5.11 7.38 3 4.79c-.37.63-.58 1.37-.58 2.15 0 1.49.75 2.81 1.91 3.56-.71 0-1.37-.2-1.95-.5v.03c0 2.08 1.48 3.82 3.44 4.21a4.22 4.22 0 0 1-1.93.07 4.28 4.28 0 0 0 4 2.98 8.521 8.521 0 0 1-5.33 1.84c-.34 0-.68-.02-1.02-.06C3.44 20.29 5.7 21 8.12 21 16 21 20.33 14.46 20.33 8.79c0-.19 0-.37-.01-.56.84-.6 1.56-1.36 2.14-2.23z"/>
                  </svg>
                </a>
                <a href="#" className="text-slate-400 hover:text-orange-400 transition-colors">
                  <svg className="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
                  </svg>
                </a>
                <a href="#" className="text-slate-400 hover:text-orange-400 transition-colors">
                  <svg className="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/>
                  </svg>
                </a>
                <a href="#" className="text-slate-400 hover:text-orange-400 transition-colors">
                  <svg className="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M12.017 0C5.396 0 .029 5.367.029 11.987c0 5.079 3.158 9.417 7.618 11.174-.105-.949-.199-2.403.041-3.439.219-.937 1.406-5.957 1.406-5.957s-.359-.72-.359-1.781c0-1.663.967-2.911 2.168-2.911 1.024 0 1.518.769 1.518 1.688 0 1.029-.653 2.567-.992 3.992-.285 1.193.6 2.165 1.775 2.165 2.128 0 3.768-2.245 3.768-5.487 0-2.861-2.063-4.869-5.008-4.869-3.41 0-5.409 2.562-5.409 5.199 0 1.033.394 2.143.889 2.741.099.12.112.225.085.345-.09.375-.293 1.199-.334 1.363-.053.225-.172.271-.402.165-1.495-.69-2.433-2.878-2.433-4.646 0-3.776 2.748-7.252 7.92-7.252 4.158 0 7.392 2.967 7.392 6.923 0 4.135-2.607 7.462-6.233 7.462-1.214 0-2.357-.629-2.75-1.378l-.748 2.853c-.271 1.043-1.002 2.35-1.492 3.146C9.57 23.812 10.763 24.009 12.017 24c6.624 0 11.99-5.367 11.99-11.987C24.007 5.367 18.641.001 12.017.001z"/>
                  </svg>
                </a>
              </div>
            </div>
            <div>
              <h4 className="text-lg font-semibold text-white mb-4">Services</h4>
              <ul className="space-y-2 text-slate-300">
                <li>SEO Optimization</li>
                <li>PPC Advertising</li>
                <li>Social Media Marketing</li>
                <li>Content Marketing</li>
                <li>Web Development</li>
              </ul>
            </div>
            <div>
              <h4 className="text-lg font-semibold text-white mb-4">Company</h4>
              <ul className="space-y-2 text-slate-300">
                <li>About Us</li>
                <li>Our Team</li>
                <li>Case Studies</li>
                <li>Blog</li>
                <li>Contact</li>
              </ul>
            </div>
          </div>
          <Separator className="my-8 bg-slate-700" />
          <div className="text-center text-slate-400">
            <p>&copy; 2025 Wickimedia. All rights reserved.</p>
          </div>
        </div>
      </footer>
    </div>
  );
}
