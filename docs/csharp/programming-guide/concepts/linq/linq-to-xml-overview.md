---
title: Übersicht über LINQ to XML (C#)
ms.date: 10/30/2018
ms.assetid: 716b94d3-0091-4de1-8e05-41bc069fa9dd
ms.openlocfilehash: dd41d8607ef3f2e6e6be9a1f3964ef0ae937e2ac
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241837"
---
# <a name="linq-to-xml-overview-c"></a>Übersicht über LINQ to XML (C#)

LINQ to XML stellt eine XML-Programmierschnittstelle im Arbeitsspeicher bereit, die das .NET Language-Integrated Query-Framework (LINQ) nutzt. LINQ to XML verwendet die neuesten .NET-Funktionen und ist mit einer aktualisierten und neu gestalteten DOM-XML-Programmierschnittstelle vergleichbar.

XML hat sich mittlerweile als hervorragende Möglichkeit durchgesetzt, Daten in einer Vielzahl von Kontexten zu formatieren. Sie finden XML beispielsweise im Internet, in Konfigurationsdateien, in Microsoft Office Word-Dateien und in Datenbanken.

Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] steht Ihnen ein topaktueller, völlig neu gestalteter Ansatz für die Programmierung mit XML zur Verfügung, Dabei werden die arbeitsspeicherinternen Dokumentänderungsfunktionen des Dokumentobjektmodells (DOM) bereitgestellt und LINQ-Abfrageausdrücke unterstützt. Obwohl sich diese Abfrageausdrücke syntaktisch von XPath unterscheiden, bieten sie eine ähnliche Funktionalität.

## <a name="linq-to-xml-developers"></a>LINQ to XML-Entwickler

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] eignet sich für ein breites Spektrum von Entwicklern. Für einen ganz normalen Entwickler, der einfach eine Aufgabe erledigen möchte, vereinfacht [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] das Arbeiten mit XML, weil der Umgang mit Abfragen ähnlich wie in SQL ist. Programmierer werden so innerhalb kurzer Zeit in die Lage versetzt, kompakte und dennoch leistungsfähige Abfragen in der Programmiersprache ihrer Wahl zu erstellen.

Professionelle Entwickler können mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ihre Produktivität deutlich steigern. Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] muss weniger Code geschrieben werden, und dieser Code ist ausdrucksvoller, kompakter und leistungsstärker. Sie können Abfrageausdrücke aus mehreren Datendomänen gleichzeitig verwenden.

## <a name="what-is-linq-to-xml"></a>Was ist LINQ to XML?

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist eine LINQ-fähige XML-Programmierschnittstelle im Arbeitsspeicher, mit der Sie aus .NET-Programmiersprachen heraus mit XML arbeiten können.

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ähnelt dem Dokumentobjektmodell (DOM) darin, dass das XML-Dokument im Arbeitsspeicher bereitgestellt wird. Sie können das Dokument abfragen und ändern, und nach dem Ändern können Sie es in einer Datei speichern oder es serialisieren und über das Internet versenden. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] unterscheidet sich aber auch vom DOM: Es stellt ein neues Objektmodell bereit, das leichter und einfacher zu handhaben ist und das sich Sprachfunktionen in C# zunutze macht.

Der wichtigste Vorteil von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] besteht in dessen Integration in LINQ (Language Integrated Query). Diese Integration ermöglicht es Ihnen, Abfragen für das XML-Dokument im Arbeitsspeicher zu schreiben, um Auflistungen von Elementen und Attributen abzurufen. Die Abfragefunktion von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist von ihrer Funktionalität her mit der von XPath und XQuery vergleichbar, die Syntax ist allerdings eine andere. Die Integration von LINQ in C# bietet eine stärkere Typisierung, Syntaxüberprüfung bei der Kompilierung und verbesserte Debuggerunterstützung.

Ein weiterer Vorteil von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist die Fähigkeit, Abfrageergebnisse als Parameter für <xref:System.Xml.Linq.XElement>-Objektkonstruktoren und <xref:System.Xml.Linq.XAttribute>-Objektkonstruktoren zu verwenden. Dies ist ein sehr effizienter Ansatz zum Erstellen von XML-Strukturen. Diese Herangehensweise, die als *funktionale Konstruktion* bezeichnet wird, versetzt Entwickler in die Lage, XML-Strukturen problemlos von einer Form in eine andere zu transformieren.

Nehmen Sie das Beispiel einer typischen XML-Bestellung, wie sie in [Beispiel-XML-Datei: Typische Bestellung (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml-1.md) beschrieben wird. Durch die Verwendung von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie zum Abrufen des Attributwerts der Teilenummer für jedes Artikelelement im Auftrag die folgende Abfrage ausführen:

```csharp
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load(purchaseOrderFilepath);

IEnumerable<string> partNos =  from item in purchaseOrder.Descendants("Item")
                               select (string) item.Attribute("PartNumber");
```

Diese kann im Methodensyntaxformat umgeschrieben werden:

```csharp
IEnumerable<string> partNos = purchaseOrder.Descendants("Item").Select(x => (string) x.Attribute("PartNumber"));
```

Ein anderes Beispiel: Sie möchten, sortiert nach Teilenummer, eine Liste der Artikel abfragen, deren Wert über 100 Dollar liegt. Zum Abfragen dieser Informationen könnten Sie die folgende Abfrage ausführen:

```csharp
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load(purchaseOrderFilepath);

IEnumerable<XElement> pricesByPartNos =  from item in purchaseOrder.Descendants("Item")
                                 where (int) item.Element("Quantity") * (decimal) item.Element("USPrice") > 100
                                 orderby (string)item.Element("PartNumber")
                                 select item;
```

Auch diese kann wieder im Methodensyntaxformat umgeschrieben werden:

```csharp
IEnumerable<XElement> pricesByPartNos = purchaseOrder.Descendants("Item")
                                        .Where(item => (int)item.Element("Quantity") * (decimal)item.Element("USPrice") > 100)
                                        .OrderBy(order => order.Element("PartNumber"));
```

Zusätzlich zu diesen LINQ-Funktionen stellt [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] eine verbesserte XML-Programmierschnittstelle bereit. Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie Folgendes durchführen:

- Laden Sie XML aus [Dateien](how-to-load-xml-from-a-file.md) oder [Streams](how-to-stream-xml-fragments-from-an-xmlreader.md).

- XML in Dateien oder Streams serialisieren

- XML mittels funktionaler Konstruktion von Grund auf neu erstellen

- XML mit XPath-ähnlichen Achsen abfragen

- XML-Strukturen im Arbeitsspeicher mit Methoden wie <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A> und <xref:System.Xml.Linq.XElement.SetValue%2A> bearbeiten

- XML-Strukturen mit XSD validieren

- XML-Strukturen mit einer Kombination aus diesen Funktionen von einer Form in eine andere transformieren

## <a name="creating-xml-trees"></a>Erstellen von XML-Strukturen

Einer der bedeutendsten Vorteile beim Programmieren mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist die einfache Erstellung von XML-Strukturen. Wenn Sie z.B. eine kleine XML-Struktur erstellen möchten, können Sie einen Code wie im folgenden Beispiel schreiben:

```csharp
XElement contacts =
new XElement("Contacts",
    new XElement("Contact",
        new XElement("Name", "Patrick Hines"),
        new XElement("Phone", "206-555-0144",
            new XAttribute("Type", "Home")),
        new XElement("phone", "425-555-0145",
            new XAttribute("Type", "Work")),
        new XElement("Address",
            new XElement("Street1", "123 Main St"),
            new XElement("City", "Mercer Island"),
            new XElement("State", "WA"),
            new XElement("Postal", "68042")
        )
    )
);
```

Weitere Informationen finden Sie unter [Creating XML Trees (C#) (Erstellen von XML-Strukturen (C#))](./creating-xml-trees-linq-to-xml-2.md).

## <a name="see-also"></a>Siehe auch

- [Verweis (LINQ to XML)](./reference-linq-to-xml.md)
- [LINQ to XML im Vergleich zu DOM (C#)](./linq-to-xml-vs-dom.md)
- [LINQ to XML im Vergleich zu anderen XML-Technologien](./linq-to-xml-vs-other-xml-technologies.md)
- <xref:System.Xml.Linq>
