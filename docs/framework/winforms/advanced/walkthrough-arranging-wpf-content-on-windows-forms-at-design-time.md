---
title: 'Exemplarische Vorgehensweise: Anordnen von WPF-Inhalt in Windows Forms zur Entwurfszeit'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
ms.openlocfilehash: 1466591a06e9e7ca61f94683e037566f8d0cb31a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509774"
---
# <a name="walkthrough-arranging-wpf-content-on-windows-forms-at-design-time"></a>Exemplarische Vorgehensweise: Anordnen von WPF-Inhalt in Windows Forms zur Entwurfszeit
In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie die Windows Forms-Layoutfunktionen, z. B. Verankern und Ausrichtungslinien, verwendet werden können, um WPF-Steuerelemente (Windows Presentation Foundation) anzuordnen.  
  
 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:  
  
-   Erstellen eines Projekts  
  
-   Erstellen des WPF-Steuerelements  
  
-   Hosten von WPF-Steuerelementen in einem Layoutbereich  
  
-   Verwenden von Ausrichtungslinien zum Ausrichten von WPF-Steuerelementen  
  
-   Verankern und Andocken von WPF-Steuerelementen  
  
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
  
-   Erstellen Sie ein neues Windows Forms-Anwendungsprojekt in Visual Basic oder Visual c# mit dem Namen `ArrangeElementHost`.  
  
## <a name="creating-the-wpf-control"></a>Erstellen des WPF-Steuerelements  
 Nachdem Sie dem Projekt ein WPF-Steuerelement hinzugefügt haben, können Sie dieses auf dem Formular anordnen.  
  
#### <a name="to-create-wpf-controls"></a>So erstellen Sie ein WPF-Steuerelement  
  
1.  Fügen Sie dem Projekt ein neues WPF-<xref:System.Windows.Controls.UserControl>-Objekt hinzu. Verwenden Sie den Standardnamen (`UserControl1.xaml`) für den Steuerelementtyp. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen neuen WPF-Inhalt in Windows Forms zur Entwurfszeit](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist. Weitere Informationen finden Sie unter [Vorgehensweise: auswählen und Verschieben von Elementen auf der Entwurfsoberfläche](https://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).  
  
3.  In der **Eigenschaften** legen den Wert des der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften `200`.  
  
4.  Legen Sie den Wert der <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft auf `Blue` fest.  
  
5.  Erstellen Sie das Projekt.  
  
## <a name="hosting-wpf-controls-in-a-layout-panel"></a>Hosten von WPF-Steuerelementen in einem Layoutbereich  
 Sie können WPF-Steuerelemente in Layoutbereichen auf die gleiche Weise verwenden wie andere Windows Forms-Steuerelemente.  
  
#### <a name="to-host-wpf-controls-in-a-layout-panel"></a>So hosten Sie WPF-Steuerelemente in einem Layoutbereich  
  
1.  Öffnen Sie `Form1` im Windows Forms-Designer.  
  
2.  In der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement auf das Formular.  
  
3.  Auf der <xref:System.Windows.Forms.TableLayoutPanel> des Steuerelements im Smarttagbereich auf **letzte Zeile entfernen**.  
  
4.  Ändern Sie die Größe des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements, sodass es breiter und höher wird.  
  
5.  In der **Toolbox**, doppelklicken Sie auf `UserControl1` zum Erstellen einer Instanz von `UserControl1` in der ersten Zelle der <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.  
  
     Die Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.  
  
6.  In der **Toolbox**, doppelklicken Sie auf `UserControl1` zum Erstellen von einer anderen Instanz in der zweiten Zelle die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.  
  
7.  In der **Dokumentgliederung** wählen Sie im Fenster `tableLayoutPanel1`. Weitere Informationen finden Sie unter [Dokumentgliederung (Fenster)](https://msdn.microsoft.com/library/9054f2bc-f6f8-4242-9fe0-be71089b12f8).  
  
8.  In der **Eigenschaften** legen den Wert des der <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft `10, 10, 10, 10`.  
  
     Die Größe beider <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelemente wird entsprechend dem neuen Layout angepasst.  
  
## <a name="using-snaplines-to-align-wpf-controls"></a>Verwenden von Ausrichtungslinien zum Ausrichten von WPF-Steuerelementen  
 Ausrichtungslinien erleichtern die Ausrichtung von Steuerelementen auf einem Formular. Sie können Ausrichtungslinien auch verwenden, um WPF-Steuerelemente auszurichten. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
#### <a name="to-use-snaplines-to-align-wpf-controls"></a>So verwenden Sie Ausrichtungslinien zum Ausrichten von WPF-Steuerelementen  
  
1.  Aus der **Toolbox**, ziehen Sie eine Instanz des `UserControl1` auf das Formular, und fügen Sie ihn in den Bereich unterhalb der <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.  
  
     Die Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost3` gehostet.  
  
2.  Richten Sie den linken Rand von `elementHost3` mithilfe der Ausrichtungslinien am linken Rand des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements aus.  
  
3.  Legen Sie die Breite von `elementHost3` mithilfe der Ausrichtungslinien auf dieselbe Breite wie das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement fest.  
  
4.  Verschieben Sie `elementHost3` in Richtung des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements,  steuern, bis zwischen den Steuerelementen eine mittige Ausrichtungslinie angezeigt wird.  
  
5.  In der **Eigenschaften** legen den Wert der Margin-Eigenschaft auf `20, 20, 20, 20`.  
  
6.  Verschieben Sie `elementHost3` vom <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement weg, bis die mittige Ausrichtungslinie erneut angezeigt wird. Die mittige Ausrichtungslinie kennzeichnet jetzt einen Rand von 20.  
  
7.  Verschieben Sie `elementHost3` nach rechts, bis dessen linker Rand am linken Rand von `elementHost1` ausgerichtet ist.  
  
8.  Ändern Sie die Breite von `elementHost3` bis dessen rechter Rand am rechten Rand von `elementHost2` ausgerichtet ist.  
  
## <a name="anchoring-and-docking-wpf-controls"></a>Verankern und Andocken von WPF-Steuerelementen  
 Ein auf einem Formular gehostetes WPF-Steuerelement hat dasselbe Verankerungs- und Andockverhalten auf wie andere Windows Forms-Steuerelemente.  
  
#### <a name="to-anchor-and-dock-wpf-controls"></a>So verankern Sie WPF-Steuerelemente und docken diese an  
  
1.  Klicken Sie auf `elementHost1`.  
  
2.  In der **Eigenschaften** legen die <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft **Top, Bottom, Left, Right**.  
  
3.  Vergrößern Sie das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement.  
  
     Die Größe des `elementHost1`-Steuerelements wird geändert, sodass es die Zelle ausfüllt.  
  
4.  Klicken Sie auf `elementHost2`.  
  
5.  In der **Eigenschaften** legen den Wert des der <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Fill>.  
  
     Die Größe des `elementHost2`-Steuerelements wird geändert, sodass es die Zelle ausfüllt.  
  
6.  Wählen Sie das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement.  
  
7.  Legen Sie den Wert von dessen <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Top> fest.  
  
8.  Klicken Sie auf `elementHost3`.  
  
9. Legen Sie den Wert von dessen <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill> fest.  
  
     Die Größe des `elementHost3`-Steuerelements wird so geändert, dass es den verbleibenden Platz auf dem Formular ausfüllt.  
  
10. Ändern Sie die Größe des Formulars.  
  
     Die Größen aller drei <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelemente werden entsprechend angepasst.  
  
     Weitere Informationen finden Sie unter [Vorgehensweise: Anker und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [Vorgehensweise: Ausrichten eines Steuerelements an den Rändern eines Formulars zur Entwurfszeit](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [Migration und Interoperabilität](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [Verwenden von WPF-Steuerelementen](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
