---
title: 'Vorgehensweise: Parsen einer Zeichenfolge (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d0fd7c7adcfbd7e2136d1a652017d470634016b9
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-parse-a-string-visual-basic"></a><span data-ttu-id="9bdb4-102">Vorgehensweise: Parsen einer Zeichenfolge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9bdb4-102">How to: Parse a String (Visual Basic)</span></span>
<span data-ttu-id="9bdb4-103">In diesem Thema wird das Erstellen einer XML-Struktur in c# veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9bdb4-103">This topic shows how to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bdb4-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9bdb4-104">Example</span></span>  
 <span data-ttu-id="9bdb4-105">Sie können eine Zeichenfolge in Visual Basic analysieren, mit der `XElement.Parse` Methode.</span><span class="sxs-lookup"><span data-stu-id="9bdb4-105">You can parse a string in Visual Basic by using the `XElement.Parse` method.</span></span> <span data-ttu-id="9bdb4-106">Es ist aber dennoch effizienter, XML-Literale zu verwenden (siehe folgender Code), da XML-Literale nicht dieselben Leistungseinbußen zur Folge haben wie dies beim Analysieren von XML aus einer Zeichenfolge der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="9bdb4-106">However, it is more efficient to use XML literals, as shown in following code, because XML literals do not suffer from the same performance penalties as parsing XML from a string.</span></span>  
  
 <span data-ttu-id="9bdb4-107">Mithilfe von XML-Literalen können Sie einfach kopieren und fügen Sie den XML-Code in Visual Basic-Programms.</span><span class="sxs-lookup"><span data-stu-id="9bdb4-107">By using XML literals, you can just copy and paste your XML into your Visual Basic program.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9bdb4-108">Das Analysieren von Text oder das Laden eines XML-Dokuments aus einer Textdatei ist weniger effizient als die funktionale Konstruktion.</span><span class="sxs-lookup"><span data-stu-id="9bdb4-108">Parsing text or loading an XML document from a text file is less efficient than functional construction.</span></span> <span data-ttu-id="9bdb4-109">Wenn Sie eine XML-Struktur aus Code initialisieren, verbraucht die funktionale Konstruktion weniger Verarbeitungszeit als das Analysieren des Textes.</span><span class="sxs-lookup"><span data-stu-id="9bdb4-109">If you are initializing an XML tree from code, it takes less processor time to use functional construction than to parse text.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9bdb4-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9bdb4-110">See Also</span></span>  
 [<span data-ttu-id="9bdb4-111">Analysieren von XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9bdb4-111">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
