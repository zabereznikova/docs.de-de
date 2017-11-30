---
title: "Gewusst wie: Überspannen von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0380e63925dcbd27a7ee6262ddbfb2706455c2a9
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a>Gewusst wie: Überspannen von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement
Steuerelemente in einem <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement können Sie benachbarte Zeilen und Spalten umfassen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-span-columns-and-rows"></a>Spalten und Zeilen erstrecken.  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** in der linken oberen Zelle von den <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.  
  
3.  Legen Sie die <xref:System.Windows.Forms.Button> des Steuerelements **ColumnSpan** Eigenschaft **2**. Beachten Sie, dass die <xref:System.Windows.Forms.Button> Steuerelement umfasst der ersten und zweiten Spalte.  
  
4.  Legen Sie die <xref:System.Windows.Forms.Button> des Steuerelements **RowSpan** Eigenschaft **2**. Beachten Sie, dass die <xref:System.Windows.Forms.Button> Steuerelement erstreckt sich über die ersten und zweiten Zeilen.  
  
5.  Legen Sie die <xref:System.Windows.Forms.Button> des Steuerelements **ColumnSpan** Eigenschaft **1**. Beachten Sie, dass die <xref:System.Windows.Forms.Button> Steuerelement bewegt sich in der ersten Spalte und erstreckt sich über die ersten und zweiten Zeilen.  
  
## <a name="see-also"></a>Siehe auch  
 [TableLayoutPanel-Steuerelement](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
