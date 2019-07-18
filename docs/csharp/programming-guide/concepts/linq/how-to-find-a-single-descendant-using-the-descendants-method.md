---
title: 'Vorgehensweise: Suchen eines einzelnen Nachfolgers mit der Descendants-Methode (C#)'
ms.date: 07/20/2015
ms.assetid: 6f735be9-0293-4680-8007-ca9d96bfebed
ms.openlocfilehash: 1979814a2a1485938b584d7774b76a020c885f0c
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486831"
---
# <a name="how-to-find-a-single-descendant-using-the-descendants-method-c"></a>Vorgehensweise: Suchen eines einzelnen Nachfolgers mit der Descendants-Methode (C#)
Mit der <xref:System.Xml.Linq.XContainer.Descendants%2A>-Achsenmethode können Sie schnell Code zum Suchen nach einem einzelnen eindeutig benannten Element schreiben. Diese Technik ist besonders nützlich, wenn Sie einen bestimmten Nachfolger mit einem bestimmten Namen ermitteln möchten. Sie könnten den Code zwar so schreiben, dass eine Navigation zum gewünschten Element erfolgt, es ist aber häufig schneller und einfacher, den Code mit der <xref:System.Xml.Linq.XContainer.Descendants%2A>-Achse zu schreiben.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der <xref:System.Linq.Enumerable.First%2A>-Standardabfrageoperator verwendet.  
  
```csharp  
XElement root = XElement.Parse(@"<Root>  
  <Child1>  
    <GrandChild1>GC1 Value</GrandChild1>  
  </Child1>  
  <Child2>  
    <GrandChild2>GC2 Value</GrandChild2>  
  </Child2>  
  <Child3>  
    <GrandChild3>GC3 Value</GrandChild3>  
  </Child3>  
  <Child4>  
    <GrandChild4>GC4 Value</GrandChild4>  
  </Child4>  
</Root>");  
string grandChild3 = (string)  
    (from el in root.Descendants("GrandChild3")  
    select el).First();  
Console.WriteLine(grandChild3);  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```  
GC3 Value  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt. Weitere Informationen finden Sie unter [Working with XML Namespaces (C#) (Arbeiten mit XML-Namespaces (C#))](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md).  
  
```csharp  
XElement root = XElement.Parse(@"<aw:Root xmlns:aw='http://www.adventure-works.com'>  
  <aw:Child1>  
    <aw:GrandChild1>GC1 Value</aw:GrandChild1>  
  </aw:Child1>  
  <aw:Child2>  
    <aw:GrandChild2>GC2 Value</aw:GrandChild2>  
  </aw:Child2>  
  <aw:Child3>  
    <aw:GrandChild3>GC3 Value</aw:GrandChild3>  
  </aw:Child3>  
  <aw:Child4>  
    <aw:GrandChild4>GC4 Value</aw:GrandChild4>  
  </aw:Child4>  
</aw:Root>");  
XNamespace aw = "http://www.adventure-works.com";  
string grandChild3 = (string)  
    (from el in root.Descendants(aw + "GrandChild3")  
     select el).First();  
Console.WriteLine(grandChild3);  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```  
GC3 Value  
```  
