---
title: 'Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with TableLayoutPanel
- TableLayoutPanel control [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d474885e-12cc-4ab7-b997-2a23a643049b
ms.openlocfilehash: 289a8427540c713758c3f155e72efffe9f3c85bc
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "69666805"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel"></a>Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel

Einige Anwendungen erfordern ein Formular mit einem Layout, das sich selbst entsprechend neu anordnet, wenn sich die Größe des Formulars oder des Inhalts ändert. Wenn Sie ein dynamisches Layout benötigen und <xref:System.Windows.Forms.Control.Layout> -Ereignisse nicht explizit im Code verarbeiten möchten, ziehen Sie die Verwendung eines Layoutbereichs in Erwägung.

Das <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement und das <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement stellen intuitive Verfahren zum Anordnen von Steuerelementen auf Formularen dar. Beide bieten die Möglichkeit, die relativen Positionen der in ihnen enthaltenen untergeordneten Steuerelemente automatisch und konfigurierbar zu steuern, und beide stellen dynamische Layoutfunktionen zur Laufzeit zur Verfügung, sodass sie Größe und Position von untergeordneten Steuerelementen ändern können, wenn sich die Abmessungen des übergeordneten Formulars ändern. Layoutbereiche können in Layoutbereichen geschachtelt werden, um die Realisierung raffinierter Benutzeroberflächen zu ermöglichen.

Das <xref:System.Windows.Forms.FlowLayoutPanel> ordnet seinen Inhalt in einer bestimmten Flussrichtung an: horizontal oder vertikal. Dieser Inhalt kann von einer Zeile zur nächsten oder von einer Spalte zur nächsten umbrochen werden. Alternativ kann dieser Inhalt abgeschnitten werden, statt dass er umbrochen wird. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe eines FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)-Elements.

Ordnet seinen Inhalt in einem Raster an und bietet ähnliche Funktionen wie die HTML \<-Tabelle >-Elements. <xref:System.Windows.Forms.TableLayoutPanel> Mit <xref:System.Windows.Forms.TableLayoutPanel> dem-Steuerelement können Sie Steuerelemente in einem Raster Layout platzieren, ohne dass Sie genau die Position der einzelnen Steuerelemente angeben müssen. Seine Zellen sind in Zeilen und Spalten angeordnet, und diese können verschiedene Größen haben. Zellen können über Zeilen und Spalten hinweg zusammengeführt werden. Zellen können alles enthalten, was ein Formular enthalten kann und sich in den meisten anderen Punkten als Container verhält.

Das <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement stellt zur Laufzeit auch eine proportionale Größen Änderungs Funktion bereit, sodass sich das Layout reibungslos ändern kann, wenn die Größe des Formulars geändert wird. Dadurch eignet sich <xref:System.Windows.Forms.TableLayoutPanel> das Steuerelement gut für Zwecke wie Dateneingabeformulare und lokalisierte Anwendungen. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen eines in der Größe geänderten Windows Forms für](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)) die [Dateneingabe und Exemplarische Vorgehensweise: Erstellen eines lokalisierbaren](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100))Windows Forms.

Im Allgemeinen sollten Sie kein- <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement als Container für das gesamte Layout verwenden. Verwenden <xref:System.Windows.Forms.TableLayoutPanel> Sie-Steuerelemente, um Teile des Layouts proportional zum Ändern der Größe bereitzustellen.

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

1. Erstellen Sie ein Windows-Anwendungsprojekt mit dem Namen "TableLayoutPanelExample". Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie ein Windows Forms-](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Anwendungsprojekt.

2. Wählen Sie das Formular im **Windows** **Forms-Designer**aus.

## <a name="arranging-controls-in-rows-and-columns"></a>Anordnen von Steuerelementen in Zeilen und Spalten

Das <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement ermöglicht Ihnen das einfache Anordnen von Steuerelementen in Zeilen und Spalten.

#### <a name="to-arrange-controls-in-rows-and-columns-using-a-tablelayoutpanel"></a>So ordnen Sie Steuerelemente in Zeilen und Spalten mithilfe von TableLayoutPanel an

1. Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular. Beachten Sie, dass das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement standardmäßig über vier Zellen verfügt.

2. Ziehen Sie <xref:System.Windows.Forms.Button> ein-Steuerelement aus der <xref:System.Windows.Forms.TableLayoutPanel> **Toolbox** in das-Steuerelement, und legen Sie es in einer der Zellen ab. Beachten Sie, <xref:System.Windows.Forms.Button> dass das-Steuerelement in der ausgewählten Zelle erstellt wird.

3. Ziehen Sie drei <xref:System.Windows.Forms.Button> weitere Steuerelemente aus der **Toolbox** in das <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement, damit jede Zelle eine Schaltfläche enthält.

4. Ziehen Sie das vertikale Größen Zieh Punkt zwischen den beiden Spalten, und verschieben Sie ihn nach links. Beachten Sie, <xref:System.Windows.Forms.Button> dass die Größe der Steuerelemente in der ersten Spalte in eine geringere Breite geändert wird, <xref:System.Windows.Forms.Button> während die Größe der Steuerelemente in der zweiten Spalte unverändert bleibt.

5. Ziehen Sie das vertikale Größen Zieh Punkt zwischen den beiden Spalten, und verschieben Sie ihn nach rechts. Beachten Sie, <xref:System.Windows.Forms.Button> dass die Steuerelemente in der ersten Spalte auf Ihre ursprüngliche Größe zurück <xref:System.Windows.Forms.Button> kehren, während die Steuerelemente in der zweiten Spalte nach rechts verschoben werden.

6. Bewegen Sie den horizontalen Größen Zieh Punkt nach oben und unten, um die Auswirkung auf die Steuerelemente im Panel anzuzeigen.

## <a name="positioning-controls-within-cells-using-docking-and-anchoring"></a>Positionieren von Steuerelementen in Zellen mit Andocken und verankern

Das Verankerungs Verhalten von untergeordneten Steuer <xref:System.Windows.Forms.TableLayoutPanel> Elementen in einem unterscheidet sich vom Verhalten in anderen Container Steuerelementen. Das Andock Verhalten von untergeordneten Steuerelementen ist identisch mit anderen Container Steuerelementen.

#### <a name="positioning-controls-within-cells"></a>Positionieren von Steuerelementen in Zellen

1. Wählen Sie das <xref:System.Windows.Forms.Button> erste Steuerelement aus. Legen Sie den Wert seiner <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill>fest. Beachten Sie, <xref:System.Windows.Forms.Button> dass das Steuerelement erweitert wird, um seine Zelle auszufüllen.

2. Wählen Sie eines der anderen <xref:System.Windows.Forms.Button> Steuerelemente aus. Legen Sie den Wert seiner <xref:System.Windows.Forms.Control.Anchor%2A> -Eigenschaft auf <xref:System.Windows.Forms.AnchorStyles.Right>fest. Beachten Sie, dass Sie verschoben wird, sodass sich der Rechte Rahmen in der Nähe des rechten Rahmens der Zelle befindet. Der Abstand zwischen den Rahmen ist die Summe aus <xref:System.Windows.Forms.Button> der-Eigenschaft des- <xref:System.Windows.Forms.Control.Margin%2A> Steuer Elements und <xref:System.Windows.Forms.Control.Padding%2A> der-Eigenschaft des-Panels.

3. Ändern Sie den Wert der <xref:System.Windows.Forms.Button> -Eigenschaft <xref:System.Windows.Forms.Control.Anchor%2A> des- <xref:System.Windows.Forms.AnchorStyles.Right> Steuer <xref:System.Windows.Forms.AnchorStyles.Left>Elements in und. Beachten Sie, dass die Größe des Steuer Elements auf die Breite der Zelle fest <xref:System.Windows.Forms.Control.Margin%2A> gelegt <xref:System.Windows.Forms.Control.Padding%2A> wird, wobei die Werte und berücksichtigt werden.

4. Wiederholen Sie die Schritte 2 und <xref:System.Windows.Forms.AnchorStyles.Top> 3 <xref:System.Windows.Forms.AnchorStyles.Bottom> mit den Stilen und.

## <a name="setting-row-and-column-properties"></a>Festlegen von Zeilen-und Spalten Eigenschaften

Sie können einzelne Eigenschaften von Zeilen und Spalten mit den <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> -und- <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> Auflistungen festlegen.

#### <a name="to-set-row-and-column-properties"></a>So legen Sie Zeilen-und Spalten Eigenschaften fest

1. Wählen Sie <xref:System.Windows.Forms.TableLayoutPanel> im **Windows Forms-Designer**das Steuerelement aus.

2. Öffnen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> Auflistung, indem Sie auf![die Schaltfläche mit den Auslassungs Punkten (...) in der Eigenschaftenfenster der Visual Studio](./media/visual-studio-ellipsis-button.png).)-Schaltfläche neben dem Eintrag **Spalten** klicken.

3. Wählen Sie die erste Spalte aus, und ändern Sie <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> den Wert <xref:System.Windows.Forms.SizeType.AutoSize>der-Eigenschaft in. Klicken Sie auf **OK** , um die Änderung zu übernehmen. Beachten Sie, dass die Breite der ersten Spalte so reduziert wird, <xref:System.Windows.Forms.Button> dass Sie dem Steuerelement entspricht. Beachten Sie außerdem, dass die Breite der Spalte nicht geändert werden kann.

4. Öffnen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> Auflistung, und wählen Sie die erste Spalte aus. Legen Sie den Wert seiner <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> -Eigenschaft auf <xref:System.Windows.Forms.SizeType.Percent>fest. Klicken Sie auf **OK** , um die Änderung zu übernehmen. Ändern Sie die <xref:System.Windows.Forms.TableLayoutPanel> Größe des Steuer Elements in eine größere Breite, und beachten Sie, dass die Breite der ersten Spalte erweitert wird. Ändern Sie die <xref:System.Windows.Forms.TableLayoutPanel> Größe des Steuer Elements in eine geringere Breite. Beachten Sie, dass die Schaltflächen in der ersten Spalte an die Zelle angepasst werden. Beachten Sie auch, dass die Breite der Spalte in der Größe geändert werden kann.

5. Öffnen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> Auflistung, und wählen Sie alle aufgelisteten Spalten aus. Legen Sie den Wert jeder <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> Eigenschaft auf <xref:System.Windows.Forms.SizeType.Percent>fest. Klicken Sie auf **OK** , um die Änderung zu übernehmen. Mit der <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> Auflistung wiederholen.

6. Ziehen Sie eine der Größen Zieh Punkte der Ecke, und ändern Sie die Breite und Höhe des <xref:System.Windows.Forms.TableLayoutPanel> Steuer Elements. Beachten Sie, dass die Größe der Zeilen und Spalten geändert <xref:System.Windows.Forms.TableLayoutPanel> wird, wenn sich die Größe des Steuer Elements ändert. Beachten Sie außerdem, dass die Größe der Zeilen und Spalten mit den horizontalen und vertikalen Größen Anpassungs Handles geändert werden können.

## <a name="spanning-rows-and-columns-with-a-control"></a>Umspannen von Zeilen und Spalten mit einem-Steuerelement

Das <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement fügt Steuerelementen zur Entwurfszeit mehrere neue Eigenschaften hinzu. Zwei dieser Eigenschaften sind `RowSpan` und. `ColumnSpan` Sie können diese Eigenschaften verwenden, um ein Steuerelement auf mehr als eine Zeile oder Spalte zu überspannen.

#### <a name="to-span-rows-and-columns-with-a-control"></a>So spannen Sie Zeilen und Spalten mit einem-Steuerelement aus

1. Wählen Sie <xref:System.Windows.Forms.Button> das Steuerelement in der ersten Zeile und ersten Spalte aus.

2. Ändern Sie im Fenster **Eigenschaften** den Wert der `ColumnSpan` -Eigenschaft in **2**. Beachten Sie, <xref:System.Windows.Forms.Button> dass das-Steuerelement die erste und die zweite Spalte ausfüllt. Beachten Sie auch, dass eine zusätzliche Zeile hinzugefügt wurde, um dieser Änderung Rechnung zu tragen.

3. Wiederholen Sie Schritt 2 `RowSpan` für die-Eigenschaft.

## <a name="inserting-controls-by-double-clicking-them-in-the-toolbox"></a>Einfügen von Steuerelementen durch Doppelklicken in der Toolbox

Sie können Ihr <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement auffüllen, indem Sie in der **Toolbox**auf Steuerelemente doppelklicken.

#### <a name="to-insert-controls-by-double-clicking-in-the-toolbox"></a>So fügen Sie Steuerelemente durch Doppelklicken in der Toolbox ein

1. Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.

2. Doppelklicken Sie auf das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements in der **Toolbox**. Beachten Sie, dass ein neues Button-Steuer <xref:System.Windows.Forms.TableLayoutPanel> Element in der ersten Zelle des Steuer Elements angezeigt wird.

3. Doppelklicken Sie in der **Toolbox**auf verschiedene weitere Steuerelemente. Beachten Sie, dass die neuen Steuerelemente nacheinander <xref:System.Windows.Forms.TableLayoutPanel> in den nicht belegten Zellen des Steuer Elements angezeigt werden. Beachten Sie auch, <xref:System.Windows.Forms.TableLayoutPanel> dass das Steuerelement erweitert wird, um die neuen Steuerelemente aufzunehmen, wenn keine geöffneten Zellen verfügbar sind.

## <a name="automatic-handling-of-overflows"></a>Automatische Behandlung von Überläufen

Wenn Sie Steuerelemente in das <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement einfügen, stehen Ihnen möglicherweise leere Zellen für die neuen Steuerelemente zur Verfügung. Das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement behandelt diese Situation automatisch durch Erhöhen der Anzahl von Zellen.

#### <a name="to-observe-automatic-handling-of-overflows"></a>So beobachten Sie die automatische Handhabung von Überläufen

1. Wenn im <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement noch leere Zellen vorhanden sind, fahren Sie mit <xref:System.Windows.Forms.Button> dem Einfügen neuer <xref:System.Windows.Forms.TableLayoutPanel> Steuerelemente fort, bis das Steuerelement voll ist.

2. Wenn das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement voll ist, doppelklicken Sie <xref:System.Windows.Forms.Button> auf das Symbol in der **Toolbox** , <xref:System.Windows.Forms.Button> um ein weiteres Steuerelement einzufügen. Beachten Sie, <xref:System.Windows.Forms.TableLayoutPanel> dass das Steuerelement neue Zellen erstellt, um das neue Steuerelement aufnehmen zu können Fügen Sie einige weitere Steuerelemente ein, und beobachten Sie das Verhalten beim Ändern der Größe.

3. Ändern Sie den Wert der <xref:System.Windows.Forms.TableLayoutPanel> -Eigenschaft des <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> -Steuerelements in <xref:System.Windows.Forms.TableLayoutPanelGrowStyle.FixedSize>. Doppelklicken Sie auf <xref:System.Windows.Forms.Button> das Symbol in der **Toolbox** , <xref:System.Windows.Forms.Button> um die Steuer <xref:System.Windows.Forms.TableLayoutPanel> Elemente einzufügen, bis das Steuerelement voll ist. Doppelklicken Sie erneut <xref:System.Windows.Forms.Button> auf das Symbol in der **Toolbox** . Beachten Sie, dass Sie eine Fehlermeldung vom **Windows Forms-Designer** erhalten, in der Sie darüber informiert werden, dass keine zusätzlichen Zeilen und Spalten erstellt werden können.

## <a name="inserting-a-control-by-drawing-its-outline"></a>Einfügen eines Steuerelements durch Zeichnen seiner Kontur

Sie können ein Steuerelement in ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement einfügen und seine Größe angeben, indem Sie in einer Zelle seine Kontur zeichnen.

#### <a name="to-insert-a-control-by-drawing-its-outline"></a>So fügen Sie ein Steuerelement ein, indem Sie seine Kontur zeichnen

1. Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.

2. Klicken Sie in der **Toolbox**auf das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements. Ziehen Sie es nicht auf das Formular.

3. Bewegen Sie den Mauszeiger auf das <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement. Beachten Sie, dass der Mauszeiger die Form eines Fadenkreuzes annimmt, an das das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements angefügt ist.

4. Klicken Sie, und halten Sie die Maustaste gedrückt.

5. Ziehen Sie den Mauszeiger, um die Kontur des <xref:System.Windows.Forms.Button> -Steuerelements zu zeichnen. Wenn Sie mit der Größe zufrieden sind, geben Sie die Maustaste frei. Beachten Sie, <xref:System.Windows.Forms.Button> dass das Steuerelement in der Zelle erstellt wird, in der Sie die Gliederung des Steuer Elements gezeichnet haben.

## <a name="multiple-controls-within-cells-are-not-permitted"></a>Mehrere Steuerelemente in Zellen sind nicht zulässig.

Das <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement kann nur ein untergeordnetes Steuerelement pro Zelle enthalten.

#### <a name="to-demonstrate-that-multiple-controls-within-cells-are-not-permitted"></a>So zeigen Sie, dass mehrere Steuerelemente in Zellen nicht zulässig sind

- Ziehen Sie <xref:System.Windows.Forms.Button> ein-Steuerelement aus der <xref:System.Windows.Forms.TableLayoutPanel> **Toolbox** in das-Steuerelement, und legen Sie es in einer der besetzten Zellen ab. Beachten Sie, <xref:System.Windows.Forms.TableLayoutPanel> dass das Steuerelement das <xref:System.Windows.Forms.Button> Steuerelement nicht in der besetzten Zelle ablegen kann.

## <a name="swapping-controls"></a>Austauschen von Steuerelementen

Mit <xref:System.Windows.Forms.TableLayoutPanel> dem-Steuerelement können Sie die Steuerelemente austauschen, die zwei verschiedene Zellen belegen.

#### <a name="to-swap-controls"></a>Zum Austauschen von Steuerelementen

- Ziehen Sie eines der <xref:System.Windows.Forms.Button> Steuerelemente aus einer besetzten Zelle, und legen Sie in eine andere besetzte Zelle ab. Beachten Sie, dass die beiden-Steuerelemente von einer Zelle in die andere verschoben werden.

## <a name="next-steps"></a>Nächste Schritte

Mithilfe einer Kombination aus Layoutbereichen und Steuerelementen können Sie ein komplexes Layout verwirklichen. Hier sind paar Vorschläge für weitere Experimente:

- Ändern Sie die Größe eines der <xref:System.Windows.Forms.Button> Steuerelemente in eine größere Größe, und notieren Sie sich die Auswirkung auf das Layout.

- Fügen Sie mehrere Steuerelemente in das <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement ein, und notieren Sie sich, wie die Steuerelemente eingefügt werden.

- Layoutbereiche können andere Layoutbereiche enthalten. Experimentieren Sie mit dem Ablegen eines <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelements auf dem vorhandenen Steuerelement.

- Docken Sie das <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement am übergeordneten Formular an. Ändern Sie die Größe des Formulars, und beobachten Sie die Auswirkung auf das Layout.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe von FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe von Richtungslinien](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Microsoft Windows-Benutzeroberfläche, offizielle Richtlinien für Entwickler und Designer von Benutzeroberflächen. Redmond, WA: Microsoft Press, 1999. ("US-MILLIARDE": 0-7356-0566-1)](https://www.microsoft.com/mspress/southpacific/books/book11588.htm)
- [Exemplarische Vorgehensweise: Erstellen eines in der Größe geänderten Windows Forms für die Dateneingabe](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))
- [Exemplarische Vorgehensweise: Erstellen eines lokalisierbaren Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100))
- [Empfohlene Vorgehensweisen für das TableLayoutPanel-Steuerelement](best-practices-for-the-tablelayoutpanel-control.md)
- [Übersicht über die AutoSize-Eigenschaft](autosize-property-overview.md)
- [Vorgehensweise: Steuerelemente auf Windows Forms Andocken](how-to-dock-controls-on-windows-forms.md)
- [Vorgehensweise: Verankern von Steuerelementen auf Windows Forms](how-to-anchor-controls-on-windows-forms.md)
- [Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mit Auffüll Zeichen, Rändern und der AutoSize-Eigenschaft](windows-forms-controls-padding-autosize.md)
