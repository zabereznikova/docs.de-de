---
title: Atomisierte XName- und XNamespace-Objekte (LINQ to XML) (C#)
description: Hier erfahren Sie mehr über atomisierte XName- und XNamespace-Objekte und inwiefern diese Leistungsvorteile bei Abfragen bieten.
ms.date: 07/20/2015
ms.assetid: a5b21433-b49d-415c-b00e-bcbfb0d267d7
ms.openlocfilehash: 305a233adab5c860b5f9509ae25ccc5d633e7957
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104282"
---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml-c"></a>Atomisierte XName- und XNamespace-Objekte (LINQ to XML) (C#)
Die <xref:System.Xml.Linq.XName>- und <xref:System.Xml.Linq.XNamespace>-Objekte sind *atomisiert*. Dies bedeutet, dass sie auf dasselbe Objekt verweisen, wenn sie denselben qualifizierten Namen enthalten. Dadurch wird die Leistung von Abfragen verbessert: Beim Vergleichen zweier atomisierter Namen auf Übereinstimmung muss die zugrunde liegende Intermediate Language nur ermitteln, ob die beiden Verweise auf dasselbe Objekt zeigen. Im zugrunde liegenden Code müssen keine zeitaufwändigen Zeichenfolgenvergleiche ausgeführt werden.  
  
## <a name="atomization-semantics"></a>Atomisierungssemantik  
 Atomisierung bedeutet, dass zwei <xref:System.Xml.Linq.XName>-Objekte dieselbe Instanz gemeinsam nutzen, wenn sie über denselben lokalen Namen verfügen und sich im selben Namespace befinden. Dementsprechend nutzen zwei <xref:System.Xml.Linq.XNamespace>-Objekte dieselbe Instanz gemeinsam, wenn sie über denselben Namespace-URI verfügen.  
  
 Damit eine Klasse atomisierte Objekte unterstützt, muss der Konstruktor für die Klasse privat sein, nicht öffentlich. Bei einem öffentlichen Konstruktor könnten Sie ein nicht atomisiertes Objekt erstellen. Die <xref:System.Xml.Linq.XName>-Klasse und die <xref:System.Xml.Linq.XNamespace>-Klasse implementieren einen impliziten Konvertierungsoperator, um eine Zeichenfolge in einen <xref:System.Xml.Linq.XName> oder einen <xref:System.Xml.Linq.XNamespace> zu konvertieren. Auf diese Weise können Sie eine Instanz dieser Objekte abrufen. Sie können keine Instanz über einen Konstruktor abrufen, da Sie auf den Konstruktor nicht zugreifen können.  
  
 Außerdem werden von <xref:System.Xml.Linq.XName> und <xref:System.Xml.Linq.XNamespace> Gleichheits- und Ungleichheitsoperatoren implementiert, mit denen Sie ermitteln können, ob die beiden verglichenen Objekte Verweise auf dieselbe Instanz darstellen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Code werden mehrere <xref:System.Xml.Linq.XElement>-Objekte erstellt, und es wird veranschaulicht, dass identische Namen dieselbe Instanz aufweisen.  
  
```csharp  
XElement r1 = new XElement("Root", "data1");  
XElement r2 = XElement.Parse("<Root>data2</Root>");  
  
if ((object)r1.Name == (object)r2.Name)  
    Console.WriteLine("r1 and r2 have names that refer to the same instance.");  
else  
    Console.WriteLine("Different");  
  
XName n = "Root";  
  
if ((object)n == (object)r1.Name)  
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.");  
else  
    Console.WriteLine("Different");  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```output  
r1 and r2 have names that refer to the same instance.  
The name of r1 and the name in 'n' refer to the same instance.  
```  
  
 Wie bereits erwähnt, besteht der Vorteil atomisierter Objekte darin, dass beim Verwenden einer der Achsenmethoden, die als Parameter einen <xref:System.Xml.Linq.XName> erfordert, zum Auswählen der gewünschten Elemente nur ermittelt werden muss, ob die beiden Namen auf dieselbe Instanz verweisen.  
  
 Im folgenden Beispiel wird ein <xref:System.Xml.Linq.XName> an den <xref:System.Xml.Linq.XContainer.Descendants%2A>-Methodenaufruf übergeben. Dieser erreicht aufgrund des Atomarisierungsmusters eine bessere Leistung.  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("C1", 1),  
    new XElement("Z1",  
        new XElement("C1", 2),  
        new XElement("C1", 1)  
    )  
);  
  
var query = from e in root.Descendants("C1")  
            where (int)e == 1  
            select e;  
  
foreach (var z in query)  
    Console.WriteLine(z);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<C1>1</C1>  
<C1>1</C1>  
```  
