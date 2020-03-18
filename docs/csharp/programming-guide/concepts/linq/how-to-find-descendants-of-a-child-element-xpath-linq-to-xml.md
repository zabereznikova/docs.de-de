---
title: 'Vorgehensweise: Suchen nach Nachfolgern von untergeordneten Elementen (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 505b7512-bb8b-4f85-abbf-491f039c961e
ms.openlocfilehash: fb3e20ce21c1f6d2a71f2f71b8acec7cecf0f3ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141096"
---
# <a name="how-to-find-descendants-of-a-child-element-xpath-linq-to-xml-c"></a>Vorgehensweise: Suchen nach Nachfolgern von untergeordneten Elementen (XPath-LINQ to XML) (C#)
In diesem Thema wird gezeigt, wie Sie die Nachfolgerelemente untergeordneter Elemente mit einem bestimmten Namen ermitteln können.  
  
 Der XPath-Ausdruck lautet:  
  
 `./Paragraph//Text/text()`  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel simuliert die Probleme beim Extrahieren von Text aus einer XML-Darstellung eines mit einem Textverarbeitungsprogramm erstellten Dokuments. Zunächst werden alle `Paragraph`-Elemente ausgewählt, dann erfolgt die Auswahl aller `Text`-Nachfolgerelemente des jeweiligen `Paragraph`-Elements. Die `Text`-Nachfolgerelemente des untergeordneten `Comment`-Elements werden nicht ausgewählt.  
  
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
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```output  
Results are identical  
This is the start of a sentence.  This is a second sentence.  
```  
  