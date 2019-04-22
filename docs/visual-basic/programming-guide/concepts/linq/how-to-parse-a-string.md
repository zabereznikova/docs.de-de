---
title: 'Vorgehensweise: Analysiert eine Zeichenfolge (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
ms.openlocfilehash: 815e94b3b41c2c0cc1d18d598307ab292919bea4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827301"
---
# <a name="how-to-parse-a-string-visual-basic"></a><span data-ttu-id="2a2aa-102">Vorgehensweise: Analysiert eine Zeichenfolge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a2aa-102">How to: Parse a String (Visual Basic)</span></span>
<span data-ttu-id="2a2aa-103">In diesem Thema wird gezeigt, wie zum Erstellen einer XML-Struktur in C#.</span><span class="sxs-lookup"><span data-stu-id="2a2aa-103">This topic shows how to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a2aa-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2a2aa-104">Example</span></span>  
 <span data-ttu-id="2a2aa-105">Sie können eine Zeichenfolge in Visual Basic analysieren, mit der `XElement.Parse` Methode.</span><span class="sxs-lookup"><span data-stu-id="2a2aa-105">You can parse a string in Visual Basic by using the `XElement.Parse` method.</span></span> <span data-ttu-id="2a2aa-106">Es ist aber dennoch effizienter, XML-Literale zu verwenden (siehe folgender Code), da XML-Literale nicht dieselben Leistungseinbußen zur Folge haben wie dies beim Analysieren von XML aus einer Zeichenfolge der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="2a2aa-106">However, it is more efficient to use XML literals, as shown in following code, because XML literals do not suffer from the same performance penalties as parsing XML from a string.</span></span>  
  
 <span data-ttu-id="2a2aa-107">Sie können mithilfe von XML-Literale können einfach kopieren und fügen Sie der XML-Code in Visual Basic-Programms.</span><span class="sxs-lookup"><span data-stu-id="2a2aa-107">By using XML literals, you can just copy and paste your XML into your Visual Basic program.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a2aa-108">Das Analysieren von Text oder das Laden eines XML-Dokuments aus einer Textdatei ist weniger effizient als die funktionale Konstruktion.</span><span class="sxs-lookup"><span data-stu-id="2a2aa-108">Parsing text or loading an XML document from a text file is less efficient than functional construction.</span></span> <span data-ttu-id="2a2aa-109">Wenn Sie eine XML-Struktur aus Code initialisieren, verbraucht die funktionale Konstruktion weniger Verarbeitungszeit als das Analysieren des Textes.</span><span class="sxs-lookup"><span data-stu-id="2a2aa-109">If you are initializing an XML tree from code, it takes less processor time to use functional construction than to parse text.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2a2aa-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a2aa-110">See also</span></span>

- [<span data-ttu-id="2a2aa-111">Analysieren von XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a2aa-111">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
