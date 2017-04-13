---
title: "Exemplarische Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements | Microsoft Docs"
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
  - "Symbolleisten [Windows Forms], Exemplarische Vorgehensweisen"
  - "ToolStrip-Steuerelement [Windows Forms], Erstellen von professionell gestalteten Steuerelementen"
  - "ToolStripProfessionalRenderer-Klasse [Windows Forms]"
  - "ToolStripRenderer-Klasse [Windows Forms]"
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Exemplarische Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements
Sie können den <xref:System.Windows.Forms.ToolStrip>\-Steuerelementen Ihrer Anwendung ein professionelles Aussehen und Verhalten verleihen, indem Sie eine eigene Klasse schreiben, die Sie vom <xref:System.Windows.Forms.ToolStripProfessionalRenderer>\-Typ ableiten.  
  
 In dieser exemplarischen Vorgehensweise wird gezeigt, wie mit <xref:System.Windows.Forms.ToolStrip>\-Steuerelementen ein zusammengesetztes Steuerelement erstellt wird, das dem **Navigationsbereich** von Microsoft® Outlook® ähnelt.  Die folgenden Aufgaben werden in dieser exemplarischen Vorgehensweise veranschaulicht:  
  
-   Erstellen eines Windows\-Steuerelementbibliothek\-Projekts  
  
-   Entwerfen des StackView\-Steuerelements  
  
-   Implementieren eines benutzerdefinierten Renderers  
  
 Nach Abschluss verfügen Sie über ein wiederverwendbares benutzerdefiniertes Clientsteuerelement mit dem professionellen Aussehen eines Microsoft Office® XP\-Steuerelements.  
  
 Informationen zum Kopieren des Codes in diesem Thema als einzelnes Codelisting finden Sie unter [Gewusst wie: Erstellen eines professionellen ToolStrip\-Steuerelements](../../../../docs/framework/winforms/controls/how-to-create-a-professionally-styled-toolstrip-control.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Vorbereitungsmaßnahmen  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Ausreichende Berechtigungen zum Erstellen und Ausführen von Windows Forms\-Anwendungsprojekten auf dem Computer, auf dem [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] installiert ist.  
  
## Erstellen eines Windows\-Steuerelementbibliothek\-Projekts  
 Der erste Schritt besteht darin, das Steuerelementbibliothek\-Projekt zu erstellen.  
  
#### So erstellen Sie das Steuerelementbibliothek\-Projekt  
  
1.  Erstellen Sie ein neues Windows\-Steuerelementbibliothek\-Projekt mit dem Namen `StackViewLibrary`.  
  
2.  Löschen Sie im **Projektmappen\-Explorer** das standardmäßige Steuerelement des Projekts, indem Sie je nach ausgewählter Programmiersprache die Quelldatei "UserControl1.cs" bzw. "UserControl1.vb" löschen.  
  
     Weitere Informationen finden Sie unter [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/de-de/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).  
  
3.  Fügen Sie dem Projekt **StackViewLibrary** ein neues <xref:System.Windows.Forms.UserControl>\-Element hinzu.  Weisen Sie der neuen Quelldatei den Basisnamen `StackView` zu.  
  
## Entwerfen des StackView\-Steuerelements  
 Das `StackView`\-Steuerelement ist ein zusammengesetztes Steuerelement mit einem untergeordneten <xref:System.Windows.Forms.ToolStrip>\-Steuerelement.  Weitere Informationen über zusammengesetzte Steuerelemente finden Sie unter [Arten von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md).  
  
#### So entwerfen Sie das StackView\-Steuerelement  
  
1.  Ziehen Sie von der **Toolbox** ein <xref:System.Windows.Forms.ToolStrip>\-Steuerelement auf die Entwurfsoberfläche.  
  
2.  Legen Sie im **Eigenschaftenfenster** die Eigenschaften des <xref:System.Windows.Forms.ToolStrip>\-Steuerelements entsprechend der folgenden Tabelle fest.  
  
    |Property|Wert|  
    |--------------|----------|  
    |Name|`stackStrip`|  
    |CanOverflow|`false`|  
    |Dock|<xref:System.Windows.Forms.DockStyle>|  
    |Schriftart|`Tahoma, 10pt, style=Bold`|  
    |GripStyle|<xref:System.Windows.Forms.ToolStripGripStyle>|  
    |LayoutStyle|<xref:System.Windows.Forms.ToolStripLayoutStyle>|  
    |Padding|`0, 7, 0, 0`|  
    |RenderMode|<xref:System.Windows.Forms.ToolStripRenderMode>|  
  
3.  Klicken Sie im Windows Forms\-Designer auf die Schaltfläche **Hinzufügen** des <xref:System.Windows.Forms.ToolStrip>\-Steuerelements, und fügen Sie dem `stackStrip`\-Steuerelement einen <xref:System.Windows.Forms.ToolStripButton> hinzu.  
  
4.  Legen Sie im **Eigenschaftenfenster** die Eigenschaften des <xref:System.Windows.Forms.ToolStripButton>\-Steuerelements entsprechend der folgenden Tabelle fest.  
  
    |Property|Wert|  
    |--------------|----------|  
    |Name|`mailStackButton`|  
    |CheckOnClick|true|  
    |CheckState|<xref:System.Windows.Forms.CheckState>|  
    |DisplayStyle|<xref:System.Windows.Forms.ToolStripItemDisplayStyle>|  
    |ImageAlign|<xref:System.Drawing.ContentAlignment>|  
    |ImageScaling|<xref:System.Windows.Forms.ToolStripItemImageScaling>|  
    |ImageTransparentColor|`238, 238, 238`|  
    |Margin|`0, 0, 0, 0`|  
    |Padding|`3, 3, 3, 3`|  
    |Text|E\-Mail|  
    |TextAlign|<xref:System.Drawing.ContentAlignment>|  
  
5.  Wiederholen Sie Schritt 7 für drei weitere <xref:System.Windows.Forms.ToolStripButton>\-Steuerelemente.  
  
     Nennen Sie die Steuerelemente `calendarStackButton`, `contactsStackButton` und `tasksStackButton`.  Legen Sie den Wert der <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft entsprechend auf Calendar, Contacts bzw. Tasks fest.  
  
## Behandeln von Ereignissen  
 Zwei Ereignisse sind wichtig, damit sich das `StackView`\-Steuerelement ordnungsgemäß verhält.  Behandeln Sie das <xref:System.Windows.Forms.UserControl.Load>\-Ereignis, um das Steuerelement ordnungsgemäß zu positionieren.  Behandeln Sie das <xref:System.Windows.Forms.ToolStripItem.Click>\-Ereignis für jeden <xref:System.Windows.Forms.ToolStripButton>, um dem `StackView`\-Steuerelement ein Statusverhalten zu verleihen, das dem des <xref:System.Windows.Forms.RadioButton>\-Steuerelements ähnelt.  
  
#### So behandeln Sie Ereignisse  
  
1.  Wählen Sie im Windows Forms\-Designer das `StackView`\-Steuerelement aus.  
  
2.  Klicken Sie im **Eigenschaftenfenster** auf **Ereignisse**.  
  
3.  Doppelklicken Sie auf das Load\-Ereignis, um den `StackView_Load`\-Ereignishandler zu generieren.  
  
4.  Kopieren Sie den folgenden Code, und fügen Sie ihn im `StackView_Load`\-Ereignishandler ein.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]  
  
5.  Wählen Sie im Windows Forms\-Designer das `mailStackButton`\-Steuerelement aus.  
  
6.  Klicken Sie im **Eigenschaftenfenster** auf **Ereignisse**.  
  
7.  Doppelklicken Sie auf das Click\-Ereignis.  
  
     Der `mailStackButton_Click`\-Ereignishandler wird vom Windows Forms\-Designer generiert.  
  
8.  Benennen Sie den `mailStackButton_Click`\-Ereignishandler in `stackButton_Click` um.  
  
     Weitere Informationen finden Sie unter [How to: Rename an Identifier \(Visual Basic\)](http://msdn.microsoft.com/de-de/e5a5edf8-3dba-4119-81f4-fc2aba180e0c).  
  
9. Fügen Sie den folgenden Code in den `stackButton_Click`\-Ereignishandler ein.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]  
  
10. Wählen Sie im Windows Forms\-Designer das `calendarStackButton`\-Steuerelement aus.  
  
11. Legen Sie im **Eigenschaftenfenster** das Click\-Ereignis auf den `stackButton_Click`\-Ereignishandler fest.  
  
12. Wiederholen Sie die Schritte 10 und 11 für das `contactsStackButton`\-Steuerelement und das `tasksStackButton`\-Steuerelement.  
  
## Definieren von Symbolen  
 Jede `StackView`\-Schaltfläche verfügt über ein zugeordnetes Symbol.  Zur Vereinfachung werden alle Symbole als Base64\-codierte Zeichenfolge dargestellt, die deserialisiert wird, bevor daraus eine <xref:System.Drawing.Bitmap> erstellt wird.  In einer Produktionsumgebung werden Bitmap\-Daten als Ressource gespeichert, und die Symbole werden im Windows Forms\-Designer angezeigt.  Weitere Informationen finden Sie unter [How to: Add Background Images to Windows Forms](http://msdn.microsoft.com/de-de/7a509ba2-055c-4ae6-b88a-54625c6d9aff).  
  
#### So definieren Sie Symbole  
  
1.  Fügen Sie im Code\-Editor den folgenden Code in die `StackView`\-Klassendefinition ein.  Durch diesen Code werden die Bitmaps für die <xref:System.Windows.Forms.ToolStripButton>\-Symbole initialisiert.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]  
  
2.  Fügen Sie im `StackView`\-Klassenkonstruktor der `InitializeImages`\-Methode einen Aufruf hinzu.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## Implementieren eines benutzerdefinierten Renderers  
 Die meisten Elemente des `StackView`\-Steuerelements können durch Implementieren einer Klasse angepasst werden, die von der <xref:System.Windows.Forms.ToolStripRenderer>\-Klasse abgeleitet wird.  Bei diesem Verfahren implementieren Sie eine <xref:System.Windows.Forms.ToolStripProfessionalRenderer>\-Klasse, die den Ziehpunkt anpasst und für die <xref:System.Windows.Forms.ToolStripButton>\-Steuerelemente Hintergründe mit Farbverlauf zeichnet.  
  
#### So erstellen Sie einen benutzerdefinierten Renderer  
  
1.  Fügen Sie den folgenden Code in die Definition des `StackView`\-Steuerelements ein.  
  
     Es handelt sich um die Definition für die `StackRenderer`\-Klasse, die die Methoden <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder> und <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> überschreibt, um eine benutzerdefinierte Darstellung zu erzeugen.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]  
  
2.  Erstellen Sie im Konstruktor des `StackView`\-Steuerelements eine neue Instanz der `StackRenderer`\-Klasse, und weisen Sie diese Instanz der <xref:System.Windows.Forms.ToolStrip.Renderer%2A>\-Eigenschaft des `stackStrip`\-Steuerelements zu.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## Testen des StackView\-Steuerelements  
 Das `StackView`\-Steuerelement wird von der <xref:System.Windows.Forms.UserControl>\-Klasse abgeleitet.  Daher können Sie das Steuerelement mit dem **UserControl\-Testcontainer** testen.  Weitere Informationen finden Sie unter [Gewusst wie: Testen des Laufzeitverhaltens eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
#### So testen Sie das StackView\-Steuerelement  
  
1.  Drücken Sie F5, um das Projekt zu erstellen und den **UserControl\-Testcontainer** zu starten.  
  
2.  Bewegen Sie den Mauszeiger über die Schaltflächen des `StackView`\-Steuerelements, und klicken Sie auf eine Schaltfläche, um die Darstellung im ausgewählten Zustand zu überprüfen.  
  
## Nächste Schritte  
 In dieser exemplarischen Vorgehensweise haben Sie ein wiederverwendbares benutzerdefiniertes Clientsteuerelement mit dem professionellen Aussehen eines Microsoft Office® XP\-Steuerelements erstellt.  Sie können die <xref:System.Windows.Forms.ToolStrip>\-Steuerelementfamilie für viele andere Zwecke verwenden:  
  
-   Erstellen von Kontextmenüs für die Steuerelemente mithilfe von <xref:System.Windows.Forms.ContextMenuStrip>.  Weitere Informationen finden Sie unter [Übersicht über die ContextMenu\-Komponente](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Erstellen von Formularen mit einem automatisch gefüllten Standardmenü.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).  
  
-   Erstellen eines MDI \(Multiple Document Interface\-\)Formulars mit andockbaren <xref:System.Windows.Forms.ToolStrip>\-Steuerelementen.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen eines MDI\-Formulars mit der Zusammenführungsfunktion für Menüs und ToolStrip\-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 [ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)   
 [Gewusst wie: Bereitstellen von Standardmenüelementen für ein Formular](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)