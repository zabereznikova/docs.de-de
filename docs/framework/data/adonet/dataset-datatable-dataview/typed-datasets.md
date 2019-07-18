---
title: Typisierte "DataSets"
ms.date: 03/30/2017
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
ms.openlocfilehash: 92ed3f8fd392238785fd2d205668f14fe477f2b8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607125"
---
# <a name="typed-datasets"></a>Typisierte "DataSets"
Neben dem späten Bindungszugriff auf Werte mithilfe von schwach typisierten Variablen bietet das <xref:System.Data.DataSet> über eine stark typisierte Metapher Zugriff auf Daten. Tabellen und Spalten, die Teil der **DataSet** mithilfe von benutzerfreundlichen Namen zugegriffen werden kann und stark typisierten Variablen.  
  
 Eine typisierte **DataSet** ist eine abgeleitete Klasse eine **DataSet**. Es erbt alle Methoden, Ereignisse und Eigenschaften einer **DataSet**. Darüber hinaus eine typisierte **DataSet** stellt stark typisierte Methoden, Ereignisse und Eigenschaften bereit. Das heißt, dass Sie auf Tabellen und Spalten anhand ihres Namens zugreifen können und keine auflistungsbasierten Methoden verwenden müssen. Neben der verbesserten Lesbarkeit des Codes, eine typisierte **DataSet** ermöglicht auch die Visual Studio .NET Code-Editor, um Zeilen während der Eingabe automatisch zu vervollständigen.  
  
 Darüber hinaus den stark typisierten **DataSet** ermöglicht den Zugriff auf Werte als der richtige Typ zum Zeitpunkt der Kompilierung. Mit einem stark typisierten **DataSet**, Typkonflikte werden abgefangen, wenn der Code wird kompiliert statt zur Laufzeit.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Generieren von stark typisierten DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-strongly-typed-datasets.md)  
 Beschreibt das Erstellen und Verwenden eines stark typisierten **DataSet**.  
  
 [Hinzufügen von Anmerkungen zu typisierten DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/annotating-typed-datasets.md)  
 Beschreibt, wie Sie die XML-Schema (XSD Schema Definition Language) verwendet, um eine stark typisierte generieren mit Anmerkungen versehen **DataSet**, um **DataSet** -Elementen lange Namen ohne das zugrunde liegende Schema ändern.  
  
## <a name="see-also"></a>Siehe auch

- [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
