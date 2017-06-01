---
title: "Gewusst wie: Ausrichten und Strecken eines Steuerelements in einem TableLayoutPanel-Steuerelement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Steuerelemente [Windows Forms], Ausrichten"
  - "Steuerelemente [Windows Forms], Dehnen"
  - "TableLayoutPanel-Steuerelement [Windows Forms], Dehnen von Steuerelementen"
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Ausrichten und Strecken eines Steuerelements in einem TableLayoutPanel-Steuerelement
Sie können Steuerelemente in einem <xref:System.Windows.Forms.TableLayoutPanel> mit der <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaft und der <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft ausrichten und strecken.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So richten Sie ein Steuerelement aus und strecken es  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Ziehen Sie ein <xref:System.Windows.Forms.Button>\-Steuerelement aus der **Toolbox** in die linke obere Zelle des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements.  Das <xref:System.Windows.Forms.Button>\-Steuerelement wird in der Zelle zentriert.  
  
3.  Legen Sie den Wert der <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements auf `Left,Right` fest.  Das <xref:System.Windows.Forms.Button>\-Steuerelement wird an die Breite der Zelle angepasst.  
  
4.  Legen Sie den Wert der <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements auf `Top,Bottom` fest.  Das <xref:System.Windows.Forms.Button>\-Steuerelement wird an die Höhe der Zelle angepasst.  
  
5.  Legen Sie den Wert der <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements auf <xref:System.Windows.Forms.DockStyle> fest.  Das <xref:System.Windows.Forms.Button>\-Steuerelement wird auf die Größe der Zelle erweitert.  
  
6.  Legen Sie den Wert der <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements auf <xref:System.Windows.Forms.DockStyle> fest.  Das <xref:System.Windows.Forms.Button>\-Steuerelement nimmt wieder seine ursprüngliche Größe an und wird in die obere linke Ecke der Zelle verschoben.  Im **Windows Forms\-Designer** ist die <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaft auf `Top,Left` festgelegt.  
  
7.  Legen Sie den Wert der <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements auf `Bottom,Right` fest.  Das <xref:System.Windows.Forms.Button>\-Steuerelement wird in die rechte untere Ecke der Zelle verschoben.  
  
8.  Legen Sie den Wert der <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements auf <xref:System.Windows.Forms.AnchorStyles> fest.  Das <xref:System.Windows.Forms.Button>\-Steuerelement wird ins Zentrum der Zelle verschoben.  
  
## Siehe auch  
 [TableLayoutPanel\-Steuerelement](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)