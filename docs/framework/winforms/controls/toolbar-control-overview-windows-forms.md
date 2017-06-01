---
title: "&#220;bersicht &#252;ber das ToolBar-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
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
  - "ToolBar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ToolBar-Steuerelement [Windows Forms], Informationen über ToolBar-Steuerelemente"
  - "Symbolleisten [Windows Forms], Informationen über Symbolleisten"
ms.assetid: d426b203-0216-4dbe-b834-1641e50a9c29
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# &#220;bersicht &#252;ber das ToolBar-Steuerelement (Windows&#160;Forms)
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.ToolStrip>\-Steuerelement das <xref:System.Windows.Forms.ToolBar>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ToolBar>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Das <xref:System.Windows.Forms.ToolBar>\-Steuerelement von Windows Forms wird bei Formularen als Steuerleiste verwendet. Diese Leiste enthält eine Reihe von Dropdownmenüs und Bitmapschaltflächen, über die Befehle aktiviert werden können.  Das Klicken auf eine Symbolleisten\-Schaltfläche kann somit der Auswahl eines Menübefehls entsprechen.  Diese Schaltflächen können so konfiguriert werden, dass sie wie normale Schaltflächen, Dropdownmenüs oder Trennzeichen angezeigt werden und sich entsprechend verhalten.  In der Regel enthält eine Symbolleiste Schaltflächen und Menüs, die den Optionen in der Menüstruktur einer Anwendung entsprechen und einen schnellen Zugriff auf die am häufigsten verwendeten Funktionen und Befehle einer Anwendung ermöglichen.  
  
## Arbeiten mit dem ToolBar\-Steuerelement  
 Ein <xref:System.Windows.Forms.ToolBar>\-Steuerelement wird in der Regel am oberen Rand des übergeordneten Fensters "angedockt"; es kann jedoch auch an einem beliebigen anderen Fensterrand angedockt werden.  Eine Symbolleiste kann QuickInfos anzeigen, wenn der Benutzer mit dem Mauszeiger auf eine Schaltfläche der Symbolleiste zeigt.  QuickInfos sind kleine Popupfenster, die den Zweck der Schaltfläche oder des Menüs kurz beschreiben.  Damit QuickInfos angezeigt werden, muss für die <xref:System.Windows.Forms.ToolBar.ShowToolTips%2A>\-Eigenschaft `true` festgelegt sein.  
  
> [!NOTE]
>  Bestimmte Anwendungen verfügen über mit der Symbolleiste vergleichbare Steuerelemente, die über dem Anwendungsfenster "gleiten" und neu positioniert werden können.  Das ToolBar\-Steuerelement in Windows Forms kann diese Aktionen nicht ausführen.  
  
 Wenn für die <xref:System.Windows.Forms.ToolBar.Appearance%2A> \-Eigenschaft [Normal](frlrfSystemWindowsFormsToolBarAppearanceClassTopic) festgelegt wurde, werden die Symbolleisten\-Schaltflächen erhöht und dreidimensional angezeigt.  Sie können für die <xref:System.Windows.Forms.ToolBar.Appearance%2A>\-Eigenschaft der Symbolleiste <xref:System.Windows.Forms.ToolBarAppearance> festlegen, damit die Symbolleiste und deren Schaltflächen flach dargestellt werden.  Wenn der Mauszeiger über eine flache Schaltfläche bewegt wird, wird die Schaltfläche dreidimensional dargestellt.  Symbolleisten\-Schaltflächen können mithilfe von Trennzeichen in logische Gruppen eingeteilt werden.  Ein Trennzeichen ist eine Symbolleisten\-Schaltfläche, für deren <xref:System.Windows.Forms.ToolBarButton.Style%2A>\-Eigenschaft [Separator](frlrfSystemWindowsFormsToolBarButtonStyleClassTopic) festgelegt wurde.  Es wird als leerer Zwischenraum auf der Symbolleiste dargestellt.  Wenn die Symbolleiste flach dargestellt wird, werden die Trennlinien als Linien und nicht als Zwischenraum zwischen den Schaltflächen dargestellt.  
  
 Mithilfe des <xref:System.Windows.Forms.ToolBar>\-Steuerelements können Symbolleisten erstellt werden, indem Sie einer <xref:System.Windows.Forms.ToolBar.Buttons%2A>\-Auflistung <xref:System.Windows.Forms.Button>\-Objekte hinzufügen.  Mit dem Auflistungs\-Editor können Sie einem <xref:System.Windows.Forms.ToolBar>\-Steuerelement Schaltflächen hinzufügen. Jedem <xref:System.Windows.Forms.Button>\-Objekt sollte Text oder ein Bild zugewiesen werden, Sie können jedoch auch beides zuweisen.  Das Bild wird von einer verknüpften [ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)\-Komponente zur Verfügung gestellt.  Zur Laufzeit können Sie mit der <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Add%2A>\-Methode und der <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Remove%2A>\-Methode <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection> Schaltflächen hinzufügen bzw. Schaltflächen daraus entfernen.  Zum Programmieren der Schaltflächen von <xref:System.Windows.Forms.ToolBar> fügen Sie den <xref:System.Windows.Forms.ToolBar.ButtonClick>\-Ereignissen von <xref:System.Windows.Forms.ToolBar> Code hinzu und ermitteln mithilfe der <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A>\-Eigenschaft der <xref:System.Windows.Forms.ToolBarButtonClickEventArgs>\-Klasse die Schaltfläche, auf die geklickt wurde.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolBar>   
 [ToolBar\-Steuerelement](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)   
 [Gewusst wie: Hinzufügen von Schaltflächen zu einem ToolBar\-Steuerelement](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md)   
 [Gewusst wie: Definieren eines Symbols für eine Symbolleisten\-Schaltfläche](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)   
 [Gewusst wie: Auslösen von Menüereignissen für Symbolleisten\-Schaltflächen](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)