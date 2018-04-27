---
title: 'Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit der Zusammenführungsfunktion für Menüs und ToolStrip-Steuerelemente'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
- MDI forms [Windows Forms], walkthroughs
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bc8214815beb0eac6fe3811ba198207a06ee1a9a
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a>Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit der Zusammenführungsfunktion für Menüs und ToolStrip-Steuerelemente
Der <xref:System.Windows.Forms?displayProperty=nameWithType>-Namespace unterstützt MDI-Anwendungen (Multiple Document Interface, Schnittstelle für mehrere Dokumente), und das <xref:System.Windows.Forms.MenuStrip>-Steuerelement unterstützt das Zusammenführen von Menüs. MDI-Formulare können auch <xref:System.Windows.Forms.ToolStrip>-Steuerelemente enthalten.  
  
 Diese exemplarische Vorgehensweise veranschaulicht, wie <xref:System.Windows.Forms.ToolStripPanel> -Steuerelemente mit einem MDI-Formular. Das Formular unterstützt auch Zusammenführen von Menüs mit untergeordneten Menüs. In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:  
  
-   Erstellen ein Windows Forms-Projekt.  
  
-   Erstellen im Hauptmenü für Ihr Formular. Der tatsächliche Name des Menüs variiert.  
  
-   Hinzufügen der <xref:System.Windows.Forms.ToolStripPanel> die Steuerung an die **Toolbox**.  
  
-   Erstellen eines untergeordneten Formulars an.  
  
-   Anordnen von <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente nach Z-Reihenfolge.  
  
 Wenn Sie fertig sind, müssen Sie ein MDI-Formular, das Zusammenführen von Menüs und verschiebbare unterstützt <xref:System.Windows.Forms.ToolStrip> Steuerelemente.  
  
 Um den Code in diesem Thema als einzelne Auflistung kopieren zu können, finden Sie unter [Vorgehensweise: Erstellen eines MDI-Formulars mit das Zusammenführen von Menüs und ToolStrip-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Ausreichende Berechtigungen zum Erstellen und Ausführen von Windows Forms-Anwendungsprojekten auf dem Computer, auf dem Visual Studio installiert ist.  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.  
  
#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
1.  Erstellen Sie ein Windows-Anwendungsprojekt namens **MDI-Formulars**.  
  
     Weitere Informationen finden Sie unter [How to: Create a Windows Application Project (Vorgehensweise: Erstellen eines neuen Windows Forms-Anwendungsprojekts)](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Wählen Sie in der Windows Forms-Designer das Formular aus.  
  
3.  Legen Sie im Fenster Eigenschaften den Wert von der <xref:System.Windows.Forms.Form.IsMdiContainer%2A> auf `true`.  
  
## <a name="creating-the-main-menu"></a>Erstellen Sie im Hauptmenü  
 Das übergeordnete MDI-Formular enthält das Hauptmenü. Im Hauptmenü befindet sich ein Element mit dem Namen **Fenster**. Mit der **Fenster** Menüelement klicken, können Sie untergeordnete Formulare erstellen. Menüelemente von untergeordneten Formularen werden im Hauptmenü zusammengeführt.  
  
#### <a name="to-create-the-main-menu"></a>So erstellen im Hauptmenü  
  
1.  Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.MenuStrip> -Steuerelement auf das Formular.  
  
2.  Hinzufügen einer <xref:System.Windows.Forms.ToolStripMenuItem> auf die <xref:System.Windows.Forms.MenuStrip> steuern, und nennen Sie sie **Fenster**.  
  
3.  Wählen Sie das <xref:System.Windows.Forms.MenuStrip>-Steuerelement.  
  
4.  Legen Sie im Fenster Eigenschaften den Wert von der <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> Eigenschaft `ToolStripMenuItem1`.  
  
5.  Fügen Sie ein Unterelement, das **Fenster** Menüelement, und geben Sie den Namen des Unterelements **neu**.  
  
6.  Klicken Sie im Fenster Eigenschaften auf **Ereignisse**.  
  
7.  Doppelklicken Sie auf die <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis.  
  
     Windows Forms-Designer wird ein Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis.  
  
8.  Fügen Sie den folgenden Code in den Ereignishandler an.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## <a name="adding-the-toolstrippanel-control-to-the-toolbox"></a>ToolStripPanel-Steuerelement hinzufügen zur Toolbox  
 Bei Verwendung von <xref:System.Windows.Forms.MenuStrip> -Steuerelemente mit einem MDI-Formular Sie benötigen die <xref:System.Windows.Forms.ToolStripPanel> Steuerelement. Müssen Sie hinzufügen, die <xref:System.Windows.Forms.ToolStripPanel> die Steuerung an die **Toolbox** der MDI-Formulars in Windows Forms-Designer zu erstellen.  
  
#### <a name="to-add-the-toolstrippanel-control-to-the-toolbox"></a>So fügen Sie das ToolStripPanel-Steuerelement zur Toolbox hinzu  
  
1.  Öffnen der **Toolbox**, und klicken Sie dann auf die **alle Windows Forms** Tab, um die verfügbaren Windows Forms-Steuerelemente zeigen.  
  
2.  Mit der rechten Maustaste das Kontextmenü öffnen, und wählen Sie **Elemente auswählen**.  
  
3.  In der **Toolboxelemente** (Dialogfeld), einen Bildlauf nach unten der **Namen** Spalte, bis Sie gefunden **ToolStripPanel**.  
  
4.  Wählen Sie das Kontrollkästchen **ToolStripPanel**, und klicken Sie dann auf **OK**.  
  
     Die <xref:System.Windows.Forms.ToolStripPanel> Steuerelement wird in der **Toolbox**.  
  
## <a name="creating-a-child-form"></a>Erstellen eines untergeordneten Formulars  
 In diesem Verfahren definieren Sie eine separate untergeordnete Formular-Klasse, die über ein eigenes <xref:System.Windows.Forms.MenuStrip> Steuerelement. Die Menüelemente für dieses Formular sind mit denen des übergeordneten Formulars zusammengeführt.  
  
#### <a name="to-define-a-child-form"></a>Um eine untergeordnete Formular zu definieren.  
  
1.  Fügen Sie ein neues Formular mit dem Namen `ChildForm` zum Projekt.  
  
     Weitere Informationen finden Sie unter [wie: Hinzufügen von Windows Forms zu einem Projekt](http://msdn.microsoft.com/library/3d7bb25f-fd90-47cf-9378-fa0d764686c1).  
  
2.  Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.MenuStrip> -Steuerelement auf das untergeordnete Formular.  
  
3.  Klicken Sie auf die <xref:System.Windows.Forms.MenuStrip> des Steuerelements Smarttag-Glyphe (![Smart Tag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), und wählen Sie dann **Elemente bearbeiten**.  
  
4.  In der **-Elementauflistungs-Editor** Dialogfeld Feld, fügen Sie einen neuen <xref:System.Windows.Forms.ToolStripMenuItem> mit dem Namen **ChildMenuItem** auf dem untergeordneten-Menü.  
  
     Weitere Informationen finden Sie unter [ToolStrip-Elementauflistungs-Editor](http://msdn.microsoft.com/library/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).  
  
## <a name="testing-the-form"></a>Testen das Formular  
  
#### <a name="to-test-your-form"></a>So testen Sie das Formular  
  
1.  Drücken Sie F5, um zu kompilieren und führen das Formular aus.  
  
2.  Klicken Sie auf die **Fenster** Menüelement, öffnen Sie das Menü, und klicken Sie dann auf **neu**.  
  
     Ein neues untergeordnetes Formular wird im MDI-Clientbereich des Formulars erstellt. Menü des untergeordneten Formulars wird mit dem Hauptmenü zusammengeführt.  
  
3.  Schließen Sie das untergeordnete Formular.  
  
     Menü des untergeordneten Formulars wird über das Hauptmenü entfernt.  
  
4.  Klicken Sie auf **neu** mehrmals.  
  
     Die untergeordneten Formulare sind automatisch aufgeführt, unter der W**Window** Menüelement, da die <xref:System.Windows.Forms.MenuStrip> des Steuerelements <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> Eigenschaft zugewiesen ist.  
  
## <a name="adding-toolstrip-support"></a>Hinzufügen von ToolStrip-Unterstützung  
 In diesem Verfahren fügen Sie vier <xref:System.Windows.Forms.ToolStrip> Steuerelemente zum übergeordneten MDI-Formulars. Jede <xref:System.Windows.Forms.ToolStrip> Steuerelement hinzugefügt wird, innerhalb einer <xref:System.Windows.Forms.ToolStripPanel> -Steuerelement, das an den Rand des Formulars angedockt ist.  
  
#### <a name="to-add-toolstrip-controls-to-the-mdi-parent-form"></a>Hinzufügen von ToolStrip-Steuerelementen zu übergeordneten MDI-Formulars  
  
1.  Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.ToolStripPanel> -Steuerelement auf das Formular.  
  
2.  Mit der <xref:System.Windows.Forms.ToolStripPanel> Steuerelement aktiviert ist, doppelklicken Sie auf die <xref:System.Windows.Forms.ToolStrip> steuern, der **Toolbox**.  
  
     Ein <xref:System.Windows.Forms.ToolStrip> Steuerelement wird erstellt, der <xref:System.Windows.Forms.ToolStripPanel> Steuerelement.  
  
3.  Wählen Sie das <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement.  
  
4.  Ändern Sie im Fenster Eigenschaften den Wert des Steuerelements <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Left>.  
  
     Die <xref:System.Windows.Forms.ToolStripPanel> wird an der linken Seite des Formulars, unterhalb des Hauptmenüs angedockt steuern. MDI-Clientbereichs wird an die <xref:System.Windows.Forms.ToolStripPanel> Steuerelement.  
  
5.  Wiederholen Sie die Schritte 1 bis 4.  
  
     Docken Sie die neuen <xref:System.Windows.Forms.ToolStripPanel> Steuerelement am oberen Rand des Formulars.  
  
     Die <xref:System.Windows.Forms.ToolStripPanel> Steuerelement angedockt ist unterhalb des Hauptmenüs, jedoch auf der rechten Seite des ersten <xref:System.Windows.Forms.ToolStripPanel> Steuerelement. Dieser Schritt veranschaulicht die Bedeutung der Z-Reihenfolge ordnungsgemäß Positionierung <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente.  
  
6.  Wiederholen Sie die Schritte 1 bis 4 für zwei weitere <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente.  
  
     Docken Sie die neuen <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente zum rechten und unteren Rand des Formulars.  
  
## <a name="arranging-toolstrippanel-controls-by-z-order"></a>ToolStripPanel-Steuerelementen nach Z-Reihenfolge anordnen  
 Die Position eines angedockten <xref:System.Windows.Forms.ToolStripPanel> Steuerelement im MDI-Formulars wird durch die Position des Steuerelements in der Z-Reihenfolge bestimmt. Sie können einfach die Z-Reihenfolge von den Steuerelementen im Fenster "Dokumentgliederung" anordnen.  
  
#### <a name="to-arrange-toolstrippanel-controls-by-z-order"></a>ToolStripPanel-Steuerelementen nach Z-Reihenfolge anordnen.  
  
1.  In der **Ansicht** Menü klicken Sie auf **Weitere Fenster**, und klicken Sie dann auf **Dokumentgliederung**.  
  
     Die Anordnung von Ihrem <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente aus der vorherigen Prozedur ist nicht dem Standard entsprechende. Dies ist, da die Z-Reihenfolge nicht richtig ist. Verwenden Sie das Fenster "Dokumentgliederung", um die Z-Reihenfolge der Steuerelemente ändern.  
  
2.  Wählen Sie in das Fenster "Dokumentgliederung" **ToolStripPanel4**.  
  
3.  Klicken Sie auf die nach-unten-Taste wiederholt, bis **ToolStripPanel4** befindet sich unten in der Liste.  
  
     Die **ToolStripPanel4** Steuerelement an das Ende des Formulars unter den anderen Steuerelementen angedockt ist.  
  
4.  Wählen Sie **ToolStripPanel2**.  
  
5.  Klicken Sie einmal auf die Schaltfläche nach unten weisenden Pfeil, im dritten Positionieren des Steuerelements in der Liste.  
  
     Die **ToolStripPanel2** Steuerelement am oberen Rand des Formulars, unterhalb des Hauptmenüs und über die anderen Steuerelemente angedockt ist.  
  
6.  Wählen Sie die verschiedenen Steuerelemente in der **Dokumentgliederung** Fenster und verschieben Sie sie an andere Positionen in der Z-Reihenfolge. Beachten Sie die Auswirkung der Z-Reihenfolge auf die Platzierung der angedockten Steuerelemente. Drücken Sie STRG-z oder **Rückgängig** auf die **bearbeiten** -Menü, um Ihre Änderungen rückgängig machen.  
  
## <a name="checkpoint"></a>Checkpoint  
  
#### <a name="to-test-your-form"></a>So testen Sie das Formular  
  
1.  Drücken Sie F5, um zu kompilieren und führen das Formular aus.  
  
2.  Klicken Sie auf den Ziehpunkt des eine <xref:System.Windows.Forms.ToolStrip> steuern und auf dem Formular an andere Positionen ziehen.  
  
     Ziehen Sie eine <xref:System.Windows.Forms.ToolStrip> Steuerelement aus einem <xref:System.Windows.Forms.ToolStripPanel> zu einem anderen Steuerelement.  
  
## <a name="next-steps"></a>Nächste Schritte  
 In dieser exemplarischen Vorgehensweise haben Sie einen übergeordneten MDI-Formulars mit <xref:System.Windows.Forms.ToolStrip> Steuerelemente und das Zusammenführen von Menüs. Sie können die <xref:System.Windows.Forms.ToolStrip> -Steuerelementfamilie zu vielen anderen Zwecken:  
  
-   Erstellen von Kontextmenüs für die Steuerelemente mit <xref:System.Windows.Forms.ContextMenuStrip>. Weitere Informationen finden Sie unter [Übersicht über die ContextMenu-Komponente](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Ein Formular erstellt mit einem automatisch gefüllten Standardmenü. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).  
  
-   Geben Sie Ihre <xref:System.Windows.Forms.ToolStrip> steuert ein professionelles Aussehen. Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen des ToolStrip-Renderers für eine Anwendung](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [Gewusst wie: Erstellen von übergeordneten MDI-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [Gewusst wie: Erstellen von untergeordneten MDI-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [Gewusst wie: Einfügen eines MenuStrip in ein MDI-Dropdownmenü](../../../../docs/framework/winforms/controls/how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)  
 [ToolStrip-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
