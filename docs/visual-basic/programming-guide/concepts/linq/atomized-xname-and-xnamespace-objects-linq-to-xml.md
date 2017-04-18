---
title: Atomisierte XName- und XNamespace-Objekte (LINQ to XML) (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 21ee7585-7df9-40b4-8c76-a12bb5f29bb3
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b08f3116f5acb404cf2c33072ec31fbaada4e7cb
ms.lasthandoff: 03/13/2017


---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml-visual-basic"></a>Atomisierte XName- und XNamespace-Objekte (LINQ to XML) (Visual Basic)
<xref:System.Xml.Linq.XName>und <xref:System.Xml.Linq.XNamespace>Objekte sind *atomisiert*; Dies bedeutet, wenn sie denselben qualifizierten Namen enthalten, sie verweisen auf das gleiche Objekt.</xref:System.Xml.Linq.XNamespace></xref:System.Xml.Linq.XName> Dadurch wird die Leistung von Abfragen verbessert: Beim Vergleichen zweier atomisierter Namen auf Übereinstimmung muss die zugrunde liegende Intermediate Language nur ermitteln, ob die beiden Verweise auf dasselbe Objekt zeigen. Im zugrunde liegenden Code müssen keine zeitaufwändigen Zeichenfolgenvergleiche ausgeführt werden.  
  
## <a name="atomization-semantics"></a>Atomisierungssemantik  
 Atomisierung bedeutet, dass die zwei <xref:System.Xml.Linq.XName>Objekte verfügen über denselben lokalen Namen, und sie befinden sich im gleichen Namespace, die dieselbe Instanz gemeinsam nutzen.</xref:System.Xml.Linq.XName> Auf die gleiche Weise, wenn zwei <xref:System.Xml.Linq.XNamespace>-Objekte weisen denselben Namespace-URI, die dieselbe Instanz gemeinsam nutzen.</xref:System.Xml.Linq.XNamespace>  
  
 Damit eine Klasse atomisierte Objekte unterstützt, muss der Konstruktor für die Klasse privat sein, nicht öffentlich. Bei einem öffentlichen Konstruktor könnten Sie ein nicht atomisiertes Objekt erstellen. Die <xref:System.Xml.Linq.XName>und <xref:System.Xml.Linq.XNamespace>Klassen implementieren einen impliziten Konvertierungsoperator zum Konvertieren einer Zeichenfolge in einen <xref:System.Xml.Linq.XName>oder <xref:System.Xml.Linq.XNamespace>.</xref:System.Xml.Linq.XNamespace> </xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XNamespace> </xref:System.Xml.Linq.XName> Auf diese Weise können Sie eine Instanz dieser Objekte abrufen. Sie können keine Instanz über einen Konstruktor abrufen, da Sie auf den Konstruktor nicht zugreifen können.  
  
 <xref:System.Xml.Linq.XName>und <xref:System.Xml.Linq.XNamespace>implementieren auch die Gleichheits- und Ungleichheitsoperatoren Operatoren, um festzustellen, ob die beiden verglichenen Objekte Verweise auf die gleiche Instanz.</xref:System.Xml.Linq.XNamespace></xref:System.Xml.Linq.XName>  
  
## <a name="example"></a>Beispiel  
 Der folgende Code erstellt einige <xref:System.Xml.Linq.XElement>-Objekte und veranschaulicht, dass identische Namen dieselbe Instanz aufweisen.</xref:System.Xml.Linq.XElement>  
  
```vb  
Dim r1 As New XElement("Root", "data1")  
Dim r2 As XElement = XElement.Parse("<Root>data2</Root>")  
  
If DirectCast(r1.Name, Object) = DirectCast(r2.Name, Object) Then  
    Console.WriteLine("r1 and r2 have names that refer to the same instance.")  
Else  
    Console.WriteLine("Different")  
End If  
  
Dim n As XName = "Root"  
  
If DirectCast(n, Object) = DirectCast(r1.Name, Object) Then  
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.")  
Else  
    Console.WriteLine("Different")  
End If  
  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
r1 and r2 have names that refer to the same instance.  
The name of r1 and the name in 'n' refer to the same instance.  
```  
  
 Wie bereits erwähnt, der Vorteil, dass atomisierte Objekte sich ergibt, wenn Sie eine der Achsenmethoden verwenden, die eine <xref:System.Xml.Linq.XName>als Parameter der Axis-Methode hat nur ermitteln, ob die beiden Namen der gleichen Instanz zum Auswählen der gewünschten Elemente verweisen.</xref:System.Xml.Linq.XName>  
  
 Das folgende Beispiel übergibt eine <xref:System.Xml.Linq.XName>an die <xref:System.Xml.Linq.XContainer.Descendants%2A>-Methodenaufruf, der aufgrund des atomarisierungsmusters eine bessere Leistung aufweist.</xref:System.Xml.Linq.XContainer.Descendants%2A> </xref:System.Xml.Linq.XName>  
  
```vb  
Dim root As New XElement("Root", New XElement("C1", 1), New XElement("Z1", New XElement("C1", 2), New XElement("C1", 1)))  
  
Dim query = From e In root.Descendants("C1") Where CInt(e) = 1e  
  
For Each z As var In query  
    Console.WriteLine(z)  
Next  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
<C1>1</C1>  
<C1>1</C1>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Leistung (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)
