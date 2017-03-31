---
title: 'Vorgehensweise: Abrufen des Shallow-Werts eines Elements (C#) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 924a2699-72f6-4be1-aaa6-de62f8ec73b9
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d96dc59c2d798f11d949e26d208a2ce71d9c4de2
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-c"></a>Vorgehensweise: Abrufen des Shallow-Werts eines Elements (C#)
In diesem Thema wird gezeigt, wie Sie den flachen Wert eines Elements abrufen. Der flache Wert ist ausschließlich der Wert des jeweiligen Elements, im Gegensatz zum tiefen Wert, der die Werte aller Nachfolgerelemente enthält, die zu einer einzelnen Zeichenkette verkettet werden.  
  
 Beim Abrufen des Elementwerts mithilfe des Umwandlungsverfahrens oder der <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>-Eigenschaft wird der tiefe Wert abgerufen. Um den flachen Wert abzurufen, können Sie die `ShallowValue`-Erweiterungsmethode verwenden, wie im folgenden Beispiel gezeigt wird. Das Abrufen des flachen Werts ist nützlich, wenn Sie Elemente anhand ihrer Inhalte auswählen möchten.  
  
 Im folgenden Beispiel wird eine Erweiterungsmethode deklariert, die den flachen Wert eines Elements abruft. Anschließend wird die Erweiterungsmethode in einer Abfrage verwendet, um alle Elemente aufzulisten, die einen berechneten Wert enthalten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die folgende Textdatei, Report.xml, als Quelldatei verwendet.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<Report>  
  <Section>  
    <Heading>  
      <Column Name="CustomerId">=Customer.CustomerId.Heading</Column>  
      <Column Name="Name">=Customer.Name.Heading</Column>  
    </Heading>  
    <Detail>  
      <Column Name="CustomerId">=Customer.CustomerId</Column>  
      <Column Name="Name">=Customer.Name</Column>  
    </Detail>  
  </Section>  
</Report>  
```  
  
```csharp  
public static class MyExtensions  
{  
    public static string ShallowValue(this XElement xe)  
    {  
        return xe  
               .Nodes()  
               .OfType<XText>()  
               .Aggregate(new StringBuilder(),  
                          (s, c) => s.Append(c),  
                          s => s.ToString());  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        XElement root = XElement.Load("Report.xml");  
  
        IEnumerable<XElement> query = from el in root.Descendants()  
                                      where el.ShallowValue().StartsWith("=")  
                                      select el;  
  
        foreach (var q in query)  
        {  
            Console.WriteLine("{0}{1}{2}",  
                q.Name.ToString().PadRight(8),  
                q.Attribute("Name").ToString().PadRight(20),  
                q.ShallowValue());  
        }  
    }  
}  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
Column  Name="CustomerId"   =Customer.CustomerId.Heading  
Column  Name="Name"         =Customer.Name.Heading  
Column  Name="CustomerId"   =Customer.CustomerId  
Column  Name="Name"         =Customer.Name  
```  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ to XML-Achsen (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
