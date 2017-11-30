---
title: Anpassen des DataGridView-Steuerelements von Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7d1246a8052af19057f7aa9d6729e34203177f8e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="customizing-the-windows-forms-datagridview-control"></a>Anpassen des DataGridView-Steuerelements von Windows Forms
Die `DataGridView` Steuerelement bietet mehrere Eigenschaften, die Sie zum Anpassen der Darstellung und das grundlegende Verhalten (Aussehen und Verhalten) Zellen, Zeilen und Spalten verwenden können. Wenn Sie besondere Anforderungen verfügen, die hinausgehen, das die Funktionen des die <xref:System.Windows.Forms.DataGridViewCellStyle> -Klasse, allerdings können Sie auch Ownerdrawing für das Steuerelement implementieren oder erweitern die Funktionen durch das Erstellen von benutzerdefinierten Zellen, Spalten und Zeilen.  
  
 Um Zeilen und Zellen selbst zeichnen, können Sie verschiedene behandeln `DataGridView` zeichnen-Ereignisse. Um vorhandene Funktionen zu ändern oder neue Funktionen bereitzustellen, können Sie Ihre eigenen Typen abgeleitet werden, aus der vorhandenen erstellen `DataGridViewCell`, `DataGridViewColumn`, und `DataGridViewRow` Typen. Sie können auch neue Bearbeitungsfunktionen bereitstellen, durch das Erstellen von abgeleiteter Typen, die Anzeigen eines Steuerelements Ihrer Wahl an, wenn eine Zelle im Bearbeitungsmodus befindet.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Gewusst wie: Anpassen der Darstellung von Zellen im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
 Beschreibt das Behandeln der <xref:System.Windows.Forms.DataGridView.CellPainting> Ereignis um zeichnen Zellen manuell.  
  
 [Gewusst wie: Anpassen der Darstellung von Zeilen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
 Beschreibt das Behandeln der <xref:System.Windows.Forms.DataGridView.RowPrePaint> und <xref:System.Windows.Forms.DataGridView.RowPostPaint> Ereignisse, um Zeilen mit einem benutzerdefinierten, Farbverlauf Hintergrund zeichnen, und Inhalte, die mehrere Spalten umfasst.  
  
 [Gewusst wie: Anpassen von Zellen und Spalten im DataGridView-Steuerelement in Windows Forms durch Erweitern des Aussehens und Verhaltens](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 Enthält Informationen zum Erstellen von benutzerdefinierter Typen abgeleitet `DataGridViewCell` und `DataGridViewColumn` um Zellen hervorgehoben, wenn der Mauszeiger darauf verbleibt.  
  
 [Gewusst wie: Deaktivieren von Schaltflächen in einer Schaltflächenspalte im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/disable-buttons-in-a-button-column-in-the-datagrid.md)  
 Enthält Informationen zum Erstellen von benutzerdefinierter Typen abgeleitet <xref:System.Windows.Forms.DataGridViewButtonCell> und <xref:System.Windows.Forms.DataGridViewButtonColumn> um deaktivierte Schaltflächen in einer Schaltflächenspalte anzuzeigen.  
  
 [Gewusst wie: Hosten von Steuerelementen in DataGridView-Zellen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 Beschreibt das Implementieren der `IDataGridViewEditingControl` Schnittstelle, und erstellen Sie benutzerdefinierte Typen abgeleitet `DataGridViewCell` und `DataGridViewColumn` um anzeigen eine <xref:System.Windows.Forms.DateTimePicker> steuern, wenn eine Zelle im Bearbeitungsmodus befindet.  
  
## <a name="reference"></a>Verweis  
 <xref:System.Windows.Forms.DataGridView>  
 Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridViewCell> Klasse.  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridViewRow> Klasse.  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridViewColumn> Klasse.  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.IDataGridViewEditingControl> Schnittstelle.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 Enthält Themen, in denen erörtert wird, wie die grundlegende Darstellung des Steuerelements sowie das Anzeigeformat von Zelldaten geändert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Spaltentypen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
