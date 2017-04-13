---
title: "Gewusst wie: Erstellen einer Oberfl&#228;che im Stil von Windows Explorer in einem Windows Form | Microsoft Docs"
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
  - "Formulare, Windows Explorer-Typ"
  - "SplitContainer-Steuerelement [Windows Forms], Explorer-style-Schnittstelle"
  - "Windows Explorer, Erstellen mit Windows Forms"
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Erstellen einer Oberfl&#228;che im Stil von Windows Explorer in einem Windows Form
Wegen der Vertrautheit der Benutzer mit der Benutzeroberfläche von Windows Explorer bietet diese sich als Vorbild für die Benutzeroberfläche von Anwendungen an.  
  
 Windows Explorer besteht im Grunde aus einem <xref:System.Windows.Forms.TreeView>\-Steuerelement und einem <xref:System.Windows.Forms.ListView>\-Steuerelement, die sich jeweils in getrennten Bereichen befinden.  Die Größe der Bereiche kann durch einen Splitter geändert werden.  Diese Anordnung von Steuerelementen eignet sich sehr gut für das Anzeigen und Durchsuchen von Informationen.  
  
 Im Folgenden werden die Schritte erläutert, die zum Anordnen von Steuerelementen in einer Windows Explorer\-ähnlichen Weise erforderlich sind.  Dabei wird nicht auf die Funktionalität von Windows Explorer zum Anzeigen und Durchsuchen von Dateien eingegangen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So erstellen Sie ein Windows Form im Stil von Windows Explorer  
  
1.  Erstellen Sie ein neues Projekt vom Typ **Windows\-Anwendung**.  Ausführliche Informationen finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Aus der **Toolbox**:  
  
    1.  Ziehen Sie ein <xref:System.Windows.Forms.SplitContainer>\-Steuerelement auf das Formular.  
  
    2.  Ziehen Sie ein <xref:System.Windows.Forms.TreeView>\-Steuerelement in **SplitterPanel1** \(in den als **Panel1** markierten Bereich des <xref:System.Windows.Forms.SplitContainer>\-Steuerelements\).  
  
    3.  Ziehen Sie ein <xref:System.Windows.Forms.ListView>\-Steuerelement in **SplitterPanel2** \(in den als **Panel2** markierten Bereich des <xref:System.Windows.Forms.SplitContainer>\-Steuerelements\).  
  
3.  Klicken Sie bei gedrückter STRG\-TASTE nacheinander auf alle drei Steuerelemente, um diese auszuwählen.  Klicken Sie zum Auswählen des <xref:System.Windows.Forms.SplitContainer>\-Steuerelements auf die Splitterleiste und nicht auf die Bereiche.  
  
    > [!NOTE]
    >  Verwenden Sie nicht den Befehl **Alle auswählen** aus dem Menü **Bearbeiten**.  Wenn Sie diesen Befehl verwenden, wird im nächsten Schritt im **Eigenschaftenfenster** nicht die erforderliche Eigenschaft angezeigt.  
  
4.  Legen Sie im **Eigenschaftenfenster** die <xref:System.Windows.Forms.SplitContainer.Dock%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DockStyle> fest.  
  
5.  Drücken Sie F5, um die Anwendung auszuführen.  
  
     Das Formular zeigt eine zweiteilige Benutzeroberfläche an, die der Benutzeroberfläche von Windows Explorer ähnelt.  
  
    > [!NOTE]
    >  Durch Ziehen des Splitters können Sie die Größe der Bereiche ändern.  
  
## Siehe auch  
 <xref:System.Windows.Forms.SplitContainer>   
 [Gewusst wie: Erstellen einer Multipane\-Benutzeroberfläche mit Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)   
 [Gewusst wie: Definieren des Verhaltens bei Größen\- und Positionsänderungen in einem geteilten Fenster](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)   
 [Gewusst wie: Horizontales Teilen eines Fensters](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)   
 [SplitContainer\-Steuerelement](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)