---
title: 'Exemplarische Vorgehensweise: Ändern von Eigenschaften eines gehosteten WPF-Elements zur Entwurfszeit'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], changing properties at design time
- Windows Forms, changing properties of WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- interoperability [WPF]
ms.assetid: a1f7a90c-0bbb-4781-8c3c-8cc8bef2488d
ms.openlocfilehash: 15cab9266af5840aa4b37a62b71bd5010b7a859a
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43741019"
---
# <a name="walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time"></a>Exemplarische Vorgehensweise: Ändern von Eigenschaften eines gehosteten WPF-Elements zur Entwurfszeit
In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Eigenschaftswerte eines WPF-Steuerelements (Windows Presentation Foundation) geändert werden, das in einem Windows Form-Objekt gehostet wird.  
  
 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:  
  
-   Erstellen eines Projekts  
  
-   Erstellen des WPF-Steuerelements  
  
-   Hosten der WPF-Steuerelemente in einem Windows Form-Objekt  
  
-   Verwenden des WPF-Designers für Visual Studio, um Eigenschaftswerte zu ändern  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Zunächst muss das Windows Forms-Projekt erstellt werden.  
  
> [!NOTE]
>  Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.  
  
#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
-   Erstellen Sie ein neues Windows Forms-Anwendungsprojekt in Visual Basic oder Visual c# mit dem Namen `WpfHost`.  
  
## <a name="creating-the-wpf-control"></a>Erstellen des WPF-Steuerelements  
 Nachdem Sie dem Projekt ein WPF-Steuerelement hinzugefügt haben, können Sie dieses auf dem Formular anordnen.  
  
#### <a name="to-create-wpf-controls"></a>So erstellen Sie ein WPF-Steuerelement  
  
1.  Fügen Sie dem Projekt ein neues WPF-<xref:System.Windows.Controls.UserControl>-Objekt hinzu. Verwenden Sie den Standardnamen (`UserControl1.xaml`) für den Steuerelementtyp. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen neuen WPF-Inhalt in Windows Forms zur Entwurfszeit](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  In der **Eigenschaften** legen den Wert des der <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft `Blue`.  
  
3.  Erstellen Sie das Projekt.  
  
## <a name="changing-property-values-on-the-wpf-control"></a>Ändern von Eigenschaftswerten für das WPF-Steuerelement  
 Mit dem <xref:System.Windows.Forms.Integration.ElementHost>-Smarttag lassen sich Eigenschaften von gehostetem WPF-Inhalt einfach ändern, indem der WPF-Designer verwendet wird.  
  
#### <a name="to-host-a-wpf-control"></a>So hosten Sie ein WPF-Steuerelement  
  
1.  Öffnen Sie `Form1` im Windows Forms-Designer.  
  
2.  In der **Toolbox**in die **WPF-Benutzersteuerelemente** Registerkarte, doppelklicken Sie auf `UserControl1` zum Erstellen einer Instanz von `UserControl1` auf dem Formular.  
  
     Die Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.  
  
3.  In der **ElementHost-Aufgaben** wählen Sie im Smarttagbereich **gehosteten Inhalt bearbeiten**.  
  
     Die Datei "UserControl1.xaml" wird im WPF-Designer geöffnet.  
  
4.  In der **Eigenschaften** legen den Wert des der <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft `Red`.  
  
5.  Erstellen Sie das Projekt neu.  
  
6.  Öffnen Sie `Form1` im Windows Forms-Designer.  
  
     Die Instanz von `UserControl1` hat einen roten Hintergrund.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [Vorgehensweise: Ausrichten eines Steuerelements an den Rändern eines Formulars zur Entwurfszeit](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [Migration und Interoperabilität](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [Verwenden von WPF-Steuerelementen](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
