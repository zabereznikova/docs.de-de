---
title: "Aktivieren einer Datenquelle für LINQ-Querying2 | Microsoft-Dokumentation"
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
ms.assetid: c412f0cf-ff0e-4993-ab3d-1b49e23f00f8
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 34bdc4e056d982799eac35eb2398dd3f23f6f351
ms.lasthandoff: 03/13/2017

---
# <a name="enabling-a-data-source-for-linq-querying"></a>Aktivieren einer Datenquelle für LINQ-Abfragen
Es gibt verschiedene Methoden zum Erweitern von [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] um abgefragt werden, in einer beliebigen Datenquelle aktivieren die [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Muster. Bei der Datenquelle kann es sich u. a. um eine Datenstruktur, einen Webdienst, ein Dateisystem oder eine Datenbank handeln. Das [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Muster erleichtert Clients das Ausführen von Abfragen für eine Datenquelle mit aktivierter [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfrage, da die Syntax und das Muster der Abfrage unverändert bleiben. Auf welche Weise [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] können erweitert werden, auf diese Daten Quellen umfassen Folgendes:  
  
-   Implementieren der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle in einem Typ aktivieren [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] to Objects-Abfragen für diesen Typ.</xref:System.Collections.Generic.IEnumerable%601>  
  
-   Erstellen von Standardabfrageoperator-Methoden wie z. B. <xref:System.Linq.Enumerable.Where%2A>und <xref:System.Linq.Enumerable.Select%2A>, die einen Typ erweitern, um benutzerdefinierte aktivieren [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfragen für diesen Typ.</xref:System.Linq.Enumerable.Select%2A> </xref:System.Linq.Enumerable.Where%2A>  
  
-   Erstellen eines Anbieters für die Datenquelle, die implementiert die <xref:System.Linq.IQueryable%601>Schnittstelle.</xref:System.Linq.IQueryable%601> Ein Anbieter, der diese Schnittstelle implementiert, empfängt [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfragen in Form von Ausdrucksbaumstrukturen, die er benutzerdefiniert ausführen kann, beispielsweise im Remotemodus.  
  
-   Erstellen eines Anbieters für die Datenquelle, die einer vorhandenen nutzt [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Technologie. Durch einen solchen Anbieter werden nicht nur Abfragen ermöglicht, sondern zusätzlich Einfüge-, Aktualisierungs- und Löschvorgänge sowie Zuordnungen für benutzerdefinierte Typen.  
  
 In diesem Thema werden diese Möglichkeiten erläutert.  
  
## <a name="how-to-enable-linq-querying-of-your-data-source"></a>Aktivieren von LINQ-Abfragen für eine Datenquelle  
  
### <a name="in-memory-data"></a>Daten im Arbeitsspeicher  
 Es gibt zwei Möglichkeiten, die Sie aktivieren können [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfragen von Daten im Arbeitsspeicher. Wenn die Daten von einem Typ ist, implementiert <xref:System.Collections.Generic.IEnumerable%601>, können Sie die Daten mithilfe von Abfragen [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Objekte.</xref:System.Collections.Generic.IEnumerable%601> Wenn es nicht sinnvoll ist, aktivieren Sie die Enumeration des Typs durch Implementierung der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle, die Sie definieren [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] standard Standardabfrageoperator-Methoden in diesem Typ oder erstellen Sie [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Standardabfrageoperator-Methoden, die den Typ erweitern.</xref:System.Collections.Generic.IEnumerable%601> Benutzerdefinierte Implementierungen der Standardabfrageoperatoren sollten zur Rückgabe der Ergebnisse eine verzögerte Ausführung verwenden.  
  
### <a name="remote-data"></a>Remotedaten  
 Die beste Möglichkeit zur Aktivierung [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] -Abfragen für eine Remotedatenquelle besteht darin, implementieren die <xref:System.Linq.IQueryable%601>Schnittstelle.</xref:System.Linq.IQueryable%601> Dieser Ansatz unterscheidet sich jedoch vom Erweitern eines Anbieters wie [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] für eine Datenquelle. Keine anbietermodelle zum Erweitern vorhandener [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] -Technologien, wie z. B. [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], um andere Arten von Datenquellen stehen in [!INCLUDE[vs_orcas_long](../../../../csharp/misc/includes/vs_orcas_long_md.md)].  
  
## <a name="iqueryable-linq-providers"></a>LINQ-Anbieter "IQueryable"  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]Anbieter, die implementieren <xref:System.Linq.IQueryable%601>können in ihrer Komplexität stark variieren.</xref:System.Linq.IQueryable%601> In diesem Abschnitt werden die verschiedenen Komplexitätsstufen erläutert.  
  
 Ein weniger komplexer `IQueryable`-Anbieter erstellt möglicherweise eine Schnittstelle mit einer einzelnen Methode eines Webdiensts. Dieser Anbietertyp ist sehr spezifisch, da er erwartet, dass in den von ihm verarbeiteten Abfragen bestimmte Informationen enthalten sind. Er verfügt über ein geschlossenes Typsystem und macht möglicherweise nur einen einzelnen Ergebnistyp verfügbar. Die meisten der Ausführung der Abfrage erfolgt lokal, z. B. durch Verwendung der <xref:System.Linq.Enumerable>Implementierungen der Standardabfrageoperatoren.</xref:System.Linq.Enumerable> Ein weniger komplexer Anbieter überprüft u. U. nur einen Ausdruck des Methodenaufrufs in der Ausdrucksbaumstruktur, die die Abfrage darstellt, und lässt die übrige Abfragelogik von einer anderen Instanz behandeln.  
  
 Ein `IQueryable`-Anbieter mittlerer Komplexität verwendet möglicherweise eine Datenquelle als Ziel, die über eine teilweise ausdrucksbasierte Abfragesprache verfügt. Wenn ein Webdienst als Ziel verwendet wird, stellt der Anbieter vielleicht Verbindungen zu mehr als einer Webdienstmethode her und wählt die aufzurufende Methode auf der Grundlage der Frage aus, die von der Abfrage gestellt wird. Ein Anbieter mittlerer Komplexität verfügt über ein umfangreicheres Typsystem als ein einfacher Anbieter, das jedoch weiterhin ein festes Typsystem darstellt. Der Anbieter kann beispielsweise Typen verfügbar machen, die über&1;:n-Beziehungen verfügen, die wiederum traversiert werden können, ohne eine Zuordnungstechnologie für benutzerdefinierte Typen bereitzustellen.  
  
 Ein komplexer `IQueryable`-Anbieter, wie z. B. der [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)]-Anbieter, kann möglicherweise vollständige [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfragen in eine ausdrucksbasierte Abfragesprache wie SQL übersetzen. Ein komplexer Anbieter arbeitet universeller als ein weniger komplexer Anbieter, da er eine größere Bandbreite von Fragen in der Abfrage verarbeiten kann. Außerdem verfügt er über ein offenes Typsystem und benötigt daher eine umfassende Infrastruktur für die Zuordnung benutzerdefinierter Typen. Die Entwicklung eines komplexen Anbieters ist ziemlich arbeitsaufwändig.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq.IQueryable%601></xref:System.Linq.IQueryable%601>   
 <xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>   
 <xref:System.Linq.Enumerable></xref:System.Linq.Enumerable>   
 [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
