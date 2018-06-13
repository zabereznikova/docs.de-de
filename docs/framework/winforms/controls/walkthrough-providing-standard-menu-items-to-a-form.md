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
ms.openlocfilehash: c0e3a9471afd05ec0e07e8d8a71ffd76c91ec14d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541485"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a>Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular
Mit dem <xref:System.Windows.Forms.MenuStrip>-Steuerelement können Sie ein Standardmenü für Formulare bereitstellen.  
  
 Diese exemplarische Vorgehensweise veranschaulicht, wie ein <xref:System.Windows.Forms.MenuStrip> Steuerelement ein Standardmenü erstellt. Das Formular reagiert auch auf, wenn ein Benutzer ein Menüelement auswählt. In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:  
  
-   Erstellen ein Windows Forms-Projekt.  
  
-   Erstellen ein Standardmenü.  
  
-   Erstellen einer <xref:System.Windows.Forms.StatusStrip> Steuerelement.  
  
-   Behandlung von Menüauswahl-Element.  
  
 Wenn Sie fertig sind, haben Sie ein Formular mit Standardmenü, die Menüelementauswahlen in zeigt ein <xref:System.Windows.Forms.StatusStrip> Steuerelement.  
  
 Um den Code in diesem Thema als einzelne Auflistung kopieren zu können, finden Sie unter [Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Ausreichende Berechtigungen zum Erstellen und Ausführen von Windows Forms-Anwendungsprojekten auf dem Computer, auf dem Visual Studio installiert ist.  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.  
  
#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
1.  Erstellen Sie ein Windows-Anwendungsprojekt namens **StandardMenuForm**.  
  
     Weitere Informationen finden Sie unter [How to: Create a Windows Application Project (Vorgehensweise: Erstellen eines neuen Windows Forms-Anwendungsprojekts)](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Wählen Sie in der Windows Forms-Designer das Formular aus.  
  
## <a name="creating-a-standard-menu"></a>Erstellen ein Standardmenü  
 Windows Forms-Designer automatisch Auffüllen einer <xref:System.Windows.Forms.MenuStrip> -Steuerelement mit Standardmenüelementen.  
  
#### <a name="to-create-a-standard-menu"></a>So erstellen Sie ein Standardmenü  
  
1.  Aus der **Toolbox**, ziehen Sie ein <xref:System.Windows.Forms.MenuStrip> Steuerelement auf das Formular.  
  
2.  Klicken Sie auf die <xref:System.Windows.Forms.MenuStrip> des Steuerelements Smarttag-Glyphe (![Smart Tag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), und wählen Sie **Standardelemente einfügen**.  
  
     Die <xref:System.Windows.Forms.MenuStrip> Steuerelement mit der Standardmenüelementen gefüllt wird.  
  
3.  Klicken Sie auf die **Datei** Menüelement, um die Standard-Menüelemente und entsprechende Symbole anzuzeigen.  
  
## <a name="creating-a-statusstrip-control"></a>Erstellen ein StatusStrip-Steuerelement  
 Verwenden der <xref:System.Windows.Forms.StatusStrip> -Steuerelement zum Anzeigen des Status für Windows Forms-Anwendungen. Im aktuellen Beispiel Menüelemente, die vom Benutzer ausgewählten angezeigt werden, einem <xref:System.Windows.Forms.StatusStrip> Steuerelement.  
  
#### <a name="to-create-a-statusstrip-control"></a>So erstellen ein StatusStrip-Steuerelement  
  
1.  Aus der **Toolbox**, ziehen Sie ein <xref:System.Windows.Forms.StatusStrip> Steuerelement auf das Formular.  
  
     Die <xref:System.Windows.Forms.StatusStrip> Steuerelement wird automatisch an das Ende des Formulars angedockt.  
  
2.  Klicken Sie auf die <xref:System.Windows.Forms.StatusStrip> des Steuerelements Dropdown-Schaltfläche und wählen Sie **StatusLabel** Hinzufügen einer <xref:System.Windows.Forms.ToolStripStatusLabel> die Steuerung an die <xref:System.Windows.Forms.StatusStrip> Steuerelement.  
  
## <a name="handling-item-selection"></a>Behandlung Elementauswahl  
 Behandeln der <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> Ereignis reagiert, wenn der Benutzer ein Menüelement auswählt.  
  
#### <a name="to-handle-item-selection"></a>Elementauswahl behandeln  
  
1.  Klicken Sie auf die **Datei** Menüelement, das Sie in der erstellen erstellt ein Standardmenü-Abschnitt.  
  
2.  In der **Eigenschaften** Fenster, klicken Sie auf **Ereignisse**.  
  
3.  Doppelklicken Sie auf die <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> Ereignis.  
  
     Windows Forms-Designer wird ein Ereignishandler für das <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> Ereignis.  
  
4.  Fügen Sie den folgenden Code in den Ereignishandler an.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5.  Fügen Sie der `UpdateStatus` Hilfsprogramm Methodendefinition in das Formular.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## <a name="checkpoint"></a>Checkpoint  
  
#### <a name="to-test-your-form"></a>So testen Sie das Formular  
  
1.  Drücken Sie F5, um zu kompilieren und führen das Formular aus.  
  
2.  Klicken Sie auf die **Datei** Menüelement, um das Menü zu öffnen.  
  
3.  Auf der **Datei** Menü klicken Sie auf eines der Elemente, um ihn auszuwählen.  
  
     Die <xref:System.Windows.Forms.StatusStrip> -Steuerelement zeigt das ausgewählte Element.  
  
## <a name="next-steps"></a>Nächste Schritte  
 In dieser exemplarischen Vorgehensweise haben Sie ein Formular mit Standardmenü erstellt. Sie können die <xref:System.Windows.Forms.ToolStrip> -Steuerelementfamilie zu vielen anderen Zwecken:  
  
-   Erstellen von Kontextmenüs für die Steuerelemente mit <xref:System.Windows.Forms.ContextMenuStrip>. Weitere Informationen finden Sie unter [Übersicht über die ContextMenu-Komponente](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Erstellen Sie ein Formular der multiple Document Interface (MDI) mit andockbaren <xref:System.Windows.Forms.ToolStrip> Steuerelemente. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit das Zusammenführen von Menüs und ToolStrip-Steuerelementen](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
-   Geben Sie Ihre <xref:System.Windows.Forms.ToolStrip> steuert ein professionelles Aussehen. Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen des ToolStrip-Renderers für eine Anwendung](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [MenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
