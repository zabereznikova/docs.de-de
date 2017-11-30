---
title: 'Vorgehensweise: Parsen einer Zeichenfolge (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 10b80c72cae70437ff812c4b67b2532d708f1e69
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-parse-a-string-visual-basic"></a>Vorgehensweise: Parsen einer Zeichenfolge (Visual Basic)
In diesem Thema wird das Erstellen einer XML-Struktur in c# veranschaulicht.  
  
## <a name="example"></a>Beispiel  
 Sie können eine Zeichenfolge analysieren [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] mithilfe der `XElement.Parse` Methode. Es ist aber dennoch effizienter, XML-Literale zu verwenden (siehe folgender Code), da XML-Literale nicht dieselben Leistungseinbußen zur Folge haben wie dies beim Analysieren von XML aus einer Zeichenfolge der Fall ist.  
  
 Bei der Verwendung von XML-Literalen können Sie Ihr XML durch einfaches Kopieren und Einfügen in Ihr [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]-Programm einfügen.  
  
> [!NOTE]
>  Das Analysieren von Text oder das Laden eines XML-Dokuments aus einer Textdatei ist weniger effizient als die funktionale Konstruktion. Wenn Sie eine XML-Struktur aus Code initialisieren, verbraucht die funktionale Konstruktion weniger Verarbeitungszeit als das Analysieren des Textes.  
  
```vb  
Dim contacts as XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="home">206-555-0144</Phone>  
            <Phone Type="work">425-555-0145</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>10</NetWorth>  
        </Contact>  
        <Contact>  
            <Name>Gretchen Rivas</Name>  
            <Phone Type="mobile">206-555-0163</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>11</NetWorth>  
        </Contact>  
    </Contacts>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Analysieren von XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
