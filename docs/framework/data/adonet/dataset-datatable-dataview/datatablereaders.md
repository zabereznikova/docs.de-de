---
title: "\"DataTableReaders\""
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 0e3f3da6554239b4f04e244d3339a4280e1add85
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="datatablereaders"></a>"DataTableReaders"
Der <xref:System.Data.DataTableReader> stellt den Inhalt einer <xref:System.Data.DataTable> oder eines <xref:System.Data.DataSet> in Form eines oder mehrerer schreibgeschützter vorwärts gerichteter Resultsets dar.  
  
 Beim Erstellen einer **DataTableReader** aus einem **DataTable**, das resultierende **DataTableReader** Objekt enthält die gleichen Daten wie ein Resultset der  **DataTable** aus dem er, mit Ausnahme von Zeilen erstellt wurde, die als gelöscht markiert wurden. Die Spalten angezeigt werden, in der gleichen Reihenfolge wie in der ursprünglichen **DataTable**.  
  
 Ein **DataTableReader** kann mehrere Resultsets enthalten, wenn er durch den Aufruf erstellt wurde <xref:System.Data.DataSet.CreateDataReader%2A>. Die Ergebnisse werden in der gleichen Reihenfolge wie die **DataTables** in der **DataSet** des Objekts <xref:System.Data.DataSet.Tables%2A> Auflistung.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erstellen eines DataReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 Erläutert das Erstellen einer **DataTableReader** Objekt.  
  
 [Navigieren in DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 Beschreibt die Verwendung von der **lesen** -Methode durch den Inhalt des Verschieben einer **DataTableReader**.  
  
## <a name="see-also"></a>Siehe auch  
 [Abrufen und Ändern von Daten in ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
