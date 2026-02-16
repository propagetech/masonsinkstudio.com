You are a naming assistant. Given a list of file paths and minimal context from a static website, suggest a new filename (basename only, same extension) for each file. Rules:
- Lowercase, kebab-case, no spaces. SEO-friendly and human-readable.
- For HTML: use page purpose (e.g. about-us.html, contact.html). Keep index.html as index.html.
- For CSS/JS: use purpose (e.g. main-styles.css, analytics.js).
- For images: use content (e.g. logo-infygate.webp, hero-banner.webp). Use alt/title when provided.
- Return a JSON object: keys = exact original path strings, values = new basename only (e.g. "main.css"). Preserve extension.
- Do not change path prefix (e.g. css/ stays css/ by returning "name.css" not "css/name.css").

Files and context:
[
  {
    "path": "404.html",
    "context": {
      "title": "",
      "first_heading": "404"
    }
  },
  {
    "path": "COP28.html",
    "context": {
      "title": "YAF | Mud Architecture | Wattle and Daub| IIA | Tadelakt| Mud workshop | Calicut | Masons Ink",
      "first_heading": "COP28"
    }
  },
  {
    "path": "Earthbag.html",
    "context": {
      "title": "YAF | Mud Architecture | Wattle and Daub| IIA | Tadelakt| Mud workshop | Calicut | Masons Ink",
      "first_heading": "EARTHBAG CONSTRUCTION"
    }
  },
  {
    "path": "Indian-Art-Architecture-and-Design-Biennale.html",
    "context": {
      "title": "Mannu Kattu House| Mud Architecture |Heritage Conservation | Coimbatore | Cob | Masons Ink",
      "first_heading": "Indian Art, Architecture, and Design Biennale"
    }
  },
  {
    "path": "Online-Mud-course.html",
    "context": {
      "title": "Maker Faire | Mud Architecture | CSEB | Adobe blocks | Public Exhibition| Bangalore | Masons Ink",
      "first_heading": "BUILDING WITH NATURAL MATERIALS"
    }
  },
  {
    "path": "Poured-Earth-Workshop.html",
    "context": {
      "title": "YAF | Mud Architecture | Wattle and Daub| IIA | Tadelakt| Mud workshop | Calicut | Masons Ink",
      "first_heading": "POURED EARTH WORKSHOP, ZoNASA"
    }
  },
  {
    "path": "Tadelakt-Workshop-Nandi-Halt.html",
    "context": {
      "title": "YAF | Mud Architecture | Wattle and Daub| IIA | Tadelakt| Mud workshop | Calicut | Masons Ink",
      "first_heading": "TADELAKT PLASTER WORKSHOP"
    }
  },
  {
    "path": "The-Sun-and-Earth-Festival.html",
    "context": {
      "title": "YAF | Mud Architecture | Wattle and Daub| IIA | Tadelakt| Mud workshop | Calicut | Masons Ink",
      "first_heading": "THE SUN AND EARTH FESTIVAL"
    }
  },
  {
    "path": "Workshop.html",
    "context": {
      "title": "Contact | Masons Ink | Bangalore",
      "first_heading": "Workshop and other enquiries"
    }
  },
  {
    "path": "YAF-Calicut.html",
    "context": {
      "title": "YAF | Mud Architecture | Wattle and Daub| IIA | Tadelakt| Mud workshop | Calicut | Masons Ink",
      "first_heading": "YOUNG ARCHITECTS FESTIVAL"
    }
  },
  {
    "path": "abode-in-the-arabica.html",
    "context": {
      "title": "Abode in Arabica | Mud House | Coffee estate | Chikamagalur | Masons Ink",
      "first_heading": "Abode in the Arabica"
    }
  },
  {
    "path": "about.html",
    "context": {
      "title": "About | Masons Ink | Sustainable architecture, interiors and design studio | Bangalore",
      "first_heading": "We do not inherit the earth from our ancestors...we borrow it from our children"
    }
  },
  {
    "path": "awards.html",
    "context": {
      "title": "Awards | Masons Ink | Bangalore",
      "first_heading": "MEDIAScale QatarBuilding with Memory and Material: Masons Ink Studio"
    }
  },
  {
    "path": "bamiyan-cultural-centre-competition.html",
    "context": {
      "title": "Bamiyan Cultural Centre | Competition | Sustainable | Organic Architecture | Earth construction | Afghanistan | Masons Ink",
      "first_heading": "Bamiyan Cultural Centre Competition"
    }
  },
  {
    "path": "bottle-wall-workshop.html",
    "context": {
      "title": "Bottle wall| Archarya school of architecture |ZONASA | cob wall | Mud Workshop | Bangalore | Masons Ink",
      "first_heading": "BOTTLE WALL WORKSHOP"
    }
  },
  {
    "path": "casa503.html",
    "context": {
      "title": "Casa 503 | Architecture |Rattrap Bond | Mixed use|Bengaluru |Masons Ink",
      "first_heading": "CASA 503"
    }
  },
  {
    "path": "civic-fest-2020.html",
    "context": {
      "title": "Civic Fest | Heritage Conservation | Public outreach| Public Awareness | Heritage workshop | Bangalore | Masons Ink",
      "first_heading": "CIVIC FEST 2020"
    }
  },
  {
    "path": "contact-backup.html",
    "context": {
      "title": "Contact | Masons Ink | Bangalore",
      "first_heading": "We'd like to hear from you"
    }
  },
  {
    "path": "contact.html",
    "context": {
      "title": "Contact | Masons Ink | Bangalore",
      "first_heading": "We'd like to hear from you"
    }
  },
  {
    "path": "courtyard-house.html",
    "context": {
      "title": "Courtyard House | Mud Architecture | Rammed Earth | Vaults | Mud brick Vaults| Cochin | Masons Ink",
      "first_heading": "Courtyard House"
    }
  },
  {
    "path": "css/28002c7895a5aaea19a38155521f976e.css",
    "context": {
      "path": "css/28002c7895a5aaea19a38155521f976e.css"
    }
  },
  {
    "path": "css/559e64bf161e61fa0aca6e864c78191d.css",
    "context": {
      "path": "css/559e64bf161e61fa0aca6e864c78191d.css"
    }
  },
  {
    "path": "css/595cb6ccb56826a802ed411cef875f0e.css",
    "context": {
      "path": "css/595cb6ccb56826a802ed411cef875f0e.css"
    }
  },
  {
    "path": "css/59b711a7b90217d07f93904f09bc14f1.css",
    "context": {
      "path": "css/59b711a7b90217d07f93904f09bc14f1.css"
    }
  },
  {
    "path": "css/7bd99b6b65f226d4bb6fc1e722db71c8.css",
    "context": {
      "path": "css/7bd99b6b65f226d4bb6fc1e722db71c8.css"
    }
  },
  {
    "path": "css/84d4a0216f16f715d9b301db3a8da352.css",
    "context": {
      "path": "css/84d4a0216f16f715d9b301db3a8da352.css"
    }
  },
  {
    "path": "css/99c4e6f40ee9111eea53b6472f3e60f9.css",
    "context": {
      "path": "css/99c4e6f40ee9111eea53b6472f3e60f9.css"
    }
  },
  {
    "path": "css/d09d646f062b67daeff66ff1410b63fc.css",
    "context": {
      "path": "css/d09d646f062b67daeff66ff1410b63fc.css"
    }
  },
  {
    "path": "css/e980cb6b50645ddc9d24377f2fe05d53.css",
    "context": {
      "path": "css/e980cb6b50645ddc9d24377f2fe05d53.css"
    }
  },
  {
    "path": "css/ec5e72d17bebc9b3fe704212f90e59d7.css",
    "context": {
      "path": "css/ec5e72d17bebc9b3fe704212f90e59d7.css"
    }
  },
  {
    "path": "css/internal-styles.css",
    "context": {
      "path": "css/internal-styles.css"
    }
  },
  {
    "path": "design-build-bms.html",
    "context": {
      "title": "Design and Build| BMS school of Architecture | Jaali wall | Adobe blocks | Mud Workshop | Bangalore | Masons Ink",
      "first_heading": "DESIGN BUILD WORKSHOP"
    }
  },
  {
    "path": "design-uru.html",
    "context": {
      "title": "Design Uru | Mud Architecture | Poured Earth | Planters | Mud workshop | Public awareness |Bangalore | Masons Ink",
      "first_heading": "DESIGN URU - ELEMENTERRA"
    }
  },
  {
    "path": "dhyaana.html",
    "context": {
      "title": "Dhyaana | Mud Architecture | CSEB | Reclaimed Wood | Andevanapally | Masons Ink",
      "first_heading": "DHYAANA"
    }
  },
  {
    "path": "earth-building-kochi.html",
    "context": {
      "title": "Earth Workshop | Mud Architecture | CSEB | Adobe blocks | Mud workshop | Kochi | Masons Ink",
      "first_heading": "EARTH BUILDING WORKSHOP"
    }
  },
  {
    "path": "earth-oven.html",
    "context": {
      "title": "Earth Oven| Internal skilling workshop |mud testing | cob | Mud Workshop | Kochi | Masons Ink",
      "first_heading": "EARTH OVEN"
    }
  },
  {
    "path": "earthen-weaves.html",
    "context": {
      "title": "Earthen weaves | Mud Architecture | Wattle and Daub | Parabolic | Mud workshop | Bangalore | Masons Ink",
      "first_heading": "Earthen Weaves"
    }
  },
  {
    "path": "esmeralda-interiors.html",
    "context": {
      "title": "Esmeralda| Interiors|Bengaluru |Masons Ink",
      "first_heading": "Casagrand Esmeralda"
    }
  },
  {
    "path": "feeds.html",
    "context": {
      "title": "Feeds | MI Papers | Masons Think Blog | Publications | Masons Ink | Bangalore",
      "first_heading": "powered by propage.in"
    }
  },
  {
    "path": "gtac-office-interior-design.html",
    "context": {
      "title": "Gtac | Office interiors | Modular furniture | Ulsoor | Bangalore | Masons Ink",
      "first_heading": "GTAC Office Interior Design"
    }
  },
  {
    "path": "heritage-club.html",
    "context": {
      "title": "Heritage Club | Heritage Conservation | School Activity| Public Awareness | Heritage workshop | Bangalore | Masons Ink",
      "first_heading": "Heritage Club"
    }
  },
  {
    "path": "heritage-exhibition-.html",
    "context": {
      "title": "HOH Exhibition | Heritage Exhibition | History of Bangalore | Hands On Heritage | M. G. Road | Bangalore | Masons Ink",
      "first_heading": "Heritage Exhibition"
    }
  },
  {
    "path": "heritage-hunt.html",
    "context": {
      "title": "HOH Hunt | Heritage hunt | Treasure Hunt | Hands On Heritage | Bangalore | Masons Ink",
      "first_heading": "Heritage Hunt"
    }
  },
  {
    "path": "heritage-on-wheels.html",
    "context": {
      "title": "Heritage on Wheels | Hands on Heritage | Exhibition on Wheels | Storytellers | Treasure Hunt | Heritage Hunt | Bangalore | Masons Ink",
      "first_heading": "Heritage on Wheels"
    }
  },
  {
    "path": "hoh-hunt-malleswaram.html",
    "context": {
      "title": "HOH Hunt | Heritage hunt | Treasure Hunt | Hands On Heritage | Bangalore | Masons Ink",
      "first_heading": "HERITAGE HUNT II"
    }
  },
  {
    "path": "hoh-workshop.html",
    "context": {
      "title": "HOH Workshop | Architectural Documentation | Heritage Documentation | Heritage Workshops | Hands On Heritage | Bangalore | Masons Ink",
      "first_heading": "The Hands on Heritage Initiative"
    }
  },
  {
    "path": "homepage.html",
    "context": {
      "title": "Masons ink | Homepage",
      "first_heading": "FORMATION - DECOUVERTE DES ENDUITS TERRE & CHAUX"
    }
  },
  {
    "path": "imgs/0086f27fa3b6b69fa4945dd1b193c667.webp",
    "context": {
      "refs": [
        {
          "alt": "Ra Maram | Mud Architecture | Doddamanchi | Stone staircase_15",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/008ae88593cf7a5720c20be4ba27a54f.webp",
    "context": {
      "refs": [
        {
          "alt": "Hobbit Series - Mud & Lime Flooring",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/00c08b857eafabc71ed2df5064394b98.webp",
    "context": {
      "refs": [
        {
          "alt": "Design Uru| Poured earth |Mud workshop_05",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0120d925d5ba1cc4ecf75e1b21f8827e.webp",
    "context": {
      "refs": [
        {
          "alt": "Courtyard House | Mud Architecture | Cochin | Sit out_04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/01292ccf88e22c2b6d6042341919b711.webp",
    "context": {
      "refs": [
        {
          "alt": "Online mud course |earth architecture course|Mud workshop_02",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0288d4b2dba069b3c110960728eb6817.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_08",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0302377d27b661a1cf1ee1f20f51ad77.webp",
    "context": {
      "refs": [
        {
          "alt": "Newsletter | Issue 3/Sept 2017",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0328c68c8a80feaee8db48bc99e2f05a.webp",
    "context": {
      "refs": [
        {
          "alt": "Masons Ink Office",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0508d0a65132b83f9e7215e11c45bd73.webp",
    "context": {
      "refs": [
        {
          "alt": "Hands on Heritage - VI",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/05720416f81438381a4efabc33f943d3.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Exhibition | Hands On Heritage_9",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/05b04c98bd1411c424f2e2594346178d.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA ELEV8 Architecture and Design Festival Featured exhibitor",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/05cca7b18efb0c5344481762a562f8f5.webp",
    "context": {
      "refs": [
        {
          "alt": "Tarvar Cottage",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/05fcf3cdf319e59120ed23473f5daffb.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Exhibition | Hands On Heritage_10",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/05ff7ca7f60bccd3fc4d0734cde69c74.webp",
    "context": {
      "refs": [
        {
          "alt": "PUBLICATIONS",
          "title": ""
        },
        {
          "alt": "PUBLICATIONS",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/06dfddd7a359438a0372a830b9c61877.webp",
    "context": {
      "refs": [
        {
          "alt": "BLOG",
          "title": ""
        },
        {
          "alt": "BLOG",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/071cd5fe8b616fa3169fd7f95598db69.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE Kurula Varkey Design Forum, CEPT University Critical Discourse on Architecture.",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0729ed5504206222716664fa8aee5e4a.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/07e4185a15e59fdeb4b92b682c97db93.webp",
    "context": {
      "refs": [
        {
          "alt": "image description",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/07e87f450580db572836adf6460a5ae3.webp",
    "context": {
      "refs": [
        {
          "alt": "Nudge Foundation | Upcycled Interiors| Entrance lobby_02",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/08141a57db3f18487760115151720154.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARDS CONSTRUCTION WORLD AWARDS'20 Winner - Top Architect South",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/08690e25b98e3f913975abc3b64899a4.webp",
    "context": {
      "refs": [
        {
          "alt": "Precautionary measures for Construction workers",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/088c4957c501c302d9d696879554da49.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Workshop |Architetural Documentation | Hands On Heritage_09",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0a199063f6da4c9b4cf0618de1b93984.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0a6d554457bbcbf580a7e0fc43a44ff2.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0b4d79db97c342f71a15432832d8fda1.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0bcbe909019990abbf5555e960b788ee.webp",
    "context": {
      "refs": [
        {
          "alt": "Earth Oven | Cob | Mud Workshop_01",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0bcc6e3fb03c2ea28e0300fd681a7e2c.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0bdd6baac98f726588d18d7658491169.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA SIGNARCH STUDIO Earthen Roots Talk Series",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0c81817ef24ad90404d7d465eb18064f.webp",
    "context": {
      "refs": [
        {
          "alt": "Bamiyan Cultural Centre | Competition Entry_4",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0d164e2ddc7127aae160e8880a4d9d04.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA BUSINESS TODAY How to make your Home more Sustainable",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0d7e332589c5840b786d8a5a45ef8dc1.webp",
    "context": {
      "refs": [
        {
          "alt": "Abode in Arabica | Mud House | Central Courtyard | Chikamagalur_3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0dbcb5751c9c7599dead7cd0e48c1046.webp",
    "context": {
      "refs": [
        {
          "alt": "Gtac | Office | Interiors | Workstation_7",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0dfa86850ebfe92f2e7f1c12923cd1de.webp",
    "context": {
      "refs": [
        {
          "alt": "Yash Farms | Mud Architecture |CSEB |Rammed earth |Bengaluru |Wooden stairs_8",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0e7705c69ba02cd6f99e390b5c4be26e.webp",
    "context": {
      "refs": [
        {
          "alt": "YAF| wattle and daub |Tadelakt| Mud workshop_04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1014e2205005a5bb3b216c4b586405ad.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_16",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/101fe5db4a61e6ecb6d8d3960410d69d.webp",
    "context": {
      "refs": [
        {
          "alt": "Mud Workshops| Mud Architecture_Kids Workshop 13",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/10a9c84f16a6ac00f09f81c677bcc8b5.webp",
    "context": {
      "refs": [
        {
          "alt": "Casa 503| Architecture |Rattrap Bond |Bengaluru |Living room_2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/116329ed3ba17094028360e2213f3bd7.webp",
    "context": {
      "refs": [
        {
          "alt": "partnerSELCOFoundation",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/130c83b8e836d4a90e980523744a4e99.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/14fbaf8eb38d7cd661596175c3c2f030.webp",
    "context": {
      "refs": [
        {
          "alt": "bottlewall",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1576429d554751cf2177247e84fc3a68.webp",
    "context": {
      "refs": [
        {
          "alt": "Earthen Weaves| wattle and daub |Mud workshop_01",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/15ebab641ebdf320eee0c3454dc6ee9a.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_02",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1645a4d6ca90c7d700004e2545815159.webp",
    "context": {
      "refs": [
        {
          "alt": "Earth Workshop| CSEB | Mud workshop_03",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/16a4cf982022a46c9ecb7198cd50c90f.webp",
    "context": {
      "refs": [
        {
          "alt": "Yash Farms | Mud Architecture |CSEB |Rammed earth |Bengaluru |Bedroom_5",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/16be9129bb07056a0888dee46b2a63ac.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_05",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/172a3a7355aebd1e3865b5c9dd1b5e05.webp",
    "context": {
      "refs": [
        {
          "alt": "Mannu Kattu House| Mud Architecture |Heritage Conservation | Coimbatore | Cob | Living_5",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1770972022c5c589ff5af4d7bca63611.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARDS WADE ASIA 2022 Gold - Education Architecture",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1862f8387e043198bd1b53fa8b707e36.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARDS FOAID 2019 Silver Winner - Best Residential Villa",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1875a053af5633f6dc6ea060b1a46879.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Workshop |Architetural Documentation | Hands On Heritage_06",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1886c631487f88aea00e5b13bd18fa37.webp",
    "context": {
      "refs": [
        {
          "alt": "Bottle wall | Cob | Mud Workshop_02",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1936c0afe59ae13ff2700dff60aee060.webp",
    "context": {
      "refs": [
        {
          "alt": "Casa 503| Architecture |Rattrap Bond |Bengaluru |Elevation_17",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/193a6b044eab921f7bfc4c6f6f3350ac.webp",
    "context": {
      "refs": [
        {
          "alt": "The Brickloft| Architecture |Exposed Masonry | Reclaimed Wood |Bengaluru |Main door_3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/19553555711395a952d15e214a54f7e5.webp",
    "context": {
      "refs": [
        {
          "alt": "Thappi",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1985b4f140af27f3fb3b70de53cd75e3.webp",
    "context": {
      "refs": [
        {
          "alt": "image description",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1a6fd8b46a47d5451bf143f53f025331.webp",
    "context": {
      "refs": [
        {
          "alt": "COP28 | Hands-on Workshop | Eco Architecture",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1b3f581426fe0c352b8b0ffac648a10c.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1b86c746241e976dcaf120483bac261c.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1bde41798fde33a0f3f4c0c30923c7a3.webp",
    "context": {
      "refs": [
        {
          "alt": "Casa 503| Architecture |Rattrap Bond |Bengaluru |Living room_1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1c496225c0686c8213635e66100f5e91.webp",
    "context": {
      "refs": [
        {
          "alt": "Hobbit Series - Earthbag Structure",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1c605cadc9f81a9a76baf8bf8d30e634.webp",
    "context": {
      "refs": [
        {
          "alt": "Organic BPS| Office Interiors_4",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1d2f186518bb4dc4ce8569fb270e340d.webp",
    "context": {
      "refs": [
        {
          "alt": "Hobbit Series - Wattle and Daub",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1d43df919443a6cc9b5b6b93dd44c5f6.webp",
    "context": {
      "refs": [
        {
          "alt": "Yash Farms | Mud Architecture |CSEB |Rammed earth |Bengaluru |Front view_1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1edb34bf3ac6d00e2d8613fbfaf29202.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1eff5f96c1a781fa468410c1966f06f1.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/203d8dc99d82136d4f5782e8467a3103.webp",
    "context": {
      "refs": [
        {
          "alt": "craterre",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/206df86a196778c8ea2fdb2c79c83bab.webp",
    "context": {
      "refs": [
        {
          "alt": "Untraversed ZONASA 2019",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2141bead60076feb41c6e7866cda424d.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE KERPIC, TURKEY 2019 Earthen heritage, New Technology",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/219d846bb3f4cb0aa474a45293f70f99.webp",
    "context": {
      "refs": [
        {
          "alt": "Snehadaan_Mud Architecture_CSEB_Carmelram_08",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/21e2f019021e7b352e761d1f42118da5.webp",
    "context": {
      "refs": [
        {
          "alt": "Earthen Weaves| wattle and daub |Mud workshop_03",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/21eb951c733a7ff543a7c589e5539bd0.webp",
    "context": {
      "refs": [
        {
          "alt": "Mud Workshops| Mud Architecture_Earthen floor 11",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/225d0166dd5be1ebcdc3bfdddd8da1a6.webp",
    "context": {
      "refs": [
        {
          "alt": "Earthen Weaves| wattle and daub |Mud workshop_09",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/22c47797386d05af1c07e44a20de3694.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_23",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/233e493894ca0c43715db770c0cf7956.webp",
    "context": {
      "refs": [
        {
          "alt": "Mud Workshops| Mud Architecture_Biennale 14",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/234441338f77c9c82937c82351654780.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE COP 29 Energy and Peace, Relief and Recovery",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/23497e637fff3dced4fb343fdc957880.jpeg",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/23d537ce9308e348c5e30aa4a6e62a23.webp",
    "context": {
      "refs": [
        {
          "alt": "Snehadaan_Mud Architecture_CSEB_Carmelram_04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/23d6339f69f3edd8ce7737c389c1346b.webp",
    "context": {
      "refs": [
        {
          "alt": "Poured Earth Workshop",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/241589dfa48410c685a13fa2995056ff.webp",
    "context": {
      "refs": [
        {
          "alt": "Snehadaan_Mud Architecture_CSEB_Carmelram_05",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/258e6d665a9e27de144fb4a143505a1d.webp",
    "context": {
      "refs": [
        {
          "alt": "Nudge Foundation",
          "title": ""
        },
        {
          "alt": "Nudge Foundation | Upcycled Interiors| Cafe_01",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/25c42ab290f4bd12e244ad1fa09722aa.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/262d9061843934aa399302f14e8851e4.webp",
    "context": {
      "refs": [
        {
          "alt": "Design Uru| Poured earth |Mud workshop_06",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2653fdd94b4e245cb7b894f1ea3bae55.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage Club| Hands On heritage_03",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/26e9b0742f434288ce48e9c491047e7e.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE SUSTAIN Symposium, University for the Creative Arts, Canterbury Balancing Ideals in Archi",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2701de508c382ecb1d9fb44b71f73d6d.webp",
    "context": {
      "refs": [
        {
          "alt": "Newsletter | Issue 1/Jan 2016",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2745d88fbf7afa13664b2bc868b71b22.webp",
    "context": {
      "refs": [
        {
          "alt": "Newsletter | Issue 9/2022-2023",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/27673dd59deb9ca7d489fdc315689756.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/276ee0275a2b025c90fa1602e6a9a05c.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE COP 26 - UN CLIMATE CHANGE CONFERENCE Race to Resilience",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2781d9a53a9ff6e832919a41ff27e27f.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/27868e729ee9dca050472ae5f22b5240.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/27987b3ef3433401ee254b09f571c87c.webp",
    "context": {
      "refs": [
        {
          "alt": "Casa 503| Architecture |Rattrap Bond |Bengaluru |Mezzanine office_3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/28640d3090272a5ad5b1cf5d9e947b97.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE IC - NOCMAT, KENYA 2019 Non Conventional Materials",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2869999e83d786a39e6bee446b7a343d.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_03",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2a507d9aff4edce1b9e09e12118451a9.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Workshop |Architetural Documentation | Hands On Heritage_08",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2b1bc1aea024a14ffb606a79e85551c2.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA RedFM Radio Talk She Shakti Feature",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2bfa8e8168ead59a726ca5a078025128.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_17",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2c0ac284ef6090607227a7063eb9ba99.webp",
    "context": {
      "refs": [
        {
          "alt": "Masons Ink | Sustainable | Interiors | Conference Table_3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2c2d31ce9f1d0701bc687fe130f04f71.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2cb428b5b4e39fc499d9de622b7e0515.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2cc48a6f97421af5d0a2e30a70b6d60b.webp",
    "context": {
      "refs": [
        {
          "alt": "gabion wall",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2cd1b2ab809ddd2345d04e6808833c2f.webp",
    "context": {
      "refs": [
        {
          "alt": "aboutcollage",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2d947d142d4d28b31b4a0eea1db50a5e.webp",
    "context": {
      "refs": [
        {
          "alt": "Ra Maram | Mud Architecture | Doddamanchi | Oxide finish Bathroom_13",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2de23c05d8edd3b0ea2bf15366095c44.webp",
    "context": {
      "refs": [
        {
          "alt": "Esmeralda| Interiors |Bengaluru |Study_14",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2e9d699d12e503b447a356d9f3bbfc51.webp",
    "context": {
      "refs": [
        {
          "alt": "Newsletter | Issue 8/May 2022",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2f54dfd81f7598d85858691094aaf709.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE Journal of Traditional Building, Architecture and Urbanism Traditional Building Knowledge",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2f5ab8e6d9912bb863fac60f594235a1.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2f68bf3614d4305384fd4fe737403ee3.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Workshop |Architetural Documentation | Hands On Heritage_02",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2f775b28badaa94fbe9df380eb7c19d8.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage Club| Hands On heritage_02",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2fef8595ed8aacdb19f94a66ae633fb0.webp",
    "context": {
      "refs": [
        {
          "alt": "Online mud course |earth architecture course|Mud workshop_07",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2ff1bda35fb3f6e77a8aa1a28a4419fb.png",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/305d113dea5dba41c733f1746d060186.webp",
    "context": {
      "refs": [
        {
          "alt": "Inspirit | Rammed Earth | Mud workshop_05",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/306cbde7a15211aba8b9f43671540374.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/30c3fe60c12dfb6ae7d5a24f853850fe.webp",
    "context": {
      "refs": [
        {
          "alt": "partnerSELCOFoundation",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/31b6100705fbb959a6184aee347e737d.webp",
    "context": {
      "refs": [
        {
          "alt": "The Brickloft| Architecture |Exposed Masonry | Reclaimed Wood |Bengaluru |Dining Room_6",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/322e0d2e78632de4a28f7454b6809018.webp",
    "context": {
      "refs": [
        {
          "alt": "Bamiyan Cultural Centre | Competition Entry_2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/32cc777b29c6f9bbc832128d53dbd3cd.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/32db46757ce562e65db9ad543bb2c535.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE Southern Heritage and Insights for Transformation Project Presentation at Paris",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/332f622c66b798682fc4f20032849b10.webp",
    "context": {
      "refs": [
        {
          "alt": "St.Johns Woods | Interiors | Master Bedroom Wardrobe_13",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3370d8bb7ff58b689f3d5740fe7ad3ea.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA Living Etc Cover Feature Casa 503, a Mediterranean-inspired Bengaluru Bungalow",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3385e8dafcf5de4c9bd8474b410cef3e.webp",
    "context": {
      "refs": [
        {
          "alt": "Snehadaan_Mud Architecture_CSEB_Carmelram_07",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/33fe444f9719eb7f9d152fb0205b8ef4.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3463c26b676374a56464f8f8efa42345.webp",
    "context": {
      "refs": [
        {
          "alt": "Rammed Earth Wall",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3585415bad84de20e7d82039f4fd5213.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/35c2a3f415c526fe85dd9b41883181d0.webp",
    "context": {
      "refs": [
        {
          "alt": "Earth Oven | Cob | Mud Workshop_03",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/365dc37a165eb7a781104d35bc004863.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/367b888d2f1e6727d1c9087f7e125ede.webp",
    "context": {
      "refs": [
        {
          "alt": "Courtyard House | Mud Architecture | Cochin | Seminar hall_05",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/36bdd06e82a35ba2a2835be4736e8482.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/36e24d89fb203ca67a062c77dd5c343d.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE NATCON 2025 Nashik Duanter",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/36f8d05a955f41eeefc55f3dabd78648.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/37ebd916c243d565eeab2df3f6975de3.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage Hunt| Hands On heritage_08",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/381df104d65b1eb5f1a2fc36c79c1fa1.webp",
    "context": {
      "refs": [
        {
          "alt": "Earth Oven | Cob | Mud Workshop_08",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/38570bd7d587fd8d74dbac6e36e588cb.webp",
    "context": {
      "refs": [
        {
          "alt": "Inspirit | Rammed Earth | Mud workshop_07",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/391eab73cd816402fa8fc03990a9fa70.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage Workshops",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/39d3307162dcca1a6def60c658accc90.webp",
    "context": {
      "refs": [
        {
          "alt": "Civic Fest| Heritage conservation |Hands on Heritage_06",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/39de0ed389dbb8b7deeb06582ec810cc.webp",
    "context": {
      "refs": [
        {
          "alt": "Yash Farms | Mud Architecture |CSEB |Rammed earth |Bengaluru |Courtyard_2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3a0e4ee63b81d23de3775cc65fe11e45.webp",
    "context": {
      "refs": [
        {
          "alt": "Maker Faire| Adobe | Public Exhibition_08",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3a9d78eb1045097dcf4fb8d0cea39533.webp",
    "context": {
      "refs": [
        {
          "alt": "Maker Faire| Adobe | Public Exhibition_03",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3aebfe5bbd815f23ac3394007c75f544.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA City Shapers Collective 1.0, BLR Design Centre Bengaluru and Beyond - Design shaping the City",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3aeea3edcca03b9e03cb9e51c4f6dbfd.webp",
    "context": {
      "refs": [
        {
          "alt": "Online mud course |earth architecture course|Mud workshop_05",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3aef512feff6c7f23548d32049bb8fe8.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3b101ee162ff11e7060167a7cdd2b121.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3c130408f1a95aeefa948aee29b9efe7.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3d432d1e5167ce66081f268c2df48ee0.webp",
    "context": {
      "refs": [
        {
          "alt": "Organic BPS| Office Interiors_7",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3db5639a14ee0f7cb0c8e8c81f0bebae.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3e56c619b371cda300b0471b5f60bdb6.webp",
    "context": {
      "refs": [
        {
          "alt": "St.Johns Woods | Interiors | Kitchen_4",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3ec7c1ff3a4d6d86866fa247675e8e2f.webp",
    "context": {
      "refs": [
        {
          "alt": "Nudge Foundation | Upcycled Interiors| Marketing room_08",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3ed09e10024a87e3ac78e70d491ec530.webp",
    "context": {
      "refs": [
        {
          "alt": "Inspirit | Rammed Earth | Mud workshop_01",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3f5cf9928f9722a3f84bf4833dfb9197.webp",
    "context": {
      "refs": [
        {
          "alt": "Human",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3f68940e37542864a1824cd878de542d.webp",
    "context": {
      "refs": [
        {
          "alt": "Esmeralda| Interiors |Bengaluru |Living room_1",
          "title": ""
        },
        {
          "alt": "1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4037c28e7f4206266107cf3a8692e220.webp",
    "context": {
      "refs": [
        {
          "alt": "Design Uru| Poured earth |Mud workshop_04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/40894be827b90969fd63c79659dd9382.webp",
    "context": {
      "refs": [
        {
          "alt": "Civic20207",
          "title": ""
        },
        {
          "alt": "Civic Fest| Heritage conservation |Hands on Heritage_07",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/40a26ba082e10a3a31985f5eaba49ead.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Hunt | Hands On Heritage_7",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/416911797ada34bfd9e3c8424514fc5f.webp",
    "context": {
      "refs": [
        {
          "alt": "Abode in Arabica",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/41b2c75e8954fa3bbee69193fda7150b.webp",
    "context": {
      "refs": [
        {
          "alt": "Ra Maram | Mud Architecture | Doddamanchi | Dining room_06",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4250c090e1a175b2ad8ce2a959f97aaf.webp",
    "context": {
      "refs": [
        {
          "alt": "NEWSLETTER",
          "title": ""
        },
        {
          "alt": "NEWSLETTER",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4263b02ab850e7f8212aa70ad3507f96.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage Hunt| Hands On heritage_04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/428e46b2d4d08287bef9ac70bdbf0846.webp",
    "context": {
      "refs": [
        {
          "alt": "Bottle wall | Cob | Mud Workshop_05",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/42fda860029f4c3587aed0605b71815c.webp",
    "context": {
      "refs": [
        {
          "alt": "YAF| wattle and daub |Tadelakt| Mud workshop_10",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/42ffb01e15d7f9feb2c39ab142546132.webp",
    "context": {
      "refs": [
        {
          "alt": "Masons Ink | Sustainable | Interiors | Barn door_6",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/43158ca8bd27b1f91c1cfefdd36c9243.webp",
    "context": {
      "refs": [
        {
          "alt": "The Brickloft| Architecture |Exposed Masonry | Reclaimed Wood |Bengaluru |Hallway_8",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/434028f013e4ee6528a90c0a62d648e1.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE International Seminar on Vernacular Settlements Vernacular Architecture in Climate Mitiga",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4396415951cde27dd2402a72470d86c6.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA BIOMIMIC THEORY Planet Pioneers",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/439bd06cea55879cb797a56f29f90d1c.webp",
    "context": {
      "refs": [
        {
          "alt": "Yash Farms | Mud Architecture |CSEB |Rammed earth |Bengaluru |Private Living_6",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/442f75bd224067dc7934247edf8a8616.webp",
    "context": {
      "refs": [
        {
          "alt": "Earth Workshop| CSEB | Mud workshop_04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/44c9f26ac56715f3d65b2b1d320321d7.webp",
    "context": {
      "refs": [
        {
          "alt": "Nudge Foundation | Upcycled Interiors| Entrance lobby_03",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/450d56c9781222ddaa1657e2f1bc9ffb.webp",
    "context": {
      "refs": [
        {
          "alt": "MessageMail",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4585acd7854d99c6bddc79518ca395b6.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Exhibition | Hands On Heritage_5",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/45b6d45436404b2aba009f900f0e5d92.jpeg",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/463fe742a8d0f4ec0e8d8fd4d772ed4a.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARDS FOAID 2020 Platinum Winner - Best Public Building",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/468cacab769e10cc1d39e918174bc3e8.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/46b8b70c920def6154ccf61380475263.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/47893fbb1bf323709871c05ab9665001.webp",
    "context": {
      "refs": [
        {
          "alt": "Design Uru| Poured earth |Mud workshop_03",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/47d7a53e8df0a3ad2cafd34a6d6a97f9.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARDS FOAID 2020 Platinum Winner - Green Building",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/47d7b9bc2ccb6daf22c0434cbd4cdbb9.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARDS SPACIUX DESIGN AWARDS 2022 Platinum Award - Commercial Architecture",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/484fe981af8c0bc476e083949f3f02aa.webp",
    "context": {
      "refs": [
        {
          "alt": "Esmeralda| Interiors |Bengaluru |Bedroom_13",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/485527013d2ec8bfd4c3a62a6fee55c1.webp",
    "context": {
      "refs": [
        {
          "alt": "Organic BPS| Office Interiors_2",
          "title": ""
        },
        {
          "alt": "Organic BPS",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/48a07b8ca7fc46cc3d544e19819bc42d.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA TEDx NITK SURATHKAL Grassroot Green Architecture",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/48ea8e40e50ad50d9757922f2f80e1ee.webp",
    "context": {
      "refs": [
        {
          "alt": "Mud Workshops| Mud Architecture_Barn restoration 15",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/48ec64d354a84a50891b69f72dea3762.webp",
    "context": {
      "refs": [
        {
          "alt": "aveirevised",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/49c802bfc0d1d970f6f3dd46ee072463.webp",
    "context": {
      "refs": [
        {
          "alt": "Design and build | Adobe | Mud Workshop_03",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4a0dc4322581b6a7e92641ff1e7ae807.webp",
    "context": {
      "refs": [
        {
          "alt": "Nudge Foundation | Upcycled Interiors| Admissions room_04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4a3209b5bcccb26a980f05a45d60ff1c.webp",
    "context": {
      "refs": [
        {
          "alt": "Esmeralda| Interiors |Bengaluru |Garden_7",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4b166328ace0d2e1d8302766d167a99c.webp",
    "context": {
      "refs": [
        {
          "alt": "Inspirit | Rammed Earth | Mud workshop_08",
          "title": ""
        },
        {
          "alt": "Inspirit 2019",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4b3c4b9810be387c81e6c5068cbbff52.webp",
    "context": {
      "refs": [
        {
          "alt": "Abode in Arabica | Mud House | Chikamagalur_2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4b40a3ea2c3aa2dc922597867c9ac271.webp",
    "context": {
      "refs": [
        {
          "alt": "Yash Farms | Mud Architecture |CSEB |Rammed earth |Bengaluru |Bedroom_7",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4b467f354f770fb4930406e51c2d1b4f.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_13",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4c3e777da58e65d22fdf177ac53d327f.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage Club| Hands On heritage_08",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4c45cd71a769824635753bc6fcb4bed6.webp",
    "context": {
      "refs": [
        {
          "alt": "Courtyard House | Mud Architecture | Cochin | Courtyard_07",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4c7ebfe7a1b77dc24681496af0cf0348.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE Built Environment, Design and Gender From Mud to Mastery: Stories of Resilience and Empow",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4cc08160a5d0db7b6ddc373d439b5a96.webp",
    "context": {
      "refs": [
        {
          "alt": "Esmeralda| Interiors |Bengaluru |Bedroom_9",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4ce8319bb60b0788d39921ba17d5f150.webp",
    "context": {
      "refs": [
        {
          "alt": "Courtyard House | Mud Architecture | Cochin | Artists studio_09",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4cee8f293ea2e5cf95b23d107c3931d1.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA DESIGN PATAKI Highlighting Mud Architecture",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4dd2d93fc25b5d33b0b72de49119f04f.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4de75ea828351cf837c8e0af68dc879d.webp",
    "context": {
      "refs": [
        {
          "alt": "Earth Workshop| CSEB | Mud workshop_07",
          "title": ""
        },
        {
          "alt": "kochi8",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4e68a031a0d5925616da3b60a1013b00.webp",
    "context": {
      "refs": [
        {
          "alt": "Casa 503| Architecture |Rattrap Bond |Bengaluru |Courtyard_5",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4ec324a422b70e8f49e713e2e59585dd.webp",
    "context": {
      "refs": [
        {
          "alt": "Yash Farms | Mud Architecture |CSEB |Rammed earth |Bengaluru |Powder room_10",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4ec5e1c315abec66abaa7412063e5261.webp",
    "context": {
      "refs": [
        {
          "alt": "Foundersbnwupdated",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4ef73526e5e10bf57bf5502e21934480.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE IHCN, BHUBANESWAR 2018 Role of Heritage in Urban Sustainability",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4fe3e92da6d82503965f171bd1b52f43.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage Hunt I",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5031eb99c3855b2f6b6e0f191e4fb6dc.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/506b7ea9387227a3cc4c22bb430d70fc.webp",
    "context": {
      "refs": [
        {
          "alt": "The Brickloft| Architecture |Exposed Masonry | Reclaimed Wood |Bengaluru |Living room _4",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/50e104073e49f5be75740e2b4bda6972.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5118fbe2638d9740f4230fc899b464c2.webp",
    "context": {
      "refs": [
        {
          "alt": "Esmeralda| Interiors |Bengaluru |Living room_3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/515750e94d8bcd59d8a5378a0bc0f728.webp",
    "context": {
      "refs": [
        {
          "alt": "Inspirit | Rammed Earth | Mud workshop_06",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/52781a3d305118e1e0a9cf7260e975d6.webp",
    "context": {
      "refs": [
        {
          "alt": "Hands-on workshop | Earth Water, Air and Fire Workshop",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/528009975a8c0bd340a0a18be9e3ef12.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA INSCAPE Think Local Act Local",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/52d1ab41453426bcd2deb6819f9a0934.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA HOMEGROWN 8 Indian Firms in Sustainability",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5342a6f217f716b89d784725816f6f13.webp",
    "context": {
      "refs": [
        {
          "alt": "Casa 503| Architecture |Rattrap Bond |Bengaluru |Living room_8",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5343a36a7b2314373b266cdd9b4450e1.webp",
    "context": {
      "refs": [
        {
          "alt": "Esmeralda| Interiors |Bengaluru |Garden_8",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/534bc1588547e8dac24c4e27f0b2e002.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Exhibition | Hands On Heritage_3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/53d206979a221890161b519e03248d9a.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Hunt | Hands On Heritage_6",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/540e69a18c84e61b77718c01ce21322d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/544edb71dfaf29e9673a7dcb1985f8ed.webp",
    "context": {
      "refs": [
        {
          "alt": "Casa 503| Architecture |Rattrap Bond |Bengaluru |Courtyard_6",
          "title": ""
        },
        {
          "alt": "5",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/54f1a46de8477702e857d4d2bb6ec75b.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARD INTBAU Grassroot Grantee Feature Keeping Building Traditions Alive: Masons Ink\u2019s work with wom",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/54fd62794ad3d7a8140ca0f43de6762a.webp",
    "context": {
      "refs": [
        {
          "alt": "Bottle wall | Cob | Mud Workshop_08",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/550624c7e8d40b9cee7a68529c4d91d5.webp",
    "context": {
      "refs": [
        {
          "alt": "Masons Ink | Sustainable | Interiors | Nameplate_2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/55377f2fc83236e9f14ebfd16492ec28.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5677e5cb317fe0343df808c651fd2b7e.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Workshop |Architetural Documentation | Hands On Heritage_05",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/570def3f3140385f36ab71302782ec21.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/57f1fbb334b763533d25adb38dcd96fd.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5824805644786ac2c27930a9e8f766ed.webp",
    "context": {
      "refs": [
        {
          "alt": "Bottle wall | Cob | Mud Workshop_01",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/586c191625a6bea4fa524e4870dd7c1d.webp",
    "context": {
      "refs": [
        {
          "alt": "YAF| wattle and daub |Tadelakt| Mud workshop_08",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/587fc14030db48df8a6c25ae6b08c756.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage Hunt| Hands On heritage_07",
          "title": ""
        },
        {
          "alt": "Heritage Hunt II",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/588328831916987d58390146307e0d13.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/589a6838ab77bf121365110b9264ce55.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/589d05b6079d1e055838e8eee0a0ebd8.webp",
    "context": {
      "refs": [
        {
          "alt": "SAMATVA IAAD BIENNALE",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/58bc9cd8d0810ea0c1b63f1463896ae6.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE BUILDINGS AND CLIMATE GLOBAL FORUM Heritage and the Existing Built Environment",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/58eed4f56780511edd046b00b60a9c32.webp",
    "context": {
      "refs": [
        {
          "alt": "Esmeralda| Interiors |Bengaluru |Study_11",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/599ca4a48fd1a8d3dd4147eabebc1c9b.webp",
    "context": {
      "refs": [
        {
          "alt": "Earth Oven | Cob | Mud Workshop_02",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/59b7e451bf4bb05faec62ab3a9fc48b0.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Exhibition | Hands On Heritage_15",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/59ef53d97c09425a6fcad73b58e85abe.webp",
    "context": {
      "refs": [
        {
          "alt": "Dhyaana_Mud Architecture_CSEB_Andevanapally_02",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5a0c611eb1a4e100f739c37866f0eac0.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5a5c77c5cdeedc80ee2bb2c4a13bd86c.webp",
    "context": {
      "refs": [
        {
          "alt": "St.Johns Woods | Interiors | Modular Kitchen_3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5a5e27498b523f0e4fc85210349ddf6a.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5a77f037c3523284ab9e77b7cbed504f.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5b05ecec9b2095689dcbe0db120dfff5.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_11",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5b1dc326a069b95ae8f44b4ee282b753.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE ODISHA HERITAGE MANAGEMENT PLANS Bubaneswar, India",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5b1eac04628e6e661712615a929d6e61.webp",
    "context": {
      "refs": [
        {
          "alt": "Ra Maram | Mud Architecture | Doddamanchi | Courtyard_10",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5b23cef9e5b3c3085279e69737a2a02e.webp",
    "context": {
      "refs": [
        {
          "alt": "Anavangot Tharavadu",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5b6d28cc1a8365a36b931d1fd1d82bb6.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA BETTER INDIA Sustainable Homes",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5bcd77871ffca009c9be812585293efd.webp",
    "context": {
      "refs": [
        {
          "alt": "Design Uru| Poured earth |Mud workshop_01",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5bda4100cd1d81aa97505351a2154c9d.webp",
    "context": {
      "refs": [
        {
          "alt": "Hobbit Series - Rajasthani Lime Plastering",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5bfed21f23c6343eeeb5664f7466d854.webp",
    "context": {
      "refs": [
        {
          "alt": "Snehadaan_Mud Architecture_CSEB_Carmelram_02",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5cb7f5a2f61dc77dbc069433f98008a0.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5ccfdcc7b715d599870f4826eb3aa594.webp",
    "context": {
      "refs": [
        {
          "alt": "Earth Workshop| CSEB | Mud workshop_01",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5dbb8c6f47456360e09d0868fed63ab4.webp",
    "context": {
      "refs": [
        {
          "alt": "Casa 503| Architecture |Rattrap Bond |Bengaluru |Master bathroom_13",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5de0aad3bd208fc75036dfc7fc2ee76a.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_15",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5de7c82efca12f70f671f5c240af2a3c.webp",
    "context": {
      "refs": [
        {
          "alt": "Hands",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5f3eaf109777a1211477b67f99923b1d.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE YOUNG ARCHITECTS FESTIVAL Crossroads 2022",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5fc8a36e1b97899cd18d29766c98a417.webp",
    "context": {
      "refs": [
        {
          "alt": "St.Johns Woods | Interiors | Kids Bedroom_10",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5fed2bc0b24120e6696f1b1e382f761d.webp",
    "context": {
      "refs": [
        {
          "alt": "Civic Fest| Heritage conservation |Hands on Heritage_08",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/60235a375249c5c2b7b246a679f79f8d.webp",
    "context": {
      "refs": [
        {
          "alt": "Casa 503| Architecture |Rattrap Bond |Bengaluru |Kitchen_10",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/60a1b1766c7ee0f38f0cb9c3c28e505c.webp",
    "context": {
      "refs": [
        {
          "alt": "Ra Maram | Mud Architecture | Doddamanchi | Living room_05",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/60a4f441d50795507cefa984c063eb8a.webp",
    "context": {
      "refs": [
        {
          "alt": "The Brickloft_Architecture_Exposed Masonry_Reclaimed Wood_Bengaluru_Lobby_13",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/613531c5e4ecd24d4a41f4c8d8bb1e28.webp",
    "context": {
      "refs": [
        {
          "alt": "Cheerville | Earthbag | Sustainable Architecture",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/622d21fc262b3fdd92c9a60ba5cb8b19.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Workshop |Architetural Documentation | Hands On Heritage_01",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6263eb6b44ca5fef38c86ed4137cd47a.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARDS ID HONOURS 2023 Sustainable Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/62974627f57d7823deff537b837d8ab9.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/62d570bc191289b1915a958b10535c3f.webp",
    "context": {
      "refs": [
        {
          "alt": "Earth Oven | Cob | Mud Workshop_04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/63a1ba6d6cb192cc7741093cd0723ee8.webp",
    "context": {
      "refs": [
        {
          "alt": "Gtac | Office | Interiors | Conference room_2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6531edfb73414b374b5c4394abd5f94f.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARDS FOAID 2021 Platinum Winner - Residential Villa",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6554f64567d8d82d226c9969ba07f869.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/655d2276feecba7225abc494fc7ede41.webp",
    "context": {
      "refs": [
        {
          "alt": "St.Johns Woods | Interiors | Master Bedroom_12",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/65782b1d883d817d8e6ff9195c290e7f.webp",
    "context": {
      "refs": [
        {
          "alt": "Online mud course |earth architecture course|Mud workshop_06",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/663311e1bfdbeb3a41699b5dac9f1237.webp",
    "context": {
      "refs": [
        {
          "alt": "Ra Maram | Mud Architecture | Doddamanchi | Bedroom_12",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6707278a2ec787fc0d3a64bcf36d10ce.webp",
    "context": {
      "refs": [
        {
          "alt": "St.Johns Woods | Interiors | Formal Living Room_7",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6746ff264f78b688f026d1f5719261d5.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE Dasra Philanthropy Week X ClimateRISE Alliance Panel Discussion on Redefining the Built E",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/677ac86a2eee435341cecfa41c4a83dd.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA SIGNARCH STUDIO Earthen Roots Talk Series",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/67df47c2dbe26a5fd4269d9f28324706.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6814ff2139ea2cb844c53d67bc8d957b.webp",
    "context": {
      "refs": [
        {
          "alt": "Mud Workshops| Mud Architecture_Scrafitto 06",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6836049b03eef6a147acae3702ebbb34.webp",
    "context": {
      "refs": [
        {
          "alt": "Esmeralda| Interiors |Bengaluru |Living room_2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/69144b165f4a8d55a3b770a9ced20f3e.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Hunt | Hands On Heritage_5",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/694cc13dbb54e2ddc1ba095d80cd0dfc.webp",
    "context": {
      "refs": [
        {
          "alt": "Sustainable Architecture | The Sun and Earth Festival",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/69ec123d66cf7377202848bd1ad23b90.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Exhibition | Hands On Heritage_7",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6a350c60bc614268bf0c0ed460faff6c.webp",
    "context": {
      "refs": [
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6a43baffc5222d3ea255cf65019a1c62.webp",
    "context": {
      "refs": [
        {
          "alt": "Civic Fest| Heritage conservation |Hands on Heritage_02",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6a7747cf6aadcf664c9db45d2157e2a0.webp",
    "context": {
      "refs": [
        {
          "alt": "Earth Oven | Cob | Mud Workshop_07",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6a9e5cd0735af94e72229c5796f1f7f1.webp",
    "context": {
      "refs": [
        {
          "alt": "Thappi Workshop, Marseille, France",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6b0df135040915146bfad9898b03a2da.webp",
    "context": {
      "refs": [
        {
          "alt": "Maker Faire| Adobe | Public Exhibition_09",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6be8ddf23fba88b2035857f7c15d93ee.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6c1bca17c37ccdf91ad71d297c9eeb83.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA The Sustainable Design Showcase Panel Discussion on Sustainability",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6c27da71fe87bbd250810fcf7b4a93a1.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE G20 CULTURAL MINISTERIAL Culture based Solutions driving Climate Actions",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6c7dbbf3e0e09412e5c0fb98aad7a6e9.webp",
    "context": {
      "refs": [
        {
          "alt": "Public - Heritage Exhibition",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6d7c96a366ed13d08ea03c64a97972fb.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6e0db5cfd746de9ef7f77acdd21c836d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6ee24ae71656a2ba6b5480ae2c7abc13.webp",
    "context": {
      "refs": [
        {
          "alt": "Snehadaan_Mud Architecture_CSEB_Carmelram_06",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6f067dcd5f4c8ee03cdb6b0ad8bf2752.webp",
    "context": {
      "refs": [
        {
          "alt": "INTACH | Hands-on Workshop | Tadelakt",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6f0e98d152a0d064ec700f2a6d335099.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6f1a1d42ecd9346a76378e6c80e83eb2.webp",
    "context": {
      "refs": [
        {
          "alt": "St.Johns Woods | Interiors | Kids Bedroom storage_11",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6f4b285a8801d729de3891716658780c.webp",
    "context": {
      "refs": [
        {
          "alt": "Casa 503| Architecture |Rattrap Bond |Bengaluru |Master balcony_14",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6fef8c5c076d2286ede1dc8fccd0f2cb.webp",
    "context": {
      "refs": [
        {
          "alt": "Design and build | Adobe | Mud Workshop_06",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7011bd23399b210cb5ac1315527c219f.webp",
    "context": {
      "refs": [
        {
          "alt": "Snehadaan_Mud Architecture_CSEB_Carmelram_03",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/70d14b78a30104f63968869dfe29a631.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/721babc928dc62431aab85924daf42f3.webp",
    "context": {
      "refs": [
        {
          "alt": "MessageMail",
          "title": ""
        },
        {
          "alt": "MessageMail",
          "title": ""
        },
        {
          "alt": "MessageMail",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7245ee50bee1fef719576c48b0cb276c.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_19",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/726223d3c78f77fb36542da9014e2c52.webp",
    "context": {
      "refs": [
        {
          "alt": "jardin2Mud Workshops| Mud Architecture_Jardin Immaginaire 04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/728b3483e5f1d1e4d77c31699bb8e5d6.webp",
    "context": {
      "refs": [
        {
          "alt": "Design and build | Adobe | Mud Workshop_07",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/72aed29bac5bbffb762062c96c39f3dd.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE Adizya 2025, NIT, Calicut Panelist for The Living Fabric: Weaving Vernacular Wisdow into ",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/72d62d6372dd16a91130232153c97a11.webp",
    "context": {
      "refs": [
        {
          "alt": "Newsletter | Issue 2/Nov 2016",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/72df80732f32cd2f587e59164385d918.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE COP 27 - UN CLIMATE CHANGE CONFERENCE Culture @ COP 27",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/732a5a056f08103a8f8e1cfb628b2904.webp",
    "context": {
      "refs": [
        {
          "alt": "Mannu Kattu House",
          "title": ""
        },
        {
          "alt": "Mannu Kattu House| Mud Architecture |Heritage Conservation | Coimbatore | Cob | Courtyard_1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7379b79572f02b6afe92ae836bd23aba.webp",
    "context": {
      "refs": [
        {
          "alt": "The Heritage On Wheels report",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7501b4a7a11d1b8817c660e186ff9172.webp",
    "context": {
      "refs": [
        {
          "alt": "Courtyard House | Mud Architecture | Cochin | Main Entrance_03",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/758e4213fc28dae599695f18140c4470.webp",
    "context": {
      "refs": [
        {
          "alt": "Indian Council of Historic Research",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/759f65cd891914af48672a3c45342e53.webp",
    "context": {
      "refs": [
        {
          "alt": "Courtyard House | Mud Architecture | Cochin | MD's Cabin_11",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/75a386da531bd70868ea5bd44b21e36a.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/75ec426264ced9dbd530c6ef6b8de184.webp",
    "context": {
      "refs": [
        {
          "alt": "Online mud course |earth architecture course|Mud workshop_04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/76055fb2a94595e72cf117e0b0ea16c5.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Workshop |Architetural Documentation | Hands On Heritage_03",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/766b6aea9ea9b04e522172ab85226728.webp",
    "context": {
      "refs": [
        {
          "alt": "SNEHADAAN",
          "title": ""
        },
        {
          "alt": "Snehadaan_Mud Architecture_CSEB_Carmelram_01",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/76860d5c8b967cfa7f23aecfa6d2e39d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/770ed4ac9bfff9fa6c9eb52aef00c397.webp",
    "context": {
      "refs": [
        {
          "alt": "Gtac | Office | Interiors | Workstation_7",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/77f12c05f20618f38c562d9f55491e74.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA FEVER 104 Architects with a difference",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7809d85e18332c49a493a8df9fd10c51.webp",
    "context": {
      "refs": [
        {
          "alt": "INTERNATIONAL WORKSHOPS",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7857e32075171a35fc68a0c3b192ff03.webp",
    "context": {
      "refs": [
        {
          "alt": "Indian Art, Architecture and Design Biennale",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/791d15c97d025f114cb5bd6d84c70abc.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE CIPA 2025 Seoul Integrating Manual and Digital Techniques in Heritage Documentation: Deve",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/79e6fa1d070707082c7334dc8ab0a6de.webp",
    "context": {
      "refs": [
        {
          "alt": "Abode in Arabica | Mud House | Anteroom | Chikamagalur_5",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7a070734b1e4133fa4e839181aa9a185.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA Feature Stories on PYNR Harnessing mud and clay for climate-resilient architecture",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7a2b1ee38be806f30587b7052c80497f.webp",
    "context": {
      "refs": [
        {
          "alt": "Nudge Foundation | Upcycled Interiors| Product design room_09",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7b9df4e52eb4a63c9274718ad2b5a8e1.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_20",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7ba52891988652d6a8a6f70de708a6df.webp",
    "context": {
      "refs": [
        {
          "alt": "Mannu Kattu House",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7bb40a29a17affdf277f18e8c95af6fe.webp",
    "context": {
      "refs": [
        {
          "alt": "Maker Faire| Adobe | Public Exhibition_04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7c4d5a78a435510002dfb0879a39e75a.webp",
    "context": {
      "refs": [
        {
          "alt": "Nudge Foundation | Upcycled Interiors| Entrance porch_10",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7c4ec446f0475d362fa13c98ba252a37.webp",
    "context": {
      "refs": [
        {
          "alt": "FORMATION - DECOUVERTE DES ENDUITS TERRE & CHAUX",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7d251d46d62c3143598cc1e99bae8523.webp",
    "context": {
      "refs": [
        {
          "alt": "Maker Faire| Adobe | Public Exhibition_01",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7ee4eec288a9a0f9f75447b31c8cb728.webp",
    "context": {
      "refs": [
        {
          "alt": "Civic Fest| Heritage conservation |Hands on Heritage_03",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7eebb05f961c1b75524ad45965efd072.webp",
    "context": {
      "refs": [
        {
          "alt": "Casa 503| Architecture |Rattrap Bond |Bengaluru |Bathroom_16",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8083c00420b4ca64f303ba34f68016a4.webp",
    "context": {
      "refs": [
        {
          "alt": "Inspirit | Rammed Earth | Mud workshop_04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/80b7d1216fa6f9c6e05d67c5b03182ed.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_21",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/80d6c7a839ca19fdc719084fc4f5e75f.webp",
    "context": {
      "refs": [
        {
          "alt": "Dhyaana_Mud Architecture_CSEB_Andevanapally_01",
          "title": ""
        },
        {
          "alt": "DHYAANA",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/810332d2e493ea9eda7cc29975e9466a.webp",
    "context": {
      "refs": [
        {
          "alt": "image description",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8136f5bf6b09889a20678e9291d8fb38.webp",
    "context": {
      "refs": [
        {
          "alt": "Design Uru| Poured earth |Mud workshop_07",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/814fd9164b7a41eb40d0c8348e17398d.webp",
    "context": {
      "refs": [
        {
          "alt": "Ra Maram | Mud Architecture | Doddamanchi | Feature Wall_09",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/817614b6a2b613bb2e84b6d5f67fb851.webp",
    "context": {
      "refs": [
        {
          "alt": "Earthen Weaves| wattle and daub |Mud workshop_05",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/81859db2b9c33bafc4541663f927613f.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Workshop |Architetural Documentation | Hands On Heritage_10",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/81e83e1cb0f35fb0f52221b80befff7d.webp",
    "context": {
      "refs": [
        {
          "alt": "St.Johns Woods | Interiors | Formal Living_8",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/81f1cfeea45d9f4f5e1e832b0263bd19.webp",
    "context": {
      "refs": [
        {
          "alt": "Casa 503| Architecture |Rattrap Bond |Bengaluru |Master bedroom_11",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8200d3aa0607ca3bc26863cd4b858356.webp",
    "context": {
      "refs": [
        {
          "alt": "Casa 503| Architecture |Rattrap Bond |Bengaluru |Staircase_7",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/827b0da95416f297e5f63f5e66859e05.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8283eaa1f3186ade3727475e26655b5b.webp",
    "context": {
      "refs": [
        {
          "alt": "Bottle wall | Cob | Mud Workshop_03",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/82a76aab8bbfc67c9b604277e2e0e653.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE TERRA EDUCATION, FRANCE 2018 Perspectives for Development",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/83a9c51bffc8ca8545fcdde42753f569.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Exhibition | Hands On Heritage_8",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/83adf65ca17e8fea3676d29ce60f8088.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA The Architects\u2019 Diaries\u2019 TADPOD How to Build with Mud?",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/844fcb62e7fa5f04eef3f3d02de7ec00.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE ISES, INDIA 2018 Earthen Dwellings and Structures",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/84830e6ada9a25d184e4a0b12ac98e32.webp",
    "context": {
      "refs": [
        {
          "alt": "Gtac | Office | Interiors | Modular | detachabletable_3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/84aff6a097e8531f503463888489a810.webp",
    "context": {
      "refs": [
        {
          "alt": "Maker Faire| Adobe | Public Exhibition_06",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/85252bff55a4e2f1fd52d2f06797f19b.webp",
    "context": {
      "refs": [
        {
          "alt": "St.Johns Woods | Interiors | Wardrobe_15",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8552dc54eca1c123701fd5ed358cc0ad.webp",
    "context": {
      "refs": [
        {
          "alt": "Architecture_CSEB_Andevanapally_03",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/863bdf4acb7736a72879dd9c45426376.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage Hunt| Hands On heritage_01",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/86d0560ef1b5704a0e77f5cf24368822.webp",
    "context": {
      "refs": [
        {
          "alt": "Bottle wall | Cob | Mud Workshop_04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/86d0ab570f80f36d684c8acb0f72f08e.webp",
    "context": {
      "refs": [
        {
          "alt": "Bamiyan Cultural Centre | Competition Entry_7",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/86e0fbc48a84dad1a4a000609777fc6e.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/86fa4261a67aac56884bc843b8feb193.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/87c1e609661522aed4a8d2f1ad121721.webp",
    "context": {
      "refs": [
        {
          "alt": "The Brickloft| Architecture |Exposed Masonry | Reclaimed Wood |Bengaluru | Entrance _16",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/87e52fc9d4dd5f567b79b4cf53b70dec.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8874c164a99963fdc1b55df83b58e8d6.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/897f34951cd4a258fc68ad72e5c68f22.webp",
    "context": {
      "refs": [
        {
          "alt": "Bungalow 7",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/89aba4a4a590aacbdd22639743fb9efe.webp",
    "context": {
      "refs": [
        {
          "alt": "Masons Ink | Sustainable | Interiors | Library_8",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8a52ca9df5800a3d528bb87cd68ed6f5.webp",
    "context": {
      "refs": [
        {
          "alt": "Architecture_CSEB_Andevanapally_05",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8b3dae9c483140df5b7115d5d891a174.webp",
    "context": {
      "refs": [
        {
          "alt": "Earth Workshop| CSEB | Mud workshop_06",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8b67e51d575f2067cc469fe1f4b07ed7.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8b766c6ee8fb245fd0eae5e6bc73e05a.webp",
    "context": {
      "refs": [
        {
          "alt": "St. Johns Woods | Interiors | Partition Detail_1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8ca713301a4d814e6fa88160c60e0f8f.webp",
    "context": {
      "refs": [
        {
          "alt": "Ra Maram | Mud Architecture | Doddamanchi | Oxide finish Bathroom_14",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8df1b2d13b3555da28995c1e655e46fd.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage Hunt| Hands On heritage_05",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8dfbb4948d66e5b6476835cc1b23454e.webp",
    "context": {
      "refs": [
        {
          "alt": "Designnbuild",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8ededa4054f4faeaf24aa440ffa164ca.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARDS TERRA FIBRA AWARD 2021 Finalist - Public Education and Sport Facilities",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8efd25cd188416eed0c2d55109cddc34.webp",
    "context": {
      "refs": [
        {
          "alt": "Inspirit | Rammed Earth | Mud workshop_02",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8f1f5ab5eea1e69805dc460d188d31e4.webp",
    "context": {
      "refs": [
        {
          "alt": "The Brickloft| Architecture |Exposed Masonry | Reclaimed Wood |Bengaluru |entrance lobby_15",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8fafd4bfcce34e49deb132544388dd99.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARDS THE MERIT LIST The Merit List Shorlist",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8fd653a80015cae4e9d64b4158c2d4cc.webp",
    "context": {
      "refs": [
        {
          "alt": "Casa 503| Architecture |Rattrap Bond |Bengaluru |Master bedroom_12",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/90e2cf8a7b554a4c1ac41520745cabb2.webp",
    "context": {
      "refs": [
        {
          "alt": "Hobbit Series - Gabion Walls",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/91f0b5bcb148033602552f4ee87facf3.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage Club| Hands On heritage_06",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9227477a7687270c000a25508273f82e.webp",
    "context": {
      "refs": [
        {
          "alt": "The Brickloft| Architecture |Exposed Masonry | Reclaimed Wood |Bengaluru |Kitchen_7",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/926b4593eec4e4a19a59215baa40992e.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA Elev8 Bangalore Featured Exhibitor",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/92aed835ab8758cc557e45831249a8e3.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/935620b22962b25bea2a03dac33f15ba.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA Scale Qatar Building with Memory and Material: Masons Ink Studio",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/93635baedf52b00197b399bdfd5ea7f2.webp",
    "context": {
      "refs": [
        {
          "alt": "Earthen Weaves| wattle and daub |Mud workshop_04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/93b7a364ded0042ca1b4b6224fdbdd6f.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Hunt | Hands On Heritage_2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/93f2b987da37a08bc8096f460f6e82c8.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_06",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/947a459a4e05fe531ed65c42ad255918.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/950c7120f2937ab882987daa15913a16.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA IAAAD BIENALLE 2023 Samatva - Exhibition Honoring work of 80 women architects",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/953bb1379ee50acd865a1bc298324328.webp",
    "context": {
      "refs": [
        {
          "alt": "Esmeralda| Interiors |Bengaluru |Study_10",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/95f6ae9b5fd1ffac503d42d5f238c12a.webp",
    "context": {
      "refs": [
        {
          "alt": "Gtac | Office | Interiors | Reception_5",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/970ede0f633de772b94f6e3497b94687.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/97ac9ef0b9836ca7ca9494acfb85903e.webp",
    "context": {
      "refs": [
        {
          "alt": "Earthen Weaves| wattle and daub |Mud workshop_06",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/97ed74f6f8f0fa9bfc5a18cdfdd1dc1d.webp",
    "context": {
      "refs": [
        {
          "alt": "Architecture_CSEB_Andevanapally_04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/98adc87a434f50fb1fe4c576e71f4820.webp",
    "context": {
      "refs": [
        {
          "alt": "Yash Farms | Mud Architecture |CSEB |Rammed earth |Bengaluru |Study_9",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/98e300e1dc6bdc4b42c49e57d5f39c9e.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Hunt | Hands On Heritage_1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/992df6885cbaab81fe3cda2ef09c989b.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARDS HOUSE BY ARCHDIAS 2019 First Runner up",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/996e6769dd7f54a09dc7e065e3c21a48.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Hunt | Hands On Heritage_3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9a2556f5f7dd1d10c1d3f6c2a060e3e0.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9a417405ce79edf216ee87312827076a.webp",
    "context": {
      "refs": [
        {
          "alt": "St.Johns Woods",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9a527853aed34721dc7c8d3c2d097220.webp",
    "context": {
      "refs": [
        {
          "alt": "aveirevised",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9ad8c1b332f892feca2f8cfb7b3cba8e.webp",
    "context": {
      "refs": [
        {
          "alt": "Masons Ink | Sustainable | Interiors | frames_7",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9b06278a167a9979ce2703b476c3c21a.webp",
    "context": {
      "refs": [
        {
          "alt": "The Brickloft| Architecture |Exposed Masonry | Reclaimed Wood |Bengaluru |Living room _2",
          "title": ""
        },
        {
          "alt": "1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9bfad8fbfdf4fb60a91c77b4130cf34b.webp",
    "context": {
      "refs": [
        {
          "alt": "Newsletter | Issue 4/Jan 2018",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9c6e528e7ae5df56b44ec8073d77730c.webp",
    "context": {
      "refs": [
        {
          "alt": "Bamiyan Cultural Centre | Competition Entry_3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9ca221abf33ee647713043d91da6e684.webp",
    "context": {
      "refs": [
        {
          "alt": "Newsletter | Issue 7/Sept 2020",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9d4352f2c7daf129469c8d18cc10a827.webp",
    "context": {
      "refs": [
        {
          "alt": "Ra Maram | Mud Architecture | Doddamanchi | Day view_03",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9d67d1b0ef4fcfb291ef18db9ea6df87.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA The Showcase Featuring The COurtyard",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9d8361f07c1a44f8cefcaa0363566218.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9e2209a95a1a0304fcc9b52964038446.webp",
    "context": {
      "refs": [
        {
          "alt": "Bottle wall | Cob | Mud Workshop_06",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9e6c5b647fa29ad21cb909c842b0ccd3.webp",
    "context": {
      "refs": [
        {
          "alt": "Inspirit | Rammed Earth | Mud workshop_03",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9f36b0e650a70e39de4dd525e925baad.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a0c95dcbf16f64c5ded3e43b3c984755.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a11612b7b4e28a6e6de9b2ed08df03f0.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Exhibition | Hands On Heritage_12",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a18f6d629ad851f000acf991451e9645.webp",
    "context": {
      "refs": [
        {
          "alt": "Jayamahal",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a27a4acca0fdb3efe786c52a09e7784e.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a3837c8cbf450745b848192e21c9d715.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_07",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a61ba135ff2aba33a065be356c2505bb.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA UN STORY A Masons Ink Feature",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a628b5ea4715dbdf6ed70586acc3b0dc.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage Hunt| Hands On heritage_06",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a66c48646350f350ffcfdf0103b7aeff.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage Club| Hands On heritage_04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a66f08b99bff35f04ff9689e643d1673.webp",
    "context": {
      "refs": [
        {
          "alt": "craterre",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a67b77c2451c6533f3c34e1b4b527932.webp",
    "context": {
      "refs": [
        {
          "alt": "YAF| wattle and daub |Tadelakt| Mud workshop_07",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a6949688ae945794a02b437d9563a7ac.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a736fc50ee3a32ec0f24579cef0123fe.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a7a8e7e6acd3d020790d705b4589ac7f.webp",
    "context": {
      "refs": [
        {
          "alt": "St.Johns Woods | Interiors | Dining Room_6",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a8822f1e6f7d44882c6b400b56dc9bc9.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a8fa3f3428f222fba591916e816004ae.webp",
    "context": {
      "refs": [
        {
          "alt": "coverpage",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a96f06aa8c2f5a86faefbbb5bb1d0155.webp",
    "context": {
      "refs": [
        {
          "alt": "NHVPS - Heritage Club",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a9b451971c7a442044e658c7f16beb59.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA The Hindu Property Plus Featuring Brick Loft - a home designed for pets and humans alike.",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ac35beccf8e71cb490a1108f61c77542.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARDS WADE ASIA 2022 Runner up - Young Emerging Architects",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ad651ea61cd199c87554790450adb780.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARDS 2ACAA INTERNATIONAL AWARDS'19 Finalist - Best Public Building",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/adf8f2cab95860b2bb571db5215b52c4.webp",
    "context": {
      "refs": [
        {
          "alt": "Masons Ink | Sustainable | Interiors | foyer_1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ae9db793055bfe10720ee4ead8a0e091.webp",
    "context": {
      "refs": [
        {
          "alt": "Earthen Weaves| wattle and daub |Mud workshop_08",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/aea56f928a22c940aaf195c8f889ca39.webp",
    "context": {
      "refs": [
        {
          "alt": "Nudge Foundation | Upcycled Interiors| Internal meeting room_05",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/af1c5860c530fd18191a70b71ded08a2.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARDS VANITHA VEEDU DESIGN AWARDS'18 Young Architect of the Year",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/afca56b564b2bfee490e54ab362e0c5b.webp",
    "context": {
      "refs": [
        {
          "alt": "The Brickloft| Architecture |Exposed Masonry | Reclaimed Wood |Bengaluru |Master Bedroom_9",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b01b6b0bcef1f2ae6b1788a2ed5f1c2b.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage Club| Hands On heritage_07",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b0d8a52af9705875479716cc31092feb.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b138084f00d66a165bac475cf3905b49.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b2f880baaa5a3b0048abdc4f322fde32.webp",
    "context": {
      "refs": [
        {
          "alt": "Earth Oven | Cob | Mud Workshop_05",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b3b24cda6fe143a672172a7efa7c7809.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage Hunt| Hands On heritage_02",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b43e763f72dd30bd3b499467d7ed636f.webp",
    "context": {
      "refs": [
        {
          "alt": "Ra Maram | Mud Architecture | Doddamanchi | Night view_01",
          "title": ""
        },
        {
          "alt": "Raa Maram",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b4cbf4877d182f932a34b0b28a236568.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA Zenden Media\u2019s House Tour of Brick Loft This 2BHK Bangalore Home Proves Budget Doesn\u2019t Mean Co",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b4f75e493b1e8c49c8e737482b35f7fc.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b52c3c361ded3fffae21f9ab757f3338.webp",
    "context": {
      "refs": [
        {
          "alt": "St.Johns Woods | Interiors | Foyer_2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b5358e40c41e5fbcfee2ecea7f192ab2.webp",
    "context": {
      "refs": [
        {
          "alt": "Courtyard House | Mud Architecture | Cochin | Courtyard_06",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b6972339aeca3becbe407f69185f5d05.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b6fe936dc33b2b935d6e3ea9e34cb685.webp",
    "context": {
      "refs": [
        {
          "alt": "Rammed Earth | Hands-on workshop",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b78002c27ceddf9178272ecc199bb6f4.webp",
    "context": {
      "refs": [
        {
          "alt": "The Brickloft| Architecture |Exposed Masonry | Reclaimed Wood |Bengaluru |Living room _1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b7c52f53a80bc37d6df6894af1f75cbe.webp",
    "context": {
      "refs": [
        {
          "alt": "Design Uru| Poured earth |Mud workshop_02",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b7ff348f2704113d83f298e03e458deb.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE 2ACAA INTERNATIONAL AWARDS'19 Interaction Forum",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b92cc04e91210513e077e5e0f9bc7e71.webp",
    "context": {
      "refs": [
        {
          "alt": "Courtyard House | Mud Architecture | Cochin | Reception_10",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b9cf3a7f7add4143e984b0e3315cfb72.webp",
    "context": {
      "refs": [
        {
          "alt": "Esmeralda| Interiors |Bengaluru |Study_15",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ba2ffd24412d361e5fd0cf3e87f83b48.webp",
    "context": {
      "refs": [
        {
          "alt": "Bamiyan Cultural Centre | Competition Entry_5",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bb60a2f089693c01f243b6c476d48682.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA Scroll.in Eco India Can sustainable architecture really beat the urban heat?",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bb7f8a29ddfae6b4b00d6a6ca9059c06.webp",
    "context": {
      "refs": [
        {
          "alt": "Courtyard House | Mud Architecture | Cochin | MI Office_08",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bbba4ca4361eb07c4cc6a6fbe693a03f.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARDS DVL EARTH BUILDING PRIZE Traditional Additives in Earth Building (R&D)",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bbc189babb236dba825fe19aa7c5699b.webp",
    "context": {
      "refs": [
        {
          "alt": "Maker Faire| Adobe | Public Exhibition_02",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bd6b07be4dbe5f12597b994ca87139e6.webp",
    "context": {
      "refs": [
        {
          "alt": "Bottle wall | Cob | Mud Workshop_07",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bdf9f5ba2c35e233202036bc05d386de.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARDS SURFACE DESIGN INTERNATIONAL AWARDS Finalist - Housing Interior",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/be52f031650b3b71f62a9bcd02338439.jpeg",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/be5311cebed9e7359fd8074a24cb974c.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_09",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bef85f6d460928976055b78733f0ceb6.webp",
    "context": {
      "refs": [
        {
          "alt": "Maker Faire| Adobe | Public Exhibition_07",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bf920ba1242456e486d250207a10f124.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage Hunt| Hands On heritage_03",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bf9c08078040bd16cd62f914646e9c62.webp",
    "context": {
      "refs": [
        {
          "alt": "Earth Oven | Cob | Mud Workshop_06",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c06f18722bb8f1425ab5c3fe8a24bace.webp",
    "context": {
      "refs": [
        {
          "alt": "Gtac | Office | Interiors | Workarea_8",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c126a31862e5004886a57976f5a369e8.webp",
    "context": {
      "refs": [
        {
          "alt": "Ra Maram | Mud Architecture | Doddamanchi | Night view_02",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c137df909396115501501a5d50c50273.webp",
    "context": {
      "refs": [
        {
          "alt": "Organic BPS| Office Interiors_8",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c1436af3afc7580e74c8031a985a6038.webp",
    "context": {
      "refs": [
        {
          "alt": "Abode in Arabica | Mud House | Chikamagalur_1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c15da8a12972336b29d9547f9fd37267.webp",
    "context": {
      "refs": [
        {
          "alt": "The Hands On Heritage report",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c16416cf8031c93a78caa8def10427a9.webp",
    "context": {
      "refs": [
        {
          "alt": "Earthen Weaves| wattle and daub |Mud workshop_02",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c1a95c114372b5308afa13450585a132.webp",
    "context": {
      "refs": [
        {
          "alt": "Esmeralda| Interiors |Bengaluru |Library_6",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c1b8259a7c1578ea0336dffe55f6aae7.webp",
    "context": {
      "refs": [
        {
          "alt": "Courtyard House | Mud Architecture | Cochin | View_01",
          "title": ""
        },
        {
          "alt": "Courtyard House",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c2ab59f38c7671a46ce0f8e6b2114703.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARDS DH CHANGEMAKERS Winner - Changemakers 2020",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c317700b2698c56a454f7c92f373cf70.webp",
    "context": {
      "refs": [
        {
          "alt": "YAF",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c35af51b2347716026c773804abb4471.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c3c3df0a981b04fa4036e97228786acb.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARD Women Climate Collective Women Inclusive Climate Action",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c4b4a05eb0f6006ace503f57100c577c.webp",
    "context": {
      "refs": [
        {
          "alt": "Casa 503| Architecture |Rattrap Bond |Bengaluru |Bedroom_15",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c4b556e90520422c6501ed0099aea15b.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARDS CONSTRUCTION WORLD AWARDS'20 Winner - Noteworthy Project",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c53885412d228c261fd6fd73ed32d746.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c63f78970c2a70d9e654a8121050ddb9.webp",
    "context": {
      "refs": [
        {
          "alt": "Gtac | Office | Interiors | modular | conference table_4",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c668f252380c8fa3a9658208f55f4021.webp",
    "context": {
      "refs": [
        {
          "alt": "Mannu Kattu House| Mud Architecture |Heritage Conservation | Coimbatore | Cob | Courtyard_2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c68eada1c5644e6ff757ef5a332a4ebd.webp",
    "context": {
      "refs": [
        {
          "alt": "Civic Fest| Heritage conservation |Hands on Heritage_01",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c6931b1c8c009c3215acf4a792ef3a39.webp",
    "context": {
      "refs": [
        {
          "alt": "Ra Maram | Mud Architecture | Doddamanchi | Wrap around verandah_11",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c751278bcda5bf217c88bdee90f7c49b.webp",
    "context": {
      "refs": [
        {
          "alt": "Araish | Lime Plaster | Hands-on Workshop",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c7597554a918b59875c76644fb1b59ef.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c7a2eb31d9b8caf41cdb3b63fae20e45.webp",
    "context": {
      "refs": [
        {
          "alt": "YAF| wattle and daub |Tadelakt| Mud workshop_05",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c7efee977c1b34e49ca2909fc2cc9b1c.webp",
    "context": {
      "refs": [
        {
          "alt": "Newsletter | Issue 6/July 2019",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c89a12e7aacc1eb77a62c3c2c4ba8fe6.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c94d237368384ba678079abcb5c0ddaa.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA Vogue India - Culture & Living Reimagining Home - How a Nature Enthusiast, Manssi Vedhya Karam",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c95713b2d1ff3f6c85b80a1406a2e648.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE LEHM 2020 Building with Earth",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c9ca54972af8a2cdbab79bdb3fc74fdd.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE TERRE, FEMMES ET SAVOIR- FAIRE Paroles de Batisseuses 2022",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ca165d04389a49477757f43237817887.webp",
    "context": {
      "refs": [
        {
          "alt": "YAF| wattle and daub |Tadelakt| Mud workshop_03",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ca348e520350cb5dac5f530c1f8305fd.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cb7c4701dfab11edd45eceb81cd859c5.webp",
    "context": {
      "refs": [
        {
          "alt": "Casa 503| Architecture |Rattrap Bond |Bengaluru |Dining room_9",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cb9b2a44eb2f9ce03bcc06d7869c266d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cdff7b3bf7e6cc0f04e427a305175e70.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ce41c6f0cd7ef101e4c0d18ea383362d.webp",
    "context": {
      "refs": [
        {
          "alt": "Design and build | Adobe | Mud Workshop_02",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ce75e6f7c97ac273ce6a9aaf1616349b.webp",
    "context": {
      "refs": [
        {
          "alt": "Casa 503| Architecture |Rattrap Bond |Bengaluru |Courtyard_4",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cf035a717d6e8c943d6f32c3eea65a84.webp",
    "context": {
      "refs": [
        {
          "alt": "Esmeralda| Interiors |Bengaluru |Master Bedroom_12",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cf1aecafd01313acbf1b7175d8f8b4db.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Exhibition | Hands On Heritage_6",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d086e2dc83f13deb1fe1de7a1a544765.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d0bbc77776d7ebe64bac2bc75ba7e0ff.webp",
    "context": {
      "refs": [
        {
          "alt": "St.Johns Woods | Interiors | Wine Bottles_5",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d0c22318ea963d77c1117f2dfa3f3356.webp",
    "context": {
      "refs": [
        {
          "alt": "The Brickloft| Architecture |Exposed Masonry | Reclaimed Wood |Bengaluru |Master Bath _11",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d13dcd5b96237ce13fdc51f9dece6e84.webp",
    "context": {
      "refs": [
        {
          "alt": "Ra Maram | Mud Architecture | Doddamanchi | Prayer Nook_08",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d1a3d75162863727e1b09dfc3effbb77.webp",
    "context": {
      "refs": [
        {
          "alt": "Nudge Foundation | Upcycled Interiors| Meeting room_06",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d1fcc0177c2dc8e7cffae94d78270dc0.webp",
    "context": {
      "refs": [
        {
          "alt": "YAF| wattle and daub |Tadelakt| Mud workshop_01",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d20101883aef79a0ed924846d923eb99.webp",
    "context": {
      "refs": [
        {
          "alt": "Yash Farms",
          "title": ""
        },
        {
          "alt": "Yash Farms | Mud Architecture |CSEB |Rammed earth |Bengaluru |Private Living_3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d29a493da7f4908380f4d6bc0213a982.webp",
    "context": {
      "refs": [
        {
          "alt": "craterre",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d32ba0c185678c2cf718ad3c554cf135.webp",
    "context": {
      "refs": [
        {
          "alt": "St.Johns Woods | Interiors | Wardrobe Detail_11",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d4ee3142a595704dcc3e7394ae880a42.webp",
    "context": {
      "refs": [
        {
          "alt": "Civic Fest| Heritage conservation |Hands on Heritage_04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d526d7a55f8f4700d57d04bce36fea6d.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Exhibition | Hands On Heritage_11",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d55733d252f3fab6f8a2bf42c7eb08bc.webp",
    "context": {
      "refs": [
        {
          "alt": "Earthen Weaves| wattle and daub |Mud workshop_07",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d68816faac8ff9677648e74d7f840cba.webp",
    "context": {
      "refs": [
        {
          "alt": "partnerSELCOFoundation",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d6ffcec1c003ce161da5f293fc50933a.webp",
    "context": {
      "refs": [
        {
          "alt": "Newsletter | Issue 5/Jan 2019",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d7000a129612487159dea55a89c15e4f.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE The Sun and Earth Festival On Mud Plaster and Moroccan Lime Plaster",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d77222099d7b56defc0fa2e9a11248c1.webp",
    "context": {
      "refs": [
        {
          "alt": "Tadelakt Plastering - A Report",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d7a2c7d71ff3fab412828ee72f7addfe.webp",
    "context": {
      "refs": [
        {
          "alt": "St.Johns Woods | Interiors | Bathroom_14",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d7b08da2b141273edc47aeeb4420dad3.webp",
    "context": {
      "refs": [
        {
          "alt": "The Brickloft| Architecture |Exposed Masonry | Reclaimed Wood |Bengaluru |Entrance_17",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d7bb8152c9bdfac31500930dff6a8322.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Exhibition | Hands On Heritage_14",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d9173840270e3e1b7b39077720c61761.webp",
    "context": {
      "refs": [
        {
          "alt": "Earthen Weaves| wattle and daub |Mud workshop_10",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d9fc06495c1f4bdf394ffb1198f816d2.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/da3c5f02d15673be575e88d6bf1eda3e.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARDS WADE ASIA 2022 Silver - Public Building",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/dac6124f88e8bfd6b0350ec20495e9b4.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/db4d20196f0dcaf97f8b540491c43bc9.webp",
    "context": {
      "refs": [
        {
          "alt": "EarthenWeaves",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/db729ed6df8e96b2f43bdac2804ead5f.webp",
    "context": {
      "refs": [
        {
          "alt": "Earth Workshop| CSEB | Mud workshop_05",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/db9d7fe9c1690e096d9a6174e6c60fa4.webp",
    "context": {
      "refs": [
        {
          "alt": "aveirevised",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/dbb7e59b6b8d6c455d788582da3b3df8.webp",
    "context": {
      "refs": [
        {
          "alt": "Maker Faire| Adobe | Public Exhibition_05",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/dbe83f762a46b3f15f26cd0be97872a2.webp",
    "context": {
      "refs": [
        {
          "alt": "Soilful Skilling- A report",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/dd155f486eab6679af8d83bc42c3fd2a.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_10",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/de11e074abe85bc9f0edbec542db46bc.webp",
    "context": {
      "refs": [
        {
          "alt": "Esmeralda| Interiors |Bengaluru |Library_5",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/de5f33280ae3b8d9c260a4cda8191743.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Hunt | Hands On Heritage_4",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/de62eded111f161a03901406a489217a.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/de6c6967917db93eb6ef2e770a4ef7a0.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE Sustainable Built Environment (SBE) Conference 2025 \u2013 ETH Zurich Empowering Women as Agen",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/de7f3bee984b039fd51b59de011d497d.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Workshop |Architetural Documentation | Hands On Heritage_07",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/dee2f5848e81ab2dff07b0686a29966c.webp",
    "context": {
      "refs": [
        {
          "alt": "Gtac | Office | Interiors | Seating_6",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/df043ccce3db38e2399f6ad041c70ddc.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/df0f24983ed9f2bc72952c24ac7f0f02.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Workshop |Architetural Documentation | Hands On Heritage_11",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/df5129cf1a137864cc6c09b697b84f91.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARD The Saint-Gobain Grants Program with Ethos Foundation and Arcause A Mobile Exhibition Promotin",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e0497aa5f4805f33892fc9fdce40a558.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_22",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e0d491ec1bbf7f3c104a5c9c2bad0b89.webp",
    "context": {
      "refs": [
        {
          "alt": "Scraffito Workshop",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e1e8df7b649dbb3e3f231fa7dec502f4.jpeg",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/e2685e2a20fc5b2df528c19006dd1b94.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_14",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e31c95fe24552a7a4c785e5af6b7e810.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE ACTIVISM THROUGH ACHITECTURE Digital Master class",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e322aa4223c186bc18df8ca9ce5b5ee0.webp",
    "context": {
      "refs": [
        {
          "alt": "MessageMail",
          "title": ""
        },
        {
          "alt": "MessageMail",
          "title": ""
        },
        {
          "alt": "MessageMail",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e331a1efdab214103fd0b5b105642e4f.webp",
    "context": {
      "refs": [
        {
          "alt": "Organic BPS| Office Interiors_6",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e3ef947f87693a30c7096ca0852f16f2.webp",
    "context": {
      "refs": [
        {
          "alt": "Organic BPS| Office Interiors_3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e450572cb4705be9a0345493a0c88f31.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage Club| Hands On heritage_05",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e470c8fb41086e9052881f5357d255c0.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e4c636485dcd2a4a333d2ad86f89a5d4.webp",
    "context": {
      "refs": [
        {
          "alt": "Bamiyan Cultural Centre | Competition Entry_1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e4ea3ddb60147663b5d8e12b1b45af3c.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_12",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e5ca1fd6449f28b157a18253358e6792.webp",
    "context": {
      "refs": [
        {
          "alt": "Esmeralda| Interiors |Bengaluru |Staircase_4",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e602152ccc225ba8be51fde055e7cd95.webp",
    "context": {
      "refs": [
        {
          "alt": "YAF| wattle and daub |Tadelakt| Mud workshop_09",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e6029f9e8906292687bb0dc7f033eaee.webp",
    "context": {
      "refs": [
        {
          "alt": "Online mud course |earth architecture course|Mud workshop_03",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e62eb0ea1482e9737cfa89d949653a55.jpeg",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/e6b999b2449c1a5a114ebb55e8d4b290.webp",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/e6faba6ffe48e718bf677b6f8a996ba3.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e702f765f990bb5cd37c6a0a63148ba1.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Exhibition | Hands On Heritage_4",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e70b773eb6a48ed63da6cf795e287697.webp",
    "context": {
      "refs": [
        {
          "alt": "Nudge Foundation | Upcycled Interiors| Meeting room_07",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e7a3d294f4bb811348662d8413355482.webp",
    "context": {
      "refs": [
        {
          "alt": "Earth Workshop| CSEB | Mud workshop_02",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e7e1eb8a3d25a3194c5cbb61212e5224.webp",
    "context": {
      "refs": [
        {
          "alt": "Online mud course |earth architecture course|Mud workshop_08",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e90d78326143528bbf7b581bb892fe1a.webp",
    "context": {
      "refs": [
        {
          "alt": "St.Johns Woods | Interiors | Informal Living_9",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e9892626ed5e703a73a3c8403fb8abfd.webp",
    "context": {
      "refs": [
        {
          "alt": "Gtac |Office | Interiors | Signboard_1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e9df51b59d20a07ae978148e92143754.webp",
    "context": {
      "refs": [
        {
          "alt": "Masons Ink | Sustainable | Interiors_5",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ea1eb9f2b7c161d48d5008d22244a941.webp",
    "context": {
      "refs": [
        {
          "alt": "Organic BPS| Office Interiors_5",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ea39235689984c2cd41ce35dbd0b5313.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Exhibition | Hands On Heritage_13",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/eab98ccffcbfc8a0b96edc90e12d9802.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA Volume Zero Feature Featuring The Brick Loft",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ec2033077e644c06f2d26da27afe880e.webp",
    "context": {
      "refs": [
        {
          "alt": "Mannu Kattu House| Mud Architecture |Heritage Conservation | Coimbatore | Cob | Courtyard_3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ec3700fb326f3d6a5a8b3bb1a145172e.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Exhibition | Hands On Heritage_1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ec6c83fc769debae46c9b27cf66f8d04.webp",
    "context": {
      "refs": [
        {
          "alt": "Ra Maram | Mud Architecture | Doddamanchi | Master Bedroom_07",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ecab107960d4a984c1f9867f6c57f83a.webp",
    "context": {
      "refs": [
        {
          "alt": "Courtyard House | Mud Architecture | Cochin | View_02",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ecff735202e236622c3d7db0174afbde.webp",
    "context": {
      "refs": [
        {
          "alt": "Mud and Lime Flooring | Hands-on workshop | Earth Architecture",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ee563688d9fa1b90901c82123f387c9f.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE COP 27 - UN CLIMATE CHANGE CONFERENCE Together for Implementation",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ee5de07731a15b281af491b8c3db42b6.webp",
    "context": {
      "refs": [
        {
          "alt": "Ra Maram | Mud Architecture | Doddamanchi | Wrap around verandah_04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ee8dc5f87a3f4bb77e1cef4a2315f0dc.webp",
    "context": {
      "refs": [
        {
          "alt": "Bamiyan Cultural Centre | Competition Entry_6",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ef64472259192e250acd6b3de94dc9b2.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_01",
          "title": ""
        },
        {
          "alt": "Heritage on Wheels",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ef811eba4065ec65f2300ec55774b3ab.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA DESIGNURU Adaptive Reuse - How to identify and work with Built Heritage",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/efcf09e727f699718c92955779561566.webp",
    "context": {
      "refs": [
        {
          "alt": "The Brickloft| Architecture |Exposed Masonry | Reclaimed Wood |Bengaluru |Main door _12",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f04d2e924becc95cfbda9d1fcf0059a1.webp",
    "context": {
      "refs": [
        {
          "alt": "The Brickloft_Architecture_Exposed Masonry_Reclaimed Wood_Bengaluru_Office_14",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f10581e40811576ed1b6e650edf96aaa.webp",
    "context": {
      "refs": [
        {
          "alt": "Yash Farms | Mud Architecture |CSEB |Rammed earth |Bengaluru |Living Room_4",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f19eeac40d71bc2018bae55988b6042d.webp",
    "context": {
      "refs": [
        {
          "alt": "makerfaire",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f23ae12a2e1511a9fb639981ba120f25.webp",
    "context": {
      "refs": [
        {
          "alt": "Bamiyan Cultural Centre",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f321fa65fb935be38a4d33f6421be165.webp",
    "context": {
      "refs": [
        {
          "alt": "Abode in Arabica | Mud House | Chikamagalur_4",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f38b874ebfc26338e5902fc2a21ce9aa.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA COP 26 TV INTERVIEW Vision and Mission of Masons Ink",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f4ff79fb3db42d9036ae38248e235ea5.webp",
    "context": {
      "refs": [
        {
          "alt": "AWARDS WADE ASIA 2022 Runner up - Most Sustainable Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f5358a08c3716b0817f236e60727700b.webp",
    "context": {
      "refs": [
        {
          "alt": "Online mud course |earth architecture course|Mud workshop_01",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f5b896683d9dbbd1b218cae10a9da3d7.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Exhibition | Hands On Heritage_2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f5b9da2cbfa70b569fffad3f8d791dcb.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE CONSTRUCTION TECH Sustainable construction",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f5e7857a492bd02e3543a0d9a1dd01c0.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f61c5d2aea2b3dea0d81f3d7069c8090.webp",
    "context": {
      "refs": [
        {
          "alt": "Mannu Kattu House| Mud Architecture |Heritage Conservation | Coimbatore | Cob | Entrance_4",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f64d16f72c0cb78228ed1b9876bf6793.webp",
    "context": {
      "refs": [
        {
          "alt": "Civic Fest| Heritage conservation |Hands on Heritage_05",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f66156626d505417540401fe95688025.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage Club| Hands On heritage_01",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f68b4a588965c9c4bebd0f311295aa5b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f7979d927fb91d0017b701899d1c5da9.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f86a7c447c3916ba71054a98b4f94ff7.webp",
    "context": {
      "refs": [
        {
          "alt": "HOH Workshop |Architetural Documentation | Hands On Heritage_04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f8b4a0c47f9700dd4544ddbb9fcc4618.webp",
    "context": {
      "refs": [
        {
          "alt": "DESIGNURU",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f94c1f9940de2f31bf0967c987778efa.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f9662a90716e30d5b8dbb0801555256b.webp",
    "context": {
      "refs": [
        {
          "alt": "Heart",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fa59837a2e8f56f03c22f88b1778defa.webp",
    "context": {
      "refs": [
        {
          "alt": "Mud Workshops| Mud Architecture_Masons Training 10",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fa7e4853d4d224f8efb9d2a05237041c.webp",
    "context": {
      "refs": [
        {
          "alt": "Esmeralda| Interiors |Bengaluru |Tadelakt plaster_16",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fac3bef19ea05a42c66cb0db656dd986.webp",
    "context": {
      "refs": [
        {
          "alt": "Mud - InternalWorkshop",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fb88daa4d11517dcb30c2f884f077bc9.webp",
    "context": {
      "refs": [
        {
          "alt": "Design and build | Adobe | Mud Workshop_01",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fbd5e27dd718ec29d2774ba96df36aa3.webp",
    "context": {
      "refs": [
        {
          "alt": "Organic BPS| Office Interiors_1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fbfa00c0dc4764c1bcd11b5ce14be6a9.webp",
    "context": {
      "refs": [
        {
          "alt": "The Brickloft| Architecture |Exposed Masonry | Reclaimed Wood |Bengaluru |Dining room_5",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fd060db4251aab41217c57980a05e85f.webp",
    "context": {
      "refs": [
        {
          "alt": "Design and build | Adobe | Mud Workshop_05",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fd0f09dbe30ed2236917a9c047105194.webp",
    "context": {
      "refs": [
        {
          "alt": "Design and build | Adobe | Mud Workshop_04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fe37487e25c24328f20706c4ecfd15b8.webp",
    "context": {
      "refs": [
        {
          "alt": "Heritage on Wheels| Hands On heritage_18",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fedac1349cbea47becb243a473285a12.webp",
    "context": {
      "refs": [
        {
          "alt": "MEDIA Shethepeople Heritage, Equality & Sustainability In Architecture",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ff107e914a9b4edf6eb4d35862a6d53d.webp",
    "context": {
      "refs": [
        {
          "alt": "CONFERENCE COP 28 - UN CLIMATE CHANGE CONFERENCE Unite. Act.Deliver",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ffdf67c64e3874ebbf291523e32cd115.webp",
    "context": {
      "refs": [
        {
          "alt": "The Brickloft| Architecture |Exposed Masonry | Reclaimed Wood |Bengaluru |Walk in Wardrobe _10",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "index.html",
    "context": {
      "title": "Masonsink | YOUR . DESIGN/SUSTAINABLE/EARTH/HERITAGE . STUDIO",
      "first_heading": "United Nations ExplainerHow to Build a Sustainable Home:The Magic of Mud"
    }
  },
  {
    "path": "inspirit-2019-candleholder.html",
    "context": {
      "title": "Inspirit | Mud Architecture | Rammed Earth | Ramaiah institute of Technology | Mud workshop |Bangalore | Masons Ink",
      "first_heading": "earthen hues"
    }
  },
  {
    "path": "js/03b2eaae6007054a68c38e495f894dba.js",
    "context": {
      "path": "js/03b2eaae6007054a68c38e495f894dba.js"
    }
  },
  {
    "path": "js/0a105d712b6a6c836c48dd97d0f0cac1.js",
    "context": {
      "path": "js/0a105d712b6a6c836c48dd97d0f0cac1.js"
    }
  },
  {
    "path": "js/0c46896987137b0016246f6bc2243099.js",
    "context": {
      "path": "js/0c46896987137b0016246f6bc2243099.js"
    }
  },
  {
    "path": "js/165d7b0ddfa33362140feea997351b77.js",
    "context": {
      "path": "js/165d7b0ddfa33362140feea997351b77.js"
    }
  },
  {
    "path": "js/16df9ef05001a1741857bf99f5a5738f.js",
    "context": {
      "path": "js/16df9ef05001a1741857bf99f5a5738f.js"
    }
  },
  {
    "path": "js/2a85c11e395a8380b5915443e926b569.js",
    "context": {
      "path": "js/2a85c11e395a8380b5915443e926b569.js"
    }
  },
  {
    "path": "js/34be5330971fdbd18985525bd994b0aa.js",
    "context": {
      "path": "js/34be5330971fdbd18985525bd994b0aa.js"
    }
  },
  {
    "path": "js/35c5f9e096d4da33d2a62031daf14248.js",
    "context": {
      "path": "js/35c5f9e096d4da33d2a62031daf14248.js"
    }
  },
  {
    "path": "js/3d70953a848219e749fedc2cdb906675.js",
    "context": {
      "path": "js/3d70953a848219e749fedc2cdb906675.js"
    }
  },
  {
    "path": "js/3e940a33e44b65c1c0af8bb80a893530.js",
    "context": {
      "path": "js/3e940a33e44b65c1c0af8bb80a893530.js"
    }
  },
  {
    "path": "js/544d012df7acf9c3f0920f67c9e322b9.js",
    "context": {
      "path": "js/544d012df7acf9c3f0920f67c9e322b9.js"
    }
  },
  {
    "path": "js/57d119d998d518b01f9d5ccb5e4d4c52.js",
    "context": {
      "path": "js/57d119d998d518b01f9d5ccb5e4d4c52.js"
    }
  },
  {
    "path": "js/5bb6b0dbd57f0d423ad45110ac3925c4.js",
    "context": {
      "path": "js/5bb6b0dbd57f0d423ad45110ac3925c4.js"
    }
  },
  {
    "path": "js/67f6e2f99c3c3133e0dc669919fff5c5.js",
    "context": {
      "path": "js/67f6e2f99c3c3133e0dc669919fff5c5.js"
    }
  },
  {
    "path": "js/7045b35c5bd0e9c7cf59f1900eeeec41.js",
    "context": {
      "path": "js/7045b35c5bd0e9c7cf59f1900eeeec41.js"
    }
  },
  {
    "path": "js/7260bab328b0ad74815a5efb377bcc67.js",
    "context": {
      "path": "js/7260bab328b0ad74815a5efb377bcc67.js"
    }
  },
  {
    "path": "js/893de96f1b6da546bd7c814964723eca.js",
    "context": {
      "path": "js/893de96f1b6da546bd7c814964723eca.js"
    }
  },
  {
    "path": "js/93e29fe348ddc9b71aba9c842adc18b8.js",
    "context": {
      "path": "js/93e29fe348ddc9b71aba9c842adc18b8.js"
    }
  },
  {
    "path": "js/9455859483e31e4da0e28f10d0742c2a.js",
    "context": {
      "path": "js/9455859483e31e4da0e28f10d0742c2a.js"
    }
  },
  {
    "path": "js/9bee8945c1cd6e5ec63a0180d8f74783.js",
    "context": {
      "path": "js/9bee8945c1cd6e5ec63a0180d8f74783.js"
    }
  },
  {
    "path": "js/9db10375d298678e53777a2347b87073.js",
    "context": {
      "path": "js/9db10375d298678e53777a2347b87073.js"
    }
  },
  {
    "path": "js/9f9b6e54f82a6bbc8bac9b89327024bc.js",
    "context": {
      "path": "js/9f9b6e54f82a6bbc8bac9b89327024bc.js"
    }
  },
  {
    "path": "js/a2261649751fa61b606222c9b2ea3b80.js",
    "context": {
      "path": "js/a2261649751fa61b606222c9b2ea3b80.js"
    }
  },
  {
    "path": "js/b0bade6d42c2702ca85774296cc507c4.js",
    "context": {
      "path": "js/b0bade6d42c2702ca85774296cc507c4.js"
    }
  },
  {
    "path": "js/cd1ed86c1e7f06d985fd71bc10bd4b04.js",
    "context": {
      "path": "js/cd1ed86c1e7f06d985fd71bc10bd4b04.js"
    }
  },
  {
    "path": "js/cecb447a04bbe3e8982190dd6e697120.js",
    "context": {
      "path": "js/cecb447a04bbe3e8982190dd6e697120.js"
    }
  },
  {
    "path": "js/d23b88e70dfdf0290f3b74c4efdc8e56.js",
    "context": {
      "path": "js/d23b88e70dfdf0290f3b74c4efdc8e56.js"
    }
  },
  {
    "path": "js/d80b370d82680fc786dcc943a327b9f2.js",
    "context": {
      "path": "js/d80b370d82680fc786dcc943a327b9f2.js"
    }
  },
  {
    "path": "js/df80c5cbcb312a9c7c0b2ebb6ac5f592.js",
    "context": {
      "path": "js/df80c5cbcb312a9c7c0b2ebb6ac5f592.js"
    }
  },
  {
    "path": "js/f1e5dbc1ece900d164c2e9aa2d6a1386.js",
    "context": {
      "path": "js/f1e5dbc1ece900d164c2e9aa2d6a1386.js"
    }
  },
  {
    "path": "js/f3f02c438592c8e1bbe551f4dbbf4f5c.js",
    "context": {
      "path": "js/f3f02c438592c8e1bbe551f4dbbf4f5c.js"
    }
  },
  {
    "path": "js/f787cc1963bb3473ea998e23b0d3b1ed.js",
    "context": {
      "path": "js/f787cc1963bb3473ea998e23b0d3b1ed.js"
    }
  },
  {
    "path": "js/faf9ce4e848522206b5c3043551fb2d7.js",
    "context": {
      "path": "js/faf9ce4e848522206b5c3043551fb2d7.js"
    }
  },
  {
    "path": "maker-faire.html",
    "context": {
      "title": "Maker Faire | Mud Architecture | CSEB | Adobe blocks | Public Exhibition| Bangalore | Masons Ink",
      "first_heading": "MAKER FAIRE"
    }
  },
  {
    "path": "mannu-kattu-house.html",
    "context": {
      "title": "Mannu Kattu House| Mud Architecture |Heritage Conservation | Coimbatore | Cob | Masons Ink",
      "first_heading": "Mannu Kattu House"
    }
  },
  {
    "path": "masons-ink-office-interior-design.html",
    "context": {
      "title": "Masons Ink Office | Sustainable interiors | Repurposed interiors | Handmade Lights | Barn door | Infantry Road | Bangalore | Mason Ink",
      "first_heading": "Masons Ink Office Interior Design"
    }
  },
  {
    "path": "mud-workshops.html",
    "context": {
      "title": "International Workshops | Education | Awareness | Hands On | College | Bangalore | Kochi | Masons Ink",
      "first_heading": "INTERNATIONAL MUD WORKSHOPS"
    }
  },
  {
    "path": "newsletter.html",
    "context": {
      "title": "MI Papers | Masons Ink",
      "first_heading": "Newsletter | Issue 9/2022-2023"
    }
  },
  {
    "path": "nudge-foundation.html",
    "context": {
      "title": "Nudge foundation | Office Interiors | Upcycled Furniture | Hands On | HSR Layout | Bangalore | Masons Ink",
      "first_heading": "Nudge foundation"
    }
  },
  {
    "path": "organic-bps.html",
    "context": {
      "title": "Office Interiors | Modular Furniture |Kochi | Masons Ink",
      "first_heading": "Organic BPS"
    }
  },
  {
    "path": "outreach.html",
    "context": {
      "title": "Outreach | Masons ink | Bangalore",
      "first_heading": ""
    }
  },
  {
    "path": "publications.html",
    "context": {
      "title": "Publications | Masons Ink",
      "first_heading": "Rammed Earth Wall"
    }
  },
  {
    "path": "ra-maram.html",
    "context": {
      "title": "Ra Maram | Mud Architecture | Earth Architecture | CSEB | Reclaimed wood | Doddamanchi | Masons Ink",
      "first_heading": "Ra Maram"
    }
  },
  {
    "path": "snehadaan.html",
    "context": {
      "title": "Snehadaan | Mud Architecture | CSEB | Reclaimed Wood | Doddamanchi | Masons Ink",
      "first_heading": "SNEHADAAN"
    }
  },
  {
    "path": "st-johns-woods\u2013apartment-interiors.html",
    "context": {
      "title": "St. John | Interiors desigen | residential interiors | koramangala",
      "first_heading": "St Johns Woods Apartment Interiors"
    }
  },
  {
    "path": "the-brickloft.html",
    "context": {
      "title": "The Brickloft| Architecture |Exposed Masonry | Reclaimed Wood | Mixed use|Bengaluru |Masons Ink",
      "first_heading": "The Brickloft"
    }
  },
  {
    "path": "untraversed.html",
    "context": {
      "title": "Ra Maram | Mud Architecture | Earth Architecture | CSEB | Reclaimed wood | Doddamanchi | Masons Ink",
      "first_heading": "Earthen Weaves"
    }
  },
  {
    "path": "work.html",
    "context": {
      "title": "Work | Masons ink | Bangalore",
      "first_heading": ""
    }
  },
  {
    "path": "yash-farm.html",
    "context": {
      "title": "Yash Farms | Mud Architecture |CSEB |Rammed earth |Bengaluru |Masons Ink| CSEB | Reclaimed Wood | Andevanapally | Masons Ink",
      "first_heading": "Yash Farms"
    }
  }
]

Return only a JSON object mapping each path to its new basename (same extension). No other text.