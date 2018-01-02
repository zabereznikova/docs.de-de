---
title: Typisierte "DataSets"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6ede928352c9e0f02f6ad4c27ce8f5347b868986
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="typed-datasets"></a>Typisierte "DataSets"
Neben dem späten Bindungszugriff auf Werte mithilfe von schwach typisierten Variablen bietet das <xref:System.Data.DataSet> über eine stark typisierte Metapher Zugriff auf Daten. Tabellen und Spalten, die Teil der **DataSet** mithilfe von benutzerfreundlichen Namen zugegriffen werden kann und stark typisierten Variablen.  
  
 Eine typisierte **DataSet** ist eine Klasse, die von abgeleitet ist ein **DataSet**. Es erbt alle Methoden, Ereignisse und Eigenschaften einer **DataSet**. Darüber hinaus eine typisierte **DataSet** stellt stark typisierte Methoden, Ereignisse und Eigenschaften bereit. Das heißt, dass Sie auf Tabellen und Spalten anhand ihres Namens zugreifen können und keine auflistungsbasierten Methoden verwenden müssen. Abgesehen von der verbesserten Lesbarkeit des Codes, eine typisierte **DataSet** können auch den Visual Studio .NET Code-Editor, um Zeilen während der Eingabe automatisch zu vervollständigen.  
  
 Darüber hinaus die stark typisierte **DataSet** ermöglicht den Zugriff auf Werte als richtigen Typ zum Zeitpunkt der Kompilierung. Mit einem stark typisierten **DataSet**, Konflikt-Typfehler werden abgefangen, wenn der Code wird kompiliert statt zur Laufzeit.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Generieren von stark typisierten DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-strongly-typed-datasets.md)  
 Beschreibt das Erstellen und Verwenden eines stark typisierten **DataSet**.  
  
 [Hinzufügen von Anmerkungen zu typisierten DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/annotating-typed-datasets.md)  
 Beschreibt die Vorgehensweise zum Erstellen eines stark typisierten Schema der XML Schema Definition Language (XSD) mit Anmerkungen versehen **DataSet**, um **DataSet** -Elementen lange Namen ohne die zugrunde liegende Schema ändern.  
  
## <a name="see-also"></a>Siehe auch  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
