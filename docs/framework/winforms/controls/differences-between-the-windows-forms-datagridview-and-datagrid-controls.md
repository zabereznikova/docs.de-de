---
title: Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms
- DataGrid control [Windows Forms], DataGridView control compared
- DataGridView control [Windows Forms], DataGrid control compared
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
ms.openlocfilehash: d0a82d5724ebe142ae080fc930665733e701e237
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="differences-between-the-windows-forms-datagridview-and-datagrid-controls"></a>Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms
Die <xref:System.Windows.Forms.DataGridView> -Steuerelement ist ein neues Steuerelement, das ersetzt die <xref:System.Windows.Forms.DataGrid> Steuerelement. Die <xref:System.Windows.Forms.DataGridView> Steuerelement bietet zahlreiche grundlegende und erweiterte Funktionen, die fehlen in der <xref:System.Windows.Forms.DataGrid> Steuerelement. Darüber hinaus die Architektur der <xref:System.Windows.Forms.DataGridView> Steuerelement kann es viel einfacher erweitern und anpassen, die als die <xref:System.Windows.Forms.DataGrid> Steuerelement.  
  
 Die folgende Tabelle beschreibt die wichtigsten Features zur Verfügung, in ein Paar der <xref:System.Windows.Forms.DataGridView> Steuerelement, das Fehlen der <xref:System.Windows.Forms.DataGrid> Steuerelement.  
  
|DataGridView-Steuerelement-Funktion|Beschreibung|  
|----------------------------------|-----------------|  
|Mehrere Spaltentypen|Die <xref:System.Windows.Forms.DataGridView> Steuerelement stellt mehr integrierte Spaltentypen als die <xref:System.Windows.Forms.DataGrid> Steuerelement. Diese Spaltentypen erfüllen die häufigsten Szenarien, aber sind einfacher zu erweitern oder ersetzen, als die Spaltentypen in der <xref:System.Windows.Forms.DataGrid> Steuerelement. Weitere Informationen finden Sie unter [Spaltentypen im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md).|  
|Mehrere Möglichkeiten zum Anzeigen von Daten|Die <xref:System.Windows.Forms.DataGrid> Steuerelement zum Anzeigen von Daten aus einer externen Datenquelle beschränkt ist. Die <xref:System.Windows.Forms.DataGridView> -Steuerelement, kann jedoch nicht gebundene Daten im Steuerelement, Daten aus einer Datenquelle gebundenen Daten oder gebunden ist, und nicht gebundene Daten zusammen gespeichert anzeigen. Sie können auch virtuellen Modus im Implementieren der <xref:System.Windows.Forms.DataGridView> Steuerelement, um benutzerdefinierte Daten zur Verwaltung von. Weitere Informationen finden Sie unter [Datenanzeigemodi im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md).|  
|Mehrere Möglichkeiten zum Anpassen der Anzeige von Daten|Die <xref:System.Windows.Forms.DataGridView> Steuerelement stellt zahlreiche Eigenschaften und Ereignisse, mit denen Sie angeben, wie Daten formatiert und angezeigt werden. Beispielsweise können Sie die Darstellung von Zellen, Zeilen und Spalten je nach den darin enthaltenen Daten ändern, oder Sie können Daten mit einem Datentyp durch entsprechende Daten eines anderen Typs ersetzen. Weitere Informationen finden Sie unter [Datenformatierung im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md).|  
|Mehrere Optionen zum Ändern der Zelle, Zeile, Spalten und Header Darstellung und Verhalten|Die <xref:System.Windows.Forms.DataGridView> -Steuerelement ermöglicht Ihnen die Arbeit mit einzelnen Komponenten auf unterschiedliche Weise. Beispielsweise können Sie Zeilen und Spalten zu verhindern, dass Durchführen eines Bildlaufs fixieren; Ausblenden von Zeilen, Spalten und Header; Ändern Sie die Möglichkeit, die Zeile, Spalten und Header angepasst werden; Ändern Sie die Möglichkeit, die Benutzer eine Auswahl treffen. und geben Sie QuickInfos und Kontextmenüs für einzelne Zellen, Zeilen und Spalten.|  
  
 Die <xref:System.Windows.Forms.DataGrid> Steuerelement wird beibehalten, für die Abwärtskompatibilität und für spezielle Zwecke. Sie sollten für fast alle Zwecke verwenden die <xref:System.Windows.Forms.DataGridView> Steuerelement. Die einzige Funktion, die in verfügbar ist die <xref:System.Windows.Forms.DataGrid> Steuerelement, das in nicht verfügbar ist die <xref:System.Windows.Forms.DataGridView> -Steuerelement ist die hierarchische Anzeige von Informationen aus zwei verknüpften Tabellen in einem einzelnen Steuerelement. Verwenden Sie zwei <xref:System.Windows.Forms.DataGridView> Steuerelemente zum Anzeigen von Informationen aus zwei Tabellen, die in einer Master/Detail-Beziehung sind.  
  
## <a name="upgrading-to-the-datagridview-control"></a>Aktualisieren von an das DataGridView-Steuerelement  
 Wenn Sie vorhandene Anwendungen verfügen, verwenden die <xref:System.Windows.Forms.DataGrid> Steuerelement in einem einfachen Szenario datengebundenen ohne Anpassungen können Sie einfach das alte Steuerelement mit dem neuen Steuerelement ersetzen. Beide Steuerelemente verwenden die standardmäßige Architektur von Windows Forms-Datenbindung, sodass der <xref:System.Windows.Forms.DataGridView> Steuerelement zeigt die gebundenen Daten keine zusätzliche Konfiguration erforderlich. Sie sollten in Betracht ziehen, profitieren von Datenbindungsfunktionen Verbesserungen, jedoch durch Ihre Daten zu binden einer <xref:System.Windows.Forms.BindingSource> -Komponente, die Sie dann eine Bindung an die <xref:System.Windows.Forms.DataGridView> Steuerelement. Weitere Informationen finden Sie unter [BindingSource-Komponente](../../../../docs/framework/winforms/controls/bindingsource-component.md).  
  
 Da die <xref:System.Windows.Forms.DataGridView> Steuerelement verfügt über eine völlig neue Architektur, gibt es keine einfache konvertierungspfad, die Sie verwenden kann, wird <xref:System.Windows.Forms.DataGrid> Anpassungen durch den <xref:System.Windows.Forms.DataGridView> Steuerelement. Viele <xref:System.Windows.Forms.DataGrid> Anpassungen sind nicht erforderlich, mit der <xref:System.Windows.Forms.DataGridView> steuern, jedoch aufgrund der integrierten Features, die in das neue Steuerelement verfügbar. Wenn Sie benutzerdefinierte Spaltentypen für erstellt haben die <xref:System.Windows.Forms.DataGrid> mit den gewünschten Steuerelementtyp der <xref:System.Windows.Forms.DataGridView> -Steuerelement, müssen Sie sie erneut mit der neuen Architektur zu implementieren. Weitere Informationen finden Sie unter [anpassen im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGrid>  
 <xref:System.Windows.Forms.BindingSource>  
 [DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [BindingSource-Komponente](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [Spaltentypen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 [Zellstile im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)  
 [Datenformatierung im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)  
 [Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)  
 [Spaltensortiermodi im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
 [Auswahlmodi im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)  
 [Anpassen des DataGridView-Steuerelements von Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
