---
title: 'Vorgehensweise: Ermitteln untergeordneter Elemente anhand der Position (XPath-LINQ to XML) (C#)'
description: Erfahren Sie, wie Sie mithilfe eines XPath-Ausdrucks untergeordnete Elemente anhand ihrer Position finden. Hier finden Sie ein Codebeispiel, das eine XML-Beispieldatei verwendet.
ms.date: 07/20/2015
ms.assetid: e35bb269-ec86-4c96-8321-12491a0eb2c3
ms.openlocfilehash: 2603d3ac94ace645bde1ce85a43a43af7321014e
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301670"
---
# <a name="how-to-find-child-elements-based-on-position-xpath-linq-to-xml-c"></a>Vorgehensweise: Ermitteln untergeordneter Elemente anhand der Position (XPath-LINQ to XML) (C#)
Es kann passieren, dass Sie Elemente anhand ihrer Position ermitteln, also z. B. das zweite oder das dritte bis fünfte Element finden möchten.  
  
 Der XPath-Ausdruck lautet:  
  
 `Test[position() >= 2 and position() <= 4]`  
  
 Für das Schreiben dieser [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfrage mit verzögerter Auswertung gibt es zwei Ansätze: Sie können entweder die Operatoren <xref:System.Linq.Enumerable.Skip%2A> und <xref:System.Linq.Enumerable.Take%2A> verwenden, oder Sie können die <xref:System.Linq.Enumerable.Where%2A>-Überladung verwenden, die einen Index akzeptiert. Wenn Sie die <xref:System.Linq.Enumerable.Where%2A>-Überladung verwenden, verwenden Sie einen Lambdaausdruck, der zwei Argumente akzeptiert. Im folgenden Beispiel werden beide Methoden für die positionsbasierte Auswahl gezeigt:  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel ermittelt das zweite bis vierte `Test`-Element. Das Ergebnis ist eine Auflistung von Elementen.  
  
 In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Testkonfiguration (LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md).  
  
```csharp  
XElement testCfg = XElement.Load("TestConfig.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    testCfg  
    .Elements("Test")  
    .Skip(1)  
    .Take(3);  
  
// LINQ to XML query  
IEnumerable<XElement> list2 =  
    testCfg  
    .Elements("Test")  
    .Where((el, idx) => idx >= 1 && idx <= 3);  
  
// XPath expression  
IEnumerable<XElement> list3 =  
  testCfg.XPathSelectElements("Test[position() >= 2 and position() <= 4]");  
  
if (list1.Count() == list2.Count() &&  
    list1.Count() == list3.Count() &&  
    list1.Intersect(list2).Count() == list1.Count() &&  
    list1.Intersect(list3).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```output  
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
