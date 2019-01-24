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
ms.openlocfilehash: 36f34fad49ed76293a83d3c018eea48fcdb2944a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714892"
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a>Exemplarische Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements
Sie können Ihrer Anwendungsverzeichnis erteilen <xref:System.Windows.Forms.ToolStrip> steuert, ein professionelles Aussehen und Verhalten durch eine eigene Klasse abgeleitet schreiben die <xref:System.Windows.Forms.ToolStripProfessionalRenderer> Typ.  
  
 In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie mit <xref:System.Windows.Forms.ToolStrip> Steuerelemente, um ein zusammengesetztes Steuerelement zu erstellen, ähnelt die **Navigationsbereich** von Microsoft® Outlook® bereitgestellten. Die folgenden Aufgaben werden in dieser exemplarischen Vorgehensweise veranschaulicht:  
  
-   Erstellen eines Windows-Steuerelementbibliothek-Projekts.  
  
-   Entwerfen des StackView-Steuerelements.  
  
-   Implementieren eines benutzerdefinierten Renderers.  
  
 Wenn Sie fertig sind, müssen Sie ein Steuerelement wiederverwendbare benutzerdefinierte Clienteinstellungen, mit der professionelle Darstellung eines Microsoft Office® XP-Steuerelements.  
  
 Um den Code in diesem Thema als einzelne Auflistung kopieren möchten, finden Sie unter [Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements](../../../../docs/framework/winforms/controls/how-to-create-a-professionally-styled-toolstrip-control.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Vorraussetzungen  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Berechtigt sind, können zum Erstellen und Ausführen von Windows Forms-Anwendungsprojekten auf dem Computer, auf dem Visual Studio installiert ist.  
  
## <a name="creating-a-windows-control-library-project"></a>Erstellen eine Windows-Steuerelementbibliothek-Projekt  
 Der erste Schritt ist das Steuerelementbibliothek-Projekt zu erstellen.  
  
#### <a name="to-create-the-control-library-project"></a>Um die Steuerelementbibliothek-Projekt zu erstellen.  
  
1.  Erstellen Sie ein neues Windows-Steuerelementbibliothek-Projekt namens `StackViewLibrary`.  
  
2.  In **Projektmappen-Explorer**, löschen Sie Standardsteuerelement des Projekts, indem Sie die Quelldatei, die mit dem Namen "UserControl1.cs" oder "UserControl1.vb", abhängig von der Sprache Ihrer Wahl löschen.  
  
     Weitere Informationen finden Sie unter [NIB: Vorgehensweise: Entfernen, löschen und Ausschließen von Elementen](https://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).  
  
3.  Fügen Sie einen neuen <xref:System.Windows.Forms.UserControl> Element für die **StackViewLibrary** Projekt. Weisen Sie der neuen Quelldatei Basisnamen `StackView`.  
  
## <a name="designing-the-stackview-control"></a>Entwerfen des StackView-Steuerelements  
 Die `StackView` Steuerelement ist ein zusammengesetztes Steuerelement mit einem untergeordneten <xref:System.Windows.Forms.ToolStrip> Steuerelement. Weitere Informationen über zusammengesetzte Steuerelemente finden Sie unter [Varieties of Custom Controls](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md).  
  
#### <a name="to-design-the-stackview-control"></a>So entwerfen Sie die StackView-Steuerelement  
  
1.  Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.ToolStrip> Steuerelement auf die Entwurfsoberfläche.  
  
2.  In der **Eigenschaften** legen die <xref:System.Windows.Forms.ToolStrip> Eigenschaften des Steuerelements entsprechend der folgenden Tabelle.  
  
    |Eigenschaft|Wert|  
    |--------------|-----------|  
    |name|`stackStrip`|  
    |CanOverflow|`false`|  
    |Andocken|<xref:System.Windows.Forms.DockStyle.Bottom>|  
    |Schriftart|`Tahoma, 10pt, style=Bold`|  
    |GripStyle|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|  
    |LayoutStyle|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|  
    |Textabstand|`0, 7, 0, 0`|  
    |RenderMode|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|  
  
3.  Im Windows Forms-Designer, klicken Sie auf die <xref:System.Windows.Forms.ToolStrip> des Steuerelements **hinzufügen** Schaltfläche, und fügen eine <xref:System.Windows.Forms.ToolStripButton> auf die `stackStrip` Steuerelement.  
  
4.  In der **Eigenschaften** legen die <xref:System.Windows.Forms.ToolStripButton> Eigenschaften des Steuerelements entsprechend der folgenden Tabelle.  
  
    |Eigenschaft|Wert|  
    |--------------|-----------|  
    |name|`mailStackButton`|  
    |CheckOnClick|true|  
    |CheckState|<xref:System.Windows.Forms.CheckState.Checked>|  
    |DisplayStyle|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|  
    |ImageAlign|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
    |ImageScaling|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|  
    |ImageTransparentColor|`238, 238, 238`|  
    |Margin|`0, 0, 0, 0`|  
    |Textabstand|`3, 3, 3, 3`|  
    |Text|**E-Mail-Nachrichten**|  
    |TextAlign|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
  
5.  Wiederholen Sie Schritt 7 für drei weitere <xref:System.Windows.Forms.ToolStripButton> Steuerelemente.  
  
     Benennen Sie die Steuerelemente `calendarStackButton`, `contactsStackButton`, und `tasksStackButton`. Legen Sie den Wert, der die <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft **Kalender**, **Kontakte**, und **Aufgaben**bzw.  
  
## <a name="handling-events"></a>Behandeln von Ereignissen  
 Zwei Ereignisse sind wichtig, zu der `StackView` -Steuerelement ordnungsgemäß verhält. Behandeln der <xref:System.Windows.Forms.UserControl.Load> Ereignis, um das Steuerelement ordnungsgemäß zu positionieren. Behandeln der <xref:System.Windows.Forms.ToolStripItem.Click> -Ereignis für jeden <xref:System.Windows.Forms.ToolStripButton> gerne die `StackView` steuern das Verhalten ähnlich wie die <xref:System.Windows.Forms.RadioButton> Steuerelement.  
  
#### <a name="to-handle-events"></a>Zum Behandeln von Ereignissen  
  
1.  Wählen Sie in der Windows Forms-Designer die `StackView` Steuerelement.  
  
2.  Klicken Sie im Fenster **Eigenschaften** auf **Ereignisse**.  
  
3.  Doppelklicken Sie auf das Load-Ereignis zum Generieren der `StackView_Load` -Ereignishandler.  
  
4.  Kopieren Sie den folgenden Code und fügen Sie ihn in den `StackView_Load`-Ereignishandler ein.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]  
  
5.  Wählen Sie in der Windows Forms-Designer die `mailStackButton` Steuerelement.  
  
6.  Klicken Sie im Fenster **Eigenschaften** auf **Ereignisse**.  
  
7.  Doppelklicken Sie auf das Click-Ereignis.  
  
     Die Windows Forms-Designer generiert die `mailStackButton_Click` -Ereignishandler.  
  
8.  Benennen Sie die `mailStackButton_Click` Ereignishandler `stackButton_Click`.  
  
     Weitere Informationen finden Sie unter [Vorgehensweise: Umbenennen von Bezeichnern (Visual Basic)](https://msdn.microsoft.com/library/e5a5edf8-3dba-4119-81f4-fc2aba180e0c).  
  
9. Fügen Sie folgenden Code in die `stackButton_Click` -Ereignishandler.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]  
  
10. Wählen Sie in der Windows Forms-Designer die `calendarStackButton` Steuerelement.  
  
11. In der **Eigenschaften** legen das Click-Ereignis das `stackButton_Click` -Ereignishandler.  
  
12. Wiederholen Sie die Schritte 10 und 11 für den `contactsStackButton` und `tasksStackButton` Steuerelemente.  
  
## <a name="defining-icons"></a>Definieren von Symbolen  
 Jede `StackView` Schaltfläche verfügt über ein zugeordnetes Symbol. Der Einfachheit halber jedes Symbol wird dargestellt, als Base64-codierte Zeichenfolge, die deserialisiert wird, bevor Sie eine <xref:System.Drawing.Bitmap> daraus erstellt wird. In einer produktionsumgebung Bitmapdaten werden als Ressource gespeichert, und die Symbole, die im Windows Forms-Designer angezeigt werden. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Hintergrundbildern zu Windows Forms](https://msdn.microsoft.com/library/7a509ba2-055c-4ae6-b88a-54625c6d9aff).  
  
#### <a name="to-define-icons"></a>Um Symbole zu definieren.  
  
1.  Im Code-Editor, fügen Sie folgenden Code in die `StackView` Definition der Klasse. Dieser Code initialisiert die Bitmaps für die <xref:System.Windows.Forms.ToolStripButton> Symbole.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]  
  
2.  Fügen Sie einen Aufruf an die `InitializeImages` -Methode in der die `StackView` Klassenkonstruktor.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="implementing-a-custom-renderer"></a>Implementieren eines benutzerdefinierten Renderers  
 Sie können anpassen, dass die meisten Elemente der `StackView` steuern Implementieren einer Klasse, die von abgeleitet der <xref:System.Windows.Forms.ToolStripRenderer> Klasse. In diesem Verfahren implementieren Sie eine <xref:System.Windows.Forms.ToolStripProfessionalRenderer> -Klasse, die den Ziehpunkt anpasst und Hintergründe mit Farbverlauf für zeichnet die <xref:System.Windows.Forms.ToolStripButton> Steuerelemente.  
  
#### <a name="to-implement-a-custom-renderer"></a>Zum Implementieren eines benutzerdefinierten Renderers  
  
1.  Fügen Sie folgenden Code in die `StackView` Definition zu steuern.  
  
     Dies ist die Definition für die `StackRenderer` Klasse, welche Außerkraftsetzungen der <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, und <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> Methoden, um eine benutzerdefinierte Darstellung zu erzeugen.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]  
  
2.  In der `StackView` Konstruktor des Steuerelements, erstellen Sie eine neue Instanz der dem `StackRenderer` Klasse, und weisen Sie diese Instanz mit der `stackStrip` des Steuerelements <xref:System.Windows.Forms.ToolStrip.Renderer%2A> Eigenschaft.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="testing-the-stackview-control"></a>Testen des Steuerelements StackView  
 Die `StackView` Steuerelement abgeleitet wird, aus der <xref:System.Windows.Forms.UserControl> Klasse. Aus diesem Grund können Sie testen, das Steuerelement mit dem **UserControl-Testcontainer**. Weitere Informationen finden Sie unter [Vorgehensweise: Testen Sie das Laufzeitverhalten eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
#### <a name="to-test-the-stackview-control"></a>So testen Sie die StackView-Steuerelement  
  
1.  Drücken Sie F5, um das Projekt erstellen und starten Sie den **UserControl-Testcontainer**.  
  
2.  Bewegen Sie den Zeiger über die Schaltflächen des der `StackView` steuern, und klicken Sie dann auf eine Schaltfläche, um die Darstellung im ausgewählten Zustand anzuzeigen.  
  
## <a name="next-steps"></a>Nächste Schritte  
 In dieser exemplarischen Vorgehensweise haben Sie eine wiederverwendbare benutzerdefinierte Clientsteuerelement mit der professionelle Darstellung eines Steuerelements Office XP erstellt. Sie können die <xref:System.Windows.Forms.ToolStrip> -Steuerelementfamilie zu vielen anderen Zwecken:  
  
-   Erstellen von Kontextmenüs für Ihre Steuerelemente mit <xref:System.Windows.Forms.ContextMenuStrip>. Weitere Informationen finden Sie unter [Übersicht über die ContextMenu-Komponente](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Erstellen Sie ein Formular mit einem automatisch angegebenen Standardmenü. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).  
  
-   Erstellen Sie ein Formular für multiple Document Interface (MDI) mit andockbaren <xref:System.Windows.Forms.ToolStrip> Steuerelemente. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines MDI-Formulars mit das Zusammenführen von Menüs und ToolStrip-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [ToolStrip-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
- [Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)
