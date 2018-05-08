---
title: 'Exemplarische Vorgehensweise: Ausführen von häufigen Aufgaben mit Smarttags auf Windows Forms-Steuerelementen'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: a558f6d274f260fc91fd140e9dae2c740b1ae00d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a>Exemplarische Vorgehensweise: Ausführen von häufigen Aufgaben mit Smarttags auf Windows Forms-Steuerelementen
Wie Sie Formulare und Steuerelemente für Windows Forms-Anwendung erstellen, sind viele Aufgaben, die wiederholt ausgeführt werden. Dies sind einige der häufig ausgeführten Aufgaben, die auftreten können:  
  
-   Hinzufügen oder Entfernen einer Registerkarte auf eine <xref:System.Windows.Forms.TabControl>.  
  
-   Andocken eines Steuerelements an seinem übergeordneten Element.  
  
-   Ändern der Ausrichtung eines ein <xref:System.Windows.Forms.SplitContainer> Steuerelement.  
  
 Zum Beschleunigen der Entwicklung bieten viele Steuerelemente Smarttags kontextbezogene Menüs sind, mit die häufige Aufgaben wie diese in eine einzelne Geste zur Entwurfszeit ausführen kann. Diese Aufgaben heißen *Smarttag-Verben*.  
  
 Smarttags für seine Lebensdauer im Designer mit einer Instanz des Steuerelements verbunden bleiben und sind immer verfügbar.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen eines Windows Forms-Projekts  
  
-   Mithilfe der Smarttags  
  
-   Aktivieren und Deaktivieren von Smarttags  
  
 Wenn Sie diese Aufgaben durchgearbeitet haben, besitzen Sie ein Verständnis für die Rolle, die diese wichtigen Layoutfunktionen spielen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.  
  
#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
1.  Erstellen Sie ein Windows-basierten Anwendung mit dem Namen "SmartTagsExample". Weitere Informationen finden Sie unter [How to: Create a Windows Application Project (Vorgehensweise: Erstellen eines neuen Windows Forms-Anwendungsprojekts)](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Wählen Sie das Formular in der **Windows Forms-Designer**.  
  
## <a name="using-smart-tags"></a>Mithilfe der Smarttags  
 Smarttags sind zur Entwurfszeit auf Steuerelemente, die sie bieten immer verfügbar.  
  
#### <a name="to-use-smart-tags"></a>Verwendung von smart tags  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.TabControl> aus der **Toolbox** auf das Formular. Beachten Sie das Smarttag-Symbol (![Smart Tag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), die angezeigt wird, auf der Seite des der <xref:System.Windows.Forms.TabControl>.  
  
2.  Klicken Sie auf das Smarttag-Symbol. Wählen Sie im Kontextmenü, das neben dem Symbol angezeigt wird, die **Registerkarte hinzufügen** Element. Beachten Sie, dass eine neue Registerkarte hinzugefügt wird die <xref:System.Windows.Forms.TabControl>.  
  
3.  Ziehen Sie eine <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.  
  
4.  Klicken Sie auf das Smarttag-Symbol. Wählen Sie im Kontextmenü, das neben dem Symbol angezeigt wird, die **Add Column** Element. Beachten Sie, dass eine neue Spalte hinzugefügt wird die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.  
  
5.  Ziehen Sie eine <xref:System.Windows.Forms.SplitContainer> -Steuerelement aus der **Toolbox** auf das Formular.  
  
6.  Klicken Sie auf das Smarttag-Symbol. Wählen Sie im Kontextmenü, das neben dem Symbol angezeigt wird, die **horizontale aufteilungsausrichtung** Element. Beachten Sie, dass die <xref:System.Windows.Forms.SplitContainer> des Steuerelements Teilerleiste ist jetzt horizontal ausgerichtet.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.TextBox>  
 <xref:System.Windows.Forms.TabControl>  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.ComponentModel.Design.DesignerActionList>  
 [Exemplarische Vorgehensweise: Hinzufügen von Smarttags in eine Komponente für Windows Forms](http://msdn.microsoft.com/library/a6814169-fa7d-4527-808c-637ca5c95f63)
