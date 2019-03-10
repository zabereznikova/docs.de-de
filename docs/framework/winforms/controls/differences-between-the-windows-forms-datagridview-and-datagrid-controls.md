---
title: Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms
- DataGrid control [Windows Forms], DataGridView control compared
- DataGridView control [Windows Forms], DataGrid control compared
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
ms.openlocfilehash: b7d97431bfdbdafd5e87bfbfb9c5badd9ba273ea
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720487"
---
# <a name="differences-between-the-windows-forms-datagridview-and-datagrid-controls"></a>Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms
Die <xref:System.Windows.Forms.DataGridView> Steuerelement ist ein neues Steuerelement, das ersetzt die <xref:System.Windows.Forms.DataGrid> Steuerelement. Die <xref:System.Windows.Forms.DataGridView> -Steuerelement stellt zahlreiche grundlegenden und erweiterten Features, die fehlen in der <xref:System.Windows.Forms.DataGrid> Steuerelement. Darüber hinaus die Architektur der <xref:System.Windows.Forms.DataGridView> Steuerelement erleichtert das Erweitern und anpassen, die als die <xref:System.Windows.Forms.DataGrid> Steuerelement.  
  
 Die folgende Tabelle beschreibt die primären Funktionen von ein Paar der <xref:System.Windows.Forms.DataGridView> -Steuerelement, das Fehlen der <xref:System.Windows.Forms.DataGrid> Steuerelement.  
  
|DataGridView-Steuerelement-Funktion|Beschreibung|  
|----------------------------------|-----------------|  
|Mehrere Spaltentypen|Die <xref:System.Windows.Forms.DataGridView> Steuerelement bietet mehr integrierte Spaltentypen als die <xref:System.Windows.Forms.DataGrid> Steuerelement. Diese Spaltentypen erfüllen die Anforderungen der meisten häufigen Szenarien, aber es sind auch leichter zu erweitern oder ersetzen als den Spaltentypen in den <xref:System.Windows.Forms.DataGrid> Steuerelement. Weitere Informationen finden Sie unter [Spaltentypen im DataGridView-Steuerelement in Windows Forms](column-types-in-the-windows-forms-datagridview-control.md).|  
|Mehrere Möglichkeiten zum Anzeigen von Daten|Die <xref:System.Windows.Forms.DataGrid> Steuerelement zum Anzeigen von Daten aus einer externen Datenquelle beschränkt ist. Die <xref:System.Windows.Forms.DataGridView> -Steuerelement, kann jedoch nicht gebundene Daten zusammen gespeichert in der Steuerelement-, Daten aus einer gebundenen Datenquelle, oder gebunden ist, und nicht gebundene Daten anzeigen. Sie können auch die Implementieren des virtuellen Modus in der <xref:System.Windows.Forms.DataGridView> Steuerelement, um benutzerdefinierte Datenmanagement zu ermöglichen. Weitere Informationen finden Sie unter [Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md).|  
|Mehrere Möglichkeiten zum Anpassen der Anzeige von Daten|Die <xref:System.Windows.Forms.DataGridView> Steuerelement bietet zahlreiche Eigenschaften und Ereignisse, mit denen Sie angeben, wie die Daten formatiert und angezeigt werden. Beispielsweise können Sie die Darstellung von Zellen, Zeilen und Spalten, die von der darin enthaltenen Daten ändern, oder Sie können Daten mit einem Datentyp mit entsprechenden Daten eines anderen Typs ersetzen. Weitere Informationen finden Sie unter [Datenformatierung im DataGridView-Steuerelement in Windows Forms](data-formatting-in-the-windows-forms-datagridview-control.md).|  
|Mehrere Optionen zum Ändern der Zelle, Zeile, Spalte und Header Aussehen und Verhalten|Die <xref:System.Windows.Forms.DataGridView> Steuerelement können Sie einzelne Komponenten auf verschiedene Weise ausführen möchten. Beispielsweise können Sie Zeilen und Spalten, um zu verhindern, dass Sie einen Bildlauf fixieren; Ausblenden von Zeilen, Spalten und Header; Ändern Sie die Möglichkeit, die Zeile, Spalte und Header angepasst werden; Ändern Sie die Möglichkeit, die Benutzer eine Auswahl treffen. und geben Sie QuickInfos und Kontextmenüs für einzelne Zellen, Zeilen und Spalten.|  
  
 Die <xref:System.Windows.Forms.DataGrid> -Steuerelement für die Abwärtskompatibilität und für spezielle Anforderungen beibehalten. Verwenden Sie für nahezu alle Verwendungsmöglichkeiten der <xref:System.Windows.Forms.DataGridView> Steuerelement. Das einzige Feature, das in verfügbar ist. die <xref:System.Windows.Forms.DataGrid> -Steuerelement, das in nicht verfügbar ist die <xref:System.Windows.Forms.DataGridView> Steuerelement ist die hierarchische Anzeige von Informationen aus zwei verknüpften Tabellen in einem einzelnen Steuerelement. Verwenden Sie zwei <xref:System.Windows.Forms.DataGridView> Steuerelemente zum Anzeigen von Informationen aus zwei Tabellen, die in einer Master/Detail-Beziehung sind.  
  
## <a name="upgrading-to-the-datagridview-control"></a>Ein Upgrade auf das DataGridView-Steuerelement  
 Wenn Sie vorhandene Anwendungen verfügen, verwenden die <xref:System.Windows.Forms.DataGrid> Steuerelement in einem einfachen Szenario für datengebundene ohne Anpassungen, können Sie einfach das alte Steuerelement durch das neue Steuerelement ersetzen. Beide Steuerelemente verwenden die Windows Forms-Datenbindung-Architektur, sodass die <xref:System.Windows.Forms.DataGridView> Steuerelement zeigt die gebundenen Daten keine zusätzliche Konfiguration erforderlich. Möglicherweise möchten Sie in Erwägung ziehen die Datenbindung Verbesserungen, jedoch durch die Bindung Ihrer Daten in einem <xref:System.Windows.Forms.BindingSource> -Komponente, die Sie dann eine Bindung an die <xref:System.Windows.Forms.DataGridView> Steuerelement. Weitere Informationen finden Sie unter [BindingSource-Komponente](bindingsource-component.md).  
  
 Da die <xref:System.Windows.Forms.DataGridView> Steuerelement verfügt über eine völlig neue Architektur, gibt es keine einfache konvertierungspfad, mit denen Sie verwenden kann <xref:System.Windows.Forms.DataGrid> Anpassungen, mit der <xref:System.Windows.Forms.DataGridView> Steuerelement. Viele <xref:System.Windows.Forms.DataGrid> Anpassungen sind nicht erforderlich, mit der <xref:System.Windows.Forms.DataGridView> zu steuern, jedoch aufgrund der integrierten Features, die in das neue Steuerelement verfügbar. Bei der Erstellung benutzerdefinierter Spaltentypen für die <xref:System.Windows.Forms.DataGrid> -Steuerelement, das Sie mit der verwenden möchten die <xref:System.Windows.Forms.DataGridView> -Steuerelement, müssen Sie sie erneut mit der neuen Architektur zu implementieren. Weitere Informationen finden Sie unter [Anpassen des DataGridView-Steuerelements in Windows Forms](customizing-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Windows.Forms.BindingSource>
- [DataGridView-Steuerelement](datagridview-control-windows-forms.md)
- [DataGrid-Steuerelement](datagrid-control-windows-forms.md)
- [BindingSource-Komponente](bindingsource-component.md)
- [Spaltentypen im DataGridView-Steuerelement in Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
- [Zellstile im DataGridView-Steuerelement in Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md)
- [Datenformatierung im DataGridView-Steuerelement in Windows Forms](data-formatting-in-the-windows-forms-datagridview-control.md)
- [Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md)
- [Spaltensortiermodi im DataGridView-Steuerelement von Windows Forms](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [Auswahlmodi im DataGridView-Steuerelement von Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md)
- [Anpassen des DataGridView-Steuerelements von Windows Forms](customizing-the-windows-forms-datagridview-control.md)
