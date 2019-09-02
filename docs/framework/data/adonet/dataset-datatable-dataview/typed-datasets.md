---
title: Typisierte "DataSets"
ms.date: 03/30/2017
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
ms.openlocfilehash: 33876cb9f614a93cab2fa3fd9d056f94dd1e9038
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203155"
---
# <a name="typed-datasets"></a>Typisierte "DataSets"
Neben dem späten Bindungszugriff auf Werte mithilfe von schwach typisierten Variablen bietet das <xref:System.Data.DataSet> über eine stark typisierte Metapher Zugriff auf Daten. Auf Tabellen und Spalten, die Teil des **DataSets** sind, kann mit benutzerfreundlichen Namen und stark typisierten Variablen zugegriffen werden.  
  
 Ein typisiertes **DataSet** ist eine Klasse, die von einem **DataSet**abgeleitet wird. Daher erbt Sie alle Methoden, Ereignisse und Eigenschaften eines **DataSets**. Darüber hinaus stellt ein typisiertes **DataSet** stark typisierte Methoden, Ereignisse und Eigenschaften bereit. Das heißt, dass Sie auf Tabellen und Spalten anhand ihres Namens zugreifen können und keine auflistungsbasierten Methoden verwenden müssen. Abgesehen von der verbesserten Lesbarkeit des Codes ermöglicht ein typisiertes **DataSet** auch dem Visual Studio .NET-Code-Editor das automatische Vervollständigen von Zeilen während der Eingabe.  
  
 Außerdem ermöglicht das stark typisierte **DataSet** den Zugriff auf Werte als richtigen Typ zur Kompilierzeit. Bei einem **DataSet**mit starker Typisierung werden Typen Konflikt Fehler abgefangen, wenn der Code kompiliert wird, anstatt zur Laufzeit.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Generieren von stark typisierten DataSets](generating-strongly-typed-datasets.md)  
 Beschreibt das Erstellen und Verwenden eines stark typisierten **DataSets**.  
  
 [Hinzufügen von Anmerkungen zu typisierten DataSets](annotating-typed-datasets.md)  
 Beschreibt, wie das XSD-Schema (XML Schema Definition Language) mit Anmerkungen versehen wird, das zum Generieren eines stark typisierten **DataSets**verwendet wird, um **DataSet** -Elementen anzeigen Amen zu übergeben, ohne das zugrunde liegende Schema zu ändern.  
  
## <a name="see-also"></a>Siehe auch

- [DataSets, DataTables und DataViews](index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
