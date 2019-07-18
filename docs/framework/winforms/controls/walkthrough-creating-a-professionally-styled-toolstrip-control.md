---
title: 'Exemplarische Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
ms.openlocfilehash: 226e805d0240236899ee0cc290f1060a3b0aa391
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211769"
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a>Exemplarische Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements

Sie können Ihrer Anwendungsverzeichnis erteilen <xref:System.Windows.Forms.ToolStrip> steuert, ein professionelles Aussehen und Verhalten durch eine eigene Klasse abgeleitet schreiben die <xref:System.Windows.Forms.ToolStripProfessionalRenderer> Typ.

In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie mit <xref:System.Windows.Forms.ToolStrip> Steuerelemente, um ein zusammengesetztes Steuerelement zu erstellen, ähnelt die **Navigationsbereich** von Microsoft® Outlook® bereitgestellten. Die folgenden Aufgaben werden in dieser exemplarischen Vorgehensweise veranschaulicht:

- Erstellen eines Windows-Steuerelementbibliothek-Projekts.

- Entwerfen des StackView-Steuerelements.

- Implementieren eines benutzerdefinierten Renderers.

Wenn Sie fertig sind, müssen Sie ein Steuerelement wiederverwendbare benutzerdefinierte Clienteinstellungen, mit der professionelle Darstellung eines Microsoft Office® XP-Steuerelements.

Zum Kopieren des Codes in diesem Thema als einzelne Auflistung lesen Sie [Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements](how-to-create-a-professionally-styled-toolstrip-control.md).

## <a name="prerequisites"></a>Vorraussetzungen

Sie benötigen Visual Studio zum Durchführen dieser exemplarischen Vorgehensweise.

## <a name="create-the-control-library-project"></a>Erstellen Sie die Steuerelementbibliothek-Projekt

1. Erstellen Sie in Visual Studio ein neues Windows-Steuerelementbibliothek-Projekt namens `StackViewLibrary`.

2. In **Projektmappen-Explorer**, löschen Sie Standardsteuerelement des Projekts, indem Sie die Quelldatei, die mit dem Namen "UserControl1.cs" oder "UserControl1.vb", abhängig von der Sprache Ihrer Wahl löschen.

     Weitere Informationen finden Sie unter [Vorgehensweise: Entfernen, löschen und Ausschließen von Elementen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).

3. Fügen Sie einen neuen <xref:System.Windows.Forms.UserControl> Element für die **StackViewLibrary** Projekt. Weisen Sie der neuen Quelldatei Basisnamen `StackView`.

## <a name="design-the-stackview-control"></a>Entwerfen des StackView-Steuerelements

Die `StackView` Steuerelement ist ein zusammengesetztes Steuerelement mit einem untergeordneten <xref:System.Windows.Forms.ToolStrip> Steuerelement. Weitere Informationen über zusammengesetzte Steuerelemente finden Sie unter [Varieties of Custom Controls](varieties-of-custom-controls.md).

1. Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.ToolStrip> Steuerelement auf die Entwurfsoberfläche.

2. In der **Eigenschaften** legen die <xref:System.Windows.Forms.ToolStrip> Eigenschaften des Steuerelements entsprechend der folgenden Tabelle.

    |Eigenschaft|Wert|
    |--------------|-----------|
    |Name|`stackStrip`|
    |CanOverflow|`false`|
    |Andocken|<xref:System.Windows.Forms.DockStyle.Bottom>|
    |Schriftart|`Tahoma, 10pt, style=Bold`|
    |GripStyle|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|
    |LayoutStyle|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|
    |Abstand|`0, 7, 0, 0`|
    |RenderMode|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|

3. Im Windows Forms-Designer, klicken Sie auf die <xref:System.Windows.Forms.ToolStrip> des Steuerelements **hinzufügen** Schaltfläche, und fügen eine <xref:System.Windows.Forms.ToolStripButton> auf die `stackStrip` Steuerelement.

4. In der **Eigenschaften** legen die <xref:System.Windows.Forms.ToolStripButton> Eigenschaften des Steuerelements entsprechend der folgenden Tabelle.

    |Eigenschaft|Wert|
    |--------------|-----------|
    |Name|`mailStackButton`|
    |CheckOnClick|true|
    |CheckState|<xref:System.Windows.Forms.CheckState.Checked>|
    |DisplayStyle|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|
    |ImageAlign|<xref:System.Drawing.ContentAlignment.MiddleLeft>|
    |ImageScaling|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|
    |ImageTransparentColor|`238, 238, 238`|
    |Rand|`0, 0, 0, 0`|
    |Abstand|`3, 3, 3, 3`|
    |Text|**E-Mail-Nachrichten**|
    |TextAlign|<xref:System.Drawing.ContentAlignment.MiddleLeft>|

5. Wiederholen Sie Schritt 7 für drei weitere <xref:System.Windows.Forms.ToolStripButton> Steuerelemente.

     Benennen Sie die Steuerelemente `calendarStackButton`, `contactsStackButton`, und `tasksStackButton`. Legen Sie den Wert, der die <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft **Kalender**, **Kontakte**, und **Aufgaben**bzw.

## <a name="handle-events"></a>Behandeln von Ereignissen

Zwei Ereignisse sind wichtig, zu der `StackView` -Steuerelement ordnungsgemäß verhält. Behandeln der <xref:System.Windows.Forms.UserControl.Load> Ereignis, um das Steuerelement ordnungsgemäß zu positionieren. Behandeln der <xref:System.Windows.Forms.ToolStripItem.Click> -Ereignis für jeden <xref:System.Windows.Forms.ToolStripButton> gerne die `StackView` steuern das Verhalten ähnlich wie die <xref:System.Windows.Forms.RadioButton> Steuerelement.

1. Wählen Sie in der Windows Forms-Designer die `StackView` Steuerelement.

2. Klicken Sie im Fenster **Eigenschaften** auf **Ereignisse**.

3. Doppelklicken Sie auf das Load-Ereignis zum Generieren der `StackView_Load` -Ereignishandler.

4. Kopieren Sie den folgenden Code und fügen Sie ihn in den `StackView_Load`-Ereignishandler ein.

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]

5. Wählen Sie in der Windows Forms-Designer die `mailStackButton` Steuerelement.

6. Klicken Sie im Fenster **Eigenschaften** auf **Ereignisse**.

7. Doppelklicken Sie auf das Click-Ereignis.

     Die Windows Forms-Designer generiert die `mailStackButton_Click` -Ereignishandler.

8. Benennen Sie die `mailStackButton_Click` Ereignishandler `stackButton_Click`.

     Weitere Informationen finden Sie unter [Umbenennen eines Codesymbols](/visualstudio/ide/reference/rename).

9. Fügen Sie folgenden Code in die `stackButton_Click` -Ereignishandler.

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]

10. Wählen Sie in der Windows Forms-Designer die `calendarStackButton` Steuerelement.

11. In der **Eigenschaften** legen das Click-Ereignis das `stackButton_Click` -Ereignishandler.

12. Wiederholen Sie die Schritte 10 und 11 für den `contactsStackButton` und `tasksStackButton` Steuerelemente.

## <a name="define-icons"></a>Definieren der Symbole

Jede `StackView` Schaltfläche verfügt über ein zugeordnetes Symbol. Der Einfachheit halber jedes Symbol wird dargestellt, als Base64-codierte Zeichenfolge, die deserialisiert wird, bevor Sie eine <xref:System.Drawing.Bitmap> daraus erstellt wird. In einer produktionsumgebung Bitmapdaten werden als Ressource gespeichert, und die Symbole, die im Windows Forms-Designer angezeigt werden. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Hintergrundbildern zu Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).

1. Im Code-Editor, fügen Sie folgenden Code in die `StackView` Definition der Klasse. Dieser Code initialisiert die Bitmaps für die <xref:System.Windows.Forms.ToolStripButton> Symbole.

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]

2. Fügen Sie einen Aufruf an die `InitializeImages` -Methode in der die `StackView` Klassenkonstruktor.

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="implement-a-custom-renderer"></a>Implementieren eines benutzerdefinierten Renderers

Sie können anpassen, dass die meisten Elemente der `StackView` steuern Implementieren einer Klasse, die von abgeleitet der <xref:System.Windows.Forms.ToolStripRenderer> Klasse. In diesem Verfahren implementieren Sie eine <xref:System.Windows.Forms.ToolStripProfessionalRenderer> -Klasse, die den Ziehpunkt anpasst und Hintergründe mit Farbverlauf für zeichnet die <xref:System.Windows.Forms.ToolStripButton> Steuerelemente.

1. Fügen Sie folgenden Code in die `StackView` Definition zu steuern.

     Dies ist die Definition für die `StackRenderer` Klasse, welche Außerkraftsetzungen der <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, und <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> Methoden, um eine benutzerdefinierte Darstellung zu erzeugen.

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]

2. In der `StackView` Konstruktor des Steuerelements, erstellen Sie eine neue Instanz der dem `StackRenderer` Klasse, und weisen Sie diese Instanz mit der `stackStrip` des Steuerelements <xref:System.Windows.Forms.ToolStrip.Renderer%2A> Eigenschaft.

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="test-the-stackview-control"></a>Testen Sie das Steuerelement StackView

Die `StackView` Steuerelement abgeleitet wird, aus der <xref:System.Windows.Forms.UserControl> Klasse. Aus diesem Grund können Sie testen, das Steuerelement mit dem **UserControl-Testcontainer**. Weitere Informationen finden Sie unter [Vorgehensweise: Testen Sie das Laufzeitverhalten eines UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).

1. Drücken Sie **F5** erstellen Sie das Projekt, und Starten der **UserControl-Testcontainer**.

2. Bewegen Sie den Zeiger über die Schaltflächen des der `StackView` steuern, und klicken Sie dann auf eine Schaltfläche, um die Darstellung im ausgewählten Zustand anzuzeigen.

## <a name="next-steps"></a>Nächste Schritte

In dieser exemplarischen Vorgehensweise haben Sie eine wiederverwendbare benutzerdefinierte Clientsteuerelement mit der professionelle Darstellung eines Steuerelements Office XP erstellt. Sie können die <xref:System.Windows.Forms.ToolStrip> -Steuerelementfamilie zu vielen anderen Zwecken:

- Erstellen von Kontextmenüs für Ihre Steuerelemente mit <xref:System.Windows.Forms.ContextMenuStrip>. Weitere Informationen finden Sie unter [Übersicht über die ContextMenu-Komponente](contextmenu-component-overview-windows-forms.md).

- Erstellen Sie ein Formular mit einem automatisch angegebenen Standardmenü. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](walkthrough-providing-standard-menu-items-to-a-form.md).

- Erstellen Sie ein Formular für multiple Document Interface (MDI) mit andockbaren <xref:System.Windows.Forms.ToolStrip> Steuerelemente. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines MDI-Formulars mit das Zusammenführen von Menüs und ToolStrip-Steuerelemente](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [ToolStrip-Steuerelement](toolstrip-control-windows-forms.md)
- [Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](how-to-provide-standard-menu-items-to-a-form.md)
