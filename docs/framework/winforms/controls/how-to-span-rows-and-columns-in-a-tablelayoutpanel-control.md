---
title: 'Vorgehensweise: Überspannen von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: a215b2b4e05bab5c81d2779d4b67d5b9d57b6ba5
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039697"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a>Vorgehensweise: Überspannen von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement
Steuerelemente in <xref:System.Windows.Forms.TableLayoutPanel> einem-Steuerelement können angrenzende Zeilen und Spalten umfassen.

## <a name="to-span-columns-and-rows"></a>Zum Spannen von Spalten und Zeilen

1. Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.

2. Ziehen Sie <xref:System.Windows.Forms.Button> ein-Steuerelement aus der **Toolbox** in die <xref:System.Windows.Forms.TableLayoutPanel> linke obere Zelle des-Steuer Elements.

3. Legen Sie <xref:System.Windows.Forms.Button> die **ColumnSpan** -Eigenschaft des Steuer Elements auf **2**fest. Beachten Sie, <xref:System.Windows.Forms.Button> dass das-Steuerelement die erste und die zweite Spalte umfasst.

4. Legen Sie <xref:System.Windows.Forms.Button> die **RowSpan** -Eigenschaft des Steuer Elements auf **2**fest. Beachten Sie, <xref:System.Windows.Forms.Button> dass das-Steuerelement die erste und die zweite Zeile umfasst.

5. Legen Sie <xref:System.Windows.Forms.Button> die **ColumnSpan** -Eigenschaft des Steuer Elements auf **1**fest. Beachten Sie, <xref:System.Windows.Forms.Button> dass das-Steuerelement in die erste Spalte wechselt und die erste und zweite Zeile umfasst.

## <a name="see-also"></a>Siehe auch

- [TableLayoutPanel-Steuerelement](tablelayoutpanel-control-windows-forms.md)
