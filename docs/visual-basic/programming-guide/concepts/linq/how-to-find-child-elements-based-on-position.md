---
title: 'Gewusst wie: Suchen der untergeordneten Elemente auf der Grundlage der Position (XPath-LINQ to XML) (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: 6831e1db-5e97-444f-a7a1-d0a87104b005
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7c1ef9db560de02efa20dbe88ff0e73ffd9e7fff
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-find-child-elements-based-on-position-xpath-linq-to-xml-visual-basic"></a>Gewusst wie: Suchen der untergeordneten Elemente auf der Grundlage der Position (XPath-LINQ to XML) (Visual Basic)
Es kann passieren, dass Sie Elemente anhand ihrer Position ermitteln, also z. B. das zweite oder das dritte bis fünfte Element finden möchten.  
  
 Der XPath-Ausdruck lautet:  
  
 `Test[position() >= 2 and position() <= 4]`  
  
 Für das Schreiben dieser [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Abfrage mit verzögerter Auswertung gibt es zwei Ansätze: Können Sie die <xref:System.Linq.Enumerable.Skip%2A>und <xref:System.Linq.Enumerable.Take%2A>Operatoren, oder Sie können die <xref:System.Linq.Enumerable.Where%2A>-Überladung, die einen Index akzeptiert.</xref:System.Linq.Enumerable.Where%2A> </xref:System.Linq.Enumerable.Take%2A> </xref:System.Linq.Enumerable.Skip%2A> Bei Verwendung der <xref:System.Linq.Enumerable.Where%2A>-Überladung, verwenden Sie einen Lambdaausdruck, der zwei Argumente akzeptiert.</xref:System.Linq.Enumerable.Where%2A> Im folgenden Beispiel werden beide Methoden für die positionsbasierte Auswahl gezeigt:  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel ermittelt das zweite bis vierte `Test`-Element. Das Ergebnis ist eine Auflistung von Elementen.  
  
 Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: Testkonfiguration (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).  
  
```vb  
Dim testCfg As XElement = XElement.Load("TestConfig.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = _  
    testCfg.Elements("Test").Skip(1).Take(3)  
  
'LINQ to XML query  
Dim list2 As IEnumerable(Of XElement) = _  
    testCfg.Elements("Test"). _  
    Where(Function(ByVal el, ByVal idx) idx >= 1 And idx <= 3)  
  
' XPath expression  
Dim list3 As IEnumerable(Of XElement) = _  
    testCfg.XPathSelectElements("Test[position() >= 2 and position() <= 4]")  
  
If list1.Count() = list2.Count() And _  
       list1.Count() = list3.Count() And _  
       list1.Intersect(list2).Count() = list1.Count() And _  
       list1.Intersect(list3).Count() = list1.Count() Then  
  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
Results are identical  
<Test TestId="0002" TestType="CMD">  
  <Name>Find succeeding characters</Name>  
  <CommandLine>Examp2.EXE</CommandLine>  
  <Input>abc</Input>  
  <Output>def</Output>  
</Test>  
<Test TestId="0003" TestType="GUI">  
  <Name>Convert multiple numbers to strings</Name>  
  <CommandLine>Examp2.EXE /Verbose</CommandLine>  
  <Input>123</Input>  
  <Output>One Two Three</Output>  
</Test>  
<Test TestId="0004" TestType="GUI">  
  <Name>Find correlated key</Name>  
  <CommandLine>Examp3.EXE</CommandLine>  
  <Input>a1</Input>  
  <Output>b1</Output>  
</Test>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ to XML für XPath-Benutzer (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

