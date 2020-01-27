---
title: Anordnen von Steuerelementen mithilfe von TableLayoutPanel
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with TableLayoutPanel
- TableLayoutPanel control [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d474885e-12cc-4ab7-b997-2a23a643049b
ms.openlocfilehash: 803a56f6416cf3b718890e96cf9f36ae6c4ee471
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740315"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel"></a>Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel

Einige Anwendungen erfordern ein Formular mit einem Layout, das sich selbst entsprechend neu anordnet, wenn sich die Größe des Formulars oder des Inhalts ändert. Wenn Sie ein dynamisches Layout benötigen und <xref:System.Windows.Forms.Control.Layout> -Ereignisse nicht explizit im Code verarbeiten möchten, ziehen Sie die Verwendung eines Layoutbereichs in Erwägung.

Das <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement und das <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement stellen intuitive Verfahren zum Anordnen von Steuerelementen auf Formularen dar. Beide bieten die Möglichkeit, die relativen Positionen der in ihnen enthaltenen untergeordneten Steuerelemente automatisch und konfigurierbar zu steuern, und beide stellen dynamische Layoutfunktionen zur Laufzeit zur Verfügung, sodass sie Größe und Position von untergeordneten Steuerelementen ändern können, wenn sich die Abmessungen des übergeordneten Formulars ändern. Layoutbereiche können in Layoutbereichen geschachtelt werden, um die Realisierung raffinierter Benutzeroberflächen zu ermöglichen.

Das <xref:System.Windows.Forms.FlowLayoutPanel> ordnet seinen Inhalt in einer bestimmten Flussrichtung an: horizontal oder vertikal. Dieser Inhalt kann von einer Zeile zur nächsten oder von einer Spalte zur nächsten umbrochen werden. Alternativ kann dieser Inhalt abgeschnitten werden, statt dass er umbrochen wird. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Anordnen von Steuerelementen auf Windows Forms mithilfe von FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).

Der <xref:System.Windows.Forms.TableLayoutPanel> ordnet seinen Inhalt in einem Raster an und bietet ähnliche Funktionen wie das HTML-\<Table >-Element. Mit dem <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement können Sie Steuerelemente in einem Raster Layout platzieren, ohne dass Sie genau die Position der einzelnen Steuerelemente angeben müssen. Seine Zellen sind in Zeilen und Spalten angeordnet, und diese können verschiedene Größen haben. Zellen können über Zeilen und Spalten hinweg zusammengeführt werden. Zellen können alles enthalten, was ein Formular enthalten kann und sich in den meisten anderen Punkten als Container verhält.

Das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement stellt zur Laufzeit auch eine proportionale Größen Änderungs Funktion bereit, sodass sich das Layout bei der Größenanpassung Ihres Formulars reibungslos ändern kann. Dadurch eignet sich das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement gut für Zwecke wie Dateneingabeformulare und lokalisierte Anwendungen. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Erstellen eines in der Größe geänderten Windows Forms für die Dateneingabe](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)) und Exemplarische Vorgehensweise [: Erstellen eines lokalisierbaren Windows-Formulars](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).

Im Allgemeinen sollten Sie ein <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement nicht als Container für das gesamte Layout verwenden. Verwenden Sie <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelemente, um die Optionen für die proportionale Anpassung an Teile des Layouts bereitzustellen.

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

Das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement ermöglicht das einfache Anordnen von Steuerelementen in Zeilen und Spalten.

#### <a name="to-arrange-controls-in-rows-and-columns-using-a-tablelayoutpanel"></a>So ordnen Sie Steuerelemente in Zeilen und Spalten mithilfe von TableLayoutPanel an

1. Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular. Beachten Sie, dass das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement standardmäßig über vier Zellen verfügt.

2. Ziehen Sie ein <xref:System.Windows.Forms.Button>-Steuerelement aus der **Toolbox** in das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement, und legen Sie es in einer der Zellen ab. Beachten Sie, dass das <xref:System.Windows.Forms.Button>-Steuerelement in der ausgewählten Zelle erstellt wird.

3. Ziehen Sie drei weitere <xref:System.Windows.Forms.Button> Steuerelemente aus der **Toolbox** in das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement, damit jede Zelle eine Schaltfläche enthält.

4. Ziehen Sie das vertikale Größen Zieh Punkt zwischen den beiden Spalten, und verschieben Sie ihn nach links. Beachten Sie, dass die Größe der <xref:System.Windows.Forms.Button> Steuerelemente in der ersten Spalte in eine geringere Breite geändert wird, während die Größe der <xref:System.Windows.Forms.Button> Steuerelemente in der zweiten Spalte unverändert bleibt.

5. Ziehen Sie das vertikale Größen Zieh Punkt zwischen den beiden Spalten, und verschieben Sie ihn nach rechts. Beachten Sie, dass die <xref:System.Windows.Forms.Button>-Steuerelemente in der ersten Spalte auf Ihre ursprüngliche Größe zurückkehren, während die <xref:System.Windows.Forms.Button> Steuerelemente in der zweiten Spalte nach rechts verschoben werden.

6. Bewegen Sie den horizontalen Größen Zieh Punkt nach oben und unten, um die Auswirkung auf die Steuerelemente im Panel anzuzeigen.

## <a name="positioning-controls-within-cells-using-docking-and-anchoring"></a>Positionieren von Steuerelementen in Zellen mit Andocken und verankern

Das Verankerungs Verhalten von untergeordneten Steuerelementen in einem <xref:System.Windows.Forms.TableLayoutPanel> unterscheidet sich vom Verhalten in anderen Container Steuerelementen. Das Andock Verhalten von untergeordneten Steuerelementen ist identisch mit anderen Container Steuerelementen.

#### <a name="positioning-controls-within-cells"></a>Positionieren von Steuerelementen in Zellen

1. Wählen Sie das erste <xref:System.Windows.Forms.Button> Steuerelement aus. Legen Sie den Wert seiner <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill>fest. Beachten Sie, dass das <xref:System.Windows.Forms.Button> Steuerelement erweitert wird, um seine Zelle auszufüllen.

2. Wählen Sie eines der anderen <xref:System.Windows.Forms.Button> Steuerelemente aus. Legen Sie den Wert seiner <xref:System.Windows.Forms.Control.Anchor%2A> -Eigenschaft auf <xref:System.Windows.Forms.AnchorStyles.Right>fest. Beachten Sie, dass Sie verschoben wird, sodass sich der Rechte Rahmen in der Nähe des rechten Rahmens der Zelle befindet. Der Abstand zwischen den Rahmen ist die Summe der <xref:System.Windows.Forms.Control.Margin%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuer Elements und der <xref:System.Windows.Forms.Control.Padding%2A>-Eigenschaft des Bereichs.

3. Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft des <xref:System.Windows.Forms.Button> Steuer Elements in <xref:System.Windows.Forms.AnchorStyles.Right> und <xref:System.Windows.Forms.AnchorStyles.Left>. Beachten Sie, dass die Größe des Steuer Elements auf die Breite der Zelle festgelegt wird, wobei die Werte für <xref:System.Windows.Forms.Control.Margin%2A> und <xref:System.Windows.Forms.Control.Padding%2A> berücksichtigt werden.

4. Wiederholen Sie die Schritte 2 und 3 mit den Formaten <xref:System.Windows.Forms.AnchorStyles.Top> und <xref:System.Windows.Forms.AnchorStyles.Bottom>.

## <a name="setting-row-and-column-properties"></a>Festlegen von Zeilen-und Spalten Eigenschaften

Sie können einzelne Eigenschaften von Zeilen und Spalten mit den <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A>-und <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A>-Auflistungen festlegen.

#### <a name="to-set-row-and-column-properties"></a>So legen Sie Zeilen-und Spalten Eigenschaften fest

1. Wählen Sie im **Windows Forms-Designer**das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement aus.

2. Öffnen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> Auflistung, indem Sie auf die Schaltfläche mit den Auslassungs Punkten (![der Schaltfläche mit den Auslassungs Punkten (...) in der Eigenschaftenfenster der Visual Studio.](./media/visual-studio-ellipsis-button.png))-Schaltfläche neben dem Eintrag **Spalten** klicken.

3. Wählen Sie die erste Spalte aus, und ändern Sie den Wert der <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A>-Eigenschaft in <xref:System.Windows.Forms.SizeType.AutoSize>. Klicken Sie auf **OK** , um die Änderung zu übernehmen. Beachten Sie, dass die Breite der ersten Spalte so reduziert wird, dass Sie dem <xref:System.Windows.Forms.Button>-Steuerelement entspricht. Beachten Sie außerdem, dass die Breite der Spalte nicht geändert werden kann.

4. Öffnen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> Auflistung, und wählen Sie die erste Spalte aus. Legen Sie den Wert seiner <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> -Eigenschaft auf <xref:System.Windows.Forms.SizeType.Percent>fest. Klicken Sie auf **OK** , um die Änderung zu übernehmen. Ändern Sie die Größe des <xref:System.Windows.Forms.TableLayoutPanel> Steuer Elements zu einer größeren Breite, und beachten Sie, dass die Breite der ersten Spalte erweitert wird. Ändern Sie die Größe des <xref:System.Windows.Forms.TableLayoutPanel> Steuer Elements auf eine geringere Breite. Beachten Sie, dass die Schaltflächen in der ersten Spalte an die Zelle angepasst werden. Beachten Sie auch, dass die Breite der Spalte in der Größe geändert werden kann.

5. Öffnen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> Auflistung, und wählen Sie alle aufgelisteten Spalten aus. Legen Sie den Wert jeder <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> Eigenschaft auf <xref:System.Windows.Forms.SizeType.Percent>fest. Klicken Sie auf **OK** , um die Änderung zu übernehmen. Wiederholen Sie diesen Vorgang mit der <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> Auflistung.

6. Ziehen Sie eine der Größen Zieh Punkte der Ecke, und ändern Sie die Breite und Höhe des <xref:System.Windows.Forms.TableLayoutPanel> Steuer Elements. Beachten Sie, dass die Größe der Zeilen und Spalten geändert wird, wenn sich die Größe des <xref:System.Windows.Forms.TableLayoutPanel>-Steuer Elements ändert. Beachten Sie außerdem, dass die Größe der Zeilen und Spalten mit den horizontalen und vertikalen Größen Anpassungs Handles geändert werden können.

## <a name="spanning-rows-and-columns-with-a-control"></a>Umspannen von Zeilen und Spalten mit einem-Steuerelement

Das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement fügt Steuerelementen zur Entwurfszeit mehrere neue Eigenschaften hinzu. Zwei dieser Eigenschaften sind `RowSpan` und `ColumnSpan`. Sie können diese Eigenschaften verwenden, um ein Steuerelement auf mehr als eine Zeile oder Spalte zu überspannen.

#### <a name="to-span-rows-and-columns-with-a-control"></a>So spannen Sie Zeilen und Spalten mit einem-Steuerelement aus

1. Wählen Sie in der ersten Zeile und ersten Spalte das <xref:System.Windows.Forms.Button>-Steuerelement aus.

2. Ändern Sie im Fenster **Eigenschaften** den Wert der `ColumnSpan`-Eigenschaft in **2**. Beachten Sie, dass das <xref:System.Windows.Forms.Button>-Steuerelement die erste und die zweite Spalte ausfüllt. Beachten Sie auch, dass eine zusätzliche Zeile hinzugefügt wurde, um dieser Änderung Rechnung zu tragen.

3. Wiederholen Sie Schritt 2 für die `RowSpan`-Eigenschaft.

## <a name="inserting-controls-by-double-clicking-them-in-the-toolbox"></a>Einfügen von Steuerelementen durch Doppelklicken in der Toolbox

Sie können Ihr <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement auffüllen, indem Sie in der **Toolbox**auf Steuerelemente doppelklicken.

#### <a name="to-insert-controls-by-double-clicking-in-the-toolbox"></a>So fügen Sie Steuerelemente durch Doppelklicken in der Toolbox ein

1. Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.

2. Doppelklicken Sie auf das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements in der **Toolbox**. Beachten Sie, dass ein neues Schaltflächen-Steuerelement in der ersten Zelle des <xref:System.Windows.Forms.TableLayoutPanel> Steuer Elements angezeigt wird.

3. Doppelklicken Sie in der **Toolbox**auf verschiedene weitere Steuerelemente. Beachten Sie, dass die neuen Steuerelemente nacheinander in den nicht belegten Zellen des <xref:System.Windows.Forms.TableLayoutPanel>-Steuer Elements angezeigt werden. Beachten Sie außerdem, dass das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement erweitert wird, um die neuen Steuerelemente aufzunehmen, wenn keine geöffneten Zellen verfügbar sind.

## <a name="automatic-handling-of-overflows"></a>Automatische Behandlung von Überläufen

Wenn Sie Steuerelemente in das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement einfügen, stehen Ihnen möglicherweise leere Zellen für die neuen Steuerelemente zur Verfügung. Das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement behandelt diese Situation automatisch durch Erhöhen der Anzahl von Zellen.

#### <a name="to-observe-automatic-handling-of-overflows"></a>So beobachten Sie die automatische Handhabung von Überläufen

1. Wenn das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement noch leere Zellen enthält, fahren Sie mit dem Einfügen neuer <xref:System.Windows.Forms.Button> Steuerelemente fort, bis das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement voll ist.

2. Wenn das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement voll ist, doppelklicken Sie auf das <xref:System.Windows.Forms.Button> Symbol in der **Toolbox** , um ein weiteres <xref:System.Windows.Forms.Button> Steuerelement einzufügen. Beachten Sie, dass das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement neue Zellen erstellt, um das neue Steuerelement aufnehmen zu können Fügen Sie einige weitere Steuerelemente ein, und beobachten Sie das Verhalten beim Ändern der Größe.

3. Ändern Sie den Wert der <xref:System.Windows.Forms.TableLayoutPanel> -Eigenschaft des <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> -Steuerelements in <xref:System.Windows.Forms.TableLayoutPanelGrowStyle.FixedSize>. Doppelklicken Sie auf das Symbol <xref:System.Windows.Forms.Button> in der **Toolbox** , um <xref:System.Windows.Forms.Button> Steuerelemente einzufügen, bis das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement voll ist. Doppelklicken Sie erneut auf das Symbol <xref:System.Windows.Forms.Button> in der **Toolbox** . Beachten Sie, dass Sie eine Fehlermeldung vom **Windows Forms-Designer** erhalten, in der Sie darüber informiert werden, dass keine zusätzlichen Zeilen und Spalten erstellt werden können.

## <a name="inserting-a-control-by-drawing-its-outline"></a>Einfügen eines Steuerelements durch Zeichnen seiner Kontur

Sie können ein Steuerelement in ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement einfügen und seine Größe angeben, indem Sie in einer Zelle seine Kontur zeichnen.

#### <a name="to-insert-a-control-by-drawing-its-outline"></a>So fügen Sie ein Steuerelement ein, indem Sie seine Kontur zeichnen

1. Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.

2. Klicken Sie in der **Toolbox**auf das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements. Ziehen Sie es nicht auf das Formular.

3. Bewegen Sie den Mauszeiger auf das <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement. Beachten Sie, dass der Mauszeiger die Form eines Fadenkreuzes annimmt, an das das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements angefügt ist.

4. Klicken Sie, und halten Sie die Maustaste gedrückt.

5. Ziehen Sie den Mauszeiger, um die Kontur des <xref:System.Windows.Forms.Button> -Steuerelements zu zeichnen. Wenn Sie mit der Größe zufrieden sind, geben Sie die Maustaste frei. Beachten Sie, dass das <xref:System.Windows.Forms.Button>-Steuerelement in der Zelle erstellt wird, in der Sie die Gliederung des Steuer Elements gezeichnet haben.

## <a name="multiple-controls-within-cells-are-not-permitted"></a>Mehrere Steuerelemente in Zellen sind nicht zulässig.

Das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement kann nur ein untergeordnetes Steuerelement pro Zelle enthalten.

#### <a name="to-demonstrate-that-multiple-controls-within-cells-are-not-permitted"></a>So zeigen Sie, dass mehrere Steuerelemente in Zellen nicht zulässig sind

- Ziehen Sie ein <xref:System.Windows.Forms.Button>-Steuerelement aus der **Toolbox** in das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement, und legen Sie es in einer der besetzten Zellen ab. Beachten Sie, dass das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement nicht zulässt, dass Sie das <xref:System.Windows.Forms.Button>-Steuerelement in der besetzten Zelle ablegen.

## <a name="swapping-controls"></a>Austauschen von Steuerelementen

Mit dem <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement können Sie die Steuerelemente austauschen, die zwei verschiedene Zellen belegen.

#### <a name="to-swap-controls"></a>Zum Austauschen von Steuerelementen

- Ziehen Sie eines der <xref:System.Windows.Forms.Button> Steuerelemente aus einer besetzten Zelle, und legen Sie in eine andere besetzte Zelle ab. Beachten Sie, dass die beiden-Steuerelemente von einer Zelle in die andere verschoben werden.

## <a name="next-steps"></a>Nächste Schritte

Mithilfe einer Kombination aus Layoutbereichen und Steuerelementen können Sie ein komplexes Layout verwirklichen. Hier sind paar Vorschläge für weitere Experimente:

- Ändern Sie die Größe eines der <xref:System.Windows.Forms.Button> Steuerelemente in eine größere Größe, und notieren Sie sich die Auswirkung auf das Layout.

- Fügen Sie mehrere Steuerelemente in das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement ein, und notieren Sie sich, wie die Steuerelemente eingefügt werden.

- Layoutbereiche können andere Layoutbereiche enthalten. Experimentieren Sie mit dem Ablegen eines <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelements auf dem vorhandenen Steuerelement.

- Docken Sie das <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement am übergeordneten Formular an. Ändern Sie die Größe des Formulars, und beobachten Sie die Auswirkung auf das Layout.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Exemplarische Vorgehensweise: Erstellen eines in der Größe veränderbaren Windows Forms für die Dateneingabe](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))
- [Exemplarische Vorgehensweise: Erstellen eines lokalisierbaren Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100))
- [Empfohlene Vorgehensweisen für das TableLayoutPanel-Steuerelement](best-practices-for-the-tablelayoutpanel-control.md)
- [Übersicht über die AutoSize-Eigenschaft](autosize-property-overview.md)
- [Gewusst wie: Andocken von Steuerelementen in Windows Forms](how-to-dock-controls-on-windows-forms.md)
- [Gewusst wie: Verankern von Steuerelementen in Windows Forms](how-to-anchor-controls-on-windows-forms.md)
- [Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft](windows-forms-controls-padding-autosize.md)
