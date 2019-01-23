---
title: 'Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit Zusammenführen von Menüs und ToolStrip-Steuerelemente'
ms.date: 03/30/2017
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
ms.openlocfilehash: 5924d37d946a8279297ecf479b621f6f827dd5a3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536238"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a>Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit Zusammenführen von Menüs und ToolStrip-Steuerelemente
Der <xref:System.Windows.Forms?displayProperty=nameWithType>-Namespace unterstützt MDI-Anwendungen (Multiple Document Interface, Schnittstelle für mehrere Dokumente), und das <xref:System.Windows.Forms.MenuStrip>-Steuerelement unterstützt das Zusammenführen von Menüs. MDI-Formulare können auch <xref:System.Windows.Forms.ToolStrip>-Steuerelemente enthalten.  
  
 In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie mit <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente mit einem MDI-Formular. Das Formular unterstützt auch Zusammenführen von Menüs mit untergeordneten Menüs. Die folgenden Aufgaben werden in dieser exemplarischen Vorgehensweise veranschaulicht:  
  
-   Erstellen ein Windows Forms-Projekt.  
  
-   Erstellen im Hauptmenü für Ihr Formular. Der tatsächliche Name des Menüs variieren.  
  
-   Hinzufügen der <xref:System.Windows.Forms.ToolStripPanel> die Steuerung an die **Toolbox**.  
  
-   Erstellen ein untergeordnetes Formular.  
  
-   Anordnen von <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente nach Z-Reihenfolge.  
  
 Wenn Sie fertig sind, haben Sie ein MDI-Formular, das Zusammenführen von Menüs und verschiebbare unterstützt <xref:System.Windows.Forms.ToolStrip> Steuerelemente.  
  
 Um den Code in diesem Thema als einzelne Auflistung kopieren möchten, finden Sie unter [Vorgehensweise: Erstellen eines MDI-Formulars mit das Zusammenführen von Menüs und ToolStrip-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Vorraussetzungen  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Berechtigt sind, können zum Erstellen und Ausführen von Windows Forms-Anwendungsprojekten auf dem Computer, auf dem Visual Studio installiert ist.  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.  
  
#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
1.  Erstellen Sie ein Windows-Anwendungsprojekt namens **MDI-Formulars** (**Datei** > **neu** > **Projekt**  >  **Visual C#-** oder **Visual Basic** > **Klassischer Desktop** > **Windows Forms-Anwendung**).  
  
2.  Wählen Sie im Windows Forms-Designer das Formular aus.  
  
3.  Legen Sie im Eigenschaftenfenster den Wert von der <xref:System.Windows.Forms.Form.IsMdiContainer%2A> zu `true`.  
  
## <a name="creating-the-main-menu"></a>Erstellen im Hauptmenü  
 Das übergeordnete MDI-Formular enthält das Hauptmenü. Das Hauptmenü befindet sich ein Element mit dem Namen **Fenster**. Mit der **Fenster** Menüelement, können Sie untergeordnete Formulare erstellen. Menüelemente, die aus untergeordneten Formulare werden in das Hauptmenü zusammengeführt.  
  
#### <a name="to-create-the-main-menu"></a>Erstellen Sie im Hauptmenü  
  
1.  Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.MenuStrip> -Steuerelement auf das Formular.  
  
2.  Hinzufügen einer <xref:System.Windows.Forms.ToolStripMenuItem> auf die <xref:System.Windows.Forms.MenuStrip> steuern, und nennen Sie sie **Fenster**.  
  
3.  Wählen Sie das <xref:System.Windows.Forms.MenuStrip>-Steuerelement.  
  
4.  Legen Sie im Eigenschaftenfenster den Wert von der <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> Eigenschaft `ToolStripMenuItem1`.  
  
5.  Fügen Sie ein Unterelement, das **Fenster** Menüelement, und nennen Sie das Unterelement **neu**.  
  
6.  Klicken Sie im Fenster Eigenschaften auf **Ereignisse**.  
  
7.  Doppelklicken Sie auf die <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis.  
  
     Der Windows Forms-Designer wird ein Ereignishandler für die <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis.  
  
8.  Fügen Sie den folgenden Code in den Ereignishandler an.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## <a name="adding-the-toolstrippanel-control-to-the-toolbox"></a>Das ToolStripPanel-Steuerelement hinzufügen zur Toolbox  
 Bei Verwendung von <xref:System.Windows.Forms.MenuStrip> Steuerelemente mit einem MDI-Formular, das Sie benötigen die <xref:System.Windows.Forms.ToolStripPanel> Steuerelement. Müssen Sie hinzufügen, die <xref:System.Windows.Forms.ToolStripPanel> die Steuerung an die **Toolbox** das MDI-Formular im Windows Forms-Designer zu erstellen.  
  
#### <a name="to-add-the-toolstrippanel-control-to-the-toolbox"></a>Das ToolStripPanel-Steuerelement zur Toolbox hinzufügen  
  
1.  Öffnen der **Toolbox**, und klicken Sie dann auf die **alle Windows Forms** Tab, um die verfügbaren Windows Forms-Steuerelemente anzuzeigen.  
  
2.  Mit der rechten Maustaste das Kontextmenü öffnen, und wählen **Elemente auswählen**.  
  
3.  In der **Toolboxelemente auswählen** (Dialogfeld), führen Sie einen Bildlauf nach unten der **Namen** Spalte, bis Sie gefunden **ToolStripPanel**.  
  
4.  Aktivieren Sie das Kontrollkästchen von **ToolStripPanel**, und klicken Sie dann auf **OK**.  
  
     Die <xref:System.Windows.Forms.ToolStripPanel> Steuerelement angezeigt wird, der **Toolbox**.  
  
## <a name="creating-a-child-form"></a>Erstellen ein untergeordnetes Formular  
 In diesem Verfahren definieren Sie eine separate untergeordnete Formular-Klasse, die über ein eigenes <xref:System.Windows.Forms.MenuStrip> Steuerelement. Menüelemente für dieses Formular sind mit denen des übergeordneten Formulars zusammengeführt.  
  
#### <a name="to-define-a-child-form"></a>Um ein untergeordnetes Formular zu definieren.  
  
1.  Hinzufügen eines neuen Formulars mit dem Namen `ChildForm` zum Projekt.  
  
     Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Windows Forms zu einem Projekt](https://msdn.microsoft.com/library/3d7bb25f-fd90-47cf-9378-fa0d764686c1).  
  
2.  Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.MenuStrip> Steuerelement auf das untergeordnete Formular.  
  
3.  Klicken Sie auf die <xref:System.Windows.Forms.MenuStrip> des Steuerelements Smarttag-Glyphe (![Smarttag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), und wählen Sie dann **Elemente bearbeiten**.  
  
4.  In der **-Elementauflistungs-Editor** Dialogfeld hinzu, und ein neues <xref:System.Windows.Forms.ToolStripMenuItem> mit dem Namen **ChildMenuItem** auf das Menü des untergeordneten.  
  
     Weitere Informationen finden Sie unter [ToolStrip-Elementauflistungs-Editor](https://msdn.microsoft.com/library/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).  
  
## <a name="testing-the-form"></a>Testen das Formular  
  
#### <a name="to-test-your-form"></a>So testen Sie das Formular  
  
1.  Drücken Sie F5, um Sie zu kompilieren und führen das Formular aus.  
  
2.  Klicken Sie auf die **Fenster** Menüelement öffnen Sie das Menü, und klicken Sie dann auf **neu**.  
  
     Ein neues untergeordnetes Formular wird in den MDI-Clientbereichs des Formulars erstellt. Menü des untergeordneten Formulars wird mit dem Hauptmenü zusammengeführt.  
  
3.  Schließen Sie das untergeordnete Formular.  
  
     Menü des untergeordneten Formulars wird über das Hauptmenü entfernt.  
  
4.  Klicken Sie auf **neu** mehrmals.  
  
     Die untergeordneten Formulare werden automatisch aufgelistet, unter der **Fenster** Menüelement, da die <xref:System.Windows.Forms.MenuStrip> des Steuerelements <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> -Eigenschaft zugewiesen wird.  
  
## <a name="adding-toolstrip-support"></a>Hinzufügen von ToolStrip-Unterstützung  
 In diesem Verfahren fügen Sie vier <xref:System.Windows.Forms.ToolStrip> Steuerelemente an das übergeordnete MDI-Formular. Jede <xref:System.Windows.Forms.ToolStrip> Steuerelement wird hinzugefügt, in einem <xref:System.Windows.Forms.ToolStripPanel> -Steuerelement, das den Rand des Formulars angedockt ist.  
  
#### <a name="to-add-toolstrip-controls-to-the-mdi-parent-form"></a>Hinzufügen von ToolStrip-Steuerelementen zur übergeordneten MDI-Formulars  
  
1.  Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.ToolStripPanel> -Steuerelement auf das Formular.  
  
2.  Mit der <xref:System.Windows.Forms.ToolStripPanel> -Steuerelement ausgewählt ist, doppelklicken Sie auf die <xref:System.Windows.Forms.ToolStrip> steuern, der **Toolbox**.  
  
     Ein <xref:System.Windows.Forms.ToolStrip> Steuerelement wird erstellt, der <xref:System.Windows.Forms.ToolStripPanel> Steuerelement.  
  
3.  Wählen Sie das <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement.  
  
4.  Ändern Sie im Eigenschaftenfenster den Wert des Steuerelements <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Left>.  
  
     Die <xref:System.Windows.Forms.ToolStripPanel> steuern, wird an der linken Seite des Formulars wird unterhalb des Hauptmenüs angedockt. Wird die Größe des MDI-Client-Bereichs angepasst der <xref:System.Windows.Forms.ToolStripPanel> Steuerelement.  
  
5.  Wiederholen Sie die Schritte 1 bis 4.  
  
     Docken Sie die neuen <xref:System.Windows.Forms.ToolStripPanel> Steuerelement am oberen Rand des Formulars.  
  
     Die <xref:System.Windows.Forms.ToolStripPanel> Steuerelement angedockt ist, unterhalb des Hauptmenüs, sondern auf der rechten Seite des ersten <xref:System.Windows.Forms.ToolStripPanel> Steuerelement. Dieser Schritt veranschaulicht, die Bedeutung der Z-Reihenfolge bei der Positionierung ordnungsgemäß <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente.  
  
6.  Wiederholen Sie die Schritte 1 bis 4 für zwei weitere <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente.  
  
     Docken Sie die neuen <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente am rechten und unteren Rand des Formulars.  
  
## <a name="arranging-toolstrippanel-controls-by-z-order"></a>ToolStripPanel-Steuerelementen Z-Reihenfolge anordnen  
 Die Position des angedockten <xref:System.Windows.Forms.ToolStripPanel> Steuerelement auf dem MDI-Formular richtet sich nach der die Position des Steuerelements in der Z-Reihenfolge. Sie können problemlos die Z-Reihenfolge der Steuerelemente in das Fenster "Dokumentgliederung" anordnen.  
  
#### <a name="to-arrange-toolstrippanel-controls-by-z-order"></a>ToolStripPanel-Steuerelementen Z-Reihenfolge anordnen  
  
1.  In der **Ansicht** Menü klicken Sie auf **Other Windows**, und klicken Sie dann auf **Dokumentgliederung**.  
  
     Die Anordnung von Ihrem <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente aus dem vorherigen Verfahren entspricht nicht dem Standard. Dies ist, da die Z-Reihenfolge nicht korrekt ist. Verwenden Sie das Fenster "Dokumentgliederung", um die Z-Reihenfolge der Steuerelemente ändern.  
  
2.  Wählen Sie in das Fenster "Dokumentgliederung" **ToolStripPanel4**.  
  
3.  Klicken Sie auf den Pfeil nach unten-Schaltfläche wiederholt, bis **ToolStripPanel4** wird am unteren Rand der Liste.  
  
     Die **ToolStripPanel4** Steuerelement am unteren Rand unter den anderen Steuerelementen im Formular angedockt ist.  
  
4.  Wählen Sie **ToolStripPanel2**.  
  
5.  Klicken Sie einmal auf die Schaltfläche nach unten weisenden Pfeil, dritte Positionieren des Steuerelements in der Liste.  
  
     Die **ToolStripPanel2** Steuerelement am oberen Rand des Formulars, unterhalb des Hauptmenüs und über die anderen Steuerelemente angedockt ist.  
  
6.  Wählen Sie verschiedene Steuerelemente in der **Dokumentgliederung** Fenster und verschieben Sie sie an andere Positionen in der Z-Reihenfolge. Beachten Sie die Auswirkungen der Z-Reihenfolge auf die Platzierung der angedockten Steuerelemente. Verwenden Sie STRG + Z oder **Rückgängig** auf die **bearbeiten** Menü, um Ihre Änderungen rückgängig machen.  
  
## <a name="checkpoint"></a>Checkpoint  
  
#### <a name="to-test-your-form"></a>So testen Sie das Formular  
  
1.  Drücken Sie F5, um Sie zu kompilieren und führen das Formular aus.  
  
2.  Klicken Sie auf den Ziehpunkt einer <xref:System.Windows.Forms.ToolStrip> steuern, und ziehen Sie das Steuerelement an anderen Positionen auf dem Formular.  
  
     Ziehen Sie eine <xref:System.Windows.Forms.ToolStrip> Steuerelement von einem <xref:System.Windows.Forms.ToolStripPanel> zu einem anderen Steuerelement.  
  
## <a name="next-steps"></a>Nächste Schritte  
 In dieser exemplarischen Vorgehensweise haben Sie einen übergeordneten MDI-Formulars mit <xref:System.Windows.Forms.ToolStrip> Steuerelemente und das Zusammenführen von Menüs. Sie können die <xref:System.Windows.Forms.ToolStrip> -Steuerelementfamilie zu vielen anderen Zwecken:  
  
-   Erstellen von Kontextmenüs für Ihre Steuerelemente mit <xref:System.Windows.Forms.ContextMenuStrip>. Weitere Informationen finden Sie unter [Übersicht über die ContextMenu-Komponente](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Ein Formular erstellt mit einem automatisch angegebenen Standardmenü. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).  
  
-   Geben Sie Ihre <xref:System.Windows.Forms.ToolStrip> steuert, ein professionelles Aussehen. Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen des ToolStrip-Renderers für eine Anwendung](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [Vorgehensweise: Erstellen von übergeordneten MDI-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)
- [Vorgehensweise: Erstellen von untergeordneten MDI-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)
- [Vorgehensweise: Einfügen eines MenuStrip in ein MDI-Dropdownmenü](../../../../docs/framework/winforms/controls/how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [ToolStrip-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
