---
title: 'Vorgehensweise: Parsen einer Zeichenfolge (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
ms.openlocfilehash: da12ec98e03acceae375bbed4fc6ad4c2a71ec2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-parse-a-string-visual-basic"></a>Vorgehensweise: Parsen einer Zeichenfolge (Visual Basic)
In diesem Thema wird das Erstellen einer XML-Struktur in c# veranschaulicht.  
  
## <a name="example"></a>Beispiel  
 Sie können eine Zeichenfolge in Visual Basic analysieren, mit der `XElement.Parse` Methode. Es ist aber dennoch effizienter, XML-Literale zu verwenden (siehe folgender Code), da XML-Literale nicht dieselben Leistungseinbußen zur Folge haben wie dies beim Analysieren von XML aus einer Zeichenfolge der Fall ist.  
  
 Mithilfe von XML-Literalen können Sie einfach kopieren und fügen Sie den XML-Code in Visual Basic-Programms.  
  
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
