---
title: "Anpassen des DataGridView-Steuerelements von Windows Forms | Microsoft Docs"
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
  - "Datenblätter, Anpassung"
  - "DataGridView-Steuerelement [Windows Forms], Anpassung"
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Anpassen des DataGridView-Steuerelements von Windows Forms
Das `DataGridView`\-Steuerelement umfasst mehrere Eigenschaften, mit denen Darstellung und grundlegendes Verhalten der zugehörigen Zellen, Zeilen und Spalten angepasst werden können.  Bei besonderen Anforderungen, die über die Möglichkeiten der <xref:System.Windows.Forms.DataGridViewCellStyle>\-Klasse hinausgehen, können Sie auch Ownerdrawing für das Steuerelement implementieren oder dessen Funktionen erweitern, indem Sie benutzerdefinierte Zellen, Spalten und Zeilen erstellen.  
  
 Um selbst Zellen und Zeilen zu zeichnen, können Sie verschiedene `DataGridView`\-Zeichnungsereignisse verwenden.  Um vorhandene Funktionen zu ändern oder neue Funktionen bereitzustellen, können Sie eigene, von den vorhandenen Typen `DataGridViewCell`, `DataGridViewColumn` und `DataGridViewRow` abgeleitete Typen erstellen.  Sie können auch neue Bearbeitungsfunktionen bereitstellen, indem Sie abgeleitete Typen erstellen, durch die ein von Ihnen festgelegtes Steuerelement eingeblendet wird, wenn sich eine Zelle im Bearbeitungsmodus befindet.  
  
## In diesem Abschnitt  
 [Gewusst wie: Anpassen der Darstellung von Zellen im DataGridView\-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
 Beschreibt, wie das <xref:System.Windows.Forms.DataGridView.CellPainting>\-Ereignis behandelt wird, um Zellen manuell zu zeichnen.  
  
 [Gewusst wie: Anpassen der Darstellung von Zeilen im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
 Beschreibt, wie das <xref:System.Windows.Forms.DataGridView.RowPrePaint>\-Ereignis und das <xref:System.Windows.Forms.DataGridView.RowPostPaint>\-Ereignis behandelt werden, um Zeilen mit einem benutzerdefinierten Hintergrund mit Farbverlauf und Inhalt zu zeichnen, der mehrere Spalten umfasst.  
  
 [Gewusst wie: Anpassen von Zellen und Spalten im DataGridView\-Steuerelement in Windows Forms durch Erweitern des Aussehens und Verhaltens](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 Beschreibt, wie von `DataGridViewCell` und `DataGridViewColumn` abgeleitete, benutzerdefinierte Typen erstellt werden, um Zellen hervorzuheben, sobald der Mauszeiger darauf bewegt wird.  
  
 [Gewusst wie: Deaktivieren von Schaltflächen in einer Schaltflächenspalte im DataGridView\-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/disable-buttons-in-a-button-column-in-the-datagrid.md)  
 Beschreibt, wie von <xref:System.Windows.Forms.DataGridViewButtonCell> und <xref:System.Windows.Forms.DataGridViewButtonColumn> abgeleitete, benutzerdefinierte Typen erstellt werden, um deaktivierte Schaltflächen in einer Schaltflächenspalte anzuzeigen.  
  
 [Gewusst wie: Hosten von Steuerelementen in DataGridView\-Zellen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 Beschreibt die Implementierung der `IDataGridViewEditingControl`\-Schnittstelle und die Erstellung benutzerdefinierter Typen, die von `DataGridViewCell` und von `DataGridViewColumn` abgeleitet sind, um ein <xref:System.Windows.Forms.DateTimePicker>\-Steuerelement anzuzeigen, wenn sich eine Zelle im Bearbeitungsmodus befindet.  
  
## Referenz  
 <xref:System.Windows.Forms.DataGridView>  
 Enthält die Referenzdokumentation zum <xref:System.Windows.Forms.DataGridView>\-Steuerelement.  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 Enthält die Referenzdokumentation zur <xref:System.Windows.Forms.DataGridViewCell>\-Klasse.  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 Enthält die Referenzdokumentation zur <xref:System.Windows.Forms.DataGridViewRow>\-Klasse.  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 Enthält die Referenzdokumentation zur <xref:System.Windows.Forms.DataGridViewColumn>\-Klasse.  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 Enthält die Referenzdokumentation zur <xref:System.Windows.Forms.IDataGridViewEditingControl>\-Schnittstelle.  
  
## Verwandte Abschnitte  
 [Grundlegende Formatierungen und Formate im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 Enthält Themen, in denen beschrieben wird, wie die grundlegende Darstellung des Steuerelements und das Anzeigeformat von Zelldaten geändert wird.  
  
## Siehe auch  
 [DataGridView\-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [Spaltentypen im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)