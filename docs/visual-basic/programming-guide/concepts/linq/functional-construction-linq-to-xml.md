---
title: Funktionale Konstruktion (LINQ to XML) (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: feac4273-39ab-43ae-bab7-4059c807a785
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b88b67aca337b893f9f276c8e4a6589b6946069b
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="functional-construction-linq-to-xml-visual-basic"></a><span data-ttu-id="2b61b-102">Funktionale Konstruktion (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b61b-102">Functional Construction (LINQ to XML) (Visual Basic)</span></span>
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="2b61b-103">bietet eine leistungsfähige Möglichkeit zur Erstellung von XML-Elementen *funktionale Konstruktion*.</span><span class="sxs-lookup"><span data-stu-id="2b61b-103"> provides a powerful way to create XML elements called *functional construction*.</span></span> <span data-ttu-id="2b61b-104">Funktionale Konstruktion ist die Fähigkeit, eine XML-Struktur in einer einzelnen Anweisung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2b61b-104">Functional construction is the ability to create an XML tree in a single statement.</span></span>  
  
 <span data-ttu-id="2b61b-105">Es gibt mehrere wichtige Features der [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Programmierschnittstelle, die für die funktionale Konstruktion verantwortlich sind:</span><span class="sxs-lookup"><span data-stu-id="2b61b-105">There are several key features of the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] programming interface that enable functional construction:</span></span>  
  
-   <span data-ttu-id="2b61b-106">Die <xref:System.Xml.Linq.XElement>Konstruktor akzeptiert verschiedene Argumentarten als Inhalt.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="2b61b-106">The <xref:System.Xml.Linq.XElement> constructor takes various types of arguments for content.</span></span> <span data-ttu-id="2b61b-107">Sie können z. B. übergeben einer anderen <xref:System.Xml.Linq.XElement>-Objekt, das ein untergeordnetes Element wird.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="2b61b-107">For example, you can pass another <xref:System.Xml.Linq.XElement> object, which becomes a child element.</span></span> <span data-ttu-id="2b61b-108">Sie können übergeben ein <xref:System.Xml.Linq.XAttribute>-Objekt, das ein Attribut des Elements wird.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="2b61b-108">You can pass an <xref:System.Xml.Linq.XAttribute> object, which becomes an attribute of the element.</span></span> <span data-ttu-id="2b61b-109">Oder Sie übergeben ein beliebiges anderes Objekt, das in eine Zeichenfolge konvertiert wird und zum Textinhalt des Elements wird.</span><span class="sxs-lookup"><span data-stu-id="2b61b-109">Or you can pass any other type of object, which is converted to a string and becomes the text content of the element.</span></span>  
  
-   <span data-ttu-id="2b61b-110">Die <xref:System.Xml.Linq.XElement>Konstruktor akzeptiert ein `params` Array vom Typ <xref:System.Object>, sodass Sie beliebig viele Objekte an den Konstruktor übergeben können.</xref:System.Object> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="2b61b-110">The <xref:System.Xml.Linq.XElement> constructor takes a `params` array of type <xref:System.Object>, so that you can pass any number of objects to the constructor.</span></span> <span data-ttu-id="2b61b-111">Auf diese Weise können Sie ein Element erstellen, das über komplexen Inhalt verfügt.</span><span class="sxs-lookup"><span data-stu-id="2b61b-111">This enables you to create an element that has complex content.</span></span>  
  
-   <span data-ttu-id="2b61b-112">Wenn ein Objekt implementiert <xref:System.Collections.Generic.IEnumerable%601>, die Auflistung im Objekt aufgezählt, und alle Elemente in der Auflistung hinzugefügt werden.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="2b61b-112">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="2b61b-113">Wenn die Auflistung enthält <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XAttribute>Objekte, die jedes Element in der Auflistung getrennt hinzugefügt.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="2b61b-113">If the collection contains <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="2b61b-114">Dies ist wichtig, da Sie die Übergabe der Ergebnisse von können eine [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfrage an den Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="2b61b-114">This is important because it lets you pass the results of a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query to the constructor.</span></span>  
  
 <span data-ttu-id="2b61b-115">Im Folgenden finden Sie ein Beispiel dazu:</span><span class="sxs-lookup"><span data-stu-id="2b61b-115">The following is an example:</span></span>  
  
 <span data-ttu-id="2b61b-116">Diese Funktionen ermöglichen Ihnen das Schreiben von Code mit XML-Literalen, um eine XML-Struktur zu erstellen und Code schreiben, der die Ergebnisse der [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfragen, wenn Sie eine XML-Struktur erstellen:</span><span class="sxs-lookup"><span data-stu-id="2b61b-116">These features enable you to write code using XML literals to create an XML tree, and also to write code that uses the results of [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] queries when you create an XML tree:</span></span>  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where CInt(el) > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
```  
  
 <span data-ttu-id="2b61b-117">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="2b61b-117">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b61b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b61b-118">See Also</span></span>  
 [<span data-ttu-id="2b61b-119">Erstellen von XML-Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b61b-119">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
