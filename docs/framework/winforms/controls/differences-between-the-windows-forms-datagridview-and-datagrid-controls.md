---
title: Unterschiede zwischen DataGridView-und DataGrid-Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms
- DataGrid control [Windows Forms], DataGridView control compared
- DataGridView control [Windows Forms], DataGrid control compared
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
ms.openlocfilehash: 3552abe55d8e2c1cb4ae372ca64c7ca21f1fed0e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745957"
---
# <a name="differences-between-the-windows-forms-datagridview-and-datagrid-controls"></a>Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms
Das <xref:System.Windows.Forms.DataGridView> Steuerelement ist ein neues Steuerelement, das das <xref:System.Windows.Forms.DataGrid> Steuerelement ersetzt. Das <xref:System.Windows.Forms.DataGridView>-Steuerelement bietet zahlreiche grundlegende und erweiterte Funktionen, die im <xref:System.Windows.Forms.DataGrid>-Steuerelement fehlen. Außerdem ist die Architektur des <xref:System.Windows.Forms.DataGridView>-Steuer Elements wesentlich einfacher zu erweitern und anzupassen als das <xref:System.Windows.Forms.DataGrid>-Steuerelement.  
  
 In der folgenden Tabelle werden einige der primären Features beschrieben, die in der <xref:System.Windows.Forms.DataGridView>-Steuerelement verfügbar sind, die im <xref:System.Windows.Forms.DataGrid>-Steuerelement fehlen.  
  
|Funktion des DataGridView-Steuer Elements|Beschreibung|  
|----------------------------------|-----------------|  
|Mehrere Spaltentypen|Das <xref:System.Windows.Forms.DataGridView>-Steuerelement bietet mehr integrierte Spaltentypen als das <xref:System.Windows.Forms.DataGrid>-Steuerelement. Diese Spaltentypen erfüllen die Anforderungen der gängigsten Szenarien, sind aber auch einfacher zu erweitern oder zu ersetzen, als die Spaltentypen im <xref:System.Windows.Forms.DataGrid>-Steuerelement. Weitere Informationen finden Sie unter [Spaltentypen im Windows Forms DataGridView-Steuer](column-types-in-the-windows-forms-datagridview-control.md)Element.|  
|Mehrere Möglichkeiten zum Anzeigen von Daten|Das <xref:System.Windows.Forms.DataGrid> Steuerelement ist auf die Anzeige von Daten aus einer externen Datenquelle beschränkt. Das <xref:System.Windows.Forms.DataGridView> Steuerelement kann jedoch ungebundene Daten im-Steuerelement, Daten aus einer gebundenen Datenquelle oder gebundene und ungebundene Daten anzeigen. Sie können den virtuellen Modus auch im <xref:System.Windows.Forms.DataGridView>-Steuerelement implementieren, um die benutzerdefinierte Datenverwaltung bereitzustellen. Weitere Informationen finden Sie unter [Datenanzeige Modi im Windows Forms DataGridView-Steuer](data-display-modes-in-the-windows-forms-datagridview-control.md)Element.|  
|Mehrere Möglichkeiten zum Anpassen der Anzeige von Daten|Das <xref:System.Windows.Forms.DataGridView>-Steuerelement stellt viele Eigenschaften und Ereignisse bereit, mit denen Sie angeben können, wie Daten formatiert und angezeigt werden. Beispielsweise können Sie die Darstellung von Zellen, Zeilen und Spalten abhängig von den darin enthaltenen Daten ändern, oder Sie können Daten eines Datentyps durch äquivalente Daten eines anderen Typs ersetzen. Weitere Informationen finden Sie unter [Datenformatierung im Windows Forms DataGridView-Steuer](data-formatting-in-the-windows-forms-datagridview-control.md)Element.|  
|Mehrere Optionen zum Ändern von Darstellung und Verhalten von Zellen, Zeilen, Spalten und Headern|Mit dem <xref:System.Windows.Forms.DataGridView>-Steuerelement können Sie in vielerlei Hinsicht mit einzelnen Raster Komponenten arbeiten. Beispielsweise können Sie Zeilen und Spalten Einfrieren, um einen Bildlauf zu verhindern. Zeilen, Spalten und Header ausblenden Ändern der Art und Weise, wie Zeilen-, Spalten-und Header Größen angepasst werden Ändern der Art und Weise, wie Benutzer eine Auswahl treffen und stellen Quick Infos und Kontextmenüs für einzelne Zellen, Zeilen und Spalten bereit.|  
  
 Das <xref:System.Windows.Forms.DataGrid> Steuerelement wird aus Gründen der Abwärtskompatibilität und für besondere Anforderungen beibehalten. Für fast alle Zwecke sollten Sie das <xref:System.Windows.Forms.DataGridView>-Steuerelement verwenden. Die einzige Funktion, die im <xref:System.Windows.Forms.DataGrid>-Steuerelement verfügbar ist, das im <xref:System.Windows.Forms.DataGridView>-Steuerelement nicht verfügbar ist, ist die hierarchische Anzeige von Informationen aus zwei verknüpften Tabellen in einem einzelnen Steuerelement. Sie müssen zwei <xref:System.Windows.Forms.DataGridView>-Steuerelemente verwenden, um Informationen aus zwei Tabellen anzuzeigen, die sich in einer Master/Detail-Beziehung befinden.  
  
## <a name="upgrading-to-the-datagridview-control"></a>Aktualisieren auf das DataGridView-Steuerelement  
 Wenn Sie über vorhandene Anwendungen verfügen, die das <xref:System.Windows.Forms.DataGrid>-Steuerelement in einem einfachen Daten gebundenen Szenario ohne Anpassungen verwenden, können Sie einfach das alte Steuerelement durch das neue Steuerelement ersetzen. Beide Steuerelemente verwenden die standardmäßige Windows Forms Daten Bindungs Architektur, sodass das <xref:System.Windows.Forms.DataGridView> Steuerelement Ihre gebundenen Daten ohne zusätzliche Konfiguration anzeigt. Sie sollten jedoch die Vorteile der Daten Bindungs Verbesserungen in Erwägung ziehen, indem Sie die Daten an eine <xref:System.Windows.Forms.BindingSource> Komponente binden, die Sie dann an das <xref:System.Windows.Forms.DataGridView> Steuerelement binden können. Weitere Informationen finden Sie unter [BindingSource-Komponente](bindingsource-component.md).  
  
 Da das <xref:System.Windows.Forms.DataGridView>-Steuerelement über eine völlig neue Architektur verfügt, gibt es keinen einfachen Konvertierungs Pfad, der es Ihnen ermöglicht, <xref:System.Windows.Forms.DataGrid> Anpassungen mit dem <xref:System.Windows.Forms.DataGridView>-Steuerelement zu verwenden. Viele <xref:System.Windows.Forms.DataGrid> Anpassungen sind aufgrund der integrierten Features, die im neuen Steuerelement verfügbar sind, mit dem <xref:System.Windows.Forms.DataGridView>-Steuerelement nicht erforderlich. Wenn Sie benutzerdefinierte Spaltentypen für das <xref:System.Windows.Forms.DataGrid> Steuerelement erstellt haben, das Sie mit dem <xref:System.Windows.Forms.DataGridView>-Steuerelement verwenden möchten, müssen Sie diese mithilfe der neuen Architektur erneut implementieren. Weitere Informationen finden Sie unter [Anpassen des Windows Forms DataGridView-Steuer](customizing-the-windows-forms-datagridview-control.md)Elements.  
  
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
