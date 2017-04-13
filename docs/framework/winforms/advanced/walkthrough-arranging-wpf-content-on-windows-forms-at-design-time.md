---
title: "Exemplarische Vorgehensweise: Anordnen von WPF-Inhalt in Windows Forms zur Entwurfszeit | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Interoperabilität [WPF]"
  - "Windows Forms, Verankern und Andocken von WPF-Inhalt"
  - "Windows Forms, Anordnen von WPF-Inhalt zur Entwurfszeit"
  - "WPF-Inhalt [Windows Forms], Anordnen zur Entwurfszeit"
  - "WPF-Inhalt, Hosten in Windows Forms"
  - "WPF-Benutzersteuerelement [Windows Forms], Hosten in einem Layoutbereich"
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Exemplarische Vorgehensweise: Anordnen von WPF-Inhalt in Windows Forms zur Entwurfszeit
In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie die Windows Forms\-Layoutfeatures, z. B. Verankern und Ausrichtungslinien, verwendet werden können, um WPF\-Steuerelemente \(Windows Presentation Foundation\) anzuordnen.  
  
 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:  
  
-   Erstellen eines Projekts  
  
-   Erstellen des WPF\-Steuerelements  
  
-   Hosten von WPF\-Steuerelementen in einem Layoutbereich  
  
-   Verwenden von Ausrichtungslinien zum Ausrichten von WPF\-Steuerelementen  
  
-   Verankern und Andocken von WPF\-Steuerelementen  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren**, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## Erstellen des Projekts  
 Zunächst muss das Windows Forms\-Projekt erstellt werden.  
  
> [!NOTE]
>  Beim Hosten von WPF\-Inhalt werden nur C\#\- und Visual Basic\-Projekte unterstützt.  
  
#### So erstellen Sie das Projekt  
  
-   Erstellen Sie in Visual Basic oder Visual C\# ein neues Windows Forms\-Anwendungsprojekt mit dem Namen `ArrangeElementHost`.  
  
## Erstellen des WPF\-Steuerelements  
 Nachdem Sie dem Projekt ein WPF\-Steuerelement hinzugefügt haben, können Sie dieses auf dem Formular anordnen.  
  
#### So erstellen Sie ein WPF\-Steuerelement  
  
1.  Fügen Sie dem Projekt ein neues WPF\-<xref:System.Windows.Controls.UserControl>\-Objekt hinzu.  Verwenden Sie den Standardnamen, `UserControl1.xaml`, für den Steuerelementtyp.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen neuen WPF\-Inhalts in Windows Forms zur Entwurfszeit](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.  Weitere Informationen finden Sie unter [Gewusst wie: Auswählen und Verschieben von Elementen auf der Entwurfsoberfläche](http://msdn.microsoft.com/de-de/54cb70b6-b35b-46e4-a0cc-65189399c474).  
  
3.  Legen Sie im Fenster **Eigenschaften** den Wert der Eigenschaften <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> auf `200` fest.  
  
4.  Legen Sie den Wert der <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaft auf `Blue` fest.  
  
5.  Erstellen Sie das Projekt.  
  
## Hosten von WPF\-Steuerelementen in einem Layoutbereich  
 Sie können WPF\-Steuerelemente in Layoutbereichen auf die gleiche Weise verwenden wie andere Windows Forms\-Steuerelemente.  
  
#### So hosten Sie WPF\-Steuerelemente in einem Layoutbereich  
  
1.  Öffnen Sie `Form1` im Windows Forms\-Designer.  
  
2.  Ziehen Sie aus der **Toolbox** ein <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement auf das Formular.  
  
3.  Wählen Sie im Smarttagbereich des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements die Option **Letzte Zeile entfernen** aus.  
  
4.  Ändern Sie die Größe des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements, sodass es breiter und höher wird.  
  
5.  Doppelklicken Sie in der **Toolbox** auf `UserControl1`, um eine Instanz von `UserControl1` in der ersten Zelle des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements zu erstellen.  
  
     Die Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement namens `elementHost1` gehostet.  
  
6.  Doppelklicken Sie in der **Toolbox** auf `UserControl1`, um in der zweiten Zelle des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements eine weitere Instanz zu erstellen.  
  
7.  Wählen Sie `tableLayoutPanel1` im Fenster **Dokumentgliederung** aus.  Weitere Informationen finden Sie unter [Document Outline Window](http://msdn.microsoft.com/de-de/9054f2bc-f6f8-4242-9fe0-be71089b12f8).  
  
8.  Legen Sie im **Eigenschaftenfenster** den Wert der <xref:System.Windows.Forms.Control.Padding%2A>\-Eigenschaft auf `10, 10, 10, 10` fest.  
  
     Die Größe beider <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelemente wird entsprechend dem neuen Layout angepasst.  
  
## Verwenden von Ausrichtungslinien zum Ausrichten von WPF\-Steuerelementen  
 Ausrichtungslinien erleichtern die Ausrichtung von Steuerelementen auf einem Formular.  Sie können Ausrichtungslinien auch verwenden, um WPF\-Steuerelemente auszurichten.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
#### So verwenden Sie Ausrichtungslinien zum Ausrichten von WPF\-Steuerelementen  
  
1.  Ziehen Sie aus der **Toolbox** eine Instanz von `UserControl1` auf das Formular, und platzieren Sie diese in dem Bereich unterhalb des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements.  
  
     Die Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement namens `elementHost3` gehostet.  
  
2.  Richten Sie den linken Rand von `elementHost3` mithilfe der Ausrichtungslinien am linken Rand des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements aus.  
  
3.  Legen Sie die Breite von `elementHost3` mithilfe der Ausrichtungslinien auf dieselbe Breite wie das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement fest.  
  
4.  Verschieben Sie `elementHost3` in Richtung des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements,  steuern, bis zwischen den Steuerelementen eine mittige Ausrichtungslinie angezeigt wird.  
  
5.  Legen Sie im **Eigenschaftenfenster** den Wert der Margin\-Eigenschaft auf `20, 20, 20, 20` fest.  
  
6.  Verschieben Sie `elementHost3` vom <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement weg, bis die mittige Ausrichtungslinie erneut angezeigt wird.  Die mittige Ausrichtungslinie kennzeichnet jetzt einen Rand von 20.  
  
7.  Verschieben Sie `elementHost3` nach rechts, bis dessen linker Rand am linken Rand von `elementHost1` ausgerichtet ist.  
  
8.  Ändern Sie die Breite von `elementHost3` bis dessen rechter Rand am rechten Rand von `elementHost2` ausgerichtet ist.  
  
## Verankern und Andocken von WPF\-Steuerelementen  
 Ein auf einem Formular gehostetes WPF\-Steuerelement hat dasselbe Verankerungs\- und Andockverhalten auf wie andere Windows Forms\-Steuerelemente.  
  
#### So verankern Sie WPF\-Steuerelemente und docken diese an  
  
1.  Klicken Sie auf `elementHost1`.  
  
2.  Legen Sie im **Eigenschaftenfenster** die <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaft auf **Top, Bottom, Left, Right** fest.  
  
3.  Vergrößern Sie das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement.  
  
     Die Größe des `elementHost1`\-Steuerelements wird geändert, sodass es die Zelle ausfüllt.  
  
4.  Klicken Sie auf `elementHost2`.  
  
5.  Legen Sie im **Eigenschaftenfenster** den Wert der <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DockStyle> fest.  
  
     Die Größe des `elementHost2`\-Steuerelements wird geändert, sodass es die Zelle ausfüllt.  
  
6.  Wählen Sie das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement.  
  
7.  Legen Sie den Wert von dessen <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DockStyle> fest.  
  
8.  Klicken Sie auf `elementHost3`.  
  
9. Legen Sie den Wert von dessen <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DockStyle> fest.  
  
     Die Größe des `elementHost3`\-Steuerelements wird so geändert, dass es den verbleibenden Platz auf dem Formular ausfüllt.  
  
10. Ändern Sie die Größe des Formulars.  
  
     Die Größen aller drei <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelemente werden entsprechend angepasst.  
  
     Weitere Informationen finden Sie unter [Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel\-Steuerelement](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel\-Steuerelement](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)   
 [Gewusst wie: Ausrichten eines Steuerelements an den Rändern eines Formulars zur Entwurfszeit](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)   
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)   
 [Migration und Interoperabilität](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [Verwenden von WPF\-Steuerelementen](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26)