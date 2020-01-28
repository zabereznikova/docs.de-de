---
title: Anordnen von WPF-Inhalt auf Windows Forms zur Entwurfszeit
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 5a6b12def45052e117fb149555946ea42d6cd3c2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746815"
---
# <a name="walkthrough-arrange-wpf-content-on-windows-forms-at-design-time"></a>Exemplarische Vorgehensweise: Anordnen von WPF-Inhalt auf Windows Forms zur Entwurfszeit

In diesem Artikel erfahren Sie, wie Sie die Windows Forms Layoutfeatures, wie z. b. das verankern und ausrichten, verwenden, um Windows Presentation Foundation (WPF)-Steuerelemente anzuordnen.

## <a name="prerequisites"></a>Erforderliche Komponenten

Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.

## <a name="create-the-project"></a>Erstellen eines Projekts

Öffnen Sie Visual Studio, und erstellen Sie ein neues Windows Forms-Anwendungsprojekt C# in Visual Basic oder Visual mit dem Namen `ArrangeElementHost`.

> [!NOTE]
> Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.

## <a name="create-the-wpf-control"></a>Erstellen des WPF-Steuer Elements

Nachdem Sie dem Projekt ein WPF-Steuerelement hinzugefügt haben, können Sie dieses auf dem Formular anordnen.

1. Fügen Sie dem Projekt ein neues WPF-<xref:System.Windows.Controls.UserControl>-Objekt hinzu. Verwenden Sie den Standardnamen, `UserControl1.xaml`, für den Steuerelementtyp. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Erstellen eines neuen WPF-Inhalts auf Windows Forms zur Entwurfszeit](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).

2. Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.

3. Legen Sie im Fenster **Eigenschaften** den Wert der Eigenschaften <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> auf **200**fest.

4. Legen Sie den Wert der <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft auf **Blue**fest.

5. Erstellen Sie das Projekt.

## <a name="host-wpf-controls-in-a-layout-panel"></a>WPF-Steuerelemente in einem Layoutpanel hosten

Sie können WPF-Steuerelemente in Layoutbereichen auf die gleiche Weise verwenden wie andere Windows Forms-Steuerelemente.

1. Öffnen Sie `Form1` im Windows Forms-Designer.

2. Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement in der **Toolbox**auf das Formular.

3. Wählen Sie im Smarttagbereich des <xref:System.Windows.Forms.TableLayoutPanel> Steuer Elements **letzte Zeile entfernen**aus.

4. Ändern Sie die Größe des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements, sodass es breiter und höher wird.

5. Doppelklicken Sie in der **Toolbox**auf `UserControl1`, um in der ersten Zelle des <xref:System.Windows.Forms.TableLayoutPanel>-Steuer Elements eine Instanz von `UserControl1` zu erstellen.

   Die Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.

6. Doppelklicken Sie in der **Toolbox**auf `UserControl1`, um eine weitere Instanz in der zweiten Zelle des <xref:System.Windows.Forms.TableLayoutPanel> Steuer Elements zu erstellen.

7. Wählen Sie im Fenster **Dokument** Gliederung die Option `tableLayoutPanel1`aus.

8. Legen Sie im Fenster **Eigenschaften** den Wert der <xref:System.Windows.Forms.Control.Padding%2A>-Eigenschaft auf **10, 10, 10, 10**fest.

   Die Größe beider <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelemente wird entsprechend dem neuen Layout angepasst.

## <a name="use-snaplines-to-align-wpf-controls"></a>Verwenden von Ausrichtungs Linien zum Ausrichten von WPF-Steuerelementen

Ausrichtungslinien erleichtern die Ausrichtung von Steuerelementen auf einem Formular. Sie können Ausrichtungslinien auch verwenden, um WPF-Steuerelemente auszurichten. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Anordnen von Steuerelementen auf Windows Forms mithilfe](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)von Ausrichtungs Linien.

1. Ziehen Sie aus der **Toolbox**eine Instanz von `UserControl1` auf das Formular, und platzieren Sie Sie in dem Bereich unterhalb des <xref:System.Windows.Forms.TableLayoutPanel> Steuer Elements.

   Die Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost3` gehostet.

2. Richten Sie den linken Rand von `elementHost3` mithilfe der Ausrichtungslinien am linken Rand des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements aus.

3. Legen Sie die Breite von `elementHost3` mithilfe der Ausrichtungslinien auf dieselbe Breite wie das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement fest.

4. Verschieben Sie `elementHost3` in Richtung des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements,  steuern, bis zwischen den Steuerelementen eine mittige Ausrichtungslinie angezeigt wird.

5. Legen Sie im Fenster **Eigenschaften** den Wert der Margin-Eigenschaft auf **20, 20, 20, 20**fest.

6. Verschieben Sie `elementHost3` vom <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement weg, bis die mittige Ausrichtungslinie erneut angezeigt wird. Die mittige Ausrichtungslinie kennzeichnet jetzt einen Rand von 20.

7. Verschieben Sie `elementHost3` nach rechts, bis der linke Rand am linken Rand des `elementHost1`ausgerichtet ist.

8. Ändern Sie die Breite von `elementHost3` bis dessen rechter Rand am rechten Rand von `elementHost2` ausgerichtet ist.

## <a name="anchor-and-dock-wpf-controls"></a>WPF-Steuerelemente verankern und Andocken

Ein auf einem Formular gehostetes WPF-Steuerelement hat dasselbe Verankerungs- und Andockverhalten auf wie andere Windows Forms-Steuerelemente.

1. Klicken Sie auf `elementHost1`.

2. Legen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft auf **oben, unten, Links und rechts**fest.

3. Vergrößern Sie das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement.

   Die Größe des `elementHost1`-Steuerelements wird geändert, sodass es die Zelle ausfüllt.

4. Klicken Sie auf `elementHost2`.

5. Legen Sie im Fenster **Eigenschaften** den Wert der <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill>fest.

   Die Größe des `elementHost2`-Steuerelements wird geändert, sodass es die Zelle ausfüllt.

6. Wählen Sie das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement.

7. Legen Sie den Wert von dessen <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Top> fest.

8. Klicken Sie auf `elementHost3`.

9. Legen Sie den Wert von dessen <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill> fest.

   Die Größe des `elementHost3`-Steuerelements wird so geändert, dass es den verbleibenden Platz auf dem Formular ausfüllt.

10. Ändern Sie die Größe des Formulars.

    Die Größen aller drei <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelemente werden entsprechend angepasst.

    Weitere Informationen finden Sie unter Gewusst [wie: verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuer](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)Element.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Gewusst wie: Ausrichten eines Steuerelements an den Rändern eines Formulars zur Entwurfszeit](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Migration und Interoperabilität](../../wpf/advanced/migration-and-interoperability.md)
- [Verwenden von WPF-Steuerelementen](using-wpf-controls.md)
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
