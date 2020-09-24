---
title: DataTable-Schemadefinition
ms.date: 03/30/2017
ms.assetid: efbcdda4-f5a9-421d-8be2-4c194c74552f
ms.openlocfilehash: 0c14c6012c65039e1e2e7e2d2d8c38c4202b45a7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153247"
---
# <a name="datatable-schema-definition"></a>DataTable-Schemadefinition

Das Schema oder die Struktur einer Tabelle wird durch Spalten und Einschränkungen dargestellt. Das Schema einer <xref:System.Data.DataTable> wird mit <xref:System.Data.DataColumn>-Objekten sowie <xref:System.Data.ForeignKeyConstraint>-Objekten und <xref:System.Data.UniqueConstraint>-Objekten definiert. Die Spalten einer Tabelle können Spalten in einer Datenquelle zugeordnet sein, berechnete Werte aus Ausdrücken enthalten, Werte automatisch erhöhen oder primäre Schlüsselwerte enthalten.  
  
 Bei Verweisen auf Namen von Spalten, Beziehungen und Einschränkungen in einer Tabelle muss die Groß- und Kleinschreibung berücksichtigt werden. Folglich können zwei oder mehr Spalten, Beziehungen oder Einschränkungen in einer Tabelle vorhanden sein, die den gleichen Namen in unterschiedlicher Schreibweise aufweisen. Beispielsweise können Sie über **col1** und **col1**verfügen. In diesem Fall muss die Schreibweise des Verweises auf eine der Spalten genau mit der Schreibweise des Namens der Spalte übereinstimmen. Andernfalls wird eine Ausnahme ausgelöst. Wenn die Tabelle " **MyTable** " z. b. die Spalten **col1** und **col1**enthält, verweisen Sie auf **col1** by Name als **myTable. Columns ["col1"]** und **col1** as **myTable. Columns ["col1"]**. Wenn Sie versuchen, auf eine der Spalten als **myTable. Columns ["col1"]** zu verweisen, wird eine Ausnahme generiert.  
  
 Die Groß- und Kleinschreibung muss nicht berücksichtigt werden, wenn jeweils nur eine Spalte, Beziehung oder Einschränkung einen bestimmten Namen aufweist. Das bedeutet, wenn kein anderes Spalten-, Beziehungs- oder Einschränkungsobjekt in der Tabelle mit dem Namen dieses bestimmten Spalten-, Beziehungs- oder Einschränkungsobjekts übereinstimmt, muss die Groß- und Kleinschreibung bei dem Verweis auf das Objekt nicht berücksichtigt werden, und es wird keine Ausnahme ausgelöst. Wenn die Tabelle z. b. nur **col1**enthält, können Sie mit My darauf verweisen **. Spalten ["col1"]**.  
  
> [!NOTE]
> Die- <xref:System.Data.DataTable.CaseSensitive%2A> Eigenschaft der **Daten** Tabelle wirkt sich nicht auf dieses Verhalten aus. Die **CaseSensitive** -Eigenschaft gilt für die Daten in einer Tabelle und wirkt sich auf das Sortieren, suchen, Filtern, Erzwingen von Einschränkungen und so weiter aus, aber nicht auf Verweise auf Spalten, Beziehungen und Einschränkungen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Hinzufügen von Spalten zu einer "DataTable"](adding-columns-to-a-datatable.md)  
 Beschreibt, wie die Spalten einer Tabelle mithilfe von **datacolumschlag** -Objekten definiert werden.  
  
 [Erstellen von Ausdrucksspalten](creating-expression-columns.md)  
 Erläutert, wie die **Expression** -Eigenschaft einer Spalte verwendet werden kann, um Werte auf der Grundlage der Werte aus anderen Spalten in der Zeile zu berechnen.  
  
 [Erstellen von AutoIncrement-Spalten](creating-autoincrement-columns.md)  
 Beschreibt, wie eine Spalte so festgelegt werden kann, dass die numerischen Werte automatisch erhöht werden, um sicherzustellen, dass die Werte in einer Spalte eindeutig sind.  
  
 [Definieren von Primärschlüsseln](defining-primary-keys.md)  
 Beschreibt, wie der Primärschlüssel einer Tabelle aus einem oder mehreren **datacolumschlag** -Objekten angegeben wird.  
  
 [DataTable-Einschränkungen](datatable-constraints.md)  
 Beschreibt, wie Fremdschlüsseleinschränkungen und eindeutige Einschränkungen für Spalten in einer Tabelle definiert werden.  
  
## <a name="see-also"></a>Weitere Informationen

- ["DataTables"](datatables.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
