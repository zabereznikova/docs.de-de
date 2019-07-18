---
title: DataTable-Schemadefinition
ms.date: 03/30/2017
ms.assetid: efbcdda4-f5a9-421d-8be2-4c194c74552f
ms.openlocfilehash: e8710e7d92558f525a6feaedf8d0635c5ce6e2c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034345"
---
# <a name="datatable-schema-definition"></a>DataTable-Schemadefinition
Das Schema oder die Struktur einer Tabelle wird durch Spalten und Einschränkungen dargestellt. Das Schema einer <xref:System.Data.DataTable> wird mit <xref:System.Data.DataColumn>-Objekten sowie <xref:System.Data.ForeignKeyConstraint>-Objekten und <xref:System.Data.UniqueConstraint>-Objekten definiert. Die Spalten einer Tabelle können Spalten in einer Datenquelle zugeordnet sein, berechnete Werte aus Ausdrücken enthalten, Werte automatisch erhöhen oder primäre Schlüsselwerte enthalten.  
  
 Bei Verweisen auf Namen von Spalten, Beziehungen und Einschränkungen in einer Tabelle muss die Groß- und Kleinschreibung berücksichtigt werden. Folglich können zwei oder mehr Spalten, Beziehungen oder Einschränkungen in einer Tabelle vorhanden sein, die den gleichen Namen in unterschiedlicher Schreibweise aufweisen. Sie können z. B. haben **"col1"** und **"col1"**. In diesem Fall muss die Schreibweise des Verweises auf eine der Spalten genau mit der Schreibweise des Namens der Spalte übereinstimmen. Andernfalls wird eine Ausnahme ausgelöst. Z. B. wenn die Tabelle **MyTable** enthält die Spalten **"col1"** und **"col1"**, Sie verweisen würde **"col1"** mit Namen wie  **myTable.Columns["Col1"]**, und **"col1"** als **myTable.Columns["col1"]**. Es wird versucht, eine der Spalten verweisen **myTable.Columns["COL1"]** eine Ausnahme ausgelöst.  
  
 Die Groß- und Kleinschreibung muss nicht berücksichtigt werden, wenn jeweils nur eine Spalte, Beziehung oder Einschränkung einen bestimmten Namen aufweist. Das bedeutet, wenn kein anderes Spalten-, Beziehungs- oder Einschränkungsobjekt in der Tabelle mit dem Namen dieses bestimmten Spalten-, Beziehungs- oder Einschränkungsobjekts übereinstimmt, muss die Groß- und Kleinschreibung bei dem Verweis auf das Objekt nicht berücksichtigt werden, und es wird keine Ausnahme ausgelöst. Z. B., wenn die Tabelle nur **"col1"**, Sie können darauf verweisen **meine. Spalten ["COL1"]**.  
  
> [!NOTE]
>  Die <xref:System.Data.DataTable.CaseSensitive%2A> Eigenschaft der **DataTable** wirkt sich nicht auf dieses Verhalten. Die **CaseSensitive** -Eigenschaft angewendet wird, die Daten in einer Tabelle und wirkt sich auf Sortieren, suchen, filtern, erzwingen von Einschränkungen usw., jedoch keine Verweise auf Spalten, Beziehungen und Einschränkungen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Hinzufügen von Spalten zu einer DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-columns-to-a-datatable.md)  
 Beschreibt, wie Sie definieren die Spalten einer Tabelle mit **DataColumn** Objekte.  
  
 [Erstellen von Ausdrucksspalten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-expression-columns.md)  
 Erläutert, wie die **Ausdruck** Eigenschaft einer Spalte zum Berechnen von Werten, die basierend auf den Werten aus anderen Spalten in der Zeile verwendet werden kann.  
  
 [Erstellen von AutoIncrement-Spalten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md)  
 Beschreibt, wie eine Spalte so festgelegt werden kann, dass die numerischen Werte automatisch erhöht werden, um sicherzustellen, dass die Werte in einer Spalte eindeutig sind.  
  
 [Definieren von Primärschlüsseln](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)  
 Beschreibt, wie Sie die Angabe des Primärschlüssels einer Tabelle in einer oder mehreren **DataColumn** Objekte.  
  
 [DataTable-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)  
 Beschreibt, wie Fremdschlüsseleinschränkungen und eindeutige Einschränkungen für Spalten in einer Tabelle definiert werden.  
  
## <a name="see-also"></a>Siehe auch

- [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
