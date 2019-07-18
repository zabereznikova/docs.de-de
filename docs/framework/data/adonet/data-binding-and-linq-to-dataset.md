---
title: Datenbindung und LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 310bff4a-32dd-4f20-a271-6dbd82912631
ms.openlocfilehash: 125c9b7df0164092182506a7a71d4180b81d3ca6
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504116"
---
# <a name="data-binding-and-linq-to-dataset"></a>Datenbindung und LINQ to DataSet
*Die Datenbindung* ist der Prozess, der eine Verbindung zwischen der Benutzeroberfläche der Anwendung und der Geschäftslogik hergestellt wird. Wenn die Bindungseinstellungen korrekt sind und bei einer Änderung des Werts ordnungsgemäße Benachrichtigungen ausgegeben werden, werden die Elemente, die an die Daten gebunden sind, automatisch aktualisiert. Beim <xref:System.Data.DataSet> handelt es sich um eine im Arbeitsspeicher residierende Darstellung von Daten, die – unabhängig von der Quelle der Daten – ein konsistentes relationales Programmiermodell bereitstellt. Die ADO.NET 2.0-<xref:System.Data.DataView> ermöglicht es Ihnen, die in einer <xref:System.Data.DataTable> gespeicherten Daten zu sortieren und zu filtern. Diese Funktionalität wird häufig in Datenbindungsanwendungen verwendet. Mit einer <xref:System.Data.DataView> können Sie die Daten in einer Tabelle mit verschiedenen Sortierreihenfolgen verfügbar machen und nach Zeilenstatus oder auf der Basis eines Filterausdrucks filtern. Weitere Informationen zu den <xref:System.Data.DataView> Objekt, finden Sie unter ["DataViews"](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
 LINQ to DataSet können Entwickler komplexe und leistungsstarke Abfragen über erstellen eine <xref:System.Data.DataSet> mit [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]. Eine LINQ to DataSet-Abfrage gibt jedoch eine Enumeration von <xref:System.Data.DataRow> -Objekte, die in einem Bindungsszenario nicht einfach verwendet wird. Um die Datenbindung zu erleichtern, können Sie erstellen eine <xref:System.Data.DataView> aus einer LINQ to DataSet-Abfrage. Dies <xref:System.Data.DataView> verwendet werden, die Filterung und Sortierung in der Abfrage angegeben, aber für die Datenbindung besser geeignet ist. LINQ to DataSet erweitert die Funktionalität von der <xref:System.Data.DataView> durch die Bereitstellung [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] ausdrucksbasierten Filterung und Sortierung, um eine wesentlich komplexere und leistungsfähigere filtern und Sortieroperationen als die zeichenfolgenbasierte filtern und sortieren.  
  
 Beachten Sie, dass die <xref:System.Data.DataView> die Abfrage selbst ist und es sich dabei nicht um eine Ansicht handelt, die der Abfrage aufgesetzt wurde. Die <xref:System.Data.DataView> ist an ein Benutzeroberflächensteuerelement, wie z. B. ein <xref:System.Windows.Forms.DataGrid> oder eine <xref:System.Windows.Forms.DataGridView>, gebunden und stellt so ein einfaches Datenbindungsmodell bereit. Eine <xref:System.Data.DataView> kann auch aus einer <xref:System.Data.DataTable> erstellt werden, sodass eine Standardansicht dieser Tabelle zur Verfügung steht.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erstellen eines DataView-Objekts](../../../../docs/framework/data/adonet/creating-a-dataview-object-linq-to-dataset.md)  
 Enthält Informationen zum Erstellen einer <xref:System.Data.DataView>.  
  
 [Filtern mit DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)  
 Beschreibt das Filtern mit der <xref:System.Data.DataView>.  
  
 [Sortieren mit DataView](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md)  
 Beschreibt das Sortieren mit der <xref:System.Data.DataView>.  
  
 [Abfragen der DataRowView-Sammlung in einer DataView](../../../../docs/framework/data/adonet/querying-the-datarowview-collection-in-a-dataview.md)  
 Bietet Informationen über das Abfragen der von der <xref:System.Data.DataRowView> bereitgestellten <xref:System.Data.DataView>-Auflistung.  
  
 [DataView-Leistung](../../../../docs/framework/data/adonet/dataview-performance.md)  
 Enthält Informationen zur <xref:System.Data.DataView> und zur Leistung.  
  
 [Vorgehensweise: Binden eines DataView-Objekts an ein Windows Forms-DataGridView-Steuerelement](../../../../docs/framework/data/adonet/how-to-bind-a-dataview-object-to-a-winforms-datagridview-control.md)  
 Beschreibt die Vorgehensweise beim Binden eines <xref:System.Data.DataView>-Objekts an eine <xref:System.Windows.Forms.DataGridView>.  
  
## <a name="see-also"></a>Siehe auch

- [Programmierhandbuch](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
