---
title: Datenbindung und LINQ to DataSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 310bff4a-32dd-4f20-a271-6dbd82912631
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b3b097f9bca790d1f19da9d75f834c6277507d8d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="data-binding-and-linq-to-dataset"></a>Datenbindung und LINQ to DataSet
*Die Datenbindung* ist der Prozess, der eine Verbindung zwischen der Benutzeroberfläche der Anwendung und die Geschäftslogik hergestellt wird. Wenn die Bindungseinstellungen korrekt sind und bei einer Änderung des Werts ordnungsgemäße Benachrichtigungen ausgegeben werden, werden die Elemente, die an die Daten gebunden sind, automatisch aktualisiert. Beim <xref:System.Data.DataSet> handelt es sich um eine im Arbeitsspeicher residierende Darstellung von Daten, die – unabhängig von der Quelle der Daten – ein konsistentes relationales Programmiermodell bereitstellt. Die ADO.NET 2.0-<xref:System.Data.DataView> ermöglicht es Ihnen, die in einer <xref:System.Data.DataTable> gespeicherten Daten zu sortieren und zu filtern. Diese Funktionalität wird häufig in Datenbindungsanwendungen verwendet. Mit einer <xref:System.Data.DataView> können Sie die Daten in einer Tabelle mit verschiedenen Sortierreihenfolgen verfügbar machen und nach Zeilenstatus oder auf der Basis eines Filterausdrucks filtern. Weitere Informationen zu den <xref:System.Data.DataView> Objekt, finden Sie unter ["DataViews"](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]ermöglicht Entwicklern das Erstellen von komplexer und leistungsstarke Abfragen über eine <xref:System.Data.DataSet> mit [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]. Allerdings eine [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfrage gibt eine Enumeration von <xref:System.Data.DataRow> Objekte, die in einem Datenbindungsszenario nicht ohne Probleme eingesetzt wird. Um die Datenbindung zu erleichtern, können Sie erstellen eine <xref:System.Data.DataView> aus einem [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfrage. Dies <xref:System.Data.DataView> verwendet, die Filterung und Sortierung in der Abfrage angegeben, aber für die Datenbindung besser geeignet ist. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]Erweitert die Funktionalität von der <xref:System.Data.DataView> durch die Bereitstellung [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] ausdrucksbasierten Filterung und Sortierung, sodass die wesentlich komplexere und leistungsfähigere filtern und Sortieroperationen als die zeichenfolgenbasierte Filterung und Sortierung.  
  
 Beachten Sie, dass die <xref:System.Data.DataView> die Abfrage selbst ist und es sich dabei nicht um eine Ansicht handelt, die der Abfrage aufgesetzt wurde. Die <xref:System.Data.DataView> ist an ein Benutzeroberflächensteuerelement, wie z. B. ein <xref:System.Windows.Forms.DataGrid> oder eine <xref:System.Windows.Forms.DataGridView>, gebunden und stellt so ein einfaches Datenbindungsmodell bereit. Eine <xref:System.Data.DataView> kann auch aus einer <xref:System.Data.DataTable> erstellt werden, sodass eine Standardansicht dieser Tabelle zur Verfügung steht.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erstellen eines DataView-Objekts](../../../../docs/framework/data/adonet/creating-a-dataview-object-linq-to-dataset.md)  
 Enthält Informationen zum Erstellen einer <xref:System.Data.DataView>.  
  
 [Filtern mit DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)  
 Beschreibt das Filtern mit der <xref:System.Data.DataView>.  
  
 [Sortieren mit DataView](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md)  
 Beschreibt das Sortieren mit der <xref:System.Data.DataView>.  
  
 [Abfragen der DataRowView-Auflistung in einer "DataView"](../../../../docs/framework/data/adonet/querying-the-datarowview-collection-in-a-dataview.md)  
 Bietet Informationen über das Abfragen der von der <xref:System.Data.DataRowView> bereitgestellten <xref:System.Data.DataView>-Auflistung.  
  
 [DataView-Leistung](../../../../docs/framework/data/adonet/dataview-performance.md)  
 Enthält Informationen zur <xref:System.Data.DataView> und zur Leistung.  
  
 [Vorgehensweise: Binden eines DataView-Objekts an DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/data/adonet/how-to-bind-a-dataview-object-to-a-winforms-datagridview-control.md)  
 Beschreibt die Vorgehensweise beim Binden eines <xref:System.Data.DataView>-Objekts an eine <xref:System.Windows.Forms.DataGridView>.  
  
## <a name="see-also"></a>Siehe auch  
 [Programmierhandbuch](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
