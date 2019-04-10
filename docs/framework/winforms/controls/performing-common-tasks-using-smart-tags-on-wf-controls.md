---
title: 'Exemplarische Vorgehensweise: Ausführen von häufigen Aufgaben mit Smarttags für Windows Forms-Steuerelemente'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: a93402be30cb461ac6a0ed9daa4a684598a85da1
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318246"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a>Exemplarische Vorgehensweise: Ausführen von häufigen Aufgaben mit Smarttags für Windows Forms-Steuerelemente
Wie Sie Formulare und Steuerelemente für die Windows Forms-Anwendung erstellen, gibt es viele Aufgaben, die Sie wiederholt ausführen. Dies sind einige der häufig ausgeführten Aufgaben, die auftreten:  
  
-   Hinzufügen oder Entfernen einer Registerkarte auf eine <xref:System.Windows.Forms.TabControl>.  
  
-   Andocken eines Steuerelements zu seinem übergeordneten Element.  
  
-   Ändern der Ausrichtung einer <xref:System.Windows.Forms.SplitContainer> Steuerelement.  
  
 Um die Entwicklung zu beschleunigen, bieten viele Steuerelemente Smarttags, Kontextmenüs, die Ihnen ermöglichen, allgemeine Aufgaben wie das in einer einzigen Geste zur Entwurfszeit auszuführen. Diese Aufgaben heißen *Smarttag-Verben*.  
  
 Smarttags bleiben, dessen Lebensdauer im Designer eine Steuerelementinstanz zugeordnet und stehen immer zur Verfügung.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen eines Windows Forms-Projekts  
  
-   Mithilfe von Smarttags  
  
-   Aktivieren und Deaktivieren von Smarttags  
  
 Wenn Sie diese Aufgaben durchgearbeitet haben, besitzen Sie ein Verständnis für die Rolle, die diese wichtigen Layoutfunktionen spielen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.  
  
#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
1. Erstellen Sie eine Windows-basiertes Anwendungsprojekt mit dem Namen "SmartTagsExample" (**Datei** > **neu** > **Projekt**  >   **Visual C#-** oder **Visual Basic** > **Klassischer Desktop** > **Windows Forms-Anwendung**).  
  
2. Wählen Sie das Formular in der **Windows Forms-Designer**.  
  
## <a name="using-smart-tags"></a>Mithilfe von Smarttags  
 Smarttags sind zur Entwurfszeit auf Steuerelemente, bei denen sie immer verfügbar.  
  
#### <a name="to-use-smart-tags"></a>Verwenden von Smarttags  
  
1. Ziehen Sie eine <xref:System.Windows.Forms.TabControl> aus der **Toolbox** auf das Formular. Beachten Sie die Smarttag-Glyphe (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), die angezeigt wird, auf der Seite des der <xref:System.Windows.Forms.TabControl>.  
  
2. Klicken Sie auf das Smarttag-Symbol. Wählen Sie das Kontextmenü, das neben dem Symbol angezeigt wird, die **Registerkarte hinzufügen** Element. Beachten Sie, dass eine neue Registerkarte hinzugefügt wird die <xref:System.Windows.Forms.TabControl>.  
  
3. Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.  
  
4. Klicken Sie auf das Smarttag-Symbol. Wählen Sie das Kontextmenü, das neben dem Symbol angezeigt wird, die **Add Column** Element. Beachten Sie, dass eine neue Spalte hinzugefügt wird die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.  
  
5. Ziehen Sie ein <xref:System.Windows.Forms.SplitContainer> -Steuerelement aus der **Toolbox** auf das Formular.  
  
6. Klicken Sie auf das Smarttag-Symbol. Wählen Sie das Kontextmenü, das neben dem Symbol angezeigt wird, die **horizontale teilerausrichtung** Element. Beachten Sie, dass die <xref:System.Windows.Forms.SplitContainer> Teilerleiste des Steuerelements ist jetzt horizontal ausgerichtet.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
- [Exemplarische Vorgehensweise: Hinzufügen von Smarttags zu einer Komponente in Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))
