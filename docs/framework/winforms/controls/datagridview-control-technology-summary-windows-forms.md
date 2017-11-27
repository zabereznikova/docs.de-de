---
title: Zusammenfassung der DataGridView-Steuerelementtechnologie (Windows Forms)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- data grids [Windows Forms], about data grids
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f172d28e5f03e1177db6ad1bd9e98f4c68267765
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="datagridview-control-technology-summary-windows-forms"></a>Zusammenfassung der DataGridView-Steuerelementtechnologie (Windows Forms)
In diesem Thema sind Informationen zum `DataGridView`-Steuerelement und den Klassen zusammengefasst, die seine Verwendung unterstützen.  
  
 Anzeigen von Daten in einem tabellarischen Format ist eine Aufgabe, die Sie wahrscheinlich häufig ausführen. Die `DataGridView` Steuerelement soll eine vollständige Lösung zum Darstellen von Daten in einem Raster.  
  
## <a name="keywords"></a>Stichwörter  
 DataGridView, BindingSource-Komponente, Tabelle, Zelle, die Datenbindung, Virtueller Modus  
  
## <a name="namespaces"></a>Namespaces  
 <xref:System.Windows.Forms?displayProperty=nameWithType>  
  
 <xref:System.Data?displayProperty=nameWithType>  
  
## <a name="related-technologies"></a>Verwandte Technologien  
 `BindingSource`  
  
## <a name="background"></a>Hintergrund  
 Benutzeroberflächen (UI)-Designer finden häufig zum Anzeigen von Tabellendaten für Benutzer erforderlich sind. Die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] bietet mehrere Möglichkeiten, um Daten in einer Tabelle oder einem Raster anzuzeigen. Die `DataGridView` Steuerelement darstellt, die neueste Entwicklung dieser Technologie für Windows Forms-Anwendungen.  
  
 Die `DataGridView` -Steuerelement kann Zeilen mit Daten aus einem Datenspeicher anzeigen. Viele Arten von Datenspeichern werden unterstützt. Der Datenspeicher einfache, nicht typisierte Daten enthalten, z. B. ein eindimensionales Array, oder sie können typisierte Daten enthalten, z. B. eine <xref:System.Data.DataSet>. Weitere Informationen finden Sie unter [Vorgehensweise: Binden von Daten an das DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
 Das `DataGridView`-Steuerelement ermöglicht die flexible Anzeige von Daten in tabellarischer Form. Das Steuerelement können Sie schreibgeschützt oder bearbeitbare Sichten klein, um sehr große Mengen von Daten angezeigt werden.  
  
 Sie erweitern die `DataGridView` Steuerelements auf unterschiedliche Weise benutzerdefiniertes Verhalten in Ihren Anwendungen zu integrieren. So können Sie beispielsweise programmgesteuert Ihre eigenen Sortieralgorithmen angeben und eigene Zelltypen erstellen. Die Darstellung des `DataGridView`-Steuerelements kann mithilfe mehrerer Eigenschaften ganz einfach angepasst werden. Viele Arten von Datenspeichern verwendet werden können, als Datenquelle, oder die `DataGridView` Steuerelement kann ohne eine Datenquelle gebunden ist, ausgeführt werden.  
  
## <a name="implementing-datagridview-classes"></a>Implementieren von DataGridView-Klassen  
 Es gibt mehrere Möglichkeiten, die Sie nutzen die `DataGridView` Erweiterungsfunktionen des Steuerelements. Sie können viele Aspekte des Steuerelements über Ereignisse und Eigenschaften anpassen, aber einige Anpassungen erforderlich ist, erstellen Sie neue Klassen aus vorhandenen abgeleitet `DataGridView` Klassen.  
  
 Die häufigsten verwendeten Basisklassen sind `DataGridViewCell` und `DataGridViewColumn`. Sie können eine eigene Zellenklasse von ableiten `DataGridViewCell` oder dessen untergeordneten Klassen. Obwohl Sie Zellentyp auf keine Spalte hinzufügen können, Sie werden in der Regel auch Ableiten einer Assistentenspaltenklasse aus `DataGridViewColumn` , die Zellen des benutzerdefinierten Zellentyps standardmäßig hostet.  
  
 Sie implementieren können die `IDataGridViewEditingCell` -Schnittstelle in die abgeleitete Zelle-Klasse, um einen Zellentyp zu erstellen, die Bearbeitungsfunktionen wurde jedoch kein host ein Steuerelement im Bearbeitungsmodus befindet. Sie können zur Erstellung eines Steuerelements, das Sie in einer Zelle im Bearbeitungsmodus hosten können, implementieren die `IDataGridViewEditingControl` Schnittstelle in einer Klasse abgeleitet <xref:System.Windows.Forms.Control>.  
  
 Weitere Informationen finden Sie unter [wie: Anpassen von Zellen und Spalten in Windows Forms-DataGridView-Steuerelements durch Erweitern von deren Verhalten und Aussehen](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) und [wie: Hosten-Steuerelementen in Windows Forms-DataGridView-Zellen](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="datagridview-classes-at-a-glance"></a>DataGridView-Klassen auf einen Blick  
 <xref:System.Windows.Forms>  
  
|Technologiebereich|Klassen/Schnittstellen/Konfigurationselemente|  
|---------------------|-------------------------------------------------|  
|Datenbindung|<xref:System.Windows.Forms.BindingSource>|  
|Darstellung von Daten|<xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DataGridViewCell>und abgeleitete Klassen<br /><br /> <xref:System.Windows.Forms.DataGridViewRow>und abgeleitete Klassen<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn>und abgeleitete Klassen<br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|<xref:System.Windows.Forms.DataGridView>Erweiterbarkeit|<xref:System.Windows.Forms.DataGridViewCell>und abgeleitete Klassen<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn>und abgeleitete Klassen<br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## <a name="whats-new"></a>Neues  
 Die <xref:System.Windows.Forms.DataGridView> Steuerelement soll eine vollständige Lösung für die Anzeige von Tabellendaten mit Windows Forms. Verwenden Sie die <xref:System.Windows.Forms.DataGridView> steuern, bevor Sie andere Lösungen, z. B. <xref:System.Windows.Forms.DataGrid>, wenn Sie eine neue Anwendung erstellen. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Die <xref:System.Windows.Forms.DataGridView> Steuerelement funktionieren schließen zusammen mit der <xref:System.Windows.Forms.BindingSource> Komponente. Diese Komponente dient als die primäre Datenquelle eines Formulars. Es dient zum Verwalten der Interaktion zwischen einem <xref:System.Windows.Forms.DataGridView> Steuerelement und seine Datenquelle, unabhängig von den Daten Datenquellentyp.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über das DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)  
 [Architektur des DataGridView-Steuerelements](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md)
