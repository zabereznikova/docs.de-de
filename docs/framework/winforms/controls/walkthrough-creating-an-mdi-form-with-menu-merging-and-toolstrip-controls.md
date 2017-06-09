---
title: "Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit der Zusammenf&#252;hrungsfunktion f&#252;r Men&#252;s und ToolStrip-Steuerelemente | Microsoft Docs"
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
  - "MDI-Formulare"
  - "MDI-Formulare, Erstellen"
  - "MDI-Formulare, Exemplarische Vorgehensweisen"
  - "MDI, Erstellen von Formularen"
  - "Multiple Document Interface-Formulare"
  - "Symbolleisten [Windows Forms]"
  - "ToolStrip-Steuerelement [Windows Forms]"
  - "ToolStripPanel-Steuerelement [Windows Forms]"
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit der Zusammenf&#252;hrungsfunktion f&#252;r Men&#252;s und ToolStrip-Steuerelemente
Der <xref:System.Windows.Forms?displayProperty=fullName>\-Namespace unterstützt MDI \(Multiple Document Interface\-\)Anwendungen, und das <xref:System.Windows.Forms.MenuStrip>\-Steuerelement unterstützt das Zusammenführen von Menüs.  MDI\-Formulare können auch <xref:System.Windows.Forms.ToolStrip>\-Steuerelemente darstellen.  
  
 Diese exemplarische Vorgehensweise veranschaulicht, wie <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelemente in Verbindung mit einem MDI\-Formular verwendet werden.  Das Formular unterstützt auch das Zusammenführen von Menüs mit untergeordneten Menüs.  Die folgenden Aufgaben werden in dieser exemplarischen Vorgehensweise veranschaulicht:  
  
-   Erstellen eines Windows Forms\-Projekts  
  
-   Erstellen des Hauptmenüs für das Formular.  Der tatsächliche Menüname kann unterschiedlich sein.  
  
-   Hinzufügen des <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelements zur **Toolbox**  
  
-   Erstellen eines untergeordneten Formulars  
  
-   Anordnen von <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelementen nach der Z\-Reihenfolge  
  
 Zum Schluss verfügen Sie über ein MDI\-Formular, das das Zusammenführen von Menüs sowie verschiebbare <xref:System.Windows.Forms.ToolStrip>\-Steuerelemente unterstützt.  
  
 Informationen zum Kopieren des in diesem Thema behandelten Codes als einzelne Auflistung finden Sie unter [Gewusst wie: Erstellen eines MDI\-Formulars mit der Zusammenführungsfunktion für Menüs und ToolStrip\-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Vorbereitungsmaßnahmen  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Ausreichende Berechtigungen zum Erstellen und Ausführen von Windows Forms\-Anwendungsprojekten auf dem Computer, auf dem [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] installiert ist.  
  
## Erstellen des Projekts  
 Zunächst wird das Projekt erstellt und das Formular eingerichtet.  
  
#### So erstellen Sie das Projekt  
  
1.  Erstellen Sie ein Windows\-Anwendungsprojekt mit dem Namen MdiForm.  
  
     Weitere Informationen finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Wählen Sie das Formular im Windows Forms\-Designer aus.  
  
3.  Legen Sie im Eigenschaftenfenster für <xref:System.Windows.Forms.Form.IsMdiContainer%2A> den Wert `true` fest.  
  
## Erstellen des Hauptmenüs  
 Das Hauptmenü ist im übergeordneten MDI\-Formular enthalten.  Im Hauptmenü befindet sich ein Menüelement mit dem Namen **Window**.  Mit dem Menüelement **Window** können Sie untergeordnete Formulare erstellen.  Menüelemente von untergeordneten Formularen werden im Hauptmenü zusammengeführt.  
  
#### So erstellen Sie das Hauptmenü  
  
1.  Ziehen Sie aus der **Toolbox** ein <xref:System.Windows.Forms.MenuStrip>\-Steuerelement auf das Formular.  
  
2.  Fügen Sie <xref:System.Windows.Forms.ToolStripMenuItem> zum <xref:System.Windows.Forms.MenuStrip>\-Steuerelement hinzu, und nennen Sie es Window.  
  
3.  Wählen Sie das <xref:System.Windows.Forms.MenuStrip>\-Steuerelement aus.  
  
4.  Legen Sie im Eigenschaftenfenster für die <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>\-Eigenschaft den Wert `ToolStripMenuItem1` fest.  
  
5.  Fügen Sie dem Menüelement **Window** ein Unterelement hinzu, und nennen Sie es anschließend New.  
  
6.  Klicken Sie im Eigenschaftenfenster auf **Ereignisse**.  
  
7.  Doppelklicken Sie auf das <xref:System.Windows.Forms.ToolStripItem.Click>\-Ereignis.  
  
     Der Windows Forms\-Designer generiert einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click>\-Ereignis.  
  
8.  Fügen Sie folgenden Code in den Ereignishandler ein.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## Hinzufügen des ToolStripPanel\-Steuerelements zur Toolbox  
 Wenn Sie <xref:System.Windows.Forms.MenuStrip>\-Steuerelemente mit einem MDI\-Formular verwenden, müssen Sie über das <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelement verfügen.  Sie müssen das <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelement zur **Toolbox** hinzufügen, damit das MDI\-Formular im Windows Forms\-Designer erstellt werden kann.  
  
#### So fügen Sie der Toolbox das ToolStripPanel\-Steuerelement hinzu  
  
1.  Öffnen Sie die **Toolbox**, und klicken Sie auf die Registerkarte **Alle Windows Forms**, um die verfügbaren Windows Forms\-Steuerelemente anzuzeigen.  
  
2.  Klicken Sie mit der rechten Maustaste auf die Registerkarte, um das Kontextmenü zu öffnen, und wählen Sie **Elemente auswählen** aus.  
  
3.  Führen Sie im Dialogfeld **Toolboxelemente auswählen** in der Spalte **Name** einen Bildlauf zum Element **ToolStripPanel** aus.  
  
4.  Aktivieren Sie das Kontrollkästchen neben **ToolStripPanel**, und klicken Sie auf **OK**.  
  
     Das <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelement wird in der **Toolbox** angezeigt.  
  
## Erstellen eines untergeordneten Formulars  
 In diesem Verfahren definieren Sie eine separate Klasse für untergeordnete Formulare, die über ein eigenes <xref:System.Windows.Forms.MenuStrip>\-Steuerelement verfügt.  Die Menüelemente für dieses Formular werden mit denen des übergeordneten Formulars zusammengeführt.  
  
#### So definieren Sie ein untergeordnetes Formular  
  
1.  Fügen Sie dem Projekt ein neues Formular mit dem Namen `ChildForm` hinzu.  
  
     Weitere Informationen finden Sie unter [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/de-de/3d7bb25f-fd90-47cf-9378-fa0d764686c1).  
  
2.  Ziehen Sie aus der **Toolbox** ein <xref:System.Windows.Forms.MenuStrip>\-Steuerelement auf das untergeordnete Formular.  
  
3.  Klicken Sie auf das Smarttagsymbol \(![Smarttag&#45;Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) des <xref:System.Windows.Forms.MenuStrip>\-Steuerelements, und wählen Sie anschließend **Elemente bearbeiten** aus.  
  
4.  Fügen Sie im Dialogfeld **Elementauflistungs\-Editor** dem untergeordneten Menü ein neues <xref:System.Windows.Forms.ToolStripMenuItem> mit dem Namen ChildMenuItem hinzu.  
  
     Weitere Informationen finden Sie unter [ToolStrip Items Collection Editor](http://msdn.microsoft.com/de-de/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).  
  
## Testen des Formulars  
  
#### So testen Sie das Formular  
  
1.  Drücken Sie F5, um das Formular zu kompilieren und auszuführen.  
  
2.  Klicken Sie zum Öffnen des Menüs auf das Menüelement **Fenster** und dann auf **Neu**.  
  
     Ein neues untergeordnetes Formular wird im MDI\-Clientbereich des Formulars erstellt.  Das Menü des untergeordneten Formulars wird mit dem Hauptmenü zusammengeführt.  
  
3.  Schließen Sie das untergeordnete Formular.  
  
     Das Menü des untergeordneten Formulars wird aus dem Hauptmenü entfernt.  
  
4.  Klicken Sie mehrmals auf **New**.  
  
     Die untergeordneten Formulare werden automatisch unter dem Menüelement **Window** aufgelistet, da die zum <xref:System.Windows.Forms.MenuStrip>\-Steuerelement gehörige <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>\-Eigenschaft zugewiesen ist.  
  
## Hinzufügen von ToolStrip\-Unterstützung  
 In diesem Verfahren fügen Sie dem übergeordneten MDI\-Formular vier <xref:System.Windows.Forms.ToolStrip>\-Steuerelemente hinzu.  Jedes <xref:System.Windows.Forms.ToolStrip>\-Steuerelement wird innerhalb eines <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelements hinzugefügt, das am Rand des Formulars angedockt ist.  
  
#### So fügen Sie dem übergeordneten MDI\-Formular ToolStrip\-Steuerelemente hinzu  
  
1.  Ziehen Sie aus der **Toolbox** ein <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelement auf das Formular.  
  
2.  Doppelklicken Sie, während das <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelement ausgewählt ist, auf das <xref:System.Windows.Forms.ToolStrip>\-Steuerelement in der **Toolbox**.  
  
     Ein <xref:System.Windows.Forms.ToolStrip>\-Steuerelement wird im <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelement erstellt.  
  
3.  Wählen Sie das <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelement aus.  
  
4.  Ändern Sie im Eigenschaftenfenster den Wert der <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft des Steuerelements in <xref:System.Windows.Forms.DockStyle>.  
  
     Das <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelement wird an der linken Seite des Formulars unter dem Hauptmenü angedockt.  Die Größe des MDI\-Clientbereichs wird an das <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelement angepasst.  
  
5.  Wiederholen Sie die Schritte 1 bis 4.  
  
     Docken Sie das neue <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelement an den oberen Rand des Formulars an.  
  
     Das <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelement wird unterhalb des Hauptmenüs, jedoch rechts neben dem ersten <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelement angedockt.  Dieser Vorgang veranschaulicht die Bedeutung der Z\-Reihenfolge für die ordnungsgemäße Positionierung von <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelementen.  
  
6.  Wiederholen Sie die Schritte 1 bis 4 für zwei weitere <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelemente.  
  
     Docken Sie die neuen <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelemente am rechten und unteren Rand des Formulars an.  
  
## Anordnen von ToolStripPanel\-Steuerelementen nach der Z\-Reihenfolge  
 Die Position eines angedockten <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelements auf dem MDI\-Formular wird durch die Position des Steuerelements in der Z\-Reihenfolge bestimmt.  Sie können die Z\-Reihenfolge der Steuerelemente problemlos im Fenster Dokumentgliederung anordnen.  
  
#### So ordnen Sie ToolStripPanel\-Steuerelemente nach der Z\-Reihenfolge an  
  
1.  Klicken Sie im Menü **Ansicht** auf **Weitere Fenster**, und klicken Sie anschließend auf **Dokumentgliederung**.  
  
     Die <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelemente im vorherigen Verfahren sind nicht standardmäßig angeordnet.  Das liegt daran, dass die Z\-Reihenfolge nicht korrekt ist.  Verwenden Sie das Fenster Dokumentgliederung, um die Z\-Reihenfolge der Steuerelemente zu ändern.  
  
2.  Wählen Sie im Fenster Dokumentgliederung den Eintrag **ToolStripPanel4** aus.  
  
3.  Klicken Sie wiederholt auf die Schaltfläche mit dem nach unten weisenden Pfeil, bis sich **ToolStripPanel4** ganz unten in Liste befindet.  
  
     Das **ToolStripPanel4**\-Steuerelement wird am unteren Rand des Formulars unter den anderen Steuerelementen angedockt.  
  
4.  Wählen **Sie ToolStripPanel2** aus.  
  
5.  Klicken Sie einmal auf die Schaltfläche mit dem nach unten weisenden Pfeil, um das Steuerelement in der Liste an dritter Stelle zu positionieren.  
  
     Das **ToolStripPanel2**\-Steuerelement wird am oberen Rand des Formulars unter dem Hauptmenü und über den anderen Steuerelementen angedockt.  
  
6.  Wählen Sie im Fenster **Dokumentgliederung** verschiedene Steuerelemente aus, und verschieben Sie sie an unterschiedliche Positionen in der Z\-Reihenfolge.  Beachten Sie die Auswirkung der Z\-Reihenfolge auf die Platzierung von angedockten Steuerelementen.  Verwenden Sie STRG\+Z oder im Menü **Bearbeiten** die Option **Rückgängig**, um die Änderungen rückgängig zu machen.  
  
## Checkpoint  
  
#### So testen Sie das Formular  
  
1.  Drücken Sie F5, um das Formular zu kompilieren und auszuführen.  
  
2.  Klicken Sie auf den Ziehpunkt eines <xref:System.Windows.Forms.ToolStrip>\-Steuerelements, und ziehen Sie das Steuerelement an andere Positionen auf dem Formular.  
  
     Sie können ein <xref:System.Windows.Forms.ToolStrip>\-Steuerelement von einem <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelement zu einem anderen ziehen.  
  
## Nächste Schritte  
 In dieser exemplarischen Vorgehensweise haben Sie ein übergeordnetes MDI\-Formular mit <xref:System.Windows.Forms.ToolStrip>\-Steuerelementen und Menüzusammenführung erstellt.  Sie können die <xref:System.Windows.Forms.ToolStrip>\-Steuerelementfamilie für viele andere Zwecke verwenden:  
  
-   Erstellen von Kontextmenüs für die Steuerelemente mithilfe von <xref:System.Windows.Forms.ContextMenuStrip>.  Weitere Informationen finden Sie unter [Übersicht über die ContextMenu\-Komponente](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Erstellen von Formularen mit einem automatisch gefüllten Standardmenü.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).  
  
-   Gestalten von <xref:System.Windows.Forms.ToolStrip>\-Steuerelementen mit professionellem Aussehen.  Weitere Informationen finden Sie unter [Gewusst wie: Festlegen des ToolStrip\-Renderers für eine Anwendung](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 [Gewusst wie: Erstellen von übergeordneten MDI\-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [Gewusst wie: Erstellen von untergeordneten MDI\-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [Gewusst wie: Einfügen eines MenuStrip in ein MDI\-Dropdownmenü](../../../../docs/framework/winforms/controls/how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)   
 [ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)