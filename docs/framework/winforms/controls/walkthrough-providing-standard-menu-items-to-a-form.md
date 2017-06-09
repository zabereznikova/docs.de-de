---
title: "Exemplarische Vorgehensweise: Bereitstellen von Standardmen&#252;elementen f&#252;r ein Formular | Microsoft Docs"
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
  - "Menüelemente, Standard"
  - "StatusStrip-Steuerelement [Windows Forms]"
  - "Symbolleisten [Windows Forms], Exemplarische Vorgehensweisen"
  - "ToolStrip-Steuerelement [Windows Forms]"
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Exemplarische Vorgehensweise: Bereitstellen von Standardmen&#252;elementen f&#252;r ein Formular
Mit dem <xref:System.Windows.Forms.MenuStrip>\-Steuerelement können Sie ein Standardmenü für Formulare bereitstellen.  
  
 Diese exemplarische Vorgehensweise veranschaulicht, wie ein <xref:System.Windows.Forms.MenuStrip>\-Steuerelement zum Erstellen eines Standardmenüs verwendet wird.  Das Formular reagiert auch, wenn ein Benutzer ein Menüelement auswählt.  Die folgenden Aufgaben werden in dieser exemplarischen Vorgehensweise veranschaulicht:  
  
-   Erstellen eines Windows Forms\-Projekts  
  
-   Erstellen eines Standardmenüs  
  
-   Erstellen eines <xref:System.Windows.Forms.StatusStrip>\-Steuerelements  
  
-   Behandeln der Auswahl von Menüelementen  
  
 Zum Schluss verfügen Sie über ein Formular mit einem Standardmenü, in dem die Menüelementauswahlen in einem <xref:System.Windows.Forms.StatusStrip>\-Steuerelement angezeigt werden.  
  
 Informationen zum Kopieren des in diesem Thema behandelten Codes als einzelne Auflistung finden Sie unter [Gewusst wie: Bereitstellen von Standardmenüelementen für ein Formular](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Vorbereitungsmaßnahmen  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Ausreichende Berechtigungen zum Erstellen und Ausführen von Windows Forms\-Anwendungsprojekten auf dem Computer, auf dem [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] installiert ist.  
  
## Erstellen des Projekts  
 Zunächst wird das Projekt erstellt und das Formular eingerichtet.  
  
#### So erstellen Sie das Projekt  
  
1.  Erstellen Sie ein Windows\-Anwendungsprojekt mit dem Namen StandardMenuForm.  
  
     Weitere Informationen finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Wählen Sie das Formular im Windows Forms\-Designer aus.  
  
## Erstellen eines Standardmenüs  
 Der Windows Forms\-Designer ist in der Lage, ein <xref:System.Windows.Forms.MenuStrip>\-Steuerelement automatisch mit Standardmenüelementen zu füllen.  
  
#### So erstellen Sie ein Standardmenü  
  
1.  Ziehen Sie aus der **Toolbox** ein <xref:System.Windows.Forms.MenuStrip>\-Steuerelement auf das Formular.  
  
2.  Klicken Sie auf das Smarttagsymbol \(![Smarttag&#45;Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) des <xref:System.Windows.Forms.MenuStrip>\-Steuerelements, und wählen Sie **Standardelemente einfügen**.  
  
     Das <xref:System.Windows.Forms.MenuStrip>\-Steuerelement wird mit den Standardmenüelementen gefüllt.  
  
3.  Klicken Sie auf das Menüelement **File**, um die Standardmenüelemente und entsprechende Symbole anzuzeigen.  
  
## Erstellen eines StatusStrip\-Steuerelements  
 Verwenden Sie das <xref:System.Windows.Forms.StatusStrip>\-Steuerelement, um Statusinformationen für Windows Forms\-Anwendungen anzuzeigen.  Im aktuellen Beispiel werden die vom Benutzer ausgewählten Menüelemente in einem <xref:System.Windows.Forms.StatusStrip>\-Steuerelement angezeigt.  
  
#### So erstellen Sie ein StatusStrip\-Steuerelement  
  
1.  Ziehen Sie aus der **Toolbox** ein <xref:System.Windows.Forms.StatusStrip>\-Steuerelement auf das Formular.  
  
     Das <xref:System.Windows.Forms.StatusStrip>\-Steuerelement wird automatisch am unteren Rand des Formulars angedockt.  
  
2.  Klicken Sie auf die Dropdown\-Schaltfläche des <xref:System.Windows.Forms.StatusStrip>\-Steuerelements, und wählen Sie **StatusLabel** aus, um ein <xref:System.Windows.Forms.ToolStripStatusLabel>\-Steuerelement zum <xref:System.Windows.Forms.StatusStrip>\-Steuerelement hinzuzufügen.  
  
## Behandeln der Auswahl von Elementen  
 Behandeln Sie das <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>\-Ereignis, um auf das Auswählen von Menüelementen durch den Benutzer zu reagieren.  
  
#### So behandeln Sie die Auswahl von Elementen  
  
1.  Klicken Sie auf das Menüelement **Datei**, das Sie im Abschnitt "Erstellen eines Standardmenüs" erstellt haben.  
  
2.  Klicken Sie im **Eigenschaftenfenster** auf **Ereignisse**.  
  
3.  Doppelklicken Sie auf das <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>\-Ereignis.  
  
     Der Windows Forms\-Designer generiert einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>\-Ereignis.  
  
4.  Fügen Sie folgenden Code in den Ereignishandler ein.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5.  Fügen Sie die Definition der `UpdateStatus`\-Dienstprogrammmethode in das Formular ein.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## Checkpoint  
  
#### So testen Sie das Formular  
  
1.  Drücken Sie F5, um das Formular zu kompilieren und auszuführen.  
  
2.  Klicken Sie auf das Menüelement **File**, um das Menü zu öffnen.  
  
3.  Klicken Sie im Menü **File** auf eines der Elemente, um es auszuwählen.  
  
     Das ausgewählte Element wird vom <xref:System.Windows.Forms.StatusStrip>\-Steuerelement angezeigt.  
  
## Nächste Schritte  
 In dieser exemplarischen Vorgehensweise haben Sie ein Formular mit einem Standardmenü erstellt.  Sie können die <xref:System.Windows.Forms.ToolStrip>\-Steuerelementfamilie für viele andere Zwecke verwenden:  
  
-   Erstellen von Kontextmenüs für die Steuerelemente mithilfe von <xref:System.Windows.Forms.ContextMenuStrip>.  Weitere Informationen finden Sie unter [Übersicht über die ContextMenu\-Komponente](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Erstellen eines MDI \(Multiple Document Interface\-\)Formulars mit andockbaren <xref:System.Windows.Forms.ToolStrip>\-Steuerelementen.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen eines MDI\-Formulars mit der Zusammenführungsfunktion für Menüs und ToolStrip\-Steuerelemente](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
-   Gestalten von <xref:System.Windows.Forms.ToolStrip>\-Steuerelementen mit professionellem Aussehen.  Weitere Informationen finden Sie unter [Gewusst wie: Festlegen des ToolStrip\-Renderers für eine Anwendung](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 [MenuStrip\-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)