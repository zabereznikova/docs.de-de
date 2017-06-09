---
title: "Gewusst wie: Definieren eines Symbols f&#252;r eine Symbolleisten-Schaltfl&#228;che mithilfe des Designers | Microsoft Docs"
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
  - "Schaltflächen [Windows Forms], Bilder"
  - "Beispiele [Windows Forms], Symbolleisten"
  - "Symbole [Windows Forms], Schaltflächen der Symbolleiste"
  - "Bilder [Windows Forms], Schaltflächen der Symbolleiste"
  - "ToolBar-Steuerelement [Windows Forms], Hinzufügen von Symbolen zu Schaltflächen"
  - "Symbolleisten [Windows Forms], Hinzufügen von Symbolen zu Schaltflächen"
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Definieren eines Symbols f&#252;r eine Symbolleisten-Schaltfl&#228;che mithilfe des Designers
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.ToolStrip>\-Steuerelement das <xref:System.Windows.Forms.ToolBar>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ToolBar>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Auf <xref:System.Windows.Forms.ToolBar>\-Schaltflächen können Symbole angezeigt werden, damit sie für die Benutzer leicht erkennbar sind.  Dazu werden der <xref:System.Windows.Forms.ImageList>\-Komponente Bilder hinzugefügt. Anschließend wird die Komponente mit dem <xref:System.Windows.Forms.ToolBar>\-Steuerelement verknüpft.  
  
 Für das folgende Verfahren wird ein Projekt vom Typ **Windows\-Anwendung** mit einem Formular benötigt, das ein <xref:System.Windows.Forms.ToolBar>\-Steuerelement und eine <xref:System.Windows.Forms.ImageList>\-Komponente enthält.  Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So legen Sie ein Symbol für eine Symbolleisten\-Schaltfläche zur Entwurfszeit fest  
  
1.  Fügen Sie der <xref:System.Windows.Forms.ImageList>\-Komponente Bilder hinzu.  Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen oder Entfernen von ImageList\-Bildern mithilfe des Designers](../../../../docs/framework/winforms/controls/how-to-add-or-remove-imagelist-images-with-the-designer.md).  
  
2.  Wählen Sie im Formular das <xref:System.Windows.Forms.ToolBar>\-Steuerelement aus.  
  
3.  Legen Sie im **Eigenschaftenfenster** die <xref:System.Windows.Forms.ToolBar.ImageList%2A>\-Eigenschaft des <xref:System.Windows.Forms.ToolBar>\-Steuerelements auf die <xref:System.Windows.Forms.ImageList>\-Komponente fest.  
  
4.  Klicken Sie auf die <xref:System.Windows.Forms.ToolBar.Buttons%2A>\-Eigenschaft des <xref:System.Windows.Forms.ToolBar>\-Steuerelements, um diese auszuwählen, und anschließend auf die Schaltfläche mit dem Auslassungszeichen \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), um den **ToolBarButton\-Auflistungs\-Editor** zu öffnen.  
  
5.  Verwenden Sie die Schaltfläche **Hinzufügen**, um dem <xref:System.Windows.Forms.ToolBar>\-Steuerelement Schaltflächen hinzuzufügen.  
  
6.  Legen Sie im **Eigenschaftenfenster**, das im Bereich rechts neben dem **ToolBarButton\-Auflistungs\-Editor** angezeigt wird, die <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A>\-Eigenschaft jeder einzelnen Symbolleisten\-Schaltfläche auf einen der Werte in der Liste fest, die entsprechend den der <xref:System.Windows.Forms.ImageList>\-Komponente hinzugefügten Bildern erstellt wurde.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolBar>   
 [Gewusst wie: Auslösen von Menüereignissen für Symbolleisten\-Schaltflächen](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)   
 [ToolBar\-Steuerelement](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)   
 [ImageList\-Komponente](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)