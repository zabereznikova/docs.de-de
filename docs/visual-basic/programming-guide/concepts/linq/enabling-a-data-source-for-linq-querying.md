---
title: Aktivieren einer Datenquelle für LINQ Querying2
ms.date: 07/20/2015
ms.assetid: c412f0cf-ff0e-4993-ab3d-1b49e23f00f8
ms.openlocfilehash: ecd43b371a8e907e9bcfc8687c04bdd0350235ac
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636886"
---
# <a name="enabling-a-data-source-for-linq-querying"></a>Aktivieren einer Datenquelle für LINQ-Abfragen

Es gibt verschiedene Möglichkeiten, LINQ zu erweitern, damit jede beliebige Datenquelle im LINQ-Muster abgefragt werden kann. Bei der Datenquelle kann es sich u. a. um eine Datenstruktur, einen Webdienst, ein Dateisystem oder eine Datenbank handeln. Das LINQ-Muster erleichtert Clients das Abfragen einer Datenquelle, für die LINQ-Abfragen aktiviert sind, da die Syntax und das Muster der Abfrage nicht geändert werden. LINQ kann auf diese Datenquellen erweitert werden:

- Implementieren der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle in einem Typ, um LINQ to Objects Abfragen dieses Typs zu ermöglichen.

- Erstellen von Standard Abfrage Operator-Methoden wie <xref:System.Linq.Enumerable.Where%2A> und <xref:System.Linq.Enumerable.Select%2A>, die einen Typ erweitern, um benutzerdefinierte LINQ-Abfragen dieses Typs zu ermöglichen.

- Erstellen eines Anbieters für die Datenquelle, die die <xref:System.Linq.IQueryable%601>-Schnittstelle implementiert. Ein Anbieter, der diese Schnittstelle implementiert, empfängt LINQ-Abfragen in Form von Ausdrucks Baumstrukturen, die er auf benutzerdefinierte Weise ausführen kann, z. b. Remote.

- Erstellen eines Anbieters für die Datenquelle, die eine vorhandene LINQ-Technologie nutzt. Durch einen solchen Anbieter werden nicht nur Abfragen ermöglicht, sondern zusätzlich Einfüge-, Aktualisierungs- und Löschvorgänge sowie Zuordnungen für benutzerdefinierte Typen.

In diesem Thema werden diese Möglichkeiten erläutert.

## <a name="how-to-enable-linq-querying-of-your-data-source"></a>Aktivieren von LINQ-Abfragen für eine Datenquelle

### <a name="in-memory-data"></a>Daten im Arbeitsspeicher
 Es gibt zwei Möglichkeiten, LINQ-Abfragen von Daten im Arbeitsspeicher zu aktivieren. Wenn die Daten einen Typ haben, der <xref:System.Collections.Generic.IEnumerable%601>implementiert, können Sie die Daten mithilfe LINQ to Objects Abfragen. Wenn es nicht sinnvoll ist, die Enumeration des Typs durch Implementierung der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle zu aktivieren, können Sie LINQ-Standard Abfrage Operator-Methoden in diesem Typ definieren oder LINQ-Standard Abfrage Operator-Methoden erstellen, die den Typ erweitern. Benutzerdefinierte Implementierungen der Standardabfrageoperatoren sollten zur Rückgabe der Ergebnisse eine verzögerte Ausführung verwenden.

### <a name="remote-data"></a>Remotedaten
 Die beste Option zum Aktivieren von LINQ-Abfragen für eine Remote Datenquelle besteht darin, die <xref:System.Linq.IQueryable%601>-Schnittstelle zu implementieren. Dieser Ansatz unterscheidet sich jedoch vom Erweitern eines Anbieters wie [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] für eine Datenquelle. In Visual Studio 2008 sind keine Anbieter Modelle zum Erweitern vorhandener LINQ-Technologien (z. b. [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]) auf andere Datenquellen Typen verfügbar.

## <a name="iqueryable-linq-providers"></a>LINQ-Anbieter "IQueryable"
 LINQ-Anbieter, die <xref:System.Linq.IQueryable%601> implementieren, können in ihrer Komplexität sehr unterschiedlich sein. In diesem Abschnitt werden die verschiedenen Komplexitätsstufen erläutert.

 Ein weniger komplexer `IQueryable`-Anbieter erstellt möglicherweise eine Schnittstelle mit einer einzelnen Methode eines Webdiensts. Dieser Anbietertyp ist sehr spezifisch, da er erwartet, dass in den von ihm verarbeiteten Abfragen bestimmte Informationen enthalten sind. Er verfügt über ein geschlossenes Typsystem und macht möglicherweise nur einen einzelnen Ergebnistyp verfügbar. Ein Großteil der Abfrageverarbeitung erfolgt lokal, beispielsweise unter Verwendung der <xref:System.Linq.Enumerable>-Implementierungen der Standardabfrageoperatoren. Ein weniger komplexer Anbieter überprüft u. U. nur einen Ausdruck des Methodenaufrufs in der Ausdrucksbaumstruktur, die die Abfrage darstellt, und lässt die übrige Abfragelogik von einer anderen Instanz behandeln.

 Ein `IQueryable`-Anbieter mittlerer Komplexität verwendet möglicherweise eine Datenquelle als Ziel, die über eine teilweise ausdrucksbasierte Abfragesprache verfügt. Wenn ein Webdienst als Ziel verwendet wird, stellt der Anbieter vielleicht Verbindungen zu mehr als einer Webdienstmethode her und wählt die aufzurufende Methode auf der Grundlage der Frage aus, die von der Abfrage gestellt wird. Ein Anbieter mittlerer Komplexität verfügt über ein umfangreicheres Typsystem als ein einfacher Anbieter, das jedoch weiterhin ein festes Typsystem darstellt. Der Anbieter kann beispielsweise Typen verfügbar machen, die über 1:n-Beziehungen verfügen, die wiederum traversiert werden können, ohne eine Zuordnungstechnologie für benutzerdefinierte Typen bereitzustellen.

 Ein komplexer `IQueryable`-Anbieter, wie z. b. der [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]-Anbieter, kann vollständige LINQ-Abfragen in eine Ausdruckssprache wie SQL übersetzen. Ein komplexer Anbieter arbeitet universeller als ein weniger komplexer Anbieter, da er eine größere Bandbreite von Fragen in der Abfrage verarbeiten kann. Außerdem verfügt er über ein offenes Typsystem und benötigt daher eine umfassende Infrastruktur für die Zuordnung benutzerdefinierter Typen. Die Entwicklung eines komplexen Anbieters ist ziemlich arbeitsaufwändig.

## <a name="see-also"></a>Siehe auch

- <xref:System.Linq.IQueryable%601>
- <xref:System.Collections.Generic.IEnumerable%601>
- <xref:System.Linq.Enumerable>
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
