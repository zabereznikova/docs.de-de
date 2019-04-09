---
title: Anpassen des DataGridView-Steuerelements von Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: ab8d1f07c608aca4f14f5e73860f8c3e263a4610
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091381"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a>Anpassen des DataGridView-Steuerelements von Windows Forms
Die `DataGridView` -Steuerelement umfasst mehrere Eigenschaften, die Sie verwenden können, um die Darstellung und das grundlegende Verhalten (Aussehen und Verhalten), der die Zellen, Zeilen und Spalten anzupassen. Wenn Sie besondere Anforderungen verfügen, die über die Funktionen von hinausgehen der <xref:System.Windows.Forms.DataGridViewCellStyle> Klasse, allerdings können Sie auch Ownerdrawing für das Steuerelement implementieren oder Erweitern Sie die Funktionen, durch das Erstellen von benutzerdefinierten Zellen, Spalten und Zeilen.  
  
 Um Zeilen und Zellen selbst zeichnen, können Sie verschiedene behandeln `DataGridView` zeichnen-Ereignisse. Um vorhandene Funktionalität ändern oder neue Funktionen bereitzustellen, können Sie Ihre eigenen Typen abgeleitet, die vorhandene erstellen `DataGridViewCell`, `DataGridViewColumn`, und `DataGridViewRow` Typen. Sie können auch neue Funktionen bereitstellen, durch das Erstellen von abgeleiteten Typen, die Anzeigen eines Steuerelements Ihrer Wahl an, wenn eine Zelle im Bearbeitungsmodus befindet.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Anpassen der Darstellung von Zellen im DataGridView-Steuerelement von Windows Forms](customize-the-appearance-of-cells-in-the-datagrid.md)  
 Beschreibt, wie Sie behandelt die <xref:System.Windows.Forms.DataGridView.CellPainting> Ereignis, um zeichnen Zellen manuell.  
  
 [Vorgehensweise: Anpassen der Darstellung von Zeilen im DataGridView-Steuerelement in Windows Forms](customize-the-appearance-of-rows-in-the-datagrid.md)  
 Beschreibt, wie Sie behandelt die <xref:System.Windows.Forms.DataGridView.RowPrePaint> und <xref:System.Windows.Forms.DataGridView.RowPostPaint> Ereignisse, um Zeilen mit einem benutzerdefinierten, Farbverlauf als Hintergrund zeichnen und den Inhalt, der mehrere Spalten umfasst.  
  
 [Vorgehensweise: Anpassen von Zellen und Spalten im DataGridView-Steuerelement in Windows Forms durch Erweitern des Aussehens und Verhaltens](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 Beschreibt das Erstellen von benutzerdefinierter Typen, die von abgeleiteten `DataGridViewCell` und `DataGridViewColumn` um Zellen zu markieren, wenn der Mauszeiger darauf zeigt.  
  
 [Vorgehensweise: Deaktivieren von Schaltflächen in einer Schaltflächenspalte im DataGridView-Steuerelement von Windows Forms](disable-buttons-in-a-button-column-in-the-datagrid.md)  
 Beschreibt das Erstellen von benutzerdefinierter Typen, die von abgeleiteten <xref:System.Windows.Forms.DataGridViewButtonCell> und <xref:System.Windows.Forms.DataGridViewButtonColumn> um deaktivierte Schaltflächen in einer Schaltflächenspalte anzuzeigen.  
  
 [Vorgehensweise: Hosten von Steuerelementen in DataGridView-Zellen in Windows Forms](how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 Beschreibt das Implementieren der `IDataGridViewEditingControl` Schnittstelle, und erstellen Sie benutzerdefinierte Typen, die von abgeleiteten `DataGridViewCell` und `DataGridViewColumn` zum Anzeigen einer <xref:System.Windows.Forms.DateTimePicker> steuern, wenn eine Zelle im Bearbeitungsmodus befindet.  
  
## <a name="reference"></a>Referenz  
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
 [Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 Enthält Themen, in denen erörtert wird, wie die grundlegende Darstellung des Steuerelements sowie das Anzeigeformat von Zelldaten geändert werden.  
  
## <a name="see-also"></a>Siehe auch

- [DataGridView-Steuerelement](datagridview-control-windows-forms.md)
- [Spaltentypen im DataGridView-Steuerelement in Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
