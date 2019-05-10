---
title: 'Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit der Zusammenführungsfunktion für Menüs und ToolStrip-Steuerelemente'
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
ms.openlocfilehash: 5853760231cbece27805923c009d83e16c9b0a5e
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211560"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a>Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit der Zusammenführungsfunktion für Menüs und ToolStrip-Steuerelemente

Der <xref:System.Windows.Forms?displayProperty=nameWithType>-Namespace unterstützt MDI-Anwendungen (Multiple Document Interface, Schnittstelle für mehrere Dokumente), und das <xref:System.Windows.Forms.MenuStrip>-Steuerelement unterstützt das Zusammenführen von Menüs. MDI-Formulare können auch <xref:System.Windows.Forms.ToolStrip>-Steuerelemente enthalten.

In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie mit <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente mit einem MDI-Formular. Das Formular unterstützt auch Zusammenführen von Menüs mit untergeordneten Menüs. Die folgenden Aufgaben werden in dieser exemplarischen Vorgehensweise veranschaulicht:

- Erstellen ein Windows Forms-Projekt.

- Erstellen im Hauptmenü für Ihr Formular. Der tatsächliche Name des Menüs variieren.

- Hinzufügen der <xref:System.Windows.Forms.ToolStripPanel> die Steuerung an die **Toolbox**.

- Erstellen ein untergeordnetes Formular.

- Anordnen von <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente nach Z-Reihenfolge.

Wenn Sie fertig sind, haben Sie ein MDI-Formular, das Zusammenführen von Menüs und verschiebbare unterstützt <xref:System.Windows.Forms.ToolStrip> Steuerelemente.

Zum Kopieren des Codes in diesem Thema als einzelne Auflistung lesen Sie [Vorgehensweise: Erstellen eines MDI-Formulars mit das Zusammenführen von Menüs und ToolStrip-Steuerelemente](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).

## <a name="prerequisites"></a>Vorraussetzungen

Sie benötigen Visual Studio zum Durchführen dieser exemplarischen Vorgehensweise.

## <a name="create-the-project"></a>Erstellen eines Projekts

1. Erstellen Sie in Visual Studio ein Windows-Anwendungsprojekt namens **MDI-Formulars** (**Datei** > **neu** > **Projekt**  >  **Visual C#**  oder **Visual Basic** > **Klassischer Desktop**  >   **Windows Forms-Anwendung**).

2. Wählen Sie im Windows Forms-Designer das Formular aus.

3. Legen Sie im Eigenschaftenfenster den Wert von der <xref:System.Windows.Forms.Form.IsMdiContainer%2A> zu `true`.

## <a name="create-the-main-menu"></a>Erstellen Sie im Hauptmenü

Das übergeordnete MDI-Formular enthält das Hauptmenü. Das Hauptmenü befindet sich ein Element mit dem Namen **Fenster**. Mit der **Fenster** Menüelement, können Sie untergeordnete Formulare erstellen. Menüelemente, die aus untergeordneten Formulare werden in das Hauptmenü zusammengeführt.

1. Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.MenuStrip> -Steuerelement auf das Formular.

2. Hinzufügen einer <xref:System.Windows.Forms.ToolStripMenuItem> auf die <xref:System.Windows.Forms.MenuStrip> steuern, und nennen Sie sie **Fenster**.

3. Wählen Sie das <xref:System.Windows.Forms.MenuStrip>-Steuerelement.

4. Legen Sie im Eigenschaftenfenster den Wert von der <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> Eigenschaft `ToolStripMenuItem1`.

5. Fügen Sie ein Unterelement, das **Fenster** Menüelement, und nennen Sie das Unterelement **neu**.

6. Klicken Sie im Fenster Eigenschaften auf **Ereignisse**.

7. Doppelklicken Sie auf die <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis.

     Der Windows Forms-Designer wird ein Ereignishandler für die <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis.

8. Fügen Sie den folgenden Code in den Ereignishandler an.

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a>Fügen Sie das ToolStripPanel-Steuerelement zur Toolbox

Bei Verwendung von <xref:System.Windows.Forms.MenuStrip> Steuerelemente mit einem MDI-Formular, das Sie benötigen die <xref:System.Windows.Forms.ToolStripPanel> Steuerelement. Müssen Sie hinzufügen, die <xref:System.Windows.Forms.ToolStripPanel> die Steuerung an die **Toolbox** das MDI-Formular im Windows Forms-Designer zu erstellen.

1. Öffnen der **Toolbox**, und klicken Sie dann auf die **alle Windows Forms** Tab, um die verfügbaren Windows Forms-Steuerelemente anzuzeigen.

2. Mit der rechten Maustaste das Kontextmenü öffnen, und wählen **Elemente auswählen**.

3. In der **Toolboxelemente auswählen** (Dialogfeld), führen Sie einen Bildlauf nach unten der **Namen** Spalte, bis Sie gefunden **ToolStripPanel**.

4. Aktivieren Sie das Kontrollkästchen von **ToolStripPanel**, und klicken Sie dann auf **OK**.

     Die <xref:System.Windows.Forms.ToolStripPanel> Steuerelement angezeigt wird, der **Toolbox**.

## <a name="create-a-child-form"></a>Erstellen Sie ein untergeordnetes Formular

In diesem Verfahren definieren Sie eine separate untergeordnete Formular-Klasse, die über ein eigenes <xref:System.Windows.Forms.MenuStrip> Steuerelement. Menüelemente für dieses Formular sind mit denen des übergeordneten Formulars zusammengeführt.

1. Hinzufügen eines neuen Formulars mit dem Namen `ChildForm` zum Projekt.

     Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Windows Forms zu einem Projekt](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).

2. Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.MenuStrip> Steuerelement auf das untergeordnete Formular.

3. Klicken Sie auf die <xref:System.Windows.Forms.MenuStrip> des Steuerelements Smarttag-Glyphe (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), und wählen Sie dann **Elemente bearbeiten**.

4. In der **-Elementauflistungs-Editor** Dialogfeld hinzu, und ein neues <xref:System.Windows.Forms.ToolStripMenuItem> mit dem Namen **ChildMenuItem** auf das Menü des untergeordneten.

     Weitere Informationen finden Sie unter [ToolStrip-Elementauflistungs-Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).

## <a name="test-the-form"></a>Testen Sie das Formular

1. Drücken Sie **F5** zum Kompilieren und führen Sie das Formular.

2. Klicken Sie auf die **Fenster** Menüelement öffnen Sie das Menü, und klicken Sie dann auf **neu**.

     Ein neues untergeordnetes Formular wird in den MDI-Clientbereichs des Formulars erstellt. Menü des untergeordneten Formulars wird mit dem Hauptmenü zusammengeführt.

3. Schließen Sie das untergeordnete Formular.

     Menü des untergeordneten Formulars wird über das Hauptmenü entfernt.

4. Klicken Sie auf **neu** mehrmals.

     Die untergeordneten Formulare werden automatisch aufgelistet, unter der **Fenster** Menüelement, da die <xref:System.Windows.Forms.MenuStrip> des Steuerelements <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> -Eigenschaft zugewiesen wird.

## <a name="add-toolstrip-support"></a>Hinzufügen von ToolStrip-Unterstützung

In diesem Verfahren fügen Sie vier <xref:System.Windows.Forms.ToolStrip> Steuerelemente an das übergeordnete MDI-Formular. Jede <xref:System.Windows.Forms.ToolStrip> Steuerelement wird hinzugefügt, in einem <xref:System.Windows.Forms.ToolStripPanel> -Steuerelement, das den Rand des Formulars angedockt ist.

1. Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.ToolStripPanel> -Steuerelement auf das Formular.

2. Mit der <xref:System.Windows.Forms.ToolStripPanel> -Steuerelement ausgewählt ist, doppelklicken Sie auf die <xref:System.Windows.Forms.ToolStrip> steuern, der **Toolbox**.

     Ein <xref:System.Windows.Forms.ToolStrip> Steuerelement wird erstellt, der <xref:System.Windows.Forms.ToolStripPanel> Steuerelement.

3. Wählen Sie das <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement.

4. Ändern Sie im Eigenschaftenfenster den Wert des Steuerelements <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Left>.

     Die <xref:System.Windows.Forms.ToolStripPanel> steuern, wird an der linken Seite des Formulars wird unterhalb des Hauptmenüs angedockt. Wird die Größe des MDI-Client-Bereichs angepasst der <xref:System.Windows.Forms.ToolStripPanel> Steuerelement.

5. Wiederholen Sie die Schritte 1 bis 4.

     Docken Sie die neuen <xref:System.Windows.Forms.ToolStripPanel> Steuerelement am oberen Rand des Formulars.

     Die <xref:System.Windows.Forms.ToolStripPanel> Steuerelement angedockt ist, unterhalb des Hauptmenüs, sondern auf der rechten Seite des ersten <xref:System.Windows.Forms.ToolStripPanel> Steuerelement. Dieser Schritt veranschaulicht, die Bedeutung der Z-Reihenfolge bei der Positionierung ordnungsgemäß <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente.

6. Wiederholen Sie die Schritte 1 bis 4 für zwei weitere <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente.

     Docken Sie die neuen <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente am rechten und unteren Rand des Formulars.

## <a name="arrange-toolstrippanel-controls-by-z-order"></a>ToolStripPanel-Steuerelementen Z-Reihenfolge anordnen

Die Position des angedockten <xref:System.Windows.Forms.ToolStripPanel> Steuerelement auf dem MDI-Formular richtet sich nach der die Position des Steuerelements in der Z-Reihenfolge. Sie können problemlos die Z-Reihenfolge der Steuerelemente in das Fenster "Dokumentgliederung" anordnen.

1. In der **Ansicht** Menü klicken Sie auf **Other Windows**, und klicken Sie dann auf **Dokumentgliederung**.

     Die Anordnung von Ihrem <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente aus dem vorherigen Verfahren entspricht nicht dem Standard. Dies ist, da die Z-Reihenfolge nicht korrekt ist. Verwenden Sie das Fenster "Dokumentgliederung", um die Z-Reihenfolge der Steuerelemente ändern.

2. Wählen Sie in das Fenster "Dokumentgliederung" **ToolStripPanel4**.

3. Klicken Sie auf den Pfeil nach unten-Schaltfläche wiederholt, bis **ToolStripPanel4** wird am unteren Rand der Liste.

     Die **ToolStripPanel4** Steuerelement am unteren Rand unter den anderen Steuerelementen im Formular angedockt ist.

4. Wählen Sie **ToolStripPanel2**.

5. Klicken Sie einmal auf die Schaltfläche nach unten weisenden Pfeil, dritte Positionieren des Steuerelements in der Liste.

     Die **ToolStripPanel2** Steuerelement am oberen Rand des Formulars, unterhalb des Hauptmenüs und über die anderen Steuerelemente angedockt ist.

6. Wählen Sie verschiedene Steuerelemente in der **Dokumentgliederung** Fenster und verschieben Sie sie an andere Positionen in der Z-Reihenfolge. Beachten Sie die Auswirkungen der Z-Reihenfolge auf die Platzierung der angedockten Steuerelemente. Verwenden Sie STRG + Z oder **Rückgängig** auf die **bearbeiten** Menü, um Ihre Änderungen rückgängig machen.

## <a name="checkpoint---test-your-form"></a>Prüfpunkt - testen Sie das Formular

1. Drücken Sie **F5** zum Kompilieren und führen Sie das Formular.

2. Klicken Sie auf den Ziehpunkt einer <xref:System.Windows.Forms.ToolStrip> steuern, und ziehen Sie das Steuerelement an anderen Positionen auf dem Formular.

     Ziehen Sie eine <xref:System.Windows.Forms.ToolStrip> Steuerelement von einem <xref:System.Windows.Forms.ToolStripPanel> zu einem anderen Steuerelement.

## <a name="next-steps"></a>Nächste Schritte

In dieser exemplarischen Vorgehensweise haben Sie einen übergeordneten MDI-Formulars mit <xref:System.Windows.Forms.ToolStrip> Steuerelemente und das Zusammenführen von Menüs. Sie können die <xref:System.Windows.Forms.ToolStrip> -Steuerelementfamilie zu vielen anderen Zwecken:

- Erstellen von Kontextmenüs für Ihre Steuerelemente mit <xref:System.Windows.Forms.ContextMenuStrip>. Weitere Informationen finden Sie unter [Übersicht über die ContextMenu-Komponente](contextmenu-component-overview-windows-forms.md).

- Ein Formular erstellt mit einem automatisch angegebenen Standardmenü. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](walkthrough-providing-standard-menu-items-to-a-form.md).

- Geben Sie Ihre <xref:System.Windows.Forms.ToolStrip> steuert, ein professionelles Aussehen. Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen des ToolStrip-Renderers für eine Anwendung](how-to-set-the-toolstrip-renderer-for-an-application.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [Vorgehensweise: Erstellen von übergeordneten MDI-Formularen](../advanced/how-to-create-mdi-parent-forms.md)
- [Vorgehensweise: Erstellen von untergeordneten MDI-Formularen](../advanced/how-to-create-mdi-child-forms.md)
- [Vorgehensweise: Einfügen eines MenuStrip in ein MDI-Dropdownmenü](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [ToolStrip-Steuerelement](toolstrip-control-windows-forms.md)
