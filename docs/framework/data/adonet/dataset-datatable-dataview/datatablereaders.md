---
title: "\"DataTableReaders\""
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 1ff7868b59c6fdc4e6c443be1b831accc84f36a6
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203816"
---
# <a name="datatablereaders"></a>"DataTableReaders"
Der <xref:System.Data.DataTableReader> stellt den Inhalt einer <xref:System.Data.DataTable> oder eines <xref:System.Data.DataSet> in Form eines oder mehrerer schreibgeschützter vorwärts gerichteter Resultsets dar.  
  
 Wenn Sie einen **DataTableReader** aus einer **Daten**Tabelle erstellen, enthält das resultierende **DataTableReader** -Objekt ein Resultset mit denselben Daten wie die Datentabelle, aus der es erstellt wurde, mit Ausnahme von Zeilen, die als Lö. Die Spalten werden in derselben Reihenfolge wie in der ursprünglichen **Daten**Tabelle angezeigt.  
  
 Ein **DataTableReader** kann mehrere Resultsets enthalten, wenn er durch Aufrufen <xref:System.Data.DataSet.CreateDataReader%2A>von erstellt wurde. Die Ergebnisse sind in derselben Reihenfolge wie die **DataTables** in der Auflistung des **DataSet** - <xref:System.Data.DataSet.Tables%2A> Objekts.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erstellen eines DataReader](creating-a-datareader.md)  
 Erläutert, wie ein **DataTableReader** -Objekt erstellt wird.  
  
 [Navigieren in DataTables](navigating-datatables.md)  
 Beschreibt die Verwendung der **Read** -Methode, um durch den Inhalt eines **DataTableReader**zu navigieren.  
  
## <a name="see-also"></a>Siehe auch

- [Abrufen und Ändern von Daten in ADO.NET](../retrieving-and-modifying-data.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
