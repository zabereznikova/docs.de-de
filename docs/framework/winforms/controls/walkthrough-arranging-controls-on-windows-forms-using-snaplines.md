---
title: 'Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with snaplines
- snaplines [Windows Forms], arranging Windows Forms controls
- SnapLine class [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
ms.openlocfilehash: 8ac1ba6b8121aabea3c992ca5b943f231fc19ce2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950070"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-snaplines"></a>Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien
Die präzise Platzierung von Steuerelementen auf dem Formular hat für viele Anwendungen einen hohen Stellenwert. Die Windows Forms-Designer bietet Ihnen viele Layouttools, um dies zu erreichen. Eine der wichtigsten Funktionen ist die <xref:System.Windows.Forms.Design.Behavior.SnapLine> -Funktion.

 Mithilfe von Richtungslinien zeigen Sie genau an, wo Sie Steuerelemente mit anderen Steuerelementen ausrichten. Außerdem zeigen Sie die empfohlenen Entfernungen für Ränder zwischen Steuerelementen gemäß den Richtlinien der Windows-Benutzeroberfläche an. Weitere Informationen finden Sie unter [Benutzeroberflächen Entwurf und-Entwicklung](https://go.microsoft.com/FWLink/?LinkId=83878).

 Ausrichtungs Linien erleichtern Ihnen das Ausrichten ihrer Steuerelemente, um die Darstellung und das Verhalten zu optimieren.

 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:

- Erstellen eines Windows Forms-Projekts

- Abstände und Ausrichten von Steuerelementen mithilfe von Ausrichtungs Linien

- Ausrichten an Form-und Container Rändern

- Ausrichten an gruppierten Steuerelementen

- Verwenden von Richtungslinien zum Platzieren eines Steuer Elements durch Gliederung der Größe

- Verwenden von Richtungslinien beim Ziehen eines Steuer Elements aus der Toolbox

- Ändern der Größe von Steuerelementen mithilfe von Richtungslinien

- Ausrichten einer Bezeichnung an den Text eines Steuer Elements

- Verwenden von Richtungslinien mit Tastatur Navigation

- Richtungslinien und Layoutpanels

- Deaktivieren von SnapLines

 Wenn Sie fertig sind, verfügen Sie über ein Verständnis der layoutrolle, die von den Features der Ausrichtungs Linien gespielt wird.

## <a name="creating-the-project"></a>Erstellen des Projekts
 Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.

### <a name="to-create-the-project"></a>So erstellen Sie das Projekt

1. Erstellen Sie ein Windows-basiertes Anwendungsprojekt mit dem Namen "SnaplineExample" (**Datei** > **New** > **Project** >  **C# Visual** oder **Visual Basic** > **Classic** Desktop > **Windows Forms Anwendung**).

2. Wählen Sie das Formular im Forms-Designer aus.

## <a name="spacing-and-aligning-controls-using-snaplines"></a>Abstände und Ausrichten von Steuerelementen mithilfe von Ausrichtungs Linien
 Ausrichtungs Linien verfügen über eine präzise und intuitive Möglichkeit zum Ausrichten von Steuerelementen auf dem Formular. Sie werden angezeigt, wenn Sie ein ausgewähltes Steuerelement oder Steuerelemente in der Nähe einer Position verschieben, die an einem anderen Steuerelement oder einer Gruppe von Steuerelementen ausgerichtet Ihre Auswahl wird an der vorgeschlagenen Position "andocken", während Sie Sie nach den anderen Steuerelementen verschieben.

### <a name="to-arrange-controls-using-snaplines"></a>So ordnen Sie Steuerelemente mithilfe von Richtungslinien an

1. Ziehen Sie ein <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular.

2. Verschieben Sie <xref:System.Windows.Forms.Button> das Steuerelement in die untere rechte Ecke des Formulars. Beachten Sie, dass die Richtungslinien, die <xref:System.Windows.Forms.Button> als Steuerelement angezeigt werden, den unteren und rechten Rand des Formulars nähern. Diese Richtungslinien zeigen den empfohlenen Abstand zwischen den Rändern des Steuer Elements und dem Formular an.

3. Verschieben Sie <xref:System.Windows.Forms.Button> das Steuerelement um die Rahmen des Formulars, und notieren Sie sich, wo die Richtungslinien angezeigt werden. Wenn Sie fertig sind, verschieben Sie <xref:System.Windows.Forms.Button> das Steuerelement in der Mitte des Formulars.

4. Ziehen Sie <xref:System.Windows.Forms.Button> ein anderes Steuerelement aus der **Toolbox** auf das Formular.

5. Verschieben Sie das <xref:System.Windows.Forms.Button> zweite-Steuerelement, bis es sich fast in der ersten befindet. Beachten Sie die Richtungslinie, die in der TextBaseline beider Schaltflächen angezeigt wird, und beachten Sie, dass das Steuerelement, das Sie verschieben, an eine Position mit dem anderen Steuerelement mit dem anderen Steuerelement bewegt wird.

6. Verschieben Sie das <xref:System.Windows.Forms.Button> zweite-Steuerelement, bis es direkt oberhalb des ersten positioniert ist. Beachten Sie die Ausrichtungs Linien, die am linken und rechten Rand beider Schaltflächen angezeigt werden, und beachten Sie, dass das Steuerelement, das Sie verschieben, an eine Position ausgerichtet wird, die exakt am anderen Steuerelement ausgerichtet ist.

7. Wählen Sie eines der <xref:System.Windows.Forms.Button> Steuerelemente aus, und verschieben Sie es in die Nähe der anderen, bis Sie fast berührt werden. Beachten Sie die angezeigte schräschlange. Diese Distanz ist die empfohlene Entfernung zwischen den Rahmen der Steuerelemente. Beachten Sie auch, dass das Steuerelement, das Sie verschieben, an diese Position anspringt.

8. Ziehen Sie <xref:System.Windows.Forms.Panel> zwei-Steuerelemente aus der **Toolbox** auf das Formular.

9. Verschieben Sie eines der <xref:System.Windows.Forms.Panel> -Steuerelemente, bis es fast mit dem ersten-Element- Beachten Sie die Richtungslinien, die am oberen und unteren Rand beider Steuerelemente angezeigt werden, und beachten Sie, dass das Steuerelement, das Sie verschieben, an eine Position mit dem anderen Steuerelement mit dem anderen Steuerelement bewegt wird.

## <a name="aligning-to-form-and-container-margins"></a>Ausrichten an Form-und Container Rändern
 Ausrichtungs Linien unterstützen Sie bei der konsistenten Ausrichtung der Steuerelemente an Form-und Container Ränder.

### <a name="to-align-controls-to-form-and-container-margins"></a>So richten Sie Steuerelemente an Form-und Container Ränder aus

1. Wählen Sie eines der <xref:System.Windows.Forms.Button> Steuerelemente aus, und verschieben Sie es nahe an den rechten Rand des Formulars, bis eine Ausrichtungslinie angezeigt wird. Der Abstand der Richtungslinie vom rechten Rand aus ist die Summe aus der- <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft des Steuer Elements und den <xref:System.Windows.Forms.Control.Padding%2A> Eigenschafts Werten des Formulars.

> [!NOTE]
> Wenn die- <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft des Formulars auf 0, 0, 0, 0 (null) festgelegt ist, gibt die <xref:System.Windows.Forms.Control.Padding%2A> Windows Forms-Designer der Form einen Shadowing Wert von 9, 9, 9, 9 an. Um dieses Verhalten zu überschreiben, weisen Sie einen anderen Wert als 0, 0, 0, 0 zu.

1. Ändern Sie den Wert der <xref:System.Windows.Forms.Button> -Eigenschaft <xref:System.Windows.Forms.Control.Margin%2A> des-Steuer Elements <xref:System.Windows.Forms.Control.Margin%2A> , indem Sie im **Eigenschaften** Fenster den Eintrag <xref:System.Windows.Forms.Padding.All%2A> erweitern und die-Eigenschaft auf 0 festlegen. Weitere Informationen finden [Sie unter Exemplarische Vorgehensweise: Das Anordnen von Windows Forms-Steuerelementen mit Auffüll Zeichen, Rändern und](windows-forms-controls-padding-autosize.md)der AutoSize-Eigenschaft.

2. Verschieben Sie <xref:System.Windows.Forms.Button> das Steuerelement in der Nähe der rechten Ecke des Formulars, bis eine Linie angezeigt wird. Diese Entfernung wird jetzt durch den Wert der- <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft des Formulars angegeben.

3. Ziehen Sie ein <xref:System.Windows.Forms.GroupBox> -Steuerelement aus der **Toolbox** auf das Formular.

4. Ändern Sie den Wert der <xref:System.Windows.Forms.GroupBox> -Eigenschaft <xref:System.Windows.Forms.Control.Padding%2A> des-Steuer Elements <xref:System.Windows.Forms.Control.Padding%2A> , indem Sie im **Eigenschaften** Fenster den Eintrag <xref:System.Windows.Forms.Padding.All%2A> erweitern und die-Eigenschaft auf 10 festlegen.

5. Ziehen Sie <xref:System.Windows.Forms.Button> ein-Steuerelement aus der <xref:System.Windows.Forms.GroupBox> **Toolbox** in das-Steuerelement.

6. Verschieben Sie <xref:System.Windows.Forms.Button> das Steuerelement nahe an den rechten Rand <xref:System.Windows.Forms.GroupBox> des Steuer Elements, bis eine angezeigte Linie angezeigt wird. Verschieben Sie <xref:System.Windows.Forms.Button> das Steuerelement <xref:System.Windows.Forms.GroupBox> im-Steuerelement, und stellen Sie fest, wo die Richtungslinien angezeigt werden.

## <a name="aligning-to-grouped-controls"></a>Ausrichten an gruppierten Steuerelementen
 Sie können Ausrichtungs Linien verwenden, um gruppierte Steuerelemente und Steuerelemente in <xref:System.Windows.Forms.GroupBox> einem Steuerelement auszurichten.

### <a name="to-align-to-grouped-controls"></a>So richten Sie gruppierte Steuerelemente aus

1. Wählen Sie zwei der Steuerelemente auf dem Formular aus. Verschieben Sie die Auswahl, und notieren Sie sich die Ausrichtungs Linien, die zwischen Ihrer Auswahl und den anderen Steuerelementen angezeigt werden.

2. Ziehen Sie ein <xref:System.Windows.Forms.GroupBox> -Steuerelement aus der **Toolbox** auf das Formular.

3. Ziehen Sie <xref:System.Windows.Forms.Button> ein-Steuerelement aus der <xref:System.Windows.Forms.GroupBox> **Toolbox** in das-Steuerelement.

4. Wählen Sie eines der <xref:System.Windows.Forms.Button> Steuerelemente aus, und verschieben <xref:System.Windows.Forms.GroupBox> Sie es um das Steuerelement. Beachten Sie die Richtungslinien, die an den Rändern des <xref:System.Windows.Forms.GroupBox> Steuer Elements angezeigt werden. Beachten Sie auch die Richtungslinien, die an den Rändern des <xref:System.Windows.Forms.Button> Steuer Elements angezeigt <xref:System.Windows.Forms.GroupBox> werden, die im-Steuerelement enthalten sind. Steuerelemente, die untergeordnete Elemente eines Container Steuer Elements sind, unterstützen auch Richtungslinien.

## <a name="using-snaplines-to-place-a-control-by-outlining-its-size"></a>Verwenden von Richtungslinien zum Platzieren eines Steuer Elements durch Gliederung der Größe
 Ausrichtungs Linien helfen Ihnen beim Ausrichten von Steuerelementen, wenn Sie Sie zum ersten Mal in einem Formular platzieren.

### <a name="to-use-snaplines-to-place-a-control-by-outlining-its-size"></a>So verwenden Sie Richtungslinien zum Platzieren eines Steuer Elements durch Gliederung der Größe

1. Klicken Sie in der **Toolbox**auf das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements. Ziehen Sie es nicht auf das Formular.

2. Bewegen Sie den Mauszeiger über die Entwurfs Oberfläche des Formulars. Beachten Sie, dass der Mauszeiger die Form eines Fadenkreuzes annimmt, an das das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements angefügt ist. Beachten Sie auch die Ausrichtungs Linien, die für das <xref:System.Windows.Forms.Button> Steuerelement ausgerichtete Positionen vorschlagen.

3. Klicken Sie, und halten Sie die Maustaste gedrückt.

4. Ziehen Sie den Mauszeiger auf das Formular. Beachten Sie, dass ein Umriss gezeichnet wird, der die Position und die Größe des Steuer Elements angibt.

5. Ziehen Sie den Zeiger, bis er sich mit einem anderen Steuerelement im Formular anpasst. Beachten Sie, dass eine Ausrichtungslinie angezeigt wird, die die Ausrichtung angibt.

6. Lassen Sie die Maustaste los. Das-Steuerelement wird an der Position und Größe erstellt, die durch die Kontur angegeben wird.

## <a name="using-snaplines-when-dragging-a-control-from-the-toolbox"></a>Verwenden von Richtungslinien beim Ziehen eines Steuer Elements aus der Toolbox
 Ausrichtungs Linien helfen Ihnen beim Ausrichten von Steuerelementen, wenn Sie Sie aus der **Toolbox** auf das Formular ziehen.

### <a name="to-use-snaplines-when-dragging-a-control-from-the-toolbox"></a>So verwenden Sie beim Ziehen eines Steuer Elements aus der Toolbox Richtungslinien

1. Ziehen Sie <xref:System.Windows.Forms.Button> ein-Steuerelement aus der **Toolbox** auf das Formular, aber lassen Sie die Maustaste los.

2. Bewegen Sie den Mauszeiger über die Entwurfs Oberfläche des Formulars. Beachten Sie, dass der Zeiger geändert wird, um die Position anzugeben <xref:System.Windows.Forms.Button> , an der das neue Steuerelement erstellt wird.

3. Ziehen Sie den Mauszeiger auf das Formular. Beachten Sie die Ausrichtungs Linien, die für das <xref:System.Windows.Forms.Button> Steuerelement ausgerichtete Positionen vorschlagen. Suchen Sie eine Position, die an anderen Steuerelementen ausgerichtet ist.

4. Lassen Sie die Maustaste los. Das Steuerelement wird an der Position erstellt, die durch die Richtungslinien angegeben wird.

## <a name="resizing-controls-using-snaplines"></a>Ändern der Größe von Steuerelementen mithilfe von Richtungslinien
 Ausrichtungs Linien helfen Ihnen beim Ausrichten von Steuerelementen bei der Größenänderung.

### <a name="to-resize-a-control-using-snaplines"></a>So ändern Sie die Größe eines Steuer Elements mithilfe von Richtungslinien

1. Ziehen Sie ein <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular.

2. Ändern Sie die <xref:System.Windows.Forms.Button> Größe des Steuer Elements, indem Sie eine der eckzieh Punkte der Ecke und ziehen. Weitere Informationen finden Sie unter [Vorgehensweise: Ändern Sie die Größe der](how-to-resize-controls-on-windows-forms.md)Steuerelemente an Windows Forms.

3. Ziehen Sie den Ziehpunkt, bis einer <xref:System.Windows.Forms.Button> der Rahmen des Steuer Elements an einem anderen Steuerelement ausgerichtet ist. Beachten Sie, dass eine Ausrichtungslinie angezeigt wird. Beachten Sie außerdem, dass das Größen Anpassungs Handle an die von der Einfügemarke festgelegten Position anspringt.

4. Ändern Sie die <xref:System.Windows.Forms.Button> Größe des Steuer Elements in verschiedene Richtungen, und richten Sie den Zieh Punkt an verschiedene Steuerelemente aus. Beachten Sie, dass die Ausrichtungs Linien in verschiedenen Ausrichtungen angezeigt werden, um die Ausrichtung anzugeben.

## <a name="aligning-a-label-to-a-controls-text"></a>Ausrichten einer Bezeichnung an den Text eines Steuer Elements
 Einige Steuerelemente bieten eine Ausrichtungslinie zum Ausrichten anderer Steuerelemente an angezeigter Text.

### <a name="to-align-a-label-to-a-controls-text"></a>So richten Sie eine Bezeichnung an den Text eines Steuer Elements aus

1. Ziehen Sie ein <xref:System.Windows.Forms.TextBox> -Steuerelement aus der **Toolbox** auf das Formular. Wenn Sie das <xref:System.Windows.Forms.TextBox> Steuerelement auf dem Formular ablegen, klicken Sie auf das Smarttagsymbol, und wählen Sie die Option **Text auf textBox1 festlegen** aus. Weitere Informationen finden [Sie unter Exemplarische Vorgehensweise: Ausführen allgemeiner Aufgaben mit Smarttags auf Windows Forms](performing-common-tasks-using-smart-tags-on-wf-controls.md)-Steuerelementen.

2. Ziehen Sie ein <xref:System.Windows.Forms.Label> -Steuerelement aus der **Toolbox** auf das Formular.

3. Ändern Sie den Wert der <xref:System.Windows.Forms.Label> -Eigenschaft des <xref:System.Windows.Forms.Control.AutoSize%2A> -Steuerelements in `true`. Beachten Sie, dass die Rahmen des Steuer Elements an den Anzeige Text angepasst werden.

4. Verschieben Sie <xref:System.Windows.Forms.Label> das-Steuerelement auf die <xref:System.Windows.Forms.TextBox> linke Seite des-Steuer Elements, sodass es am unteren Rand <xref:System.Windows.Forms.TextBox> des Steuer Elements ausgerichtet ist. Beachten Sie die Richtungslinie, die an den unteren Rändern der beiden Steuerelemente angezeigt wird.

5. Verschieben Sie <xref:System.Windows.Forms.Label> das Steuerelement geringfügig nach <xref:System.Windows.Forms.Label> oben, bis <xref:System.Windows.Forms.TextBox> der Text und der Text ausgerichtet sind. Beachten Sie, dass die anders formatierte Ausrichtungslinie angezeigt wird, die anzeigt, wann die Textfelder beider Steuerelemente ausgerichtet werden.

## <a name="using-snaplines-with-keyboard-navigation"></a>Verwenden von Richtungslinien mit Tastatur Navigation
 Ausrichtungs Linien helfen Ihnen beim Ausrichten von Steuerelementen, wenn Sie Sie mit den Pfeiltasten der Tastatur anordnen.

### <a name="to-use-snaplines-with-keyboard-navigation"></a>So verwenden Sie Richtungslinien mit Tastaturnavigation

1. Ziehen Sie ein <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular. Platzieren Sie ihn in der oberen linken Ecke des Formulars.

2. Drücken Sie STRG + nach-unten-Taste. Beachten Sie, dass das-Steuerelement das Formular bis zur ersten verfügbaren horizontalen Ausrichtungs Position verschiebt.

3. Drücken Sie STRG + nach-unten-Taste, bis das Steuerelement den unteren Bereich des Formulars erreicht. Beachten Sie die Positionen, die Sie einnimmt, wenn Sie das Formular nach unten verschieben.

4. Drücken Sie STRG + nach-rechts-Taste. Beachten Sie, dass das-Steuerelement über das Formular an die erste verfügbare vertikale Ausrichtungs Position verschoben wird.

5. Drücken Sie STRG + nach-rechts-Taste, bis das Steuerelement die Seite des Formulars erreicht. Beachten Sie die Positionen, die Sie einnimmt, wenn Sie über das Formular bewegt werden.

6. Verschieben Sie das Steuerelement um das Formular mit einer Kombination von Pfeiltasten. Beachten Sie, welche Positionen das Steuerelement einnimmt und welche Richtungslinien es begleitet.

7. Drücken Sie UMSCHALT + nach-links-Taste, <xref:System.Windows.Forms.Button> um die Größe des Steuer Elements in Schritten von einem Pixel zu ändern.

8. Drücken Sie STRG + UMSCHALT + nach-links-Taste, <xref:System.Windows.Forms.Button> um die Größe des Steuer Elements in Richtungslinien Schritten zu ändern.

## <a name="snaplines-and-layout-panels"></a>Richtungslinien und Layoutpanels
 In Layoutpanels sind die Richtungslinien deaktiviert.

### <a name="to-selectively-disable-snaplines"></a>So deaktivieren Sie die Richtungslinien selektiv

1. Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.

2. Doppelklicken Sie auf das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements in der **Toolbox**. Beachten Sie, dass ein neues Button-Steuer <xref:System.Windows.Forms.TableLayoutPanel> Element in der ersten Zelle des Steuer Elements angezeigt wird.

3. Doppelklicken Sie zweimal <xref:System.Windows.Forms.Button> auf das Symbol für das Steuerelement in der **Toolbox** . Dadurch bleibt eine leere Zelle im <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement.

4. Ziehen Sie <xref:System.Windows.Forms.Button> ein-Steuerelement aus der **Toolbox** in die <xref:System.Windows.Forms.TableLayoutPanel> leere Zelle des-Steuer Elements. Beachten Sie, dass keine Schräglinien angezeigt werden.

5. Ziehen Sie <xref:System.Windows.Forms.Button> das Steuerelement aus <xref:System.Windows.Forms.TableLayoutPanel> dem-Steuerelement, und <xref:System.Windows.Forms.TableLayoutPanel> verschieben Sie es um das Steuerelement. Beachten Sie, dass die Richtungslinien erneut angezeigt werden.

## <a name="disabling-snaplines"></a>Deaktivieren von SnapLines
 Ausrichtungs Linien sind standardmäßig aktiviert. Sie können die Richtungslinien selektiv deaktivieren, oder Sie können Sie in der Entwurfs Umgebung deaktivieren.

### <a name="to-selectively-disable-snaplines"></a>So deaktivieren Sie die Richtungslinien selektiv

- Drücken Sie die Alt-Taste, und verschieben Sie ein Steuerelement um das Formular.

     Beachten Sie, dass keine Ausrichtungs Linien angezeigt werden und das Steuerelement keine möglichen Ausrichtungs Positionen ausdostet.

### <a name="to-disable-snaplines-in-the-design-environment"></a>So deaktivieren Sie die Richtungslinien in der Entwurfs Umgebung

1. Öffnen Sie das Dialogfeld **Optionen** im Menü Extras. Öffnen Sie das Dialogfeld Windows Forms-Designer. Weitere Informationen finden Sie unter [Allgemein, Windows Forms-Designer, Dialog Feld "Optionen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))".

2. Wählen Sie den Knoten **Allgemein** aus. Ändern Sie im Abschnitt **Layoutmodus** die Auswahl von Ausrichtungs **Linien** in **snapchanraster**.

3. Klicken Sie auf OK, um die Einstellung zu übernehmen.

4. Wählen Sie ein Steuerelement auf dem Formular aus, und verschieben Sie es um die anderen Steuerelemente. Beachten Sie, dass keine Richtungslinien angezeigt werden.

## <a name="next-steps"></a>Nächste Schritte
 Ausrichtungs Linien bieten eine intuitive Möglichkeit zum Ausrichten von Steuerelementen auf dem Formular. Hier sind paar Vorschläge für weitere Experimente:

- Schachteln Sie ein <xref:System.Windows.Forms.GroupBox> Steuerelement in <xref:System.Windows.Forms.GroupBox> einem anderen Steuerelement Platzieren Sie <xref:System.Windows.Forms.Button> ein Steuerelement innerhalb <xref:System.Windows.Forms.GroupBox> des untergeordneten Steuer Elements und ein <xref:System.Windows.Forms.GroupBox> anderes innerhalb des übergeordneten Steuer Elements. Verschieben Sie <xref:System.Windows.Forms.Button> die Steuerelemente, um zu sehen, wie die Richtungslinien Container Grenzen überschreiten.

- Erstellen Sie eine Spalte <xref:System.Windows.Forms.TextBox> mit Steuerelementen und eine entsprechende <xref:System.Windows.Forms.Label> Spalte von Steuerelementen. Legen Sie den Wert der <xref:System.Windows.Forms.Label> <xref:System.Windows.Forms.Control.AutoSize%2A> -Eigenschaft des Steuer `true`Elements auf fest. Verwenden Sie Ausrichtungs Linien, um <xref:System.Windows.Forms.Label> die Steuerelemente so zu verschieben, dass der angezeigte Text <xref:System.Windows.Forms.TextBox> an dem Text in den Steuerelementen ausgerichtet ist.

 Weitere Informationen zum Design der Windows-Benutzeroberfläche finden Sie im Buch *Microsoft Windows-Benutzeroberfläche, offizielle Richtlinien für Benutzeroberflächen Entwickler und Designer* Redmond, WA: Microsoft Press, 1999. ("US-MILLIARDE": 0-7356-0566-1).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Design.Behavior.SnapLine>
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe von FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe von TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mit Auffüll Zeichen, Rändern und der AutoSize-Eigenschaft](windows-forms-controls-padding-autosize.md)
- [Anordnen von Steuerelementen in Windows Forms](arranging-controls-on-windows-forms.md)
