---
title: 'Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
ms.openlocfilehash: f9e54ecd49fc3bd295f236292715393358bab0b7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094878"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a>Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular
Mit dem <xref:System.Windows.Forms.MenuStrip>-Steuerelement können Sie ein Standardmenü für Formulare bereitstellen.  
  
 In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie mit einem <xref:System.Windows.Forms.MenuStrip> Steuerelement an ein Standardmenü zu erstellen. Das Formular reagiert auch auf, wenn ein Benutzer ein Menüelement auswählt. Die folgenden Aufgaben werden in dieser exemplarischen Vorgehensweise veranschaulicht:  
  
-   Erstellen ein Windows Forms-Projekt.  
  
-   Erstellen ein Standardmenü.  
  
-   Erstellen einer <xref:System.Windows.Forms.StatusStrip> Steuerelement.  
  
-   Behandeln von Menüauswahl-Element.  
  
 Wenn Sie fertig sind, haben Sie ein Formular mit Standardmenü, die die Auswahl von Menüelementen in zeigt eine <xref:System.Windows.Forms.StatusStrip> Steuerelement.  
  
 Zum Kopieren des Codes in diesem Thema als einzelne Auflistung lesen Sie [Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](how-to-provide-standard-menu-items-to-a-form.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Vorraussetzungen  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Berechtigt sind, können zum Erstellen und Ausführen von Windows Forms-Anwendungsprojekten auf dem Computer, auf dem Visual Studio installiert ist.  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.  
  
#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
1.  Erstellen Sie ein Windows-Anwendungsprojekt namens **StandardMenuForm** (**Datei** > **neu** > **Projekt**  >  **Visual C#-** oder **Visual Basic** > **Klassischer Desktop** > **Windows Forms Anwendung**).  
  
2.  Wählen Sie im Windows Forms-Designer das Formular aus.  
  
## <a name="creating-a-standard-menu"></a>Erstellen ein Standardmenü  
 Der Windows Forms-Designer können automatisch Auffüllen einer <xref:System.Windows.Forms.MenuStrip> -Steuerelement mit Standardmenüelementen.  
  
#### <a name="to-create-a-standard-menu"></a>So erstellen Sie ein Standardmenü  
  
1.  Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.MenuStrip> Steuerelement auf das Formular.  
  
2.  Klicken Sie auf die <xref:System.Windows.Forms.MenuStrip> des Steuerelements Smarttag-Glyphe (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), und wählen Sie **Standardelemente einfügen**.  
  
     Die <xref:System.Windows.Forms.MenuStrip> Steuerelement mit Standardmenüelemente gefüllt wird.  
  
3.  Klicken Sie auf die **Datei** Menüelement, um die Standard-Menüelemente und entsprechende Symbole anzuzeigen.  
  
## <a name="creating-a-statusstrip-control"></a>Erstellen eine StatusStrip-Steuerelement  
 Verwenden der <xref:System.Windows.Forms.StatusStrip> -Steuerelement zum Anzeigen des Status Ihrer Windows Forms-Anwendungen. Im aktuellen Beispiel-Menüelemente, die vom Benutzer ausgewählten werden angezeigt, einem <xref:System.Windows.Forms.StatusStrip> Steuerelement.  
  
#### <a name="to-create-a-statusstrip-control"></a>So erstellen Sie eine StatusStrip-Steuerelement  
  
1.  Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.StatusStrip> Steuerelement auf das Formular.  
  
     Die <xref:System.Windows.Forms.StatusStrip> Steuerelement wird automatisch am unteren Rand des Formulars angedockt.  
  
2.  Klicken Sie auf die <xref:System.Windows.Forms.StatusStrip> Dropdown-Schaltfläche des Steuerelements, und wählen **StatusLabel** Hinzufügen einer <xref:System.Windows.Forms.ToolStripStatusLabel> die Steuerung an die <xref:System.Windows.Forms.StatusStrip> Steuerelement.  
  
## <a name="handling-item-selection"></a>Behandlung von Elementauswahl  
 Behandeln der <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> Ereignis reagieren, wenn der Benutzer ein Menüelement auswählt.  
  
#### <a name="to-handle-item-selection"></a>Behandeln von Elementauswahl  
  
1.  Klicken Sie auf die **Datei** Menüelement, das Sie in der erstellen erstellt ein Standardmenü-Abschnitt.  
  
2.  Klicken Sie im Fenster **Eigenschaften** auf **Ereignisse**.  
  
3.  Doppelklicken Sie auf die <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> Ereignis.  
  
     Der Windows Forms-Designer wird ein Ereignishandler für die <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> Ereignis.  
  
4.  Fügen Sie den folgenden Code in den Ereignishandler an.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5.  Fügen Sie der `UpdateStatus` Definition des Hilfsprogramm-Methode in das Formular.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## <a name="checkpoint"></a>Checkpoint  
  
#### <a name="to-test-your-form"></a>So testen Sie das Formular  
  
1.  Drücken Sie F5, um Sie zu kompilieren und führen das Formular aus.  
  
2.  Klicken Sie auf die **Datei** Menüelement, um das Menü zu öffnen.  
  
3.  Auf der **Datei** Menü klicken Sie auf eines der Elemente, um es auszuwählen.  
  
     Die <xref:System.Windows.Forms.StatusStrip> Steuerelement zeigt das ausgewählte Element.  
  
## <a name="next-steps"></a>Nächste Schritte  
 In dieser exemplarischen Vorgehensweise haben Sie ein Formular mit Standardmenü erstellt. Sie können die <xref:System.Windows.Forms.ToolStrip> -Steuerelementfamilie zu vielen anderen Zwecken:  
  
-   Erstellen von Kontextmenüs für Ihre Steuerelemente mit <xref:System.Windows.Forms.ContextMenuStrip>. Weitere Informationen finden Sie unter [Übersicht über die ContextMenu-Komponente](contextmenu-component-overview-windows-forms.md).  
  
-   Erstellen Sie ein Formular für multiple Document Interface (MDI) mit andockbaren <xref:System.Windows.Forms.ToolStrip> Steuerelemente. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit das Zusammenführen von Menüs und ToolStrip-Steuerelemente](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
-   Geben Sie Ihre <xref:System.Windows.Forms.ToolStrip> steuert, ein professionelles Aussehen. Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen des ToolStrip-Renderers für eine Anwendung](how-to-set-the-toolstrip-renderer-for-an-application.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [MenuStrip-Steuerelement](menustrip-control-windows-forms.md)
