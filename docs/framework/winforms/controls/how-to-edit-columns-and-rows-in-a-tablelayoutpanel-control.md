---
title: "Gewusst wie: Bearbeiten von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement | Microsoft Docs"
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
  - "net.ComponentModel.StyleCollectionEditor"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Spalten [Windows Forms], Bearbeiten"
  - "Zeilen [Windows Forms], Bearbeiten"
  - "TableLayoutPanel-Steuerelement [Windows Forms], Bearbeiten"
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Bearbeiten von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement
Sie können mit dem Auflistungs\-Editor des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements, also mit dem Dialogfeld **Spalten\- und Zeilenstile**, die Zeilen und Spalten der Steuerelemente bearbeiten.  
  
> [!NOTE]
>  Wenn ein Steuerelement mehrere Zeilen oder Spalten überspannen soll, legen Sie die `RowSpan`\-Eigenschaft und die `ColumnSpan`\-Eigenschaft für das Steuerelement fest.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).  
>   
>  Wenn Sie ein Steuerelement in einer Zelle ausrichten oder strecken möchten, verwenden Sie seine <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaft.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).  
>   
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So bearbeiten Sie Zeilen und Spalten  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Klicken Sie auf das Smarttagsymbol \(![Smarttag&#45;Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements, und wählen Sie **Zeilen und Spalten bearbeiten** aus, um das Dialogfeld **Spalten\- und Zeilenstile** zu öffnen.  Sie können auch mit der rechten Maustaste auf das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement klicken und im Kontextmenü **Zeilen und Spalten bearbeiten** auswählen.  
  
3.  Um Spalten hinzuzufügen oder zu entfernen, wählen Sie in der Dropdownliste **Membertyp** die Option **Spalten** aus.  
  
4.  Um Zeilen hinzuzufügen oder zu entfernen, wählen Sie in der Dropdownliste **Membertyp** die Option **Zeilen** aus.  
  
5.  Klicken Sie auf die Schaltfläche **Hinzufügen**, um dem Ende der Liste **Member** eine Zeile oder eine Spalte hinzuzufügen.  
  
6.  Klicken Sie auf die Schaltfläche **Einfügen**, um eine Zeile oder Spalte vor dem derzeit ausgewählten Element in der Liste hinzuzufügen.  
  
7.  Wenn Sie eine Zeile oder Spalte hinzufügen, wählen Sie den **Größentyp** für die neue Zeile oder Spalte.  Weitere Informationen finden Sie unter <xref:System.Windows.Forms.SizeType>.  
  
8.  Wenn Sie eine Zeile oder Spalte entfernen möchten, klicken Sie auf die Schaltfläche **Entfernen**, um das derzeit ausgewählte Element in der Liste **Member** zu löschen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.SizeType>   
 [TableLayoutPanel\-Steuerelement](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)