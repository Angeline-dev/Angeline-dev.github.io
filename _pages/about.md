---
permalink: /
title: "Academic Pages is a ready-to-fork GitHub Pages template for academic personal websites"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

临床试验线上招募平台，这是由分中心研究者与患者可以直接在线上进行沟通交流的平台，通过临床试验项目的开展，研究者可以自己申请作为分中心的PI，可以在线审阅患者病历，患者也可以通过平台，在不泄露隐私的情况下，进行适合自己的临床试验报名，并会获得专业人士的直接与是否符合参加临床试验的资质审核。
import Link from 'next/link'
import { Button } from "@/components/ui/button"
import { Card, CardContent, CardDescription, CardFooter, CardHeader, CardTitle } from "@/components/ui/card"
import { Badge } from "@/components/ui/badge"

export default function PatientRecruitment() {
  const studies = [
    { 
      id: 1, 
      title: "Type 2 Diabetes Management Study", 
      condition: "Type 2 Diabetes",
      eligibility: "Adults 18-65, diagnosed with Type 2 Diabetes",
      location: "Multiple locations",
      compensation: "$500"
    },
    { 
      id: 2, 
      title: "Chronic Migraine Treatment Trial", 
      condition: "Chronic Migraine",
      eligibility: "Adults 21-60, experiencing 15+ headache days per month",
      location: "New York, NY",
      compensation: "$750"
    },
    { 
      id: 3, 
      title: "Rheumatoid Arthritis Therapy Evaluation", 
      condition: "Rheumatoid Arthritis",
      eligibility: "Adults 30-70, diagnosed with Rheumatoid Arthritis",
      location: "Chicago, IL",
      compensation: "$600"
    },
  ]

  return (
    <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
      <h1 className="text-3xl font-extrabold text-gray-900 mb-8">Patient Recruitment</h1>
      <p className="text-xl text-gray-600 mb-8">
        Participate in groundbreaking medical studies. Your involvement can help advance medical research and improve patient care.
      </p>
      <div className="grid gap-6">
        {studies.map((study) => (
          <Card key={study.id}>
            <CardHeader>
              <CardTitle>{study.title}</CardTitle>
              <CardDescription>Condition: {study.condition}</CardDescription>
            </CardHeader>
            <CardContent>
              <p className="text-sm text-gray-600 mb-2"><strong>Eligibility:</strong> {study.eligibility}</p>
              <p className="text-sm text-gray-600 mb-2"><strong>Location:</strong> {study.location}</p>
              <div className="flex items-center">
                <Badge variant="secondary" className="mr-2">Compensation</Badge>
                <span className="text-sm font-semibold">{study.compensation}</span>
              </div>
            </CardContent>
            <CardFooter>
              <Button asChild>
                <Link href={`/patient-recruitment/${study.id}`}>Learn More & Apply</Link>
              </Button>
            </CardFooter>
          </Card>
        ))}
      </div>
    </div>
  )
}
