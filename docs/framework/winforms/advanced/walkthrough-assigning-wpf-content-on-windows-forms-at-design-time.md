---
title: 'Exemplarische Vorgehensweise: Zuweisen von WPF-Inhalt in Windows Forms zur Entwurfszeit'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
ms.openlocfilehash: 781eaaabb7306018366450c013c227fe5a1fef78
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108679"
---
# <a name="walkthrough-assigning-wpf-content-on-windows-forms-at-design-time"></a>Exemplarische Vorgehensweise: Zuweisen von WPF-Inhalt in Windows Forms zur Entwurfszeit
In dieser exemplarischen Vorgehensweise wird gezeigt, wie die WPF-Steuerelementtypen (Windows Presentation Foundation) ausgewählt werden, die im Formular angezeigt werden sollen. Sie können alle WPF-Steuerelementtypen auswählen, die im Projekt enthalten sind.

 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:

-   Erstellen des Projekts.

-   Erstellen der WPF-Steuerelementtypen.

-   Auswählen der WPF-Steuerelemente.

> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Vorraussetzungen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   Visual Studio 2012.  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Zunächst muss das Windows Forms-Projekt erstellt werden.  
  
> [!NOTE]
>  Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.  
  
#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
-   Erstellen Sie ein neues Windows Forms-Anwendungsprojekt in Visual Basic oder Visual c# mit dem Namen `SelectingWpfContent`.  
  
## <a name="creating-the-wpf-control-types"></a>Erstellen der WPF-Steuerelementtypen  
 Nachdem Sie dem Projekt WPF-Steuerelementtypen hinzugefügt haben, können Sie diese in verschiedenen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelementen hosten.  
  
#### <a name="to-create-wpf-control-types"></a>So erstellen Sie WPF-Steuerelementtypen  
  
1.  Fügen Sie der Projektmappe ein neues WPF-<xref:System.Windows.Controls.UserControl>-Projekt hinzu. Verwenden Sie den Standardnamen, `UserControl1.xaml`, für den Steuerelementtyp. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen von neuen WPF-Inhalts in Windows Forms zur Entwurfszeit](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist. Weitere Informationen finden Sie unter [Vorgehensweise: Wählen Sie aus, und verschieben Sie Elemente auf der Entwurfsoberfläche](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).  
  
3.  In der **Eigenschaften** legen den Wert des der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften `200`.  
  
4.  Hinzufügen einer <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> die Steuerung an die <xref:System.Windows.Controls.UserControl> und legen Sie den Wert von der <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft **gehosteten Inhalt**.  
  
5.  Fügen Sie dem Projekt ein zweites WPF-<xref:System.Windows.Controls.UserControl> hinzu. Verwenden Sie den Standardnamen, `UserControl2.xaml`, für den Steuerelementtyp.  
  
6.  In der **Eigenschaften** legen den Wert des der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften `200`.  
  
7.  Hinzufügen einer <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> die Steuerung an die <xref:System.Windows.Controls.UserControl> und legen Sie den Wert von der <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft **Hosted Content 2**.  
  
 **Beachten Sie** im Allgemeinen sollten Sie anspruchsvolleren WPF-Inhalt hosten. 
  <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>-Steuerelement wird hier nur zur Veranschaulichung verwendet.   
  
1.  Erstellen Sie das Projekt.  
  
## <a name="selecting-wpf-controls"></a>Auswählen von WPF-Steuerelementen  
 Sie können einem <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement, das bereits Inhalte hostet, verschiedene WPF-Inhalte zuweisen.  
  
#### <a name="to-select-wpf-controls"></a>So wählen Sie WPF-Steuerelemente aus  
  
1.  Öffnen Sie `Form1` im Windows Forms-Designer.  
  
2.  In der **Toolbox**, doppelklicken Sie auf `UserControl1` zum Erstellen einer Instanz von `UserControl1` auf dem Formular.  
  
     Eine Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.  
  
3.  Der Smarttagbereich für `elementHost1`öffnen die **gehosteten Inhalt auswählen** Dropdown-Liste.  
  
4.  Wählen Sie **UserControl2** aus dem Dropdown-Listenfeld.  
  
     Das `elementHost1`-Steuerelement hostet jetzt eine Instanz des `UserControl2`-Typs.  
  
5.  In der **Eigenschaften** Fenster, überprüfen Sie, ob die <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> -Eigenschaftensatz auf **UserControl2**.  
  
6.  Von der **Toolbox**in die **WPF-Interoperabilität** gruppieren, ziehen Sie ein <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement auf das Formular.  
  
     Der Standardname für das neue Steuerelement ist `elementHost2`.  
  
7.  Der Smarttagbereich für `elementHost2`öffnen die **gehosteten Inhalt auswählen** Dropdown-Liste.  
  
8.  Wählen Sie **"UserControl1"** aus der Dropdown-Liste.  
  
9. Das `elementHost2`-Steuerelement hostet jetzt eine Instanz des `UserControl1`-Typs.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migration und Interoperabilität](../../wpf/advanced/migration-and-interoperability.md)
- [Verwenden von WPF-Steuerelementen](using-wpf-controls.md)
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
