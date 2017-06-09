---
title: "Gewusst wie: Erstellen einer Multipane-Benutzeroberfl&#228;che mit Windows&#160;Forms mithilfe des Designers | Microsoft Docs"
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
  - "Multipane-Benutzeroberfläche"
  - "SplitContainer-Steuerelement [Windows Forms], Verwenden des Designers"
  - "Benutzeroberfläche, Multipane"
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Erstellen einer Multipane-Benutzeroberfl&#228;che mit Windows&#160;Forms mithilfe des Designers
Mit folgenden Schritten erstellen Sie eine Benutzeroberfläche mit mehreren Bereichen, die der in Microsoft Outlook ähnelt und eine Liste **Ordner**, einen Bereich **Nachrichten** und einen Bereich **Vorschau** bietet.  Diese Anordnung wird hauptsächlich durch Andocken von Steuerelementen an das Formular erreicht.  
  
 Wenn Sie ein Steuerelement andocken, bestimmen Sie, auf welcher Seite des übergeordneten Containers ein Steuerelement angedockt wird.  Wenn Sie also die <xref:System.Windows.Forms.SplitContainer.Dock%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DockStyle> festlegen, wird der rechte Rand des Steuerelements an den rechten Rand des übergeordneten Steuerelements angedockt.  Zusätzlich wird die Größe des angedockten Randes des Steuerelements an die Größe des übergeordneten Steuerelements angepasst.  Weitere Informationen über die Funktionsweise der <xref:System.Windows.Forms.SplitContainer.Dock%2A>\-Eigenschaft finden Sie unter [Gewusst wie: Andocken von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md).  
  
 Dieses Vorgehen dient in erster Linie zum Anordnen des <xref:System.Windows.Forms.SplitContainer> und anderer Steuerelemente im Formular und nicht zum Hinzufügen von Funktionalität, mit der die Anwendung Microsoft Outlook nachahmen soll.  
  
 Zum Erstellen dieser Benutzeroberfläche müssen Sie alle Steuerelemente innerhalb eines <xref:System.Windows.Forms.SplitContainer>\-Steuerelements anordnen, das im linken Bereich ein <xref:System.Windows.Forms.TreeView>\-Steuerelement enthält.  Der rechte Bereich des <xref:System.Windows.Forms.SplitContainer>\-Steuerelements enthält ein zweites <xref:System.Windows.Forms.SplitContainer>\-Steuerelement mit einem <xref:System.Windows.Forms.ListView>\-Steuerelement über einem <xref:System.Windows.Forms.RichTextBox>\-Steuerelement.  Diese <xref:System.Windows.Forms.SplitContainer>\-Steuerelemente aktivieren unabhängige Größenanpassungen der anderen Steuerelemente im Formular.  Sie können die Techniken dieser Prozedur anpassen, um eigene Benutzeroberflächen zu entwerfen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So erstellen Sie zur Entwurfszeit eine Benutzeroberfläche im Outlook\-Design  
  
1.  Erstellen Sie ein neues Projekt vom Typ **Windows\-Anwendung**.  Ausführliche Informationen finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Ziehen Sie ein <xref:System.Windows.Forms.SplitContainer>\-Steuerelement aus der **Toolbox** in das Formular.  Legen Sie im **Eigenschaftenfenster** die <xref:System.Windows.Forms.SplitContainer.Dock%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DockStyle> fest.  
  
3.  Ziehen Sie ein <xref:System.Windows.Forms.TreeView>\-Steuerelement aus der **Toolbox** in den linken Bereich des <xref:System.Windows.Forms.SplitContainer>\-Steuerelements.  Legen Sie im **Eigenschaftenfenster** die <xref:System.Windows.Forms.SplitContainer.Dock%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DockStyle> fest. Klicken Sie dazu auf das linke Fenster im Wert\-Editor, der durch Klicken auf den Abwärtspfeil angezeigt wird.  
  
4.  Ziehen Sie ein weiteres <xref:System.Windows.Forms.SplitContainer>\-Steuerelement aus der **Toolbox**, und legen Sie es im rechten Bereich des <xref:System.Windows.Forms.SplitContainer>\-Steuerelements ab, das Sie dem Formular hinzugefügt haben.  Legen Sie im **Eigenschaftenfenster** die <xref:System.Windows.Forms.SplitContainer.Dock%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DockStyle> und die <xref:System.Windows.Forms.SplitContainer.Orientation%2A>\-Eigenschaft auf <xref:System.Windows.Forms.Orientation> fest.  
  
5.  Ziehen Sie ein <xref:System.Windows.Forms.ListView>\-Steuerelement aus der **Toolbox** in den oberen Bereich des zweiten <xref:System.Windows.Forms.SplitContainer>\-Steuerelements, das Sie dem Formular hinzugefügt haben.  Legen Sie für die <xref:System.Windows.Forms.SplitContainer.Dock%2A>\-Eigenschaft des <xref:System.Windows.Forms.ListView>\-Steuerelements <xref:System.Windows.Forms.DockStyle> fest.  
  
6.  Ziehen Sie ein <xref:System.Windows.Forms.RichTextBox>\-Steuerelement aus der **Toolbox** in den unteren Bereich des zweiten <xref:System.Windows.Forms.SplitContainer>\-Steuerelements.  Legen Sie für die <xref:System.Windows.Forms.SplitContainer.Dock%2A>\-Eigenschaft des <xref:System.Windows.Forms.RichTextBox>\-Steuerelements <xref:System.Windows.Forms.DockStyle> fest.  
  
     Wenn Sie jetzt F5 drücken, um die Anwendung auszuführen, zeigt das Formular eine aus drei Teilen bestehende Benutzeroberfläche, die der Microsoft Outlook\-Oberfläche ähnelt.  
  
    > [!NOTE]
    >  Wenn Sie den Mauszeiger auf einen der Splitter innerhalb der <xref:System.Windows.Forms.SplitContainer>\-Steuerelemente bewegen, können Sie die Größe der internen Abmessungen ändern.  
  
     Nach diesem Schritt der Anwendungsentwicklung verfügen Sie also über eine anspruchsvolle Benutzeroberfläche.  Fahren Sie fort, indem Sie die eigentliche Anwendung programmieren, z. B. durch Verbinden des <xref:System.Windows.Forms.TreeView>\-Steuerelements und der <xref:System.Windows.Forms.ListView>\-Steuerelemente mit einer Datenquelle.  Weitere Informationen zum Verbinden von Steuerelementen mit Daten finden Sie unter [Datenbindung und Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.SplitContainer>   
 [SplitContainer\-Steuerelement](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)