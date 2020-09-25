---
title: "\"DataTableReaders\""
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 911a45dad3d5d82ab5e5752b1c12f7d8a6ab1563
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202317"
---
# <a name="datatablereaders"></a>"DataTableReaders"

Der <xref:System.Data.DataTableReader> stellt den Inhalt einer <xref:System.Data.DataTable> oder eines <xref:System.Data.DataSet> in Form eines oder mehrerer schreibgeschützter vorwärts gerichteter Resultsets dar.  
  
 Wenn Sie einen **DataTableReader** aus einer **Daten**Tabelle erstellen, enthält das resultierende **DataTableReader** -Objekt ein Resultset mit denselben Daten wie die Datentabelle, aus der es erstellt wurde, mit **Ausnahme von Zeilen** , die als gelöscht markiert wurden. Die Spalten werden in derselben Reihenfolge wie in der ursprünglichen **Daten**Tabelle angezeigt.  
  
 Ein **DataTableReader** kann mehrere Resultsets enthalten, wenn er durch Aufrufen von erstellt wurde <xref:System.Data.DataSet.CreateDataReader%2A> . Die Ergebnisse sind in derselben Reihenfolge wie die **DataTables** in der Auflistung des **DataSet** -Objekts <xref:System.Data.DataSet.Tables%2A> .  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Erstellen eines "DataReader"](creating-a-datareader.md)  
 Erläutert, wie ein **DataTableReader** -Objekt erstellt wird.  
  
 [Navigieren in "DataTables"](navigating-datatables.md)  
 Beschreibt die Verwendung der **Read** -Methode, um durch den Inhalt eines **DataTableReader**zu navigieren.  
  
## <a name="see-also"></a>Weitere Informationen

- [Abrufen und Ändern von Daten in ADO.NET](../retrieving-and-modifying-data.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
