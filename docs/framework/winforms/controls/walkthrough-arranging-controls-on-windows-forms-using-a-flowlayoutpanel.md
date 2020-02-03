---
title: Anordnen von Steuerelementen mithilfe von FlowLayoutPanel
ms.date: 03/30/2017
helpviewer_keywords:
- FlowLayoutPanel control [Windows Forms], walkthroughs
- Windows Forms controls, arranging
- controls [Windows Forms], arranging with FlowLayoutPanel
- layout [Windows Forms], walkthroughs
ms.assetid: a1744323-0316-49c2-992e-ebfc0a976b85
ms.openlocfilehash: 6df0a910ee346f319fbee835e5e632808630a99e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745398"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel"></a>Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel

Einige Anwendungen erfordern ein Formular mit einem Layout, das sich selbst entsprechend neu anordnet, wenn sich die Größe des Formulars oder des Inhalts ändert. Wenn Sie ein dynamisches Layout benötigen und <xref:System.Windows.Forms.Control.Layout> -Ereignisse nicht explizit im Code verarbeiten möchten, ziehen Sie die Verwendung eines Layoutbereichs in Erwägung.

Das <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement und das <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement stellen intuitive Verfahren zum Anordnen von Steuerelementen auf Formularen dar. Beide bieten die Möglichkeit, die relativen Positionen der in ihnen enthaltenen untergeordneten Steuerelemente automatisch und konfigurierbar zu steuern, und beide stellen dynamische Layoutfunktionen zur Laufzeit zur Verfügung, sodass sie Größe und Position von untergeordneten Steuerelementen ändern können, wenn sich die Abmessungen des übergeordneten Formulars ändern. Layoutbereiche können in Layoutbereichen geschachtelt werden, um die Realisierung raffinierter Benutzeroberflächen zu ermöglichen.

Der <xref:System.Windows.Forms.TableLayoutPanel> ordnet seinen Inhalt in einem Raster an und bietet ähnliche Funktionen wie das HTML-\<Table >-Element. Seine Zellen sind in Zeilen und Spalten angeordnet, und diese können verschiedene Größen haben. Weitere Informationen finden Sie unter [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).

Das <xref:System.Windows.Forms.FlowLayoutPanel> ordnet seinen Inhalt in einer bestimmten Flussrichtung an: horizontal oder vertikal. Dieser Inhalt kann von einer Zeile zur nächsten oder von einer Spalte zur nächsten umbrochen werden. Alternativ kann dieser Inhalt abgeschnitten werden, statt dass er umbrochen wird. In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:

- Erstellen eines Windows Forms-Projekts

- Anordnen von Steuerelementen in horizontaler und vertikaler Richtung

- Ändern der Flussrichtung

- Einfügen von Flussumbrüchen

- Anordnen von Steuerelementen mithilfe von Auffüllung und Rändern

- Einfügen von Steuerelementen durch Doppelklicken in der Toolbox

- Einfügen eines Steuerelements durch Zeichnen seiner Kontur

- Einfügen von Steuerelementen mit der Einfügemarke

- Erneutes Zuweisen von vorhandenen Steuerelementen zu einem anderen übergeordneten Element

Wenn Sie fertig sind, haben Sie ein Verständnis der Rolle, die diese wichtigen Layoutfunktionen spielen.

## <a name="create-the-project"></a>Erstellen des Projekts

1. Erstellen Sie in Visual Studio ein Windows-basiertes Anwendungsprojekt mit dem Namen "FlowLayoutPanelExample" (**Datei** > **Neues** > **Projekt** > **Visual C#**  oder **Visual Basic** >  > **Anwendung**für die **klassische Desktop** Windows Forms).

2. Wählen Sie das Formular im **Forms-Designer**aus.

## <a name="arranging-controls-horizontally-and-vertically"></a>Anordnen von Steuerelementen in horizontaler und vertikaler Richtung
 Das <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement ermöglicht es Ihnen, Steuerelemente an Zeilen und Spalten zu platzieren, ohne dass Sie die genaue Position der einzelnen Steuerelemente angeben müssen.

 Das <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement kann Größe und Umbruch seiner untergeordneten Steuerelemente ändern, wenn sich die Abmessungen des übergeordneten Formulars ändern.

### <a name="to-arrange-controls-horizontally-and-vertically-using-a-flowlayoutpanel"></a>So ordnen Sie Steuerelemente mithilfe eines FlowLayoutPanels horizontal und vertikal an.

1. Ziehen Sie ein <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.

2. Ziehen Sie ein <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das <xref:System.Windows.Forms.FlowLayoutPanel>. Beachten Sie, dass es automatisch in die obere linke Ecke des <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements verschoben wird.

3. Ziehen Sie ein weiteres <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das <xref:System.Windows.Forms.FlowLayoutPanel>. Beachten Sie, dass das <xref:System.Windows.Forms.Button> -Steuerelement automatisch auf eine Position neben dem ersten <xref:System.Windows.Forms.Button> -Steuerelement verschoben wird. Wenn Ihr <xref:System.Windows.Forms.FlowLayoutPanel> zu schmal ist, um beide Steuerelemente auf der gleichen Zeile zu platzieren, wird das neue <xref:System.Windows.Forms.Button> -Steuerelement automatisch in die nächste Zeile verschoben.

4. Ziehen Sie weitere <xref:System.Windows.Forms.Button> -Steuerelemente aus der **Toolbox** auf das <xref:System.Windows.Forms.FlowLayoutPanel>. Fahren Sie mit dem Platzieren von <xref:System.Windows.Forms.Button> -Steuerelementen fort, bis bei einem der Umbruch in die nächste Zeile erfolgt.

5. Ändern Sie den Wert der <xref:System.Windows.Forms.FlowLayoutPanel> -Eigenschaft des <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> -Steuerelements in `false`. Beachten Sie, dass für die untergeordneten Steuerelemente kein Umbruch in die nächste Zeile mehr auftritt. Stattdessen werden sie in die erste Zeile verschoben und abgeschnitten.

6. Ändern Sie den Wert der <xref:System.Windows.Forms.FlowLayoutPanel> -Eigenschaft des <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> -Steuerelements in `true`. Beachten Sie, dass die untergeordneten Steuerelemente wieder in die nächste Zeile fließen.

7. Verringern Sie die Breite des <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements, bis alle <xref:System.Windows.Forms.Button> -Steuerelemente in der ersten Spalte platziert werden.

8. Erhöhen Sie die Breite des <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements, bis alle <xref:System.Windows.Forms.Button> -Steuerelemente in der ersten Zeile platziert werden. Möglicherweise müssen Sie die Größe des Formulars ändern, um der größeren Breite Rechnung zu tragen.

## <a name="changing-flow-direction"></a>Ändern der Flussrichtung
 Mithilfe der <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> -Eigenschaft können Sie die Richtung ändern, in der Steuerelemente angeordnet werden. Sie können die untergeordneten Steuerelemente von links nach rechts, rechts nach links, oben nach unten oder unten nach oben anordnen.

### <a name="to-change-the-flow-direction-in-a-flowlayoutpanel"></a>So ändern Sie die Flussrichtung in einem FlowLayoutPanel

1. Ändern Sie den Wert der <xref:System.Windows.Forms.FlowLayoutPanel> -Eigenschaft des <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> -Steuerelements in <xref:System.Windows.Forms.FlowDirection.TopDown>. Beachten Sie, dass die untergeordneten Steuerelemente je nach Höhe des Steuerelements in einer oder mehreren Spalten neu angeordnet werden.

2. Ändern Sie die Größe des <xref:System.Windows.Forms.FlowLayoutPanel> , sodass seine Höhe kleiner als die Spalte der <xref:System.Windows.Forms.Button> -Steuerelemente ist. Beachten Sie, dass das <xref:System.Windows.Forms.FlowLayoutPanel> die untergeordneten Steuerelemente so neu anordnet, dass sie in die nächste Spalte fließen. Während Sie die Höhe weiter verringern, können Sie beobachten, dass die untergeordneten Steuerelemente in benachbarte Spalten fließen. Ändern Sie den Wert der <xref:System.Windows.Forms.FlowLayoutPanel> -Eigenschaft des <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> -Steuerelements in <xref:System.Windows.Forms.FlowDirection.RightToLeft>. Beachten Sie, dass die Positionen der untergeordneten Steuerelemente umgekehrt werden. Beobachten Sie das Layout, wenn Sie den Wert der <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> -Eigenschaft in <xref:System.Windows.Forms.FlowDirection.BottomUp>ändern.

## <a name="inserting-flow-breaks"></a>Einfügen von Flussumbrüchen
 Das <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement stellt für seine untergeordneten Steuerelemente eine FlowBreak-Eigenschaft bereit. Wenn Sie den Wert der FlowBreak-Eigenschaft auf `true` festlegen, ordnet das <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement andere Steuerelemente nicht mehr in der aktuellen Flussrichtung an und bricht diese auch nicht mehr in die nächste Zeile oder Spalte um.

### <a name="to-insert-flow-breaks"></a>So fügen Sie Flussumbrüche ein

1. Ändern Sie den Wert der <xref:System.Windows.Forms.FlowLayoutPanel> -Eigenschaft des <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> -Steuerelements in <xref:System.Windows.Forms.FlowDirection.TopDown>.

2. Wählen Sie eins der <xref:System.Windows.Forms.Button> -Steuerelemente in der Mitte der äußerst linken Spalte aus.

3. Legen Sie den Wert der FlowBreak-Eigenschaft des <xref:System.Windows.Forms.Button> -Steuerelements auf `true`fest. Beachten Sie, dass die Spalte umbrochen wird und die Steuerelemente, die auf das ausgewählte <xref:System.Windows.Forms.Button> -Steuerelement folgen, in die nächste Spalte fließen. Legen Sie den Wert der FlowBreak-Eigenschaft des <xref:System.Windows.Forms.Button> -Steuerelements auf `false` fest, um zum ursprünglichen Verhalten zurückzukehren.

## <a name="positioning-controls-using-docking-and-anchoring"></a>Positionieren von Steuerelementen durch Andocken und Verankern
 Das Andock- und Verankerungsverhalten von untergeordneten Steuerelementen unterscheidet sich vom Verhalten in anderen Containersteuerelementen. Sowohl das Andocken als auch das Verankern erfolgt relativ zum größten Steuerelement in der Flussrichtung.

### <a name="to-position-controls-using-docking-and-anchoring"></a>So positionieren Sie Steuerelemente durch Andocken und Verankern

1. Vergrößern Sie das <xref:System.Windows.Forms.FlowLayoutPanel> , bis alle <xref:System.Windows.Forms.Button> -Steuerelemente in einer Spalte angeordnet sind.

2. Wählen Sie das oberste <xref:System.Windows.Forms.Button> -Steuerelement aus. Erhöhen Sie seine Breite, bis es ungefähr doppelt so breit wie die anderen <xref:System.Windows.Forms.Button> -Steuerelemente ist.

3. Wählen Sie das zweite <xref:System.Windows.Forms.Button> -Steuerelement aus. Legen Sie den Wert seiner <xref:System.Windows.Forms.Control.Anchor%2A> -Eigenschaft auf <xref:System.Windows.Forms.AnchorStyles.Right>fest. Beachten Sie, dass es so verschoben wird, dass seine rechte Kante an der rechten Kante des ersten <xref:System.Windows.Forms.Button> -Steuerelements ausgerichtet ist.

4. Ändern Sie den Wert seiner <xref:System.Windows.Forms.Control.Anchor%2A> -Eigenschaft in <xref:System.Windows.Forms.AnchorStyles.Right> und <xref:System.Windows.Forms.AnchorStyles.Left>. Beachten Sie, dass seine Größe auf die Breite des ersten <xref:System.Windows.Forms.Button> -Steuerelements geändert wird.

5. Wählen Sie das dritte <xref:System.Windows.Forms.Button> -Steuerelement aus. Legen Sie den Wert seiner <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill>fest. Beachten Sie, dass seine Größe auf die Breite des ersten <xref:System.Windows.Forms.Button> -Steuerelements geändert wird.

## <a name="arranging-controls-using-padding-and-margins"></a>Anordnen von Steuerelementen mithilfe von Auffüllung und Rändern
 Sie können Steuerelemente auf Ihrem <xref:System.Windows.Forms.FlowLayoutPanel> auch durch Ändern der Eigenschaften <xref:System.Windows.Forms.Control.Padding%2A> und <xref:System.Windows.Forms.Control.Margin%2A> anordnen.

 Mithilfe der <xref:System.Windows.Forms.Control.Padding%2A> -Eigenschaft können Sie die Platzierung von Steuerelementen innerhalb einer Zelle eines <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements steuern. Sie gibt den Abstand zwischen den untergeordneten Steuerelementen und der Kante des <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements an.

 Die <xref:System.Windows.Forms.Control.Margin%2A> -Eigenschaft ermöglicht Ihnen, den Abstand zwischen Steuerelementen zu steuern.

### <a name="to-arrange-controls-using-the-padding-and-margin-properties"></a>So ordnen Sie Steuerelemente mithilfe der Eigenschaften „Padding“ und „Margin“ an

1. Ändern Sie den Wert der <xref:System.Windows.Forms.FlowLayoutPanel> -Eigenschaft des <xref:System.Windows.Forms.Control.Dock%2A> -Steuerelements in <xref:System.Windows.Forms.DockStyle.Fill>. Wenn das Formular groß genug ist, werden die <xref:System.Windows.Forms.Button> -Steuerelemente in die erste Spalte des <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements verschoben.

2. Ändern Sie den Wert der <xref:System.Windows.Forms.FlowLayoutPanel> -Eigenschaft des <xref:System.Windows.Forms.Control.Padding%2A> -Steuerelements, indem Sie im <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaftenfenster **den Eintrag** erweitern und die <xref:System.Windows.Forms.Padding.All%2A> -Eigenschaft auf **20**festlegen. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise: Anordnen [von Windows Forms-Steuerelementen mit Auffüll Zeichen, Rändern und der AutoSize-Eigenschaft](windows-forms-controls-padding-autosize.md). Beachten Sie, dass die untergeordneten Steuerelemente zur Mitte des <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements verschoben werden. Durch den höheren Wert für die <xref:System.Windows.Forms.Control.Padding%2A> -Eigenschaft werden die untergeordneten Steuerelemente von den Kanten des <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements weg verschoben.

3. Wählen Sie alle <xref:System.Windows.Forms.Button> -Steuerelemente im <xref:System.Windows.Forms.FlowLayoutPanel> aus, und legen Sie den Wert der <xref:System.Windows.Forms.Control.Margin%2A> -Eigenschaft auf **20**fest. Beachten Sie, dass sich der Abstand zwischen den <xref:System.Windows.Forms.Button> -Steuerelementen vergrößert, sodass sie weiter auseinander gerückt werden. Möglicherweise müssen Sie die Größe des <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements erhöhen, damit Sie alle untergeordneten Steuerelemente sehen können.

## <a name="inserting-controls-by-double-clicking-them-in-the-toolbox"></a>Einfügen von Steuerelementen durch Doppelklicken in der Toolbox
 Sie können Ihr <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement auffüllen, indem Sie in der **Toolbox**auf Steuerelemente doppelklicken.

### <a name="to-insert-controls-by-double-clicking-in-the-toolbox"></a>So fügen Sie Steuerelemente durch Doppelklicken in der Toolbox ein

1. Doppelklicken Sie auf das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements in der **Toolbox**. Beachten Sie, dass ein neues <xref:System.Windows.Forms.Button> -Steuerelement im <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement angezeigt wird.

2. Doppelklicken Sie in der **Toolbox**auf verschiedene weitere Steuerelemente. Beachten Sie, dass die neuen Steuerelemente nacheinander im <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement angezeigt werden.

## <a name="inserting-a-control-by-drawing-its-outline"></a>Einfügen eines Steuerelements durch Zeichnen seiner Kontur
 Sie können ein Steuerelement in ein <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement einfügen und seine Größe angeben, indem Sie in einer Zelle seine Kontur zeichnen.

### <a name="to-insert-a-control-by-drawing-its-outline"></a>So fügen Sie ein Steuerelement ein, indem Sie seine Kontur zeichnen

1. Klicken Sie in der **Toolbox**auf das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements. Ziehen Sie es nicht auf das Formular.

2. Bewegen Sie den Mauszeiger auf das <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement. Beachten Sie, dass der Mauszeiger die Form eines Fadenkreuzes annimmt, an das das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements angefügt ist.

3. Klicken Sie, und halten Sie die Maustaste gedrückt.

4. Ziehen Sie den Mauszeiger, um die Kontur des <xref:System.Windows.Forms.Button> -Steuerelements zu zeichnen. Wenn Sie mit der Größe zufrieden sind, geben Sie die Maustaste frei. Beachten Sie, dass das <xref:System.Windows.Forms.Button> -Steuerelement an der nächsten freien Position des <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements erstellt wird.

## <a name="inserting-controls-using-the-insertion-bar"></a>Einfügen von Steuerelementen mithilfe der Einfügemarke
 Sie können Steuerelemente an einer bestimmten Position in einem <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement einfügen. Wenn Sie ein Steuerelement in den Clientbereich eines <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements ziehen, wird eine Einfügemarke angezeigt, um anzuzeigen, wo das Steuerelement eingefügt wird.

### <a name="to-insert-a-control-using-the-caret"></a>So fügen Sie ein Steuerelement mit der Einfügemarke ein

1. Ziehen Sie ein <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement, und zeigen Sie auf den Abstand zwischen zwei <xref:System.Windows.Forms.Button> -Steuerelementen. Beachten Sie, dass eine Einfügeleiste gezeichnet wird, die angibt, wo die <xref:System.Windows.Forms.Button> platziert wird, wenn Sie im <xref:System.Windows.Forms.FlowLayoutPanel> Steuerelement abgelegt wird. Bevor Sie das neue <xref:System.Windows.Forms.Button> -Steuerelement auf dem <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement ablegen, bewegen Sie den Mauszeiger umher, um zu verfolgen, wie sich die Einfügemarke bewegt.

2. Legen Sie das neue <xref:System.Windows.Forms.Button> -Steuerelement auf dem <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement ab. Beachten Sie, dass das neue <xref:System.Windows.Forms.Button> -Steuerelement nicht an den anderen ausgerichtet ist, da seine <xref:System.Windows.Forms.Control.Margin%2A> -Eigenschaft einen anderen Wert aufweist.

## <a name="reassigning-existing-controls-to-a-different-parent"></a>Erneutes Zuweisen von vorhandenen Steuerelementen zu einem anderen übergeordneten Element
 Sie können auf Ihrem Formular vorhandene Steuerelemente einem neuen <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement zuordnen.

### <a name="to-reparent-existing-controls"></a>So weisen Sie vorhandene Steuerelemente einem anderen übergeordneten Steuerelement zu

1. Ziehen Sie drei <xref:System.Windows.Forms.Button> -Steuerelemente aus der **Toolbox** auf das Formular. Positionieren Sie sie nahe beieinander, ohne sie aber auszurichten.

2. Klicken Sie in der **Toolbox**auf das Symbol des <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements. Ziehen Sie es nicht auf das Formular.

3. Bewegen Sie den Mauszeiger in die Nähe der drei <xref:System.Windows.Forms.Button> -Steuerelemente. Beachten Sie, dass der Mauszeiger die Form eines Fadenkreuzes annimmt, an das das Symbol des <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements angefügt ist.

4. Klicken Sie, und halten Sie die Maustaste gedrückt.

5. Ziehen Sie den Mauszeiger, um die Kontur des <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements zu zeichnen. Ziehen Sie die Kontur um die drei <xref:System.Windows.Forms.Button> -Steuerelemente.

6. Lassen Sie die Maustaste los. Beachten Sie, dass die drei <xref:System.Windows.Forms.Button> -Steuerelemente in das <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement eingefügt werden.

## <a name="next-steps"></a>Nächste Schritte
 Mithilfe einer Kombination aus Layoutbereichen und Steuerelementen können Sie ein komplexes Layout verwirklichen. Mit folgenden Funktionen können Sie Ihre Fähigkeiten vertiefen:

- Erhöhen Sie die Größe eines der <xref:System.Windows.Forms.Button> -Steuerelemente, und beobachten Sie die Auswirkung auf das Layout.

- Layoutbereiche können andere Layoutbereiche enthalten. Experimentieren Sie mit dem Ablegen eines <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelements auf dem vorhandenen Steuerelement.

- Docken Sie das <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement am übergeordneten Formular an. Ändern Sie die Größe des Formulars, und beobachten Sie die Auswirkung auf das Layout.

- Legen Sie die <xref:System.Windows.Forms.Control.Visible%2A> -Eigenschaft eines der Steuerelemente auf `false` fest, und beobachten Sie, wie das <xref:System.Windows.Forms.FlowLayoutPanel> als Antwort darauf einen neuen Umbruch durchführt.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Übersicht über die AutoSize-Eigenschaft](autosize-property-overview.md)
- [Gewusst wie: Andocken von Steuerelementen in Windows Forms](how-to-dock-controls-on-windows-forms.md)
- [Gewusst wie: Verankern von Steuerelementen in Windows Forms](how-to-anchor-controls-on-windows-forms.md)
- [Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft](windows-forms-controls-padding-autosize.md)
