# Carbon-Credits-workshop-
function App() {
  const [activeSection, setActiveSection] = useState('home')

  const pillars = [
    {
      title: "Integrity & Credibility",
      description: "Ensuring additionality, permanence, and conservative baselines",
      icon: <CheckCircle className="h-6 w-6" />,
      color: "bg-green-100 text-green-800"
    },
    {
      title: "Robust MRV Systems",
      description: "Measurement, Reporting, and Verification best practices",
      icon: <Target className="h-6 w-6" />,
      color: "bg-blue-100 text-blue-800"
    },
    {
      title: "Regulatory Navigation",
      description: "Understanding and engaging with policy frameworks",
      icon: <BookOpen className="h-6 w-6" />,
      color: "bg-purple-100 text-purple-800"
    },
    {
      title: "Equitable Benefit Sharing",
      description: "Fair distribution and community engagement",
      icon: <Users className="h-6 w-6" />,
      color: "bg-orange-100 text-orange-800"
    },
    {
      title: "Sustainable Financing",
      description: "Diverse funding mechanisms and financial viability",
      icon: <Globe className="h-6 w-6" />,
      color: "bg-teal-100 text-teal-800"
    }
  ]

  const resources = [
    {
      title: "Facilitator Guide",
      description: "Complete guide for conducting the 60-minute workshop",
      file: "facilitator_guide.pdf",
      type: "PDF"
    },
    {
      title: "Project Design Checklist",
      description: "Comprehensive checklist for high-integrity carbon projects",
      file: "project_design_checklist.pdf",
      type: "PDF"
    },
    {
      title: "Resource List",
      description: "Standards, funding sources, and training opportunities",
      file: "resource_list.pdf",
      type: "PDF"
    }
  ]

  const challenges = [
    "Integrity & Credibility concerns affecting market confidence",
    "Market volatility and historically poor uptake",
    "Weak regulatory frameworks creating uncertainty",
    "MRV challenges making verification difficult",
    "Social concerns including land rights and benefit distribution"
  ]

  return (
    <div className="min-h-screen bg-gradient-to-br from-green-50 to-blue-50">
      {/* Navigation */}
      <nav className="bg-white shadow-sm border-b">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex justify-between items-center h-16">
            <div className="flex items-center space-x-2">
              <Leaf className="h-8 w-8 text-green-600" />
              <span className="text-xl font-bold text-gray-900">Carbon Credit Workshop</span>
            </div>
            <div className="hidden md:flex space-x-8">
              <button 
                onClick={() => setActiveSection('home')}
                className={`px-3 py-2 text-sm font-medium ${activeSection === 'home' ? 'text-green-600 border-b-2 border-green-600' : 'text-gray-500 hover:text-gray-700'}`}
              >
                Home
              </button>
              <button 
                onClick={() => setActiveSection('workshop')}
                className={`px-3 py-2 text-sm font-medium ${activeSection === 'workshop' ? 'text-green-600 border-b-2 border-green-600' : 'text-gray-500 hover:text-gray-700'}`}
              >
                Workshop
              </button>
              <button 
                onClick={() => setActiveSection('slides')}
                className={`px-3 py-2 text-sm font-medium ${activeSection === 'slides' ? 'text-green-600 border-b-2 border-green-600' : 'text-gray-500 hover:text-gray-700'}`}
              >
                Slides
              </button>
              <button 
                onClick={() => setActiveSection('resources')}
                className={`px-3 py-2 text-sm font-medium ${activeSection === 'resources' ? 'text-green-600 border-b-2 border-green-600' : 'text-gray-500 hover:text-gray-700'}`}
              >
                Resources
              </button>
            </div>
          </div>
        </div>
      </nav>

      {/* Home Section */}
      {activeSection === 'home' && (
        <>
          {/* Hero Section */}
          <section className="relative py-20 px-4 sm:px-6 lg:px-8">
            <div className="max-w-7xl mx-auto">
              <div className="text-center">
                <h1 className="text-4xl md:text-6xl font-bold text-gray-900 mb-6">
                  Building High-Integrity
                  <span className="text-green-600 block">Carbon Credit Projects</span>
                </h1>
                <p className="text-xl text-gray-600 mb-8 max-w-3xl mx-auto">
                  A comprehensive 60-minute workshop addressing real pain points and delivering actionable solutions for carbon credit projects in Africa and South America
                </p>
                <div className="flex flex-col sm:flex-row gap-4 justify-center">
                  <Button 
                    onClick={() => setActiveSection('workshop')}
                    className="bg-green-600 hover:bg-green-700 text-white px-8 py-3 text-lg"
                  >
                    Explore Workshop <ArrowRight className="ml-2 h-5 w-5" />
                  </Button>
                  <Button 
                    onClick={() => setActiveSection('slides')}
                    variant="outline" 
                    className="border-green-600 text-green-600 hover:bg-green-50 px-8 py-3 text-lg"
                  >
                    View Slides <Presentation className="ml-2 h-5 w-5" />
                  </Button>
                  <Button 
                    onClick={() => setActiveSection('resources')}
                    variant="outline" 
                    className="border-green-600 text-green-600 hover:bg-green-50 px-8 py-3 text-lg"
                  >
                    Download Resources <Download className="ml-2 h-5 w-5" />
                  </Button>
                </div>
              </div>
            </div>
          </section>

          {/* Key Challenges Section */}
          <section className="py-16 bg-white">
            <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
              <div className="text-center mb-12">
                <h2 className="text-3xl font-bold text-gray-900 mb-4">Addressing Real Pain Points</h2>
                <p className="text-lg text-gray-600">Common challenges in carbon credit markets across Africa and South America</p>
              </div>
              <div className="grid md:grid-cols-2 gap-8 items-center">
                <div>
                  <img 
                    src={africaCarbonMap} 
                    alt="Carbon projects in Africa" 
                    className="rounded-lg shadow-lg w-full h-64 object-cover"
                  />
                </div>
                <div className="space-y-4">
                  {challenges.map((challenge, index) => (
                    <div key={index} className="flex items-start space-x-3">
                      <div className="flex-shrink-0 w-6 h-6 bg-red-100 rounded-full flex items-center justify-center mt-1">
                        <div className="w-2 h-2 bg-red-500 rounded-full"></div>
                      </div>
                      <p className="text-gray-700">{challenge}</p>
                    </div>
                  ))}
                </div>
              </div>
            </div>
          </section>

          {/* Five Pillars Section */}
          <section className="py-16 bg-gray-50">
            <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
              <div className="text-center mb-12">
                <h2 className="text-3xl font-bold text-gray-900 mb-4">Five Pillars of High-Integrity Projects</h2>
                <p className="text-lg text-gray-600">Our comprehensive framework for building successful carbon credit projects</p>
              </div>
              <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
                {pillars.map((pillar, index) => (
                  <Card key={index} className="hover:shadow-lg transition-shadow">
                    <CardHeader>
                      <div className="flex items-center space-x-3">
                        <div className={`p-2 rounded-lg ${pillar.color}`}>
                          {pillar.icon}
                        </div>
                        <CardTitle className="text-lg">{pillar.title}</CardTitle>
                      </div>
                    </CardHeader>
                    <CardContent>
                      <CardDescription className="text-gray-600">
                        {pillar.description}
                      </CardDescription>
                    </CardContent>
                  </Card>
                ))}
              </div>
            </div>
          </section>

          {/* Regional Focus Section */}
          <section className="py-16 bg-white">
            <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
              <div className="text-center mb-12">
                <h2 className="text-3xl font-bold text-gray-900 mb-4">Regional Focus</h2>
                <p className="text-lg text-gray-600">Tailored solutions for Africa and South America</p>
              </div>
              <div className="grid md:grid-cols-2 gap-8">
                <Card className="overflow-hidden">
                  <div className="h-48 overflow-hidden">
                    <img 
                      src={africaForest} 
                      alt="African forest conservation" 
                      className="w-full h-full object-cover"
                    />
                  </div>
                  <CardHeader>
                    <CardTitle className="text-xl">Africa</CardTitle>
                    <CardDescription>
                      Addressing unique challenges including low emission baselines, cost competitiveness, and capacity building needs
                    </CardDescription>
                  </CardHeader>
                </Card>
                <Card className="overflow-hidden">
                  <div className="h-48 overflow-hidden">
                    <img 
                      src={amazonReforestation} 
                      alt="Amazon reforestation project" 
                      className="w-full h-full object-cover"
                    />
                  </div>
                  <CardHeader>
                    <CardTitle className="text-xl">South America</CardTitle>
                    <CardDescription>
                      Tackling MRV variations, carbon land grabs, and leveraging the region's potential as a carbon market hub
                    </CardDescription>
                  </CardHeader>
                </Card>
              </div>
            </div>
          </section>
        </>
      )}

      {/* Workshop Section */}
      {activeSection === 'workshop' && (
        <section className="py-16">
          <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div className="text-center mb-12">
              <h2 className="text-3xl font-bold text-gray-900 mb-4">Workshop Overview</h2>
              <p className="text-lg text-gray-600">A comprehensive 60-minute learning experience</p>
            </div>
            
            <div className="grid lg:grid-cols-2 gap-8 mb-12">
              <Card>
                <CardHeader>
                  <CardTitle className="text-xl">Workshop Objectives</CardTitle>
                </CardHeader>
                <CardContent className="space-y-3">
                  <div className="flex items-start space-x-3">
                    <CheckCircle className="h-5 w-5 text-green-600 mt-1 flex-shrink-0" />
                    <p>Understand core challenges in carbon credit project development</p>
                  </div>
                  <div className="flex items-start space-x-3">
                    <CheckCircle className="h-5 w-5 text-green-600 mt-1 flex-shrink-0" />
                    <p>Recognize best practices for ensuring integrity and credibility</p>
                  </div>
                  <div className="flex items-start space-x-3">
                    <CheckCircle className="h-5 w-5 text-green-600 mt-1 flex-shrink-0" />
                    <p>Apply robust MRV principles in project implementation</p>
                  </div>
                  <div className="flex items-start space-x-3">
                    <CheckCircle className="h-5 w-5 text-green-600 mt-1 flex-shrink-0" />
                    <p>Navigate regulatory landscapes effectively</p>
                  </div>
                  <div className="flex items-start space-x-3">
                    <CheckCircle className="h-5 w-5 text-green-600 mt-1 flex-shrink-0" />
                    <p>Implement equitable benefit-sharing mechanisms</p>
                  </div>
                  <div className="flex items-start space-x-3">
                    <CheckCircle className="h-5 w-5 text-green-600 mt-1 flex-shrink-0" />
                    <p>Explore diverse financing opportunities</p>
                  </div>
                </CardContent>
              </Card>

              <Card>
                <CardHeader>
                  <CardTitle className="text-xl">Target Audience</CardTitle>
                </CardHeader>
                <CardContent className="space-y-3">
                  <Badge variant="secondary" className="mr-2 mb-2">Project Developers</Badge>
                  <Badge variant="secondary" className="mr-2 mb-2">Community Leaders</Badge>
                  <Badge variant="secondary" className="mr-2 mb-2">Government Officials</Badge>
                  <Badge variant="secondary" className="mr-2 mb-2">Investors</Badge>
                  <Badge variant="secondary" className="mr-2 mb-2">NGOs</Badge>
                  <Badge variant="secondary" className="mr-2 mb-2">Policy Makers</Badge>
                  <p className="text-gray-600 mt-4">
                    Designed for stakeholders interested in developing or investing in carbon credit projects in Africa and South America.
                  </p>
                </CardContent>
              </Card>
            </div>

            <Card className="mb-8">
              <CardHeader>
                <CardTitle className="text-xl">Workshop Agenda (60 minutes)</CardTitle>
              </CardHeader>
              <CardContent>
                <div className="space-y-4">
                  <div className="flex items-center space-x-4 p-4 bg-gray-50 rounded-lg">
                    <div className="bg-green-600 text-white rounded-full w-8 h-8 flex items-center justify-center text-sm font-bold">1</div>
                    <div>
                      <h4 className="font-semibold">Welcome & Introduction (5 min)</h4>
                      <p className="text-gray-600">Icebreaker and workshop overview</p>
                    </div>
                  </div>
                  <div className="flex items-center space-x-4 p-4 bg-gray-50 rounded-lg">
                    <div className="bg-green-600 text-white rounded-full w-8 h-8 flex items-center justify-center text-sm font-bold">2</div>
                    <div>
                      <h4 className="font-semibold">Understanding Challenges & Pain Points (10 min)</h4>
                      <p className="text-gray-600">Regional challenges and interactive discussion</p>
                    </div>
                  </div>
                  <div className="flex items-center space-x-4 p-4 bg-gray-50 rounded-lg">
                    <div className="bg-green-600 text-white rounded-full w-8 h-8 flex items-center justify-center text-sm font-bold">3</div>
                    <div>
                      <h4 className="font-semibold">Five Pillars of High-Integrity Projects (20 min)</h4>
                      <p className="text-gray-600">Deep dive into best practices with case studies</p>
                    </div>
                  </div>
                  <div className="flex items-center space-x-4 p-4 bg-gray-50 rounded-lg">
                    <div className="bg-green-600 text-white rounded-full w-8 h-8 flex items-center justify-center text-sm font-bold">4</div>
                    <div>
                      <h4 className="font-semibold">Actionable Strategies & Tools (15 min)</h4>
                      <p className="text-gray-600">Practical application and group activities</p>
                    </div>
                  </div>
                  <div className="flex items-center space-x-4 p-4 bg-gray-50 rounded-lg">
                    <div className="bg-green-600 text-white rounded-full w-8 h-8 flex items-center justify-center text-sm font-bold">5</div>
                    <div>
                      <h4 className="font-semibold">Q&A and Next Steps (10 min)</h4>
                      <p className="text-gray-600">Discussion and resource sharing</p>
                    </div>
                  </div>
                </div>
              </CardContent>
            </Card>
          </div>
        </section>
      )}

      {/* Slides Section */}
      {activeSection === 'slides' && (
        <section className="py-16">
          <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div className="text-center mb-12">
              <h2 className="text-3xl font-bold text-gray-900 mb-4">Workshop Slides</h2>
              <p className="text-lg text-gray-600">Navigate through the complete workshop presentation</p>
            </div>
            <SlidesViewer />
          </div>
        </section>
      )}

      {/* Resources Section */}
      {activeSection === 'resources' && (
        <section className="py-16">
          <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div className="text-center mb-12">
              <h2 className="text-3xl font-bold text-gray-900 mb-4">Workshop Resources</h2>
              <p className="text-lg text-gray-600">Download comprehensive materials to support your carbon credit projects</p>
            </div>
            
            <div className="grid md:grid-cols-3 gap-6 mb-12">
              {resources.map((resource, index) => (
                <Card key={index} className="hover:shadow-lg transition-shadow">
                  <CardHeader>
                    <div className="flex items-center justify-between">
                      <CardTitle className="text-lg">{resource.title}</CardTitle>
                      <Badge variant="outline">{resource.type}</Badge>
                    </div>
                  </CardHeader>
                  <CardContent>
                    <CardDescription className="mb-4">
                      {resource.description}
                    </CardDescription>
                    <Button 
                      className="w-full" 
                      onClick={() => window.open(resource.file, '_blank')}
                    >
                      <Download className="mr-2 h-4 w-4" />
                      Download
                    </Button>
                  </CardContent>
                </Card>
              ))}
            </div>

            <Card className="mb-8">
              <CardHeader>
                <CardTitle className="text-xl">Additional Resources</CardTitle>
              </CardHeader>
              <CardContent>
                <div className="grid md:grid-cols-2 gap-6">
                  <div>
                    <h4 className="font-semibold mb-3">Standards & Methodologies</h4>
                    <ul className="space-y-2 text-gray-600">
                      <li>• Verra VCS - verra.org</li>
                      <li>• Gold Standard - goldstandard.org</li>
                      <li>• ART TREES - artredd.org</li>
                      <li>• Plan Vivo - planvivo.org</li>
                    </ul>
                  </div>
                  <div>
                    <h4 className="font-semibold mb-3">Funding Sources</h4>
                    <ul className="space-y-2 text-gray-600">
                      <li>• Green Climate Fund</li>
                           <li>• Forest Carbon Partnership Facility</li>
                      <li>• LEAF Coalition</li>
                      <li>• Regional Development Banks</li>
                    </ul>
                  </div>
                </div>
              </CardContent>
            </Card>

            <div className="text-center">
              <Card className="inline-block p-6">
                <h3 className="text-lg font-semibold mb-2">Need More Information?</h3>
                <p className="text-gray-600 mb-4">Contact us for follow-up questions or additional support</p>
                <Button variant="outline">
                  carboncredits@workshop.org
                </Button>
              </Card>
            </div>
          </div>
        </section>
      )}

      {/* Footer */}
      <footer className="bg-gray-900 text-white py-12">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="grid md:grid-cols-3 gap-8">
            <div>
              <div className="flex items-center space-x-2 mb-4">
                <Leaf className="h-6 w-6 text-green-400" />
                <span className="text-lg font-bold">Carbon Credit Workshop</span>
              </div>
              <p className="text-gray-400">
                Building high-integrity carbon credit projects for sustainable development in Africa and South America.
              </p>
            </div>
            <div>
              <h4 className="font-semibold mb-4">Quick Links</h4>
              <ul className="space-y-2 text-gray-400">
                <li><button onClick={() => setActiveSection('home')} className="hover:text-white">Home</button></li>
                <li><button onClick={() => setActiveSection('workshop')} className="hover:text-white">Workshop</button></li>
                <li><button onClick={() => setActiveSection('slides')} className="hover:text-white">Slides</button></li>
                <li><button onClick={() => setActiveSection('resources')} className="hover:text-white">Resources</button></li>
              </ul>
            </div>
            <div>
              <h4 className="font-semibold mb-4">Contact</h4>
              <p className="text-gray-400">
                For questions or additional support:<br />
                carboncredits@workshop.org
              </p>
            </div>
          </div>
          <div className="border-t border-gray-800 mt-8 pt-8 text-center text-gray-400">
            <p>&copy; 2025 Carbon Credit Workshop. All rights reserved.</p>
          </div>
        </div>
      </footer>
    </div>
  )
}
