---
title: "Aktivieren einer Datenquelle für LINQ-Abfragen1 | Microsoft-Dokumentation"
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
ms.assetid: d2ef04a5-31a6-45cb-af9a-a5ce7732662c
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a5eaa6472c5fd7942f345dc5b4401b85c33504c9
ms.lasthandoff: 03/13/2017

---
# <a name="enabling-a-data-source-for-linq-querying"></a>Aktivieren einer Datenquelle für LINQ-Abfragen
Es gibt verschiedene Möglichkeiten, [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] zu erweitern, um die Abfrage einer beliebigen Datenquelle im [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Muster zu ermöglichen. Bei der Datenquelle kann es sich u. a. um eine Datenstruktur, einen Webdienst, ein Dateisystem oder eine Datenbank handeln. Das [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Muster erleichtert Clients das Ausführen von Abfragen für eine Datenquelle mit aktivierter [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfrage, da die Syntax und das Muster der Abfrage unverändert bleiben. [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] kann u.a. auf folgende Weisen für die Verwendung dieser Datenquellen erweitert werden:  
  
-   Implementieren der Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> in einen Typ, um [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-to-Objects-Abfragen dieses Typs zu aktivieren.  
  
-   Erstellen von Standardabfrageoperator-Methoden wie z.B. <xref:System.Linq.Enumerable.Where%2A> und <xref:System.Linq.Enumerable.Select%2A>, die einen Typ erweitern, um benutzerdefinierte [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfragen für diesen Typ zu aktivieren.  
  
-   Erstellen eines Anbieters für die Datenquelle, die die Schnittstelle <xref:System.Linq.IQueryable%601> implementiert. Ein Anbieter, der diese Schnittstelle implementiert, empfängt [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfragen in Form von Ausdrucksbaumstrukturen, die er benutzerdefiniert ausführen kann, beispielsweise im Remotemodus.  
  
-   Erstellen eines Anbieters für die Datenquelle, die eine vorhandene [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Technologie nutzt. Durch einen solchen Anbieter werden nicht nur Abfragen ermöglicht, sondern zusätzlich Einfüge-, Aktualisierungs- und Löschvorgänge sowie Zuordnungen für benutzerdefinierte Typen.  
  
 In diesem Thema werden diese Möglichkeiten erläutert.  
  
## <a name="how-to-enable-linq-querying-of-your-data-source"></a>Aktivieren von LINQ-Abfragen für eine Datenquelle  
  
### <a name="in-memory-data"></a>Daten im Arbeitsspeicher  
 Es gibt zwei Möglichkeiten, [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfragen von Daten im Arbeitsspeicher zu aktivieren. Wenn die Daten über einen Typ verfügen, der <xref:System.Collections.Generic.IEnumerable%601> implementiert, können Sie sie mithilfe von [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-to-Objects abfragen. Wenn es nicht sinnvoll ist, die Enumeration des Typs durch Implementierung der Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> zu aktivieren, können Sie [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Standardabfrageoperator-Methoden in diesem Typ definieren oder [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Standardabfrageoperator-Methoden erstellen, die den Typ erweitern. Benutzerdefinierte Implementierungen der Standardabfrageoperatoren sollten zur Rückgabe der Ergebnisse eine verzögerte Ausführung verwenden.  
  
### <a name="remote-data"></a>Remotedaten  
 Die beste Möglichkeit zur Aktivierung von [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfragen für eine Remotedatenquelle besteht darin, die Schnittstelle <xref:System.Linq.IQueryable%601> zu implementieren. Dieser Ansatz unterscheidet sich jedoch vom Erweitern eines Anbieters wie [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] für eine Datenquelle. Es stehen keine Anbietermodelle zum Erweitern vorhandener [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Technologien, wie [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], auf andere Datenquellentypen in [!INCLUDE[vs_orcas_long](../../../../csharp/misc/includes/vs_orcas_long_md.md)] zur Verfügung.  
  
## <a name="iqueryable-linq-providers"></a>LINQ-Anbieter "IQueryable"  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Anbieter, die <xref:System.Linq.IQueryable%601> implementieren, können in ihrer Komplexität große Unterschiede aufweisen. In diesem Abschnitt werden die verschiedenen Komplexitätsstufen erläutert.  
  
 Ein weniger komplexer `IQueryable`-Anbieter erstellt möglicherweise eine Schnittstelle mit einer einzelnen Methode eines Webdiensts. Dieser Anbietertyp ist sehr spezifisch, da er erwartet, dass in den von ihm verarbeiteten Abfragen bestimmte Informationen enthalten sind. Er verfügt über ein geschlossenes Typsystem und macht möglicherweise nur einen einzelnen Ergebnistyp verfügbar. Ein Großteil der Abfrageverarbeitung erfolgt lokal, beispielsweise unter Verwendung der Implementierungen <xref:System.Linq.Enumerable> der Standardabfrageoperatoren. Ein weniger komplexer Anbieter überprüft u. U. nur einen Ausdruck des Methodenaufrufs in der Ausdrucksbaumstruktur, die die Abfrage darstellt, und lässt die übrige Abfragelogik von einer anderen Instanz behandeln.  
  
 Ein `IQueryable`-Anbieter mittlerer Komplexität verwendet möglicherweise eine Datenquelle als Ziel, die über eine teilweise ausdrucksbasierte Abfragesprache verfügt. Wenn ein Webdienst als Ziel verwendet wird, stellt der Anbieter vielleicht Verbindungen zu mehr als einer Webdienstmethode her und wählt die aufzurufende Methode auf der Grundlage der Frage aus, die von der Abfrage gestellt wird. Ein Anbieter mittlerer Komplexität verfügt über ein umfangreicheres Typsystem als ein einfacher Anbieter, das jedoch weiterhin ein festes Typsystem darstellt. Der Anbieter kann beispielsweise Typen verfügbar machen, die über 1:n-Beziehungen verfügen, die wiederum traversiert werden können, ohne eine Zuordnungstechnologie für benutzerdefinierte Typen bereitzustellen.  
  
 Ein komplexer `IQueryable`-Anbieter, wie z. B. der [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)]-Anbieter, kann möglicherweise vollständige [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfragen in eine ausdrucksbasierte Abfragesprache wie SQL übersetzen. Ein komplexer Anbieter arbeitet universeller als ein weniger komplexer Anbieter, da er eine größere Bandbreite von Fragen in der Abfrage verarbeiten kann. Außerdem verfügt er über ein offenes Typsystem und benötigt daher eine umfassende Infrastruktur für die Zuordnung benutzerdefinierter Typen. Die Entwicklung eines komplexen Anbieters ist ziemlich arbeitsaufwändig.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq.IQueryable%601>   
 <xref:System.Collections.Generic.IEnumerable%601>   
 <xref:System.Linq.Enumerable>   
 [Übersicht über Standardabfrageoperatoren (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)
