---
title: 'Vorgehensweise: Bearbeiten von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement'
description: Erfahren Sie, wie Sie das Dialogfeld Spalten-und Zeilen Stile verwenden, um die Zeilen und Spalten der Windows Forms Steuerelemente zu bearbeiten.
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
ms.openlocfilehash: cfd2ca4be5d5a2658a9a129d911f1dba9670ccfd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619350"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a>Vorgehensweise: Bearbeiten von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement

Sie können den Auflistungs-Editor des- <xref:System.Windows.Forms.TableLayoutPanel> Steuer Elements, das als **Spalten-und Zeilen Stile** bezeichnet wird, verwenden, um die Zeilen und Spalten der Steuerelemente zu bearbeiten.

> [!NOTE]
> Wenn ein Steuerelement mehrere Zeilen oder Spalten umfassen soll, legen Sie die `RowSpan` -Eigenschaft und die-Eigenschaft `ColumnSpan` für das-Steuerelement fest. Weitere Informationen finden Sie unter [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).
>
> Wenn Sie ein Steuerelement in einer Zelle ausrichten oder ein Steuerelement innerhalb einer Zelle Strecken möchten, verwenden Sie die-Eigenschaft des-Steuer Elements <xref:System.Windows.Forms.Control.Anchor%2A> . Weitere Informationen finden Sie unter [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).

## <a name="to-edit-rows-and-columns"></a>So bearbeiten Sie Zeilen und Spalten

1. Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.

2. Klicken Sie auf das <xref:System.Windows.Forms.TableLayoutPanel> Designer-Aktions Symbol des Steuer Elements ( ![ kleiner schwarzer Pfeil ](./media/designer-actions-glyph.gif) ), und wählen Sie **Zeilen und Spalten bearbeiten** aus, um das Dialogfeld **Spalten-und Zeilen Stile** zu öffnen. Sie können auch mit der rechten Maustaste auf das Steuerelement klicken und im Kontext <xref:System.Windows.Forms.TableLayoutPanel> Menü **Zeilen und Spalten bearbeiten** auswählen.

3. Wählen Sie zum Hinzufügen oder Entfernen von Spalten im Dropdown-Listenfeld **Elementtyp den Typ** **Spalten** aus.

4. Wählen Sie zum Hinzufügen oder Entfernen von Zeilen im Dropdown-Listenfeld **Elementtyp den Typ** **Zeilen** aus.

5. Klicken Sie auf die Schaltfläche **Hinzufügen** , um am **Ende der Elementliste eine** Zeile oder Spalte hinzuzufügen.

6. Klicken Sie auf die Schaltfläche **Einfügen** , um eine Zeile oder Spalte vor dem aktuell ausgewählten Element in der Liste hinzuzufügen.

7. Wenn Sie eine Zeile oder Spalte hinzufügen, wählen Sie den **Größentyp** für die neue Zeile oder Spalte aus. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.SizeType>.

8. Um eine Zeile oder Spalte zu entfernen, klicken Sie auf die Schaltfläche **Entfernen** , um das aktuell ausgewählte Element in der **Mitglieder** Liste zu löschen.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.SizeType>
- [TableLayoutPanel-Steuerelement](tablelayoutpanel-control-windows-forms.md)
