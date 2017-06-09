---
title: "Gewusst wie: Hinzuf&#252;gen von Schaltfl&#228;chen zu einem ToolBar-Steuerelement mithilfe des Designers | Microsoft Docs"
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
  - "Beispiele [Windows Forms], Symbolleisten"
  - "ToolBar-Steuerelement [Windows Forms], Hinzufügen von Schaltflächen"
  - "ToolBar-Steuerelement [Windows Forms], Hinzufügen von Dropdownmenüs"
  - "ToolBar-Steuerelement [Windows Forms], Hinzufügen von Trennzeichen"
  - "Symbolleisten [Windows Forms], Hinzufügen von Schaltflächen"
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Hinzuf&#252;gen von Schaltfl&#228;chen zu einem ToolBar-Steuerelement mithilfe des Designers
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.ToolStrip>\-Steuerelement das <xref:System.Windows.Forms.ToolBar>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ToolBar>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Ein wesentlicher Bestandteil des <xref:System.Windows.Forms.ToolBar>\-Steuerelements sind die von Ihnen hinzugefügten Schaltflächen.  Mit diesen Schaltflächen kann ein problemloser Zugriff auf Menübefehle bereitgestellt werden. Sie können jedoch auch in einem anderen Bereich der Benutzeroberfläche der Anwendung platziert werden, um Benutzern Befehle zur Verfügung zu stellen, die in der Menüstruktur nicht verfügbar sind.  
  
 Für das folgende Verfahren wird ein Projekt vom Typ **Windows\-Anwendung** mit einem Formular benötigt, das ein <xref:System.Windows.Forms.ToolBar>\-Steuerelement enthält.  Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So fügen Sie zur Entwurfszeit Schaltflächen hinzu  
  
1.  Wählen Sie das <xref:System.Windows.Forms.ToolBar>\-Steuerelement aus.  
  
2.  Klicken Sie im **Eigenschaftenfenster** auf die <xref:System.Windows.Forms.ToolBar.Buttons%2A>\-Eigenschaft, um sie auszuwählen, und klicken Sie dann auf die Schaltfläche mit dem **Auslassungszeichen** \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), um den **ToolBarButton\-Auflistungs\-Editor** zu öffnen.  
  
3.  Verwenden Sie die Schaltflächen **Hinzufügen** und **Entfernen**, um dem <xref:System.Windows.Forms.ToolBar>\-Steuerelement Schaltflächen hinzuzufügen bzw. diese aus dem Steuerelement zu entfernen.  
  
4.  Konfigurieren Sie die Eigenschaften der einzelnen Schaltflächen im **Eigenschaftenfenster**, das im Bereich rechts neben dem Editor angezeigt wird.  In der folgenden Tabelle sind einige wichtige Eigenschaften aufgeführt.  
  
    |Property|Beschreibung|  
    |--------------|------------------|  
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|Legt das in der Dropdown\-Symbolleisten\-Schaltfläche anzuzeigende Menü fest.  Die <xref:System.Windows.Forms.ToolBarButton.Style%2A>\-Eigenschaft der Symbolleisten\-Schaltfläche muss auf <xref:System.Windows.Forms.ToolBarButtonStyle> festgelegt sein.  Diese Eigenschaft verwendet eine Instanz der <xref:System.Windows.Forms.ContextMenu>\-Klasse als Verweis.|  
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|Legt fest, ob eine umschaltbare Symbolleisten\-Schaltfläche teilweise gedrückt ist.  Die <xref:System.Windows.Forms.ToolBarButton.Style%2A>\-Eigenschaft der Symbolleisten\-Schaltfläche muss auf <xref:System.Windows.Forms.ToolBarButtonStyle> festgelegt sein.|  
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|Legt fest, ob sich eine umschaltbare Symbolleisten\-Schaltfläche derzeit im gedrückten Zustand befindet.  Die <xref:System.Windows.Forms.ToolBarButton.Style%2A>\-Eigenschaft der Symbolleisten\-Schaltfläche muss auf <xref:System.Windows.Forms.ToolBarButtonStyle> oder <xref:System.Windows.Forms.ToolBarButtonStyle>festgelegt sein.|  
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|Legt den Stil der Symbolleisten\-Schaltfläche fest.  Muss einem der Werte in der <xref:System.Windows.Forms.ToolBarButtonStyle>\-Enumeration entsprechen.|  
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|Die in der Schaltfläche angezeigte Textzeichenfolge.|  
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|Der Text, der als QuickInfo für die Schaltfläche angezeigt wird.|  
  
5.  Klicken Sie auf **OK**, um das Dialogfeld zu schließen und die angegebenen Bereiche zu erstellen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolBar>   
 [Gewusst wie: Definieren eines Symbols für eine Symbolleisten\-Schaltfläche](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)   
 [Gewusst wie: Auslösen von Menüereignissen für Symbolleisten\-Schaltflächen](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)   
 [Übersicht über das ToolBar\-Steuerelement](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)   
 [ToolBar\-Steuerelement](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)