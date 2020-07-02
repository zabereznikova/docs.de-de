---
title: Anordnen von Steuerelementen mithilfe von TableLayoutPanel
description: Erfahren Sie, wie Sie Steuerelemente auf dem Windows Forms mit dem FlowLayoutPanel-Steuerelement und dem TableLayoutPanel-Steuerelement anordnen.
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with TableLayoutPanel
- TableLayoutPanel control [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d474885e-12cc-4ab7-b997-2a23a643049b
ms.openlocfilehash: 6dfc6dbdef38d635dc94877f79a8e3659295bd98
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622795"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel"></a>Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel

Einige Anwendungen erfordern ein Formular mit einem Layout, das sich selbst entsprechend neu anordnet, wenn sich die Größe des Formulars oder des Inhalts ändert. Wenn Sie ein dynamisches Layout benötigen und <xref:System.Windows.Forms.Control.Layout> -Ereignisse nicht explizit im Code verarbeiten möchten, ziehen Sie die Verwendung eines Layoutbereichs in Erwägung.

Das <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement und das <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement stellen intuitive Verfahren zum Anordnen von Steuerelementen auf Formularen dar. Beide bieten die Möglichkeit, die relativen Positionen der in ihnen enthaltenen untergeordneten Steuerelemente automatisch und konfigurierbar zu steuern, und beide stellen dynamische Layoutfunktionen zur Laufzeit zur Verfügung, sodass sie Größe und Position von untergeordneten Steuerelementen ändern können, wenn sich die Abmessungen des übergeordneten Formulars ändern. Layoutbereiche können in Layoutbereichen geschachtelt werden, um die Realisierung raffinierter Benutzeroberflächen zu ermöglichen.

Das <xref:System.Windows.Forms.FlowLayoutPanel> ordnet seinen Inhalt in einer bestimmten Flussrichtung an: horizontal oder vertikal. Dieser Inhalt kann von einer Zeile zur nächsten oder von einer Spalte zur nächsten umbrochen werden. Alternativ kann dieser Inhalt abgeschnitten werden, statt dass er umbrochen wird. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Anordnen von Steuerelementen auf Windows Forms mithilfe von FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).

Das <xref:System.Windows.Forms.TableLayoutPanel> ordnet seinen Inhalt in einem Raster an und bietet ähnliche Funktionen wie das HTML-- \<table> Element. Mit dem- <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement können Sie Steuerelemente in einem Raster Layout platzieren, ohne dass Sie genau die Position der einzelnen Steuerelemente angeben müssen. Seine Zellen sind in Zeilen und Spalten angeordnet, und diese können verschiedene Größen haben. Zellen können über Zeilen und Spalten hinweg zusammengeführt werden. Zellen können alles enthalten, was ein Formular enthalten kann und sich in den meisten anderen Punkten als Container verhält.

Das- <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement stellt zur Laufzeit auch eine proportionale Größen Änderungs Funktion bereit, sodass sich das Layout reibungslos ändern kann, wenn die Größe des Formulars geändert wird. Dadurch eignet sich das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement gut für Zwecke wie Dateneingabeformulare und lokalisierte Anwendungen. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Erstellen eines in der Größe geänderten Windows Forms für die Dateneingabe](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)) und Exemplarische Vorgehensweise [: Erstellen eines lokalisierbaren Windows-Formulars](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).

Im Allgemeinen sollten Sie kein-Steuerelement <xref:System.Windows.Forms.TableLayoutPanel> als Container für das gesamte Layout verwenden. Verwenden <xref:System.Windows.Forms.TableLayoutPanel> Sie-Steuerelemente, um Teile des Layouts proportional zum Ändern der Größe bereitzustellen.

In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:

- Erstellen eines Windows Forms-Projekts

- Anordnen von Steuerelementen in Zeilen und Spalten

- Festlegen von Zeilen-und Spalten Eigenschaften

- Umspannen von Zeilen und Spalten mit einem-Steuerelement

- Automatische Behandlung von Überläufen

- Einfügen von Steuerelementen durch Doppelklicken in der Toolbox

- Einfügen eines Steuerelements durch Zeichnen seiner Kontur

- Erneutes Zuweisen von vorhandenen Steuerelementen zu einem anderen übergeordneten Element

Wenn Sie diese Aufgaben durchgearbeitet haben, besitzen Sie ein Verständnis für die Rolle, die diese wichtigen Layoutfunktionen spielen.

## <a name="creating-the-project"></a>Erstellen des Projekts

Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.

#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt

1. Erstellen Sie ein Windows-Anwendungsprojekt mit dem Namen "TableLayoutPanelExample". Weitere Informationen finden Sie unter Vorgehens [Weise: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) .

2. Wählen Sie das Formular im **Windows** **Forms-Designer**aus.

## <a name="arranging-controls-in-rows-and-columns"></a>Anordnen von Steuerelementen in Zeilen und Spalten

Das- <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement ermöglicht Ihnen das einfache Anordnen von Steuerelementen in Zeilen und Spalten.

#### <a name="to-arrange-controls-in-rows-and-columns-using-a-tablelayoutpanel"></a>So ordnen Sie Steuerelemente in Zeilen und Spalten mithilfe von TableLayoutPanel an

1. Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular. Beachten Sie, dass das Steuerelement standardmäßig <xref:System.Windows.Forms.TableLayoutPanel> über vier Zellen verfügt.

2. Ziehen <xref:System.Windows.Forms.Button> Sie ein-Steuerelement aus der **Toolbox** in das-Steuerelement, <xref:System.Windows.Forms.TableLayoutPanel> und legen Sie es in einer der Zellen ab. Beachten Sie, dass das- <xref:System.Windows.Forms.Button> Steuerelement in der ausgewählten Zelle erstellt wird.

3. Ziehen Sie drei weitere <xref:System.Windows.Forms.Button> Steuerelemente aus der **Toolbox** in das- <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement, damit jede Zelle eine Schaltfläche enthält.

4. Ziehen Sie das vertikale Größen Zieh Punkt zwischen den beiden Spalten, und verschieben Sie ihn nach links. Beachten Sie, dass die Größe der Steuer <xref:System.Windows.Forms.Button> Elemente in der ersten Spalte in eine geringere Breite geändert wird, während die Größe der Steuer <xref:System.Windows.Forms.Button> Elemente in der zweiten Spalte unverändert bleibt.

5. Ziehen Sie das vertikale Größen Zieh Punkt zwischen den beiden Spalten, und verschieben Sie ihn nach rechts. Beachten Sie, dass die Steuer <xref:System.Windows.Forms.Button> Elemente in der ersten Spalte auf Ihre ursprüngliche Größe zurückkehren, während die Steuer <xref:System.Windows.Forms.Button> Elemente in der zweiten Spalte nach rechts verschoben werden.

6. Bewegen Sie den horizontalen Größen Zieh Punkt nach oben und unten, um die Auswirkung auf die Steuerelemente im Panel anzuzeigen.

## <a name="positioning-controls-within-cells-using-docking-and-anchoring"></a>Positionieren von Steuerelementen in Zellen mit Andocken und verankern

Das Verankerungs Verhalten von untergeordneten Steuerelementen in einem unter <xref:System.Windows.Forms.TableLayoutPanel> scheidet sich vom Verhalten in anderen Container Steuerelementen. Das Andock Verhalten von untergeordneten Steuerelementen ist identisch mit anderen Container Steuerelementen.

#### <a name="positioning-controls-within-cells"></a>Positionieren von Steuerelementen in Zellen

1. Wählen Sie das erste Steuerelement aus <xref:System.Windows.Forms.Button> . Legen Sie den Wert seiner <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill>fest. Beachten Sie, dass das <xref:System.Windows.Forms.Button> Steuerelement erweitert wird, um seine Zelle auszufüllen.

2. Wählen Sie eines der anderen Steuer <xref:System.Windows.Forms.Button> Elemente aus. Legen Sie den Wert seiner <xref:System.Windows.Forms.Control.Anchor%2A> -Eigenschaft auf <xref:System.Windows.Forms.AnchorStyles.Right>fest. Beachten Sie, dass Sie verschoben wird, sodass sich der Rechte Rahmen in der Nähe des rechten Rahmens der Zelle befindet. Der Abstand zwischen den Rahmen ist die Summe aus der <xref:System.Windows.Forms.Button> -Eigenschaft des-Steuer Elements <xref:System.Windows.Forms.Control.Margin%2A> und der-Eigenschaft des-Panels <xref:System.Windows.Forms.Control.Padding%2A> .

3. Ändern Sie den Wert der <xref:System.Windows.Forms.Button> -Eigenschaft des-Steuer Elements <xref:System.Windows.Forms.Control.Anchor%2A> in <xref:System.Windows.Forms.AnchorStyles.Right> und <xref:System.Windows.Forms.AnchorStyles.Left> . Beachten Sie, dass die Größe des Steuer Elements auf die Breite der Zelle festgelegt wird, wobei die <xref:System.Windows.Forms.Control.Margin%2A> Werte und berücksichtigt werden <xref:System.Windows.Forms.Control.Padding%2A> .

4. Wiederholen Sie die Schritte 2 und 3 mit den <xref:System.Windows.Forms.AnchorStyles.Top> <xref:System.Windows.Forms.AnchorStyles.Bottom> Stilen und.

## <a name="setting-row-and-column-properties"></a>Festlegen von Zeilen-und Spalten Eigenschaften

Sie können einzelne Eigenschaften von Zeilen und Spalten mit den-und-Auflistungen festlegen <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> .

#### <a name="to-set-row-and-column-properties"></a>So legen Sie Zeilen-und Spalten Eigenschaften fest

1. Wählen Sie <xref:System.Windows.Forms.TableLayoutPanel> im **Windows Forms-Designer**das Steuerelement aus.

2. Öffnen Sie im Fenster **Eigenschaften** die Auflistung, indem Sie auf die Schaltfläche mit den Auslassungs Punkten ( <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> ![ ...) in der Eigenschaftenfenster der Visual Studio. ](./media/visual-studio-ellipsis-button.png) )-Schaltfläche neben dem Eintrag **Spalten** klicken.

3. Wählen Sie die erste Spalte aus, und ändern Sie den Wert der- <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> Eigenschaft in <xref:System.Windows.Forms.SizeType.AutoSize> . Klicken Sie auf **OK**, um die Änderung anzunehmen. Beachten Sie, dass die Breite der ersten Spalte so reduziert wird, dass Sie dem Steuerelement entspricht <xref:System.Windows.Forms.Button> . Beachten Sie außerdem, dass die Breite der Spalte nicht geändert werden kann.

4. Öffnen Sie im Fenster **Eigenschaften** die Auflistung, <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> und wählen Sie die erste Spalte aus. Legen Sie den Wert seiner <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> -Eigenschaft auf <xref:System.Windows.Forms.SizeType.Percent>fest. Klicken Sie auf **OK**, um die Änderung anzunehmen. Ändern Sie die Größe des <xref:System.Windows.Forms.TableLayoutPanel> Steuer Elements in eine größere Breite, und beachten Sie, dass die Breite der ersten Spalte erweitert wird. Ändern Sie die Größe des Steuer Elements in <xref:System.Windows.Forms.TableLayoutPanel> eine geringere Breite. Beachten Sie, dass die Schaltflächen in der ersten Spalte an die Zelle angepasst werden. Beachten Sie auch, dass die Breite der Spalte in der Größe geändert werden kann.

5. Öffnen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> Auflistung, und wählen Sie alle aufgelisteten Spalten aus. Legen Sie den Wert jeder <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> Eigenschaft auf fest <xref:System.Windows.Forms.SizeType.Percent> . Klicken Sie auf **OK**, um die Änderung anzunehmen. Mit der Auflistung wiederholen <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> .

6. Ziehen Sie eine der Größen Zieh Punkte der Ecke, und ändern Sie die Breite und Höhe des <xref:System.Windows.Forms.TableLayoutPanel> Steuer Elements. Beachten Sie, dass die Größe der Zeilen und Spalten geändert wird, wenn sich die <xref:System.Windows.Forms.TableLayoutPanel> Größe des Steuer Elements ändert. Beachten Sie außerdem, dass die Größe der Zeilen und Spalten mit den horizontalen und vertikalen Größen Anpassungs Handles geändert werden können.

## <a name="spanning-rows-and-columns-with-a-control"></a>Umspannen von Zeilen und Spalten mit einem-Steuerelement

Das- <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement fügt Steuerelementen zur Entwurfszeit mehrere neue Eigenschaften hinzu. Zwei dieser Eigenschaften sind `RowSpan` und `ColumnSpan` . Sie können diese Eigenschaften verwenden, um ein Steuerelement auf mehr als eine Zeile oder Spalte zu überspannen.

#### <a name="to-span-rows-and-columns-with-a-control"></a>So spannen Sie Zeilen und Spalten mit einem-Steuerelement aus

1. Wählen Sie das <xref:System.Windows.Forms.Button> Steuerelement in der ersten Zeile und ersten Spalte aus.

2. Ändern Sie im Fenster **Eigenschaften** den Wert der- `ColumnSpan` Eigenschaft in **2**. Beachten Sie, dass das <xref:System.Windows.Forms.Button> -Steuerelement die erste und die zweite Spalte ausfüllt. Beachten Sie auch, dass eine zusätzliche Zeile hinzugefügt wurde, um dieser Änderung Rechnung zu tragen.

3. Wiederholen Sie Schritt 2 für die- `RowSpan` Eigenschaft.

## <a name="inserting-controls-by-double-clicking-them-in-the-toolbox"></a>Einfügen von Steuerelementen durch Doppelklicken in der Toolbox

Sie können Ihr <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement auffüllen, indem Sie in der **Toolbox**auf Steuerelemente doppelklicken.

#### <a name="to-insert-controls-by-double-clicking-in-the-toolbox"></a>So fügen Sie Steuerelemente durch Doppelklicken in der Toolbox ein

1. Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.

2. Doppelklicken Sie auf das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements in der **Toolbox**. Beachten Sie, dass ein neues Button-Steuerelement in der ersten Zelle des Steuer Elements angezeigt wird <xref:System.Windows.Forms.TableLayoutPanel> .

3. Doppelklicken Sie in der **Toolbox**auf verschiedene weitere Steuerelemente. Beachten Sie, dass die neuen Steuerelemente nacheinander in den nicht belegten Zellen des Steuer Elements angezeigt werden <xref:System.Windows.Forms.TableLayoutPanel> . Beachten Sie auch, dass das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement erweitert wird, um die neuen Steuerelemente aufzunehmen, wenn keine geöffneten Zellen verfügbar sind.

## <a name="automatic-handling-of-overflows"></a>Automatische Behandlung von Überläufen

Wenn Sie Steuerelemente in das- <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement einfügen, stehen Ihnen möglicherweise leere Zellen für die neuen Steuerelemente zur Verfügung. Das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement behandelt diese Situation automatisch durch Erhöhen der Anzahl von Zellen.

#### <a name="to-observe-automatic-handling-of-overflows"></a>So beobachten Sie die automatische Handhabung von Überläufen

1. Wenn im Steuerelement noch leere Zellen vorhanden sind <xref:System.Windows.Forms.TableLayoutPanel> , fahren Sie mit <xref:System.Windows.Forms.Button> dem Einfügen neuer Steuerelemente fort, bis das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement voll ist.

2. Wenn das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement voll ist, doppelklicken Sie auf das <xref:System.Windows.Forms.Button> Symbol in der **Toolbox** , um ein weiteres Steuerelement einzufügen <xref:System.Windows.Forms.Button> . Beachten Sie, dass das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement neue Zellen erstellt, um das neue Steuerelement aufnehmen zu können Fügen Sie einige weitere Steuerelemente ein, und beobachten Sie das Verhalten beim Ändern der Größe.

3. Ändern Sie den Wert der <xref:System.Windows.Forms.TableLayoutPanel> -Eigenschaft des <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> -Steuerelements in <xref:System.Windows.Forms.TableLayoutPanelGrowStyle.FixedSize>. Doppelklicken Sie auf das <xref:System.Windows.Forms.Button> Symbol in der **Toolbox** , um die Steuerelemente einzufügen, <xref:System.Windows.Forms.Button> bis das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement voll ist. Doppelklicken Sie erneut auf das <xref:System.Windows.Forms.Button> Symbol in der **Toolbox** . Beachten Sie, dass Sie eine Fehlermeldung vom **Windows Forms-Designer** erhalten, in der Sie darüber informiert werden, dass keine zusätzlichen Zeilen und Spalten erstellt werden können.

## <a name="inserting-a-control-by-drawing-its-outline"></a>Einfügen eines Steuerelements durch Zeichnen seiner Kontur

Sie können ein Steuerelement in ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement einfügen und seine Größe angeben, indem Sie in einer Zelle seine Kontur zeichnen.

#### <a name="to-insert-a-control-by-drawing-its-outline"></a>So fügen Sie ein Steuerelement ein, indem Sie seine Kontur zeichnen

1. Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.

2. Klicken Sie in der **Toolbox**auf das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements. Ziehen Sie es nicht auf das Formular.

3. Bewegen Sie den Mauszeiger auf das <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement. Beachten Sie, dass der Mauszeiger die Form eines Fadenkreuzes annimmt, an das das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements angefügt ist.

4. Klicken Sie, und halten Sie die Maustaste gedrückt.

5. Ziehen Sie den Mauszeiger, um die Kontur des <xref:System.Windows.Forms.Button> -Steuerelements zu zeichnen. Wenn Sie mit der Größe zufrieden sind, geben Sie die Maustaste frei. Beachten Sie, dass das <xref:System.Windows.Forms.Button> Steuerelement in der Zelle erstellt wird, in der Sie die Gliederung des Steuer Elements gezeichnet haben.

## <a name="multiple-controls-within-cells-are-not-permitted"></a>Mehrere Steuerelemente in Zellen sind nicht zulässig.

Das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement kann nur ein untergeordnetes Steuerelement pro Zelle enthalten.

#### <a name="to-demonstrate-that-multiple-controls-within-cells-are-not-permitted"></a>So zeigen Sie, dass mehrere Steuerelemente in Zellen nicht zulässig sind

- Ziehen <xref:System.Windows.Forms.Button> Sie ein-Steuerelement aus der **Toolbox** in das-Steuerelement, <xref:System.Windows.Forms.TableLayoutPanel> und legen Sie es in einer der besetzten Zellen ab. Beachten Sie, dass das Steuerelement das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement nicht <xref:System.Windows.Forms.Button> in der besetzten Zelle ablegen kann.

## <a name="swapping-controls"></a>Austauschen von Steuerelementen

Mit dem- <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement können Sie die Steuerelemente austauschen, die zwei verschiedene Zellen belegen.

#### <a name="to-swap-controls"></a>Zum Austauschen von Steuerelementen

- Ziehen Sie eines der Steuer <xref:System.Windows.Forms.Button> Elemente aus einer besetzten Zelle, und legen Sie in eine andere besetzte Zelle ab. Beachten Sie, dass die beiden-Steuerelemente von einer Zelle in die andere verschoben werden.

## <a name="next-steps"></a>Nächste Schritte

Mithilfe einer Kombination aus Layoutbereichen und Steuerelementen können Sie ein komplexes Layout verwirklichen. Mit folgenden Funktionen können Sie Ihre Fähigkeiten vertiefen:

- Ändern Sie die Größe eines der Steuer <xref:System.Windows.Forms.Button> Elemente in eine größere Größe, und notieren Sie sich die Auswirkung auf das Layout.

- Fügen Sie mehrere Steuerelemente in das-Steuerelement ein, <xref:System.Windows.Forms.TableLayoutPanel> und notieren Sie sich, wie die Steuerelemente eingefügt werden.

- Layoutbereiche können andere Layoutbereiche enthalten. Experimentieren Sie mit dem Ablegen eines <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelements auf dem vorhandenen Steuerelement.

- Docken Sie das <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement am übergeordneten Formular an. Ändern Sie die Größe des Formulars, und beobachten Sie die Auswirkung auf das Layout.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Exemplarische Vorgehensweise: Erstellen eines in der Größe veränderbaren Windows Forms für die Dateneingabe](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))
- [Exemplarische Vorgehensweise: Erstellen eines lokalisierbaren Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100))
- [Empfohlene Vorgehensweisen für das TableLayoutPanel-Steuerelement](best-practices-for-the-tablelayoutpanel-control.md)
- [Übersicht über die AutoSize-Eigenschaft](autosize-property-overview.md)
- [Gewusst wie: Andocken von Steuerelementen in Windows Forms](how-to-dock-controls-on-windows-forms.md)
- [Gewusst wie: Verankern von Steuerelementen in Windows Forms](how-to-anchor-controls-on-windows-forms.md)
- [Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft](windows-forms-controls-padding-autosize.md)
