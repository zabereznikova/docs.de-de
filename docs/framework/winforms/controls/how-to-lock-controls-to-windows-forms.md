---
title: "Gewusst wie: Sperren von Steuerelementen f&#252;r Windows&#160;Forms | Microsoft Docs"
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
  - "Steuerelemente [Windows Forms], Sperren"
  - "Windows Forms-Steuerelemente, Sperren"
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Sperren von Steuerelementen f&#252;r Windows&#160;Forms
Während Sie die Benutzeroberfläche der Windows\-Anwendung entwerfen, können Sie die Steuerelemente sperren, sobald sie über die richtige Position verfügen. Auf diese Weise wird verhindert, dass die Elemente versehentlich verschoben, vergrößert oder verkleinert werden, wenn Sie andere Eigenschaften festlegen.  
  
 Außerdem können Sie alle Steuerelemente im Formular gleichzeitig sperren und entsperren – dies ist besonders bei Formularen mit zahlreichen Steuerelementen von Vorteil – oder einzelne Steuerelemente entsperren.  Nachdem Sie alle Steuerelemente an der gewünschten Stelle im Formular positioniert haben, sperren Sie diese, um zu vermeiden, dass sie versehentlich verschoben werden.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So sperren Sie ein Steuerelement  
  
1.  Klicken Sie im **Eigenschaftenfenster** auf die **Locked**\-Eigenschaft, und wählen Sie `true` aus.  \(Durch Doppelklicken auf den Eigenschaftennamen wird zwischen **true** und **false** gewechselt.\)  
  
     Alternativ klicken Sie mit der rechten Maustaste auf das Steuerelement und wählen **Steuerelemente sperren**.  
  
    > [!NOTE]
    >  Durch das Sperren wird verhindert, dass Steuerelemente auf eine neue Größe oder Position auf der Entwurfsoberfläche gezogen werden.  Die Größe oder Position der Steuerelemente kann jedoch weiterhin im **Eigenschaftenfenster** bzw. im Code geändert werden.  
  
### So sperren Sie alle Steuerelemente in einem Formular  
  
1.  Wählen Sie im Menü **Format** die Option **Steuerelemente sperren**.  
  
    > [!NOTE]
    >  Durch diesen Befehl wird zusätzlich die Größe des Formulars gesperrt, da es sich bei einem Formular auch um ein Steuerelement handelt.  
  
### So heben Sie die Sperrung aller gesperrten Steuerelemente in einem Formular auf  
  
1.  Wählen Sie im Menü **Format** die Option **Steuerelemente sperren**.  
  
     Die Sperrung aller zuvor im Formular gesperrten Steuerelemente wird aufgehoben.  
  
### So heben Sie die Sperrung einzelner gesperrter Steuerelemente auf  
  
1.  Klicken Sie im **Eigenschaftenfenster** auf die **Locked**\-Eigenschaft, und wählen Sie `false` aus.  \(Durch Doppelklicken auf den Eigenschaftennamen wird zwischen **true** und **false** gewechselt.\)  
  
## Siehe auch  
 [Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)   
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Windows Forms\-Steuerelemente nach Funktion](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)