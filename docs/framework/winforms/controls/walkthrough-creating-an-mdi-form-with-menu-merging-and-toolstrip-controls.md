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
ms.openlocfilehash: e0343b98cb71521b35418e70550a93e0bfe20fa8
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628786"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a>Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit der Zusammenführungsfunktion für Menüs und ToolStrip-Steuerelemente

Der <xref:System.Windows.Forms?displayProperty=nameWithType>-Namespace unterstützt MDI-Anwendungen (Multiple Document Interface, Schnittstelle für mehrere Dokumente), und das <xref:System.Windows.Forms.MenuStrip>-Steuerelement unterstützt das Zusammenführen von Menüs. MDI-Formulare können auch <xref:System.Windows.Forms.ToolStrip>-Steuerelemente enthalten.

In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente mit einem MDI-Formular verwendet werden. Das Formular unterstützt auch Zusammenführen von Menüs mit untergeordneten Menüs. In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:

- Erstellen eines Windows Forms Projekts

- Erstellen des Hauptmenüs für das Formular. Der tatsächliche Name des Menüs ist unterschiedlich.

- Das <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement wird der **Toolbox**hinzugefügt.

- Erstellen eines untergeordneten Formulars.

- Anordnen von <xref:System.Windows.Forms.ToolStripPanel> Steuerelementen durch z-Reihenfolge.

Wenn Sie fertig sind, verfügen Sie über ein MDI-Formular, das Zusammenführen von Menüs und verschiebbaren <xref:System.Windows.Forms.ToolStrip> Steuerelementen unterstützt.

Informationen zum Kopieren des Codes in diesem Thema als einzelne Auflistung finden Sie unter Gewusst [wie: Erstellen eines MDI-Formulars mit der Zusammenführung von Menüs und ToolStrip-Steuerelementen](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).

## <a name="prerequisites"></a>Voraussetzungen

Sie benötigen Visual Studio, um diese exemplarische Vorgehensweise abzuschließen.

## <a name="create-the-project"></a>Erstellen des Projekts

1. Erstellen Sie in Visual Studio ein Windows-Anwendungsprojekt mit dem Namen " **MDIForm** " (**Datei** > **neue** > **Projekt** >  **C# Visual** oder **Visual Basic** > **klassischen Desktop** > Windows Forms **Anwendung**).

2. Wählen Sie im Windows Forms-Designer das Formular aus.

3. Legen Sie in der Eigenschaftenfenster den Wert des <xref:System.Windows.Forms.Form.IsMdiContainer%2A> auf `true`fest.

## <a name="create-the-main-menu"></a>Erstellen des Hauptmenü

Das übergeordnete MDI-Formular enthält das Hauptmenü. Das Hauptmenü hat ein Menü Element mit dem Namen **Fenster**. Mit dem Menü Element **Fenster** können Sie untergeordnete Formulare erstellen. Menü Elemente aus untergeordneten Formularen werden im Hauptmenü zusammengeführt.

1. Ziehen Sie ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement aus der **Toolbox**auf das Formular.

2. Fügen Sie dem <xref:System.Windows.Forms.MenuStrip>-Steuerelement eine <xref:System.Windows.Forms.ToolStripMenuItem> hinzu, und nennen Sie es **Window**.

3. Wählen Sie das <xref:System.Windows.Forms.MenuStrip>-Steuerelement.

4. Legen Sie in der Eigenschaftenfenster den Wert der Eigenschaft <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> auf `ToolStripMenuItem1`fest.

5. Fügen Sie dem **Fenster** Menü Element ein Unterelement hinzu, und benennen Sie das Unterelement **neu**.

6. Klicken Sie im Eigenschaftenfenster auf **Ereignisse**.

7. Doppelklicken Sie auf das <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis.

     Der Windows Forms-Designer generiert einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis.

8. Fügen Sie den folgenden Code in den-Ereignishandler ein.

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a>Fügen Sie das ToolStripPanel-Steuerelement der Toolbox hinzu.

Wenn Sie <xref:System.Windows.Forms.MenuStrip> Steuerelemente mit einem MDI-Formular verwenden, müssen Sie über das <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement verfügen. Sie müssen das <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement der **Toolbox** hinzufügen, um das MDI-Formular im Windows Forms-Designer zu erstellen.

1. Öffnen Sie die **Toolbox**, und klicken Sie dann auf die Registerkarte **alle Windows Forms** , um die verfügbaren Windows Forms Steuerelemente anzuzeigen.

2. Klicken Sie mit der rechten Maustaste, um das Kontextmenü zu öffnen, und wählen Sie **Elemente auswählen**.

3. Führen Sie im Dialogfeld **Toolbox Elemente auswählen** einen **Bildlauf** nach unten in der Spalte Name aus, bis Sie **ToolStripPanel**gefunden haben.

4. Aktivieren Sie das Kontrollkästchen von **ToolStripPanel**, und klicken Sie dann auf **OK**.

     Das <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement wird in der **Toolbox**angezeigt.

## <a name="create-a-child-form"></a>Erstellen eines untergeordneten Formulars

In diesem Verfahren definieren Sie eine separate untergeordnete Formular Klasse, die über ein eigenes <xref:System.Windows.Forms.MenuStrip>-Steuerelement verfügt. Die Menü Elemente für dieses Formular werden mit denen des übergeordneten Formulars zusammengeführt.

1. Fügen Sie dem Projekt ein neues Formular mit dem Namen `ChildForm` hinzu.

     Weitere Informationen finden Sie unter Gewusst [wie: Hinzufügen von Windows Forms zu einem Projekt](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).

2. Ziehen Sie ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement aus der **Toolbox**auf das untergeordnete Formular.

3. Klicken Sie auf das Designer Aktions Symbol des <xref:System.Windows.Forms.MenuStrip> Steuer Elements (![kleinen schwarzen Pfeil](./media/designer-actions-glyph.gif)), und wählen Sie dann **Elemente bearbeiten**aus.

4. Fügen Sie im Dialogfeld Elementauflistungs- **Editor** dem untergeordneten Menü eine neue <xref:System.Windows.Forms.ToolStripMenuItem> namens **ChildMenuItem** hinzu.

     Weitere Informationen finden Sie unter [ToolStrip Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100))-Auflistungs-Editor.

## <a name="test-the-form"></a>Testen des Formulars

1. Drücken Sie **F5** , um das Formular zu kompilieren und auszuführen.

2. Klicken Sie auf das Menü Element **Fenster** , um das Menü zu öffnen, und klicken Sie dann auf **neu**.

     Im MDI-Client Bereich des Formulars wird ein neues untergeordnetes Formular erstellt. Das Menü des untergeordneten Formulars wird mit dem Hauptmenü zusammengeführt.

3. Schließen Sie das untergeordnete Formular.

     Das Menü des untergeordneten Formulars wird aus dem Hauptmenü entfernt.

4. Klicken Sie mehrmals auf **neu** .

     Die untergeordneten Formulare werden automatisch unter dem Menü Element **Fenster** aufgeführt, da die <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>-Eigenschaft des <xref:System.Windows.Forms.MenuStrip>-Steuer Elements zugewiesen wird.

## <a name="add-toolstrip-support"></a>ToolStrip-Unterstützung hinzufügen

In diesem Verfahren fügen Sie dem übergeordneten MDI-Formular vier <xref:System.Windows.Forms.ToolStrip>-Steuerelemente hinzu. Jedes <xref:System.Windows.Forms.ToolStrip> Steuerelement wird in einem <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement hinzugefügt, das an den Rand des Formulars angedockt wird.

1. Ziehen Sie ein <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement aus der **Toolbox**auf das Formular.

2. Wenn das <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement ausgewählt ist, doppelklicken Sie auf das <xref:System.Windows.Forms.ToolStrip>-Steuerelement in der **Toolbox**.

     Ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement wird im <xref:System.Windows.Forms.ToolStripPanel> Steuerelement erstellt.

3. Wählen Sie das <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement.

4. Ändern Sie in der Eigenschaftenfenster den Wert der Eigenschaft <xref:System.Windows.Forms.Control.Dock%2A> des Steuer Elements in <xref:System.Windows.Forms.DockStyle.Left>.

     Das <xref:System.Windows.Forms.ToolStripPanel> Steuerelement wird auf der linken Seite des Formulars unterhalb des Hauptmenü andocken. Die Größe des MDI-Client Bereichs wird an das <xref:System.Windows.Forms.ToolStripPanel> Steuerelement angepasst.

5. Wiederholen Sie die Schritte 1 bis 4.

     Docken Sie das neue <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement am oberen Rand des Formulars an.

     Das <xref:System.Windows.Forms.ToolStripPanel> Steuerelement wird unter dem Hauptmenü angedockt, aber auf der rechten Seite des ersten <xref:System.Windows.Forms.ToolStripPanel> Steuer Elements. Dieser Schritt veranschaulicht, wie wichtig die z-Reihenfolge bei der ordnungsgemäßen Positionierung <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente ist.

6. Wiederholen Sie die Schritte 1 bis 4 für zwei weitere <xref:System.Windows.Forms.ToolStripPanel>-Steuerelemente.

     Andocken der neuen <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente rechts und unten im Formular.

## <a name="arrange-toolstrippanel-controls-by-z-order"></a>ToolStripPanel-Steuerelemente nach Z-Reihenfolge anordnen

Die Position eines angedockten <xref:System.Windows.Forms.ToolStripPanel>-Steuer Elements auf dem MDI-Formular hängt von der Position des Steuer Elements in der z-Reihenfolge ab. Sie können die z-Reihenfolge der Steuerelemente im Fenster "Dokument Gliederung" problemlos anordnen.

1. Klicken Sie im Menü **Ansicht** auf **Weitere Fenster**, und klicken Sie dann auf **Dokument**Gliederung.

     Die Anordnung Ihrer <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente aus der vorherigen Prozedur entspricht nicht dem Standard. Dies liegt daran, dass die z-Reihenfolge nicht korrekt ist. Verwenden Sie das Fenster Dokument Gliederung, um die z-Reihenfolge der Steuerelemente zu ändern.

2. Wählen Sie im Fenster Dokument Gliederung die Option **ToolStripPanel4**aus.

3. Klicken Sie wiederholt auf die Schaltfläche mit dem Pfeil nach unten, bis sich **ToolStripPanel4** am Ende der Liste befindet.

     Das **ToolStripPanel4** -Steuerelement wird am unteren Rand des Formulars unterhalb der anderen Steuerelemente angedockt.

4. Wählen Sie **ToolStripPanel2**aus.

5. Klicken Sie einmal auf die Schaltfläche mit dem Pfeil nach unten, um das dritte Steuerelement in der Liste zu positionieren.

     Das **ToolStripPanel2** -Steuerelement wird am oberen Rand des Formulars unterhalb des Hauptmenü und über den anderen Steuerelementen angedockt.

6. Wählen Sie im **Dokument** Gliederungs Fenster verschiedene Steuerelemente aus, und verschieben Sie Sie an verschiedene Positionen in der z-Reihenfolge. Beachten Sie die Auswirkung der z-Reihenfolge auf die Platzierung von angedockten Steuerelementen. Verwenden Sie STRG + Z oder **Rückgängig** im Menü **Bearbeiten** , um die Änderungen rückgängig zu machen.

## <a name="checkpoint---test-your-form"></a>Prüfpunkt: Testen des Formulars

1. Drücken Sie **F5** , um das Formular zu kompilieren und auszuführen.

2. Klicken Sie auf den Ziehpunkt eines <xref:System.Windows.Forms.ToolStrip> Steuer Elements, und ziehen Sie das Steuerelement an verschiedene Positionen im Formular.

     Sie können ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement von einem <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement zu einem anderen ziehen.

## <a name="next-steps"></a>Nächste Schritte

In dieser exemplarischen Vorgehensweise haben Sie ein übergeordnetes MDI-Formular mit <xref:System.Windows.Forms.ToolStrip>-Steuerelementen und der Zusammenführung des Menüs erstellt. Die <xref:System.Windows.Forms.ToolStrip>-Steuerelement Familie kann für viele andere Zwecke verwendet werden:

- Erstellen Sie Kontextmenüs für die Steuerelemente mit <xref:System.Windows.Forms.ContextMenuStrip>. Weitere Informationen finden Sie unter [Übersicht über die ContextMenu-Komponente](contextmenu-component-overview-windows-forms.md).

- Erstellt ein Formular mit einem automatisch ausgefüllten Standardmenü. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Bereitstellen von Standard Menü Elementen für ein Formular](walkthrough-providing-standard-menu-items-to-a-form.md).

- Legen Sie für Ihre <xref:System.Windows.Forms.ToolStrip> Steuerelemente ein professionelles Erscheinungsbild. Weitere Informationen finden Sie unter Gewusst [wie: Festlegen des ToolStrip-Renderers für eine Anwendung](how-to-set-the-toolstrip-renderer-for-an-application.md).

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [Gewusst wie: Erstellen von übergeordneten MDI-Formularen](../advanced/how-to-create-mdi-parent-forms.md)
- [Gewusst wie: Erstellen von untergeordneten MDI-Formularen](../advanced/how-to-create-mdi-child-forms.md)
- [Gewusst wie: Einfügen eines MenuStrip in ein MDI-Dropdownmenü](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [ToolStrip-Steuerelement](toolstrip-control-windows-forms.md)
