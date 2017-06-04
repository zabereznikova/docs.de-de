---
title: "Datenbindung und LINQ to DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 310bff4a-32dd-4f20-a271-6dbd82912631
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Datenbindung und LINQ to DataSet
*Datenbindung* ist der Prozess, bei der die Benutzeroberfläche mit der Anwendung und der Geschäftslogik verbunden wird.  Wenn die Bindungseinstellungen korrekt sind und bei einer Änderung des Werts ordnungsgemäße Benachrichtigungen ausgegeben werden, werden die Elemente, die an die Daten gebunden sind, automatisch aktualisiert.  Beim <xref:System.Data.DataSet> handelt es sich um eine im Arbeitsspeicher residierende Darstellung von Daten, die – unabhängig von der Quelle der Daten – ein konsistentes relationales Programmiermodell bereitstellt.  Die ADO.NET 2.0\-<xref:System.Data.DataView> ermöglicht es Ihnen, die in einer <xref:System.Data.DataTable> gespeicherten Daten zu sortieren und zu filtern.  Diese Funktionalität wird häufig in Datenbindungsanwendungen verwendet.  Mit einer <xref:System.Data.DataView> können Sie die Daten in einer Tabelle mit verschiedenen Sortierreihenfolgen verfügbar machen und nach Zeilenstatus oder auf der Basis eines Filterausdrucks filtern.  Weitere Informationen zum <xref:System.Data.DataView>\-Objekt finden Sie unter [DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] ermöglicht es Entwicklern, mit [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] komplexe und leistungsstarke Abfragen für ein <xref:System.Data.DataSet> zu erstellen.  Eine [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfrage gibt jedoch eine Enumeration von <xref:System.Data.DataRow>\-Objekten zurück, die in einem Bindungsszenario nicht einfach verwendet werden kann. Um die Bindung zu vereinfachen, können Sie <xref:System.Data.DataView> aus einer [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfrage erstellen.  Diese <xref:System.Data.DataView> verwendet die in der Abfrage festgelegte Filterung und Sortierung, ist jedoch für die Datenbindung besser geeignet.  [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] erweitert die Funktionalität der <xref:System.Data.DataView> durch Bereitstellen der ausdrucksbasierten Filterung und Sortierung von [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]. Dadurch können im Vergleich zu zeichenfolgenbasierten noch komplexere Filterungen und Sortierungen durchgeführt werden.  
  
 Beachten Sie, dass die <xref:System.Data.DataView> die Abfrage selbst ist und es sich dabei nicht um eine Ansicht handelt, die der Abfrage aufgesetzt wurde.  Die <xref:System.Data.DataView> ist an ein Benutzeroberflächensteuerelement, wie z. B. ein <xref:System.Windows.Forms.DataGrid> oder eine <xref:System.Windows.Forms.DataGridView>, gebunden und stellt so ein einfaches Datenbindungsmodell bereit.  Eine <xref:System.Data.DataView> kann auch aus einer <xref:System.Data.DataTable> erstellt werden, sodass eine Standardansicht dieser Tabelle zur Verfügung steht.  
  
## In diesem Abschnitt  
 [Erstellen eines 'DataView'\-Objekts](../../../../docs/framework/data/adonet/creating-a-dataview-object-linq-to-dataset.md)  
 Enthält Informationen zum Erstellen einer <xref:System.Data.DataView>.  
  
 [Filtern mit 'DataView'](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)  
 Beschreibt das Filtern mit der <xref:System.Data.DataView>.  
  
 [Sortieren mit 'DataView'](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md)  
 Beschreibt das Sortieren mit der <xref:System.Data.DataView>.  
  
 [Abfragen der DataRowView\-Auflistung in einer DataView](../../../../docs/framework/data/adonet/querying-the-datarowview-collection-in-a-dataview.md)  
 Bietet Informationen über das Abfragen der von der <xref:System.Data.DataView> bereitgestellten <xref:System.Data.DataRowView>\-Auflistung.  
  
 ['DataView'\-Arbeitsgeschwindigkeit](../../../../docs/framework/data/adonet/dataview-performance.md)  
 Enthält Informationen zur <xref:System.Data.DataView> und zur Leistung.  
  
 [Vorgehensweise: Binden eines 'DataView'\-Objekts an ein Windows Forms\-'DataGridView'\-Steuerelement](../../../../docs/framework/data/adonet/how-to-bind-a-dataview-object-to-a-winforms-datagridview-control.md)  
 Beschreibt die Vorgehensweise beim Binden eines <xref:System.Data.DataView>\-Objekts an eine <xref:System.Windows.Forms.DataGridView>.  
  
## Siehe auch  
 [Informationen zum Programmieren](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)