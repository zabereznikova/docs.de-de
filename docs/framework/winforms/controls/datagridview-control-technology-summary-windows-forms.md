---
title: Zusammenfassung der DataGridView-Steuerelementtechnologie (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- data grids [Windows Forms], about data grids
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
ms.openlocfilehash: efa567e6f8a91b40d2710b4cef0d1a56d38650c0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737831"
---
# <a name="datagridview-control-technology-summary-windows-forms"></a>Zusammenfassung der DataGridView-Steuerelementtechnologie (Windows Forms)
In diesem Thema sind Informationen zum `DataGridView`-Steuerelement und den Klassen zusammengefasst, die seine Verwendung unterstützen.  
  
 Anzeigen von Daten in einem tabellarischen Format ist eine Aufgabe, die Sie wahrscheinlich häufig ausführen. Die `DataGridView` Steuerelement fungiert als eine vollständige Lösung für die Präsentation von Daten in einem Raster.  
  
## <a name="keywords"></a>Schlüsselwörter  
 DataGridView, BindingSource, Tabelle, Zelle, die Datenbindung, des virtuellen Modus  
  
## <a name="namespaces"></a>Namespaces  
 <xref:System.Windows.Forms?displayProperty=nameWithType>  
  
 <xref:System.Data?displayProperty=nameWithType>  
  
## <a name="related-technologies"></a>Verwandte Technologien  
 `BindingSource`  
  
## <a name="background"></a>Hintergrund  
 Benutzeroberflächen (UI)-Designer finden sie häufig zum Anzeigen von Tabellendaten für Benutzer erforderlich sind. Die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] bietet mehrere Möglichkeiten, Daten in einer Tabelle oder einem Raster angezeigt. Die `DataGridView` -Steuerelement darstellt, die neueste Entwicklung dieser Technologie für Windows Forms-Anwendungen.  
  
 Die `DataGridView` -Steuerelement Zeilen von Daten aus einem Datenspeicher können angezeigt werden. Viele Arten von Datenspeichern werden unterstützt. Data Store einfache, nicht typisierte Daten enthalten, z. B. ein eindimensionales Array, oder sie können typisierte Daten enthalten, z. B. eine <xref:System.Data.DataSet>. Weitere Informationen finden Sie unter [Vorgehensweise: Binden von Daten an die Windows Forms-DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
 Das `DataGridView`-Steuerelement ermöglicht die flexible Anzeige von Daten in tabellarischer Form. Sie können das Steuerelement verwenden, schreibgeschützt oder bearbeitbare Ansichten klein, um sehr große Mengen von Daten angezeigt.  
  
 Sie können die erweitern die `DataGridView` -Steuerelement in verschiedene Möglichkeiten zum Erstellen von benutzerdefinierten Verhaltens in Ihren Anwendungen. So können Sie beispielsweise programmgesteuert Ihre eigenen Sortieralgorithmen angeben und eigene Zelltypen erstellen. Die Darstellung des `DataGridView`-Steuerelements kann mithilfe mehrerer Eigenschaften ganz einfach angepasst werden. Viele Arten von Datenspeichern verwendet werden können, als eine Datenquelle, oder die `DataGridView` -Steuerelement kann ohne eine Datenquelle gebunden ist, ausgeführt werden.  
  
## <a name="implementing-datagridview-classes"></a>Implementieren von DataGridView-Klassen  
 Es gibt mehrere Möglichkeiten, die Sie nutzen die `DataGridView` Erweiterungsfunktionen des Steuerelements. Sie können zahlreiche Aspekte des Steuerelements durch Ereignisse und Eigenschaften anpassen, aber einige Anpassungen müssen Ihnen die Erstellung neue Klassen aus vorhandenen abgeleitet `DataGridView` Klassen.  
  
 Die am häufigsten verwendeten Basisklassen sind `DataGridViewCell` und `DataGridViewColumn`. Sie können eine eigene Zellenklasse von ableiten `DataGridViewCell` oder eines ihrer untergeordneten Klassen. Obwohl Sie keinerlei Zelle jeder Spalte hinzufügen können, werden in der Regel auch leiten Sie eine zugehörige Spaltenklasse aus `DataGridViewColumn` , die Zellen des benutzerdefinierten Zellentyps standardmäßig hostet.  
  
 Sie können die implementieren die `IDataGridViewEditingCell` Schnittstelle in Ihrer Klasse abgeleitete Zelle eine Zellentyp zu erstellen, verfügt über die Bearbeitungsfunktionen, jedoch ist kein host für ein Steuerelement im Bearbeitungsmodus befindet. Sie können zum Erstellen eines Steuerelements, die in einer Zelle im Bearbeitungsmodus gehostet werden kann, implementieren die `IDataGridViewEditingControl` Schnittstelle in einer Klasse abgeleitet <xref:System.Windows.Forms.Control>.  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Anpassen von Zellen und Spalten in der Windows Forms-DataGridView-Steuerelement durch Erweitern Aussehens und Verhaltens](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) und [Vorgehensweise: Hosten von Steuerelementen in Windows Forms DataGridView-Zellen](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="datagridview-classes-at-a-glance"></a>DataGridView-Klassen auf einen Blick  
 <xref:System.Windows.Forms>  
  
|Technologiebereich|Klassen/Schnittstellen/Konfigurationselemente|  
|---------------------|-------------------------------------------------|  
|Datenbindung|<xref:System.Windows.Forms.BindingSource>|  
|Darstellung von Daten|<xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DataGridViewCell> und die abgeleiteten Klassen<br /><br /> <xref:System.Windows.Forms.DataGridViewRow> und die abgeleiteten Klassen<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> und die abgeleiteten Klassen<br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|<xref:System.Windows.Forms.DataGridView> Erweiterbarkeit|<xref:System.Windows.Forms.DataGridViewCell> und die abgeleiteten Klassen<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> und die abgeleiteten Klassen<br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## <a name="whats-new"></a>Neues  
 Die <xref:System.Windows.Forms.DataGridView> Steuerelement fungiert als eine vollständige Lösung für die Anzeige von Tabellendaten mit Windows Forms. Erwägen Sie die <xref:System.Windows.Forms.DataGridView> steuern, bevor Sie andere Lösungen, wie z. B. <xref:System.Windows.Forms.DataGrid>, wenn Sie eine neue Anwendung erstellen. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Die <xref:System.Windows.Forms.DataGridView> Steuerelement arbeiten kann schließen zusammen mit den <xref:System.Windows.Forms.BindingSource> Komponente. Diese Komponente fungiert als primäre Datenquelle eines Formulars. Sie können die Interaktion zwischen verwalten eine <xref:System.Windows.Forms.DataGridView> Steuerelement und seine Datenquelle unabhängig von den Daten-Quelltyp.  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über das DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)
- [Architektur des DataGridView-Steuerelements](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)
- [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md)
