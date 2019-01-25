---
title: Typisierte "DataSets"
ms.date: 03/30/2017
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
ms.openlocfilehash: 3a61005f0064ec9ba0bbe70b759394d3691018de
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680360"
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
