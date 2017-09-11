---
title: "Gewusst wie: Arbeiten mit Wörterbüchern mit LINQ to XML (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 6cb3f969-1986-414a-b850-87418712edea
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 0b3b800c332ce9d3f976e0bb82dff96c2a8233b8
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---
# <a name="how-to-work-with-dictionaries-using-linq-to-xml-visual-basic"></a><span data-ttu-id="8c16b-102">Gewusst wie: Arbeiten mit Wörterbüchern mit LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c16b-102">How to: Work with Dictionaries Using LINQ to XML (Visual Basic)</span></span>
<span data-ttu-id="8c16b-103">Es ist häufig sinnvoll, verschiedene Datenstrukturen in XML und aus XML in andere Datenstrukturen umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="8c16b-103">It is often convenient to convert varieties of data structures to XML, and XML back to other data structures.</span></span> <span data-ttu-id="8c16b-104">In diesem Thema wird eine konkrete Implementierung dieser allgemeinen Herangehensweise gezeigt, durch Konvertieren einer <xref:System.Collections.Generic.Dictionary%602>in XML und wieder zurück.</xref:System.Collections.Generic.Dictionary%602></span><span class="sxs-lookup"><span data-stu-id="8c16b-104">This topic shows a specific implementation of this general approach by converting a <xref:System.Collections.Generic.Dictionary%602> to XML and back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c16b-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c16b-105">Example</span></span>  
 <span data-ttu-id="8c16b-106">Dieses Beispiel verwendet XML-Literale und eine Abfrage in einem eingebetteten Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8c16b-106">This example uses XML literals and a query in an embedded expression.</span></span> <span data-ttu-id="8c16b-107">Die Abfrage projiziert neue <xref:System.Xml.Linq.XElement>Objekte, die dann zum neuen Inhalt für die `Root` <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="8c16b-107">The query projects new <xref:System.Xml.Linq.XElement> objects, which then become the new content for the `Root` <xref:System.Xml.Linq.XElement> object.</span></span>  
  
```vb  
Dim dict As Dictionary(Of String, String) = New Dictionary(Of String, String)()  
dict.Add("Child1", "Value1")  
dict.Add("Child2", "Value2")  
dict.Add("Child3", "Value3")  
dict.Add("Child4", "Value4")  
Dim root As XElement = _  
    <Root>  
        <%= From keyValue In dict _  
            Select New XElement(keyValue.Key, keyValue.Value) %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="8c16b-108">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8c16b-108">This code produces the following output:</span></span>  
  
```xml  
          <Root>  
  <Child1>Value1</Child1>  
  <Child2>Value2</Child2>  
  <Child3>Value3</Child3>  
  <Child4>Value4</Child4>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="8c16b-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c16b-109">Example</span></span>  
 <span data-ttu-id="8c16b-110">Der folgende Code erstellt aus dem XML-Code ein Wörterbuch:</span><span class="sxs-lookup"><span data-stu-id="8c16b-110">The following code creates a dictionary from XML.</span></span>  
  
```vb  
Dim root As XElement = _  
        <Root>  
            <Child1>Value1</Child1>  
            <Child2>Value2</Child2>  
            <Child3>Value3</Child3>  
            <Child4>Value4</Child4>  
        </Root>  
  
Dim dict As Dictionary(Of String, String) = New Dictionary(Of String, String)  
For Each el As XElement In root.Elements  
    dict.Add(el.Name.LocalName, el.Value)  
Next  
For Each str As String In dict.Keys  
    Console.WriteLine("{0}:{1}", str, dict(str))  
Next  
```  
  
 <span data-ttu-id="8c16b-111">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8c16b-111">This code produces the following output:</span></span>  
  
```  
Child1:Value1  
Child2:Value2  
Child3:Value3  
Child4:Value4  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c16b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c16b-112">See Also</span></span>  
 [<span data-ttu-id="8c16b-113">Projektionen und Transformationen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c16b-113">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)

