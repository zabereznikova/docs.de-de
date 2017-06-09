---
title: "Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Datenblätter"
  - "DataGrid-Steuerelement [Windows Forms], DataGridView-Steuerelement im Vergleich mit"
  - "DataGridView-Steuerelement [Windows Forms], DataGrid-Steuerelement im Vergleich mit"
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms
Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement ist ein neues Steuerelement und ersetzt das <xref:System.Windows.Forms.DataGrid>\-Steuerelement.  Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement stellt zahlreiche grundlegende und erweiterte Features bereit, die das <xref:System.Windows.Forms.DataGrid>\-Steuerelement nicht aufweist.  Außerdem ermöglicht die Architektur des <xref:System.Windows.Forms.DataGridView>\-Steuerelements eine bedeutend einfachere Erweiterung und Anpassung als das <xref:System.Windows.Forms.DataGrid>\-Steuerelement.  
  
 In der folgenden Tabelle werden einige wichtige Features beschrieben, die im <xref:System.Windows.Forms.DataGridView>\-Steuerelement verfügbar sind, aber im <xref:System.Windows.Forms.DataGrid>\-Steuerelement fehlen.  
  
|DataGridView\-Steuerelementfeature|Beschreibung|  
|----------------------------------------|------------------|  
|Verschiedene Spaltentypen|Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement stellt mehr integrierte Spaltentypen bereit als das <xref:System.Windows.Forms.DataGrid>\-Steuerelement.  Diese Spaltentypen erfüllen die Anforderungen der meisten üblichen Szenarien, können aber auch einfacher erweitert oder ersetzt werden als die Spaltentypen im <xref:System.Windows.Forms.DataGrid>\-Steuerelement.  Weitere Informationen finden Sie unter [Spaltentypen im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md).|  
|Verschiedene Möglichkeiten der Datenanzeige|Das <xref:System.Windows.Forms.DataGrid>\-Steuerelement kann lediglich Daten aus einer externen Datenquelle anzeigen.  Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement kann hingegen ungebundene Daten anzeigen, die im Steuerelement gespeichert sind, Daten aus einer gebundenen Datenquelle sowie gebundene und ungebundene Daten gleichzeitig.  Darüber hinaus können Sie im <xref:System.Windows.Forms.DataGridView>\-Steuerelement auch den virtuellen Modus implementieren, um benutzerdefinierte Datenverwaltung bereitzustellen.  Weitere Informationen finden Sie unter [Datenanzeigemodi im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md).|  
|Verschiedene Möglichkeiten zur Anpassung der Datenanzeige|Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement stellt zahlreiche Eigenschaften und Ereignisse bereit, mit denen Sie festlegen können, wie Daten formatiert und angezeigt werden.  Beispielsweise können Sie die Darstellung von Zellen, Zeilen und Spalten an die darin enthaltenen Daten anpassen oder Daten eines bestimmten Datentyps durch entsprechende Daten eines anderen Datentyps ersetzen.  Weitere Informationen finden Sie unter [Datenformatierung im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md).|  
|Verschiedene Optionen zum Ändern des Aussehens und Verhaltens von Zellen, Zeilen, Spalten und Headern|Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement ermöglicht es Ihnen, auf verschiedene Weise mit den einzelnen Rasterkomponenten zu arbeiten.  Beispielsweise haben Sie folgende Möglichkeiten: Zeilen und Spalten fixieren, damit sie auch während eines Bildlaufs angezeigt werden; Zeilen, Spalten und Header ausblenden; die Art ändern, wie Zeilen, Spalten und Header angepasst werden; die Art ändern, wie Benutzer eine Auswahl treffen; QuickInfos und Kontextmenüs für einzelne Zellen, Zeilen und Spalten bereitstellen.|  
  
 Das <xref:System.Windows.Forms.DataGrid>\-Steuerelement wird aus Gründen der Abwärtskompatibilität und für besondere Anforderungen beibehalten.  Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement ist für nahezu alle Verwendungsmöglichkeiten zu empfehlen.  Das einzige Feature, das im <xref:System.Windows.Forms.DataGrid>\-Steuerelement, nicht aber im <xref:System.Windows.Forms.DataGridView>\-Steuerelement verfügbar ist, ist die hierarchische Anzeige von Informationen aus zwei zusammengehörigen Tabellen in einem einzelnen Steuerelement.  Sie müssen zwei <xref:System.Windows.Forms.DataGridView>\-Steuerelemente verwenden, um Informationen aus zwei Tabellen anzuzeigen, die in einer Master\-\/Detailbeziehung zueinander stehen.  
  
## Aktualisieren auf das DataGridView\-Steuerelement  
 Wenn Sie über Anwendungen verfügen, die das <xref:System.Windows.Forms.DataGrid>\-Steuerelement in einem einfachen datengebundenen Szenario ohne Anpassungen verwenden, können Sie das alte Steuerelement einfach durch das neue Steuerelement ersetzen.  Beide Steuerelemente verwenden die standardmäßige Datenbindungsarchitektur von Windows Forms, sodass das <xref:System.Windows.Forms.DataGridView>\-Steuerelement die gebundenen Daten anzeigt, ohne dass hierfür eine zusätzliche Konfiguration erforderlich ist.  Möglicherweise möchten Sie aber von den Datenbindungsverbesserungen profitieren, indem Sie die Daten an eine <xref:System.Windows.Forms.BindingSource>\-Komponente binden, die Sie anschließend an das <xref:System.Windows.Forms.DataGridView>\-Steuerelement binden können.  Weitere Informationen finden Sie unter [BindingSource\-Komponente](../../../../docs/framework/winforms/controls/bindingsource-component.md).  
  
 Da das <xref:System.Windows.Forms.DataGridView>\-Steuerelement eine komplett neue Architektur aufweist, gibt es keine direkte Konvertierungslösung, die es Ihnen ermöglicht, <xref:System.Windows.Forms.DataGrid>\-Anpassungen mit dem <xref:System.Windows.Forms.DataGridView>\-Steuerelement zu verwenden.  Viele <xref:System.Windows.Forms.DataGrid>\-Anpassungen sind jedoch aufgrund der integrierten Features des neuen Steuerelements mit dem <xref:System.Windows.Forms.DataGridView>\-Steuerelement überflüssig.  Wenn Sie benutzerdefinierte Spaltentypen für das <xref:System.Windows.Forms.DataGrid>\-Steuerelement erstellt haben, die Sie mit dem <xref:System.Windows.Forms.DataGridView>\-Steuerelement verwenden möchten, müssen Sie sie mithilfe der neuen Architektur erneut implementieren.  Weitere Informationen finden Sie unter [Anpassen des DataGridView\-Steuerelements von Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGrid>   
 <xref:System.Windows.Forms.BindingSource>   
 [DataGridView\-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [DataGrid\-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [BindingSource\-Komponente](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [Spaltentypen im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)   
 [Zellstile im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Datenanzeigemodi im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)   
 [Datenformatierung im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)   
 [Größenänderungsoptionen im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)   
 [Spaltenssortiermodi im DataGridView\-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)   
 [Auswahlmodi im DataGridView\-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)   
 [Anpassen des DataGridView\-Steuerelements von Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)