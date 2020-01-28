---
title: Zusammenfassung der DataGridView-Steuerelementtechnologie
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- data grids [Windows Forms], about data grids
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
ms.openlocfilehash: 18eebd067df9768e14cc81258184551d00dd1402
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742480"
---
# <a name="datagridview-control-technology-summary-windows-forms"></a>Zusammenfassung der DataGridView-Steuerelementtechnologie (Windows Forms)
In diesem Thema sind Informationen zum `DataGridView`-Steuerelement und den Klassen zusammengefasst, die seine Verwendung unterstützen.  
  
 Das Anzeigen von Daten in einem tabellarischen Format ist eine Aufgabe, die Sie wahrscheinlich häufig ausführen. Das `DataGridView`-Steuerelement ist als umfassende Lösung für die Darstellung von Daten in einem Raster konzipiert.  
  
## <a name="keywords"></a>Stichwörter  
 DataGridView, BindingSource, Table, Cell, Data Binding, Virtual Mode  
  
## <a name="namespaces"></a>-Namespaces  
 <xref:System.Windows.Forms?displayProperty=nameWithType>  
  
 <xref:System.Data?displayProperty=nameWithType>  
  
## <a name="related-technologies"></a>Verwandte Technologien  
 `BindingSource`  
  
## <a name="background"></a>-Hintergrund  
 Benutzeroberflächen-Designer finden häufig die Notwendigkeit, Tabellendaten für Benutzer anzuzeigen. Der .NET Framework bietet mehrere Möglichkeiten zum Anzeigen von Daten in einer Tabelle oder einem Raster. Das `DataGridView`-Steuerelement stellt die neueste Entwicklung dieser Technologie für Windows Forms Anwendungen dar.  
  
 Das `DataGridView`-Steuerelement kann Daten Zeilen aus einem Datenspeicher anzeigen. Viele Arten von Daten speichern werden unterstützt. Der Datenspeicher kann einfache, nicht typisierte Daten enthalten, z. b. ein eindimensionales Array, oder es kann typisierte Daten enthalten, z. b. eine <xref:System.Data.DataSet>. Weitere Informationen finden Sie unter Gewusst [wie: Binden von Daten an das Windows Forms DataGridView-Steuer](how-to-bind-data-to-the-windows-forms-datagridview-control.md)Element.  
  
 Das `DataGridView`-Steuerelement ermöglicht die flexible Anzeige von Daten in tabellarischer Form. Sie können das-Steuerelement verwenden, um schreibgeschützte oder bearbeitbare Sichten von kleinen bis sehr großen Datensätzen anzuzeigen.  
  
 Sie können das `DataGridView`-Steuerelement auf verschiedene Weise erweitern, um benutzerdefiniertes Verhalten in Ihren Anwendungen zu erstellen. So können Sie beispielsweise programmgesteuert Ihre eigenen Sortieralgorithmen angeben und eigene Zelltypen erstellen. Die Darstellung des `DataGridView`-Steuerelements kann mithilfe mehrerer Eigenschaften ganz einfach angepasst werden. Viele Typen von Daten speichern können als Datenquelle verwendet werden, oder das `DataGridView`-Steuerelement kann ohne eine Datenquelle ausgeführt werden.  
  
## <a name="implementing-datagridview-classes"></a>Implementieren von DataGridView-Klassen  
 Es gibt mehrere Möglichkeiten, die Erweiterbarkeits Features des `DataGridView`-Steuer Elements zu nutzen. Sie können zahlreiche Aspekte des Steuer Elements durch Ereignisse und Eigenschaften anpassen, aber einige Anpassungen erfordern, dass Sie neue Klassen erstellen, die von vorhandenen `DataGridView` Klassen abgeleitet werden.  
  
 Die am häufigsten verwendeten Basisklassen sind `DataGridViewCell` und `DataGridViewColumn`. Sie können eine eigene Zellklasse von `DataGridViewCell` oder einer ihrer untergeordneten Klassen ableiten. Obwohl Sie beliebige Zellen Typen zu beliebigen Spalten hinzufügen können, leiten Sie in der Regel auch eine Begleit Spalten Klasse von `DataGridViewColumn` ab, die standardmäßig Zellen Ihres benutzerdefinierten Zelltyps hostet.  
  
 Sie können die `IDataGridViewEditingCell`-Schnittstelle in der abgeleiteten Cell-Klasse implementieren, um einen Zellentyp zu erstellen, der über Bearbeitungsfunktionen verfügt, aber kein-Steuerelement im Bearbeitungsmodus hostet. Um ein Steuerelement zu erstellen, das Sie in einer Zelle im Bearbeitungsmodus hosten können, können Sie die `IDataGridViewEditingControl`-Schnittstelle in einer Klasse implementieren, die von <xref:System.Windows.Forms.Control>abgeleitet ist.  
  
 Weitere Informationen finden Sie unter Gewusst [wie: Anpassen von Zellen und Spalten im Windows Forms DataGridView-Steuerelement durch Erweiterung ihres Verhaltens und ihrer](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) Darstellung und Gewusst [wie: Hosten von Steuerelementen in Windows Forms DataGridView-Zellen](how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="datagridview-classes-at-a-glance"></a>DataGridView-Klassen auf einen Blick  
 <xref:System.Windows.Forms>  
  
|Technologiebereich|Klassen/Schnittstellen/Konfigurationselemente|  
|---------------------|-------------------------------------------------|  
|Datenbindung|<xref:System.Windows.Forms.BindingSource>|  
|Datenpräsentation|<xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DataGridViewCell> und abgeleitete Klassen<br /><br /> <xref:System.Windows.Forms.DataGridViewRow> und abgeleitete Klassen<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> und abgeleitete Klassen<br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|<xref:System.Windows.Forms.DataGridView> Erweiterbarkeit|<xref:System.Windows.Forms.DataGridViewCell> und abgeleitete Klassen<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> und abgeleitete Klassen<br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## <a name="whats-new"></a>Neuerungen  
 Das <xref:System.Windows.Forms.DataGridView>-Steuerelement ist als umfassende Lösung zum Anzeigen von Tabellendaten mit Windows Forms konzipiert. Sie sollten die Verwendung des <xref:System.Windows.Forms.DataGridView>-Steuer Elements vor anderen Lösungen wie <xref:System.Windows.Forms.DataGrid>in Erwägung gezogen haben, wenn Sie eine neue Anwendung erstellen. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Das <xref:System.Windows.Forms.DataGridView> Steuerelement kann in enger Verbindung mit der <xref:System.Windows.Forms.BindingSource> Komponente verwendet werden. Diese Komponente ist als primäre Datenquelle eines Formulars konzipiert. Die Interaktion zwischen einem <xref:System.Windows.Forms.DataGridView>-Steuerelement und seiner Datenquelle kann unabhängig vom Daten Quellentyp verwaltet werden.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über das DataGridView-Steuerelement](datagridview-control-overview-windows-forms.md)
- [Architektur des DataGridView-Steuerelements](datagridview-control-architecture-windows-forms.md)
- [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md)
