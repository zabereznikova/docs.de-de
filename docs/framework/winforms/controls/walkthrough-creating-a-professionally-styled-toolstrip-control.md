---
title: 'Exemplarische Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements'
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
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 18ffb09e581b830329a0d32f11ae09d8b0f68788
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a>Exemplarische Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements
Sie können angeben, kann Ihre Anwendung <xref:System.Windows.Forms.ToolStrip> steuert ein professionelles Aussehen und Verhalten durch Schreiben einer eigenen Klasse abgeleitet wurde. die <xref:System.Windows.Forms.ToolStripProfessionalRenderer> Typ.  
  
 Diese exemplarische Vorgehensweise veranschaulicht, wie <xref:System.Windows.Forms.ToolStrip> Steuerelemente zum Erstellen eines zusammengesetzten Steuerelements, das ähnelt der **Navigationsbereich** von Microsoft® Outlook® bereitgestellten. In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:  
  
-   Erstellen eines Windows-Steuerelementbibliothek-Projekts.  
  
-   Entwerfen des StackView-Steuerelements an.  
  
-   Implementieren eines benutzerdefinierten Renderers.  
  
 Wenn Sie fertig sind, müssen Sie ein wiederverwendbare benutzerdefinierte Clientsteuerelement mit professionelle Darstellung eines Microsoft Office® XP-Steuerelements.  
  
 Um den Code in diesem Thema als einzelne Auflistung kopieren zu können, finden Sie unter [Vorgehensweise: Erstellen einer professionellen ToolStrip-Steuerelements](../../../../docs/framework/winforms/controls/how-to-create-a-professionally-styled-toolstrip-control.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Ausreichende Berechtigungen zum Erstellen und Ausführen von Windows Forms-Anwendungsprojekten auf dem Computer, auf dem Visual Studio installiert ist.  
  
## <a name="creating-a-windows-control-library-project"></a>Erstellen eine Windows-Steuerelementbibliothek-Projekt  
 Der erste Schritt besteht darin-Steuerelementbibliothek-Projekt zu erstellen.  
  
#### <a name="to-create-the-control-library-project"></a>-Steuerelementbibliothek-Projekt erstellen  
  
1.  Erstellen Sie ein neues Windows-Steuerelementbibliothek-Projekt namens `StackViewLibrary`.  
  
2.  In **Projektmappen-Explorer**, Standardsteuerelement für das Projekt löschen, indem Sie die Quelldatei mit dem Namen "UserControl1.cs" oder "UserControl1.vb", abhängig von einer Sprache Ihrer Wahl zu löschen.  
  
     Weitere Informationen finden Sie unter [NIB: Vorgehensweise: entfernen, löschen und Ausschließen von Elementen](http://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).  
  
3.  Fügen Sie einen neuen <xref:System.Windows.Forms.UserControl> Element an der **StackViewLibrary** Projekt. Benennen Sie die neue Quelldatei Basis von `StackView`.  
  
## <a name="designing-the-stackview-control"></a>Entwerfen des StackView-Steuerelements  
 Die `StackView` Steuerelement ist ein zusammengesetztes Steuerelement mit einem untergeordneten <xref:System.Windows.Forms.ToolStrip> Steuerelement. Weitere Informationen über zusammengesetzte Steuerelemente finden Sie unter [Varianten von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md).  
  
#### <a name="to-design-the-stackview-control"></a>So entwerfen Sie das StackView-Steuerelement  
  
1.  Aus der **Toolbox**, ziehen Sie ein <xref:System.Windows.Forms.ToolStrip> Steuerelement auf die Entwurfsoberfläche.  
  
2.  In der **Eigenschaften** legen die <xref:System.Windows.Forms.ToolStrip> Eigenschaften des Steuerelements gemäß der folgenden Tabelle.  
  
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
  
3.  In Windows Forms-Designer, klicken Sie auf die <xref:System.Windows.Forms.ToolStrip> des Steuerelements **hinzufügen** Schaltfläche und Hinzufügen einer <xref:System.Windows.Forms.ToolStripButton> auf die `stackStrip` Steuerelement.  
  
4.  In der **Eigenschaften** legen die <xref:System.Windows.Forms.ToolStripButton> Eigenschaften des Steuerelements gemäß der folgenden Tabelle.  
  
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
  
     Benennen Sie die Steuerelemente `calendarStackButton`, `contactsStackButton`, und `tasksStackButton`. Legen Sie den Wert von der <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft **Kalender**, **Kontakte**, und **Aufgaben**bzw.  
  
## <a name="handling-events"></a>Behandeln von Ereignissen  
 Zwei Ereignisse sind wichtig, damit die `StackView` -Steuerelement ordnungsgemäß verhält. Behandeln der <xref:System.Windows.Forms.UserControl.Load> Ereignis, um das Steuerelement ordnungsgemäß zu positionieren. Behandeln der <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis für jedes <xref:System.Windows.Forms.ToolStripButton> so erteilen Sie die `StackView` Zustand Verhalten ähnelt steuern die <xref:System.Windows.Forms.RadioButton> Steuerelement.  
  
#### <a name="to-handle-events"></a>Um Ereignisse zu behandeln.  
  
1.  Wählen Sie in der Windows Forms-Designer die `StackView` Steuerelement.  
  
2.  In der **Eigenschaften** Fenster, klicken Sie auf **Ereignisse**.  
  
3.  Doppelklicken Sie auf das Load-Ereignis zum Generieren der `StackView_Load` -Ereignishandler.  
  
4.  Kopieren Sie den folgenden Code und fügen Sie ihn in den `StackView_Load`-Ereignishandler ein.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]  
  
5.  Wählen Sie in der Windows Forms-Designer die `mailStackButton` Steuerelement.  
  
6.  In der **Eigenschaften** Fenster, klicken Sie auf **Ereignisse**.  
  
7.  Doppelklicken Sie auf das Click-Ereignis.  
  
     Windows Forms-Designer generiert die `mailStackButton_Click` -Ereignishandler.  
  
8.  Benennen Sie die `mailStackButton_Click` Ereignishandler `stackButton_Click`.  
  
     Weitere Informationen finden Sie unter [Vorgehensweise: Umbenennen von Bezeichnern (Visual Basic)](http://msdn.microsoft.com/library/e5a5edf8-3dba-4119-81f4-fc2aba180e0c).  
  
9. Fügen Sie den folgenden Code in der `stackButton_Click` -Ereignishandler.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]  
  
10. Wählen Sie in der Windows Forms-Designer die `calendarStackButton` Steuerelement.  
  
11. In der **Eigenschaften** legen das Click-Ereignis das `stackButton_Click` -Ereignishandler.  
  
12. Wiederholen Sie die Schritte 10 und 11 für den `contactsStackButton` und `tasksStackButton` Steuerelemente.  
  
## <a name="defining-icons"></a>Definieren von Symbolen  
 Jede `StackView` Schaltfläche verfügt über ein zugeordnetes Symbol. Der Einfachheit halber jedes Symbol wird dargestellt als Base64-codierte Zeichenfolge, die deserialisiert wird, bevor Sie eine <xref:System.Drawing.Bitmap> daraus erstellt wird. In einer produktionsumgebung Bitmapdaten als Ressourcen gespeichert, und die Symbole in Windows Forms-Designer angezeigt. Weitere Informationen finden Sie unter [wie: Hinzufügen von Hintergrundbildern zu Windows Forms](http://msdn.microsoft.com/library/7a509ba2-055c-4ae6-b88a-54625c6d9aff).  
  
#### <a name="to-define-icons"></a>So definieren Sie Symbole  
  
1.  Fügen Sie im Code-Editor den folgenden Code in die `StackView` Klassendefinition. Dieser Code initialisiert die Bitmaps für die <xref:System.Windows.Forms.ToolStripButton> Symbole.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]  
  
2.  Fügen Sie einen Aufruf an die `InitializeImages` Methode in der `StackView` Klassenkonstruktor.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="implementing-a-custom-renderer"></a>Implementieren eines benutzerdefinierten Renderers  
 Sie können die meisten Elemente der Anpassen der `StackView` steuern, implementieren eine Klasse, abgeleitet wird, die <xref:System.Windows.Forms.ToolStripRenderer> Klasse. In diesem Verfahren implementieren Sie eine <xref:System.Windows.Forms.ToolStripProfessionalRenderer> -Klasse, die den Ziehpunkt anpasst und für Farbverlauf Hintergründe zeichnet die <xref:System.Windows.Forms.ToolStripButton> Steuerelemente.  
  
#### <a name="to-implement-a-custom-renderer"></a>Implementieren ein benutzerdefiniertes Renderers  
  
1.  Fügen Sie den folgenden Code in die `StackView` Definition zu steuern.  
  
     Dies ist die Definition für die `StackRenderer` Klasse, welche Außerkraftsetzungen der <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, und <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> Methoden, um eine benutzerdefinierte Darstellung zu erzeugen.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]  
  
2.  In der `StackView` Konstruktor des Steuerelements, erstellen Sie eine neue Instanz der dem `StackRenderer` Klasse, und weisen Sie diese Instanz mit der `stackStrip` des Steuerelements <xref:System.Windows.Forms.ToolStrip.Renderer%2A> Eigenschaft.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="testing-the-stackview-control"></a>Testen des StackView-Steuerelements  
 Die `StackView` Steuerelement leitet sich von der <xref:System.Windows.Forms.UserControl> Klasse. Aus diesem Grund können Sie das Steuerelement mit dem Testen der **UserControl-Testcontainer**. Weitere Informationen finden Sie unter [Vorgehensweise: Testen des Laufzeitverhaltens eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
#### <a name="to-test-the-stackview-control"></a>So testen Sie das StackView-Steuerelement  
  
1.  Drücken Sie F5, um das Projekt erstellen und starten Sie die **UserControl-Testcontainer**.  
  
2.  Bewegen Sie den Zeiger über die Schaltflächen des der `StackView` steuern, und klicken Sie dann auf eine Schaltfläche, um die Darstellung des ausgewählten Zustand anzuzeigen.  
  
## <a name="next-steps"></a>Nächste Schritte  
 In dieser exemplarischen Vorgehensweise haben Sie ein wiederverwendbare benutzerdefinierte Clientsteuerelement mit professionelle Darstellung eines Steuerelements Office XP erstellt. Sie können die <xref:System.Windows.Forms.ToolStrip> -Steuerelementfamilie zu vielen anderen Zwecken:  
  
-   Erstellen von Kontextmenüs für die Steuerelemente mit <xref:System.Windows.Forms.ContextMenuStrip>. Weitere Informationen finden Sie unter [Übersicht über die ContextMenu-Komponente](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Erstellen Sie ein Formular mit einem automatisch gefüllten Standardmenü. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).  
  
-   Erstellen Sie ein Formular der multiple Document Interface (MDI) mit andockbaren <xref:System.Windows.Forms.ToolStrip> Steuerelemente. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines MDI-Formulars mit das Zusammenführen von Menüs und ToolStrip-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [ToolStrip-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)
