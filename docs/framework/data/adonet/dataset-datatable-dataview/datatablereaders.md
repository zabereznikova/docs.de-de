---
title: "\"DataTableReaders\""
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 1559cde9cb786ccb2baf920347064b8b28d472c3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785346"
---
# <a name="datatablereaders"></a>"DataTableReaders"
Der <xref:System.Data.DataTableReader> stellt den Inhalt einer <xref:System.Data.DataTable> oder eines <xref:System.Data.DataSet> in Form eines oder mehrerer schreibgeschützter vorwärts gerichteter Resultsets dar.  
  
 Wenn Sie einen **DataTableReader** aus einer **Daten**Tabelle erstellen, enthält das resultierende **DataTableReader** -Objekt ein Resultset mit denselben Daten wie die Datentabelle, aus der es erstellt wurde, mit **Ausnahme von Zeilen** , die als Lö. Die Spalten werden in derselben Reihenfolge wie in der ursprünglichen **Daten**Tabelle angezeigt.  
  
 Ein **DataTableReader** kann mehrere Resultsets enthalten, wenn er durch Aufrufen <xref:System.Data.DataSet.CreateDataReader%2A>von erstellt wurde. Die Ergebnisse sind in derselben Reihenfolge wie die **DataTables** in der Auflistung des **DataSet** - <xref:System.Data.DataSet.Tables%2A> Objekts.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erstellen eines DataReader](creating-a-datareader.md)  
 Erläutert, wie ein **DataTableReader** -Objekt erstellt wird.  
  
 [Navigieren in DataTables](navigating-datatables.md)  
 Beschreibt die Verwendung der **Read** -Methode, um durch den Inhalt eines **DataTableReader**zu navigieren.  
  
## <a name="see-also"></a>Siehe auch

- [Abrufen und Ändern von Daten in ADO.NET](../retrieving-and-modifying-data.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
