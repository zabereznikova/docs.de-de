---
title: "Names of Declared XML Elements and Attributes (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declarations [XML in Visual Basic]"
  - "element names [XML in Visual Basic]"
  - "names in XML literals"
  - "attribute names [XML in Visual Basic]"
  - "XML literals [Visual Basic], element names"
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Names of Declared XML Elements and Attributes (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Dieses Thema enthält [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Richtlinien zur Benennung von XML\-Elementen und Attributen in XML\-Literalen. In einem XML\-Literal können Sie einen lokalen Namen oder einen qualifizierten Namen angeben.  Ein qualifizierter Name besteht aus einem XML\-Namespacepräfix, einem Doppelpunkt und einem lokalen Namen.  Weitere Informationen zu XML\-Namespacepräfixen finden Sie unter [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## Regeln  
 Für lokale Namen von Elementen oder Attributen gelten in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] die folgenden Regeln.  
  
-   Der Name kann mit einem Namespace beginnen.  Der Name muss mit einem alphabetischen Zeichen oder einem Unterstrich \(`_`\) beginnen.  
  
-   Der Name darf nur alphabetische Zeichen, Dezimalziffern, Unterstriche, Punkte \(.\) und Bindestriche \(\-\) enthalten.  
  
-   Er darf nicht mehr als 1,024 Zeichen umfassen.  
  
-   Doppelpunkte geben innerhalb von Namen Namespaceabgrenzungen an.  Daher können Sie Doppelpunkte nur zum Angeben eines XML\-Namespace für einen bestimmten Namen verwenden.  
  
 Außerdem sollten Sie folgende Richtlinie beachten.  
  
-   Alle Namen, die mit der Zeichenfolge "xml" beginnen, sind, unabhängig von Groß\- bzw. Kleinschreibung, durch die XML 1.0\-Spezifikation reserviert.  Deshalb dürfen Element\- und Attributnamen nicht auf diese Weise benannt werden.  
  
### Richtlinien zur Länge von Namen  
 Namen sollten aus praktischen Gründen so kurz wie möglich sein und gleichzeitig die Art des Elements eindeutig kennzeichnen.  Dies verbessert die Lesbarkeit des Codes und reduziert die Zeilenlänge und die Quelldateigröße.  
  
 Namen sollten jedoch nicht so kurz sein, dass nicht eindeutig aus ihnen hervorgeht, was das Element darstellt oder wie der Code das Element verwendet.  Dies ist für die Lesbarkeit des Codes wichtig.  Wenn andere Personen versuchen, den Code zu verstehen, oder Sie selbst nach langer Zeit den Code erneut durchsehen, kann die Verwendung geeigneter Elementnamen Zeit sparen,.  
  
## Groß\- und Kleinschreibung bei Namen  
 Bei XML\-Elementnamen muss die Groß\-\/Kleinschreibung beachtet werden.  Der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Compiler interpretiert Namen, die sich nur durch die Groß\- und Kleinschreibung unterscheiden, als unterschiedliche Namen.  Beispielsweise werden `ABC` und `abc` als Verweise auf verschiedene Elemente interpretiert.  
  
## XML\-Namespaces  
 Wenn Sie ein XML\-Elementliteral erstellen, können Sie das XML\-Namespacepräfix für den Elementnamen angeben.  Weitere Informationen finden Sie unter [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## Siehe auch  
 [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)