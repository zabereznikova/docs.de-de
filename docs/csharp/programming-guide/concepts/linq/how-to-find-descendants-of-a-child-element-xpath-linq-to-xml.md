---
title: 'Vorgehensweise: Suchen nach Nachfolgern von untergeordneten Elementen (XPath-LINQ to XML) (C#)'
description: Erfahren Sie, wie Sie mithilfe eines XPath-Ausdrucks nach Nachfolgerelementen eines untergeordneten Elements mit einem bestimmten Namen suchen.
ms.date: 07/20/2015
ms.assetid: 505b7512-bb8b-4f85-abbf-491f039c961e
ms.openlocfilehash: b8e110abc2e0df99c3fdf6d2846c7cbbc4736c1a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303256"
---
# <a name="how-to-find-descendants-of-a-child-element-xpath-linq-to-xml-c"></a><span data-ttu-id="17693-103">Vorgehensweise: Suchen nach Nachfolgern von untergeordneten Elementen (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="17693-103">How to find descendants of a child element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="17693-104">In diesem Thema wird gezeigt, wie Sie die Nachfolgerelemente untergeordneter Elemente mit einem bestimmten Namen ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="17693-104">This topic shows how to get the descendant elements of a child element with a particular name.</span></span>  
  
 <span data-ttu-id="17693-105">Der XPath-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="17693-105">The XPath expression is:</span></span>  
  
 `./Paragraph//Text/text()`  
  
## <a name="example"></a><span data-ttu-id="17693-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="17693-106">Example</span></span>  
 <span data-ttu-id="17693-107">Dieses Beispiel simuliert die Probleme beim Extrahieren von Text aus einer XML-Darstellung eines mit einem Textverarbeitungsprogramm erstellten Dokuments.</span><span class="sxs-lookup"><span data-stu-id="17693-107">This example simulates the problems of extracting text from an XML representation of a word processing document.</span></span> <span data-ttu-id="17693-108">Zunächst werden alle `Paragraph`-Elemente ausgewählt, dann erfolgt die Auswahl aller `Text`-Nachfolgerelemente des jeweiligen `Paragraph`-Elements.</span><span class="sxs-lookup"><span data-stu-id="17693-108">It first selects all `Paragraph` elements, and then it selects all `Text` descendant elements of each `Paragraph` element.</span></span> <span data-ttu-id="17693-109">Die `Text`-Nachfolgerelemente des untergeordneten `Comment`-Elements werden nicht ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="17693-109">This doesn't select the descendant `Text` elements of the `Comment` element.</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root>  
  <Paragraph>  
    <Text>This is the start of</Text>  
  </Paragraph>  
  <Comment>  
    <Text>This comment is not part of the paragraph text.</Text>  
  </Comment>  
  <Paragraph>  
    <Annotation Emphasis='true'>  
      <Text> a sentence.</Text>  
    </Annotation>  
  </Paragraph>  
  <Paragraph>  
    <Text>  This is a second sentence.</Text>  
  </Paragraph>  
</Root>");  
  
// LINQ to XML query  
string str1 =  
    root  
    .Elements("Paragraph")  
    .Descendants("Text")  
    .Select(s => s.Value)  
    .Aggregate(  
        new StringBuilder(),  
        (s, i) => s.Append(i),  
        s => s.ToString()  
    );  
  
// XPath expression  
string str2 =  
    ((IEnumerable)root.XPathEvaluate("./Paragraph//Text/text()"))  
    .Cast<XText>()  
    .Select(s => s.Value)  
    .Aggregate(  
        new StringBuilder(),  
        (s, i) => s.Append(i),  
        s => s.ToString()  
    );  
  
if (str1 == str2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(str2);  
```  
  
 <span data-ttu-id="17693-110">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="17693-110">This example produces the following output:</span></span>  
  
```output  
Results are identical  
This is the start of a sentence.  This is a second sentence.  
```  
  