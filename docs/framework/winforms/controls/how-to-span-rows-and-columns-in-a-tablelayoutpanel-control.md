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
ms.openlocfilehash: fdcb4bccefe814554148aaac6e2d42e49893b7e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685229"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a>Vorgehensweise: Überspannen von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement
Steuerelemente in einem <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement kann angrenzenden Zeilen und Spalten umfassen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-span-columns-and-rows"></a>Spalten und Zeilen umfassen.  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** in die linke obere Zelle des der <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.  
  
3.  Legen Sie die <xref:System.Windows.Forms.Button> des Steuerelements **ColumnSpan** Eigenschaft **2**. Beachten Sie, dass die <xref:System.Windows.Forms.Button> Steuerelement umfasst die erste und zweite Spalte.  
  
4.  Legen Sie die <xref:System.Windows.Forms.Button> des Steuerelements **RowSpan** Eigenschaft **2**. Beachten Sie, dass die <xref:System.Windows.Forms.Button> Steuerelement umfasst die ersten und zweiten Zeile.  
  
5.  Legen Sie die <xref:System.Windows.Forms.Button> des Steuerelements **ColumnSpan** Eigenschaft **1**. Beachten Sie, dass die <xref:System.Windows.Forms.Button> Steuerelement in der ersten Spalte verschoben werden und umfasst die ersten und zweiten Zeile.  
  
## <a name="see-also"></a>Siehe auch
- [TableLayoutPanel-Steuerelement](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
