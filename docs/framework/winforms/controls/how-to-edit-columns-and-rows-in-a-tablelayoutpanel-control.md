---
title: 'Gewusst wie: Bearbeiten von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bf54a02a409bead598a4e98315d5709e55677f3b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a>Gewusst wie: Bearbeiten von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement
Können Sie den auflistungs-Editor von der <xref:System.Windows.Forms.TableLayoutPanel> als Steuerelement der **Spalten- und Zeilenstile** (Dialogfeld), um die Zeilen und Spalten der Steuerelemente zu bearbeiten.  
  
> [!NOTE]
>  Wenn Sie ein Steuerelement, die mehrere Zeilen oder Spalten umfassen soll, legen die `RowSpan` und `ColumnSpan` Eigenschaften des Steuerelements. Weitere Informationen finden Sie unter [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).  
>   
>  Wenn Sie ein Steuerelement in einer Zelle ausrichten möchten, oder ein Steuerelement in einer Zelle gestreckt werden soll, verwenden Sie des Steuerelements <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft. Weitere Informationen finden Sie unter [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).  
>   
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-edit-rows-and-columns"></a>So bearbeiten Sie die Zeilen und Spalten  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Klicken Sie auf die <xref:System.Windows.Forms.TableLayoutPanel> des Steuerelements Smarttag-Glyphe (![Smart Tag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), und wählen Sie **Zeilen und Spalten bearbeiten** So öffnen die  **Spalten- und Zeilenstile** (Dialogfeld). Sie können auch mit der rechten Maustaste auf die <xref:System.Windows.Forms.TableLayoutPanel> steuern, und wählen Sie **Zeilen und Spalten bearbeiten** aus dem Kontextmenü.  
  
3.  Wählen Sie zum Hinzufügen oder Entfernen von Spalten, **Spalten** aus der **Elementtyp** Dropdown Listenfeld aus.  
  
4.  Wählen Sie zum Hinzufügen oder Entfernen von Zeilen, **Zeilen** aus der **Elementtyp** Dropdown Listenfeld aus.  
  
5.  Klicken Sie auf die **hinzufügen** Schaltfläche zum Hinzufügen einer Zeile oder Spalte an das Ende der **Member** Liste.  
  
6.  Klicken Sie auf die **einfügen** Schaltfläche, um eine Zeile oder Spalte vor dem aktuell ausgewählten Element in der Liste hinzuzufügen.  
  
7.  Wenn Sie eine Zeile oder Spalte hinzufügen, wählen Sie die **Größentyps** für die neue Zeile oder Spalte. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.SizeType>.  
  
8.  Um eine Zeile oder Spalte zu entfernen, klicken Sie auf die **entfernen** Schaltfläche, um das aktuell ausgewählte Element im Löschen der **Member** Liste.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.SizeType>  
 [TableLayoutPanel-Steuerelement](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
