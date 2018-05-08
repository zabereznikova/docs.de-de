---
title: 'Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with snaplines
- snaplines [Windows Forms], arranging Windows Forms controls
- SnapLine class [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
ms.openlocfilehash: f8e8122f82bc6a8c4fab17b8b73c07d08bab4d26
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-snaplines"></a>Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien
Die präzise Platzierung von Steuerelementen auf dem Formular hat für viele Anwendungen einen hohen Stellenwert. Windows Forms-Designer bietet Ihnen viele Layout-Tools, um dies zu erreichen. Zu den wichtigsten ist die <xref:System.Windows.Forms.Design.Behavior.SnapLine> Funktion.  
  
 Mithilfe von Ausrichtungslinien können Sie genau, wo Steuerelemente mit anderen Steuerelementen ausrichten. Darüber hinaus zeigen Sie die empfohlenen Abstände für Ränder zwischen entsprechend den Angaben von Richtlinien zur Benutzeroberfläche der Windows-Steuerelemente. Weitere Informationen finden Sie unter [User Interface Design und Entwicklung](http://go.microsoft.com/FWLink/?LinkId=83878).  
  
 Ausrichtungslinien erleichtern das Ausrichten von Steuerelementen für Crisp, professionelles Aussehen und Verhalten (Aussehen und Verhalten).  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen eines Windows Forms-Projekts  
  
-   Abstand und Ausrichtung von Steuerelementen mithilfe von Ausrichtungslinien  
  
-   Ausrichten an das Formular und die Ränder des Containers  
  
-   Für gruppierte Steuerelemente ausrichten  
  
-   Verwenden von Ausrichtungslinien zum Platzieren eines Steuerelements durch seine Größe Gliedern  
  
-   Mithilfe von Ausrichtungslinien beim Ziehen eines Steuerelements aus der Toolbox  
  
-   Ändern der Größe von Steuerelementen mithilfe von Ausrichtungslinien  
  
-   Ausrichten von einer Bezeichnung, die Text eines Steuerelements  
  
-   Mithilfe von Ausrichtungslinien die Tastaturnavigation  
  
-   Ausrichtungslinien und LayoutPanel-Elemente  
  
-   Deaktivieren von Ausrichtungslinien  
  
 Wenn Sie fertig sind, müssen Sie einen Überblick über die Rolle "Layout" von Ausrichtungslinien wiedergegeben.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.  
  
#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
1.  Erstellen Sie ein Windows-basierten Anwendung mit dem Namen "SnaplineExample". Weitere Informationen finden Sie unter [How to: Create a Windows Application Project (Vorgehensweise: Erstellen eines neuen Windows Forms-Anwendungsprojekts)](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Wählen Sie im Formular-Designer das Formular aus.  
  
## <a name="spacing-and-aligning-controls-using-snaplines"></a>Abstand und Ausrichtung von Steuerelementen mithilfe von Ausrichtungslinien  
 Ausrichtungslinien bieten Ihnen eine präzise und intuitive Möglichkeit zum Ausrichten von Steuerelementen auf dem Formular. Sie werden angezeigt, wenn Sie ein ausgewähltes Steuerelement oder Steuerelemente in der Nähe von einer Position verschieben, die mit einem anderen Steuerelement oder eine Gruppe von Steuerelementen ausgerichtet würden. Ihre Auswahl wird an der vorgeschlagenen Position "ausgerichtet" werden, wie Sie es hinter dem andere Steuerelemente verschieben.  
  
#### <a name="to-arrange-controls-using-snaplines"></a>So ordnen Sie Steuerelemente mithilfe von Ausrichtungslinien an  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Verschieben der <xref:System.Windows.Forms.Button> Steuerelement in der unteren rechten Ecke des Formulars. Beachten Sie die Ausrichtungslinien, die als die <xref:System.Windows.Forms.Button> Steuerelement nähert sich dem unteren und rechten Rand des Formulars. Diese Ausrichtungslinien zeigen den empfohlenen Abstand zwischen den Rändern des Steuerelements und das Formular.  
  
3.  Verschieben der <xref:System.Windows.Forms.Button> Steuerelement, um die Rahmen des Formulars und beachten Sie, wo die Ausrichtungslinien angezeigt werden. Wenn Sie fertig sind, verschieben die <xref:System.Windows.Forms.Button> Steuerelement in der Mitte des Formulars.  
  
4.  Ziehen Sie ein weiteres <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular.  
  
5.  Verschieben Sie das zweite <xref:System.Windows.Forms.Button> steuern, bis sie nahezu mit der ersten Ebene ist. Beachten Sie die Ausrichtungslinie, die auf der Textbasislinie, der beide Schaltflächen angezeigt wird, und beachten Sie, dass das Steuerelement, das Sie verschieben eine Position ausgerichtet wird, die genau mit dem anderen Steuerelement ist.  
  
6.  Verschieben Sie das zweite <xref:System.Windows.Forms.Button> steuern, bis es direkt über dem ersten positioniert ist. Beachten Sie die Ausrichtungslinien, die an den linken und rechten Rändern der beiden Schaltflächen angezeigt, und beachten Sie, dass das Steuerelement verschieben Snaps an eine Position, die genau mit dem anderen Steuerelement ausgerichtet wird.  
  
7.  Wählen Sie eine von der <xref:System.Windows.Forms.Button> -Steuerelemente sowie die in der Nähe der anderen zu verschieben, bis sie fast berühren. Beachten Sie die Ausrichtungslinie, die zwischen ihnen angezeigt wird. Dieser Abstand wird die empfohlene Abstand zwischen den Rändern der Steuerelemente. Beachten Sie außerdem, dass das Steuerelement, das Sie verschieben möchten, auf diese Position einrastet.  
  
8.  Ziehen Sie zwei <xref:System.Windows.Forms.Panel> -Steuerelemente aus der **Toolbox** auf das Formular.  
  
9. Verschieben Sie eine von der <xref:System.Windows.Forms.Panel> -Steuerelemente fort, bis es nahezu mit der ersten Ebene ist. Beachten Sie die Ausrichtungslinien, die am oberen und unteren Rand des beide Steuerelemente angezeigt, und beachten Sie, dass das Steuerelement, das Sie verschieben eine Position ausgerichtet wird, die genau mit dem anderen Steuerelement ist.  
  
## <a name="aligning-to-form-and-container-margins"></a>Ausrichten an das Formular und die Ränder des Containers  
 Mit Ausrichtungslinien können Sie zum Ausrichten von Steuerelementen für die Form und Container Ränder konsistent.  
  
#### <a name="to-align-controls-to-form-and-container-margins"></a>Zum Ausrichten von Steuerelementen zum Formular und Container Ränder  
  
1.  Wählen Sie eine von der <xref:System.Windows.Forms.Button> steuert und verschieben Sie sie nahe am rechten Rand von dem Formular aus, bis eine Ausrichtungslinie angezeigt wird. Der Abstand der Ausrichtungslinie vom rechten Rand ist die Summe des Steuerelements <xref:System.Windows.Forms.Control.Margin%2A> -Eigenschaft und des Formulars <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaftswerte.  
  
> [!NOTE]
>  Wenn des Formulars <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft auf 0,0,0,0 festgelegt ist, der Windows Forms-Designer dem Formular bietet ein Shadowing <xref:System.Windows.Forms.Control.Padding%2A> -Wert 9,9,9,9 zu. Um dieses Verhalten außer Kraft setzen, weisen Sie einen anderen Wert als 0,0,0,0.  
  
1.  Ändern Sie den Wert von der <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft durch Erweitern der <xref:System.Windows.Forms.Control.Margin%2A> Eintrag in der **Eigenschaften** Fenster und der Einstellung der <xref:System.Windows.Forms.Padding.All%2A> Eigenschaft auf 0. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md).  
  
2.  Verschieben der <xref:System.Windows.Forms.Button> Steuerelement nahe bei den rechten Rand des Formulars, bis eine Ausrichtungslinie angezeigt wird. Dieser Abstand wird nun durch den Wert des Formulars bestimmt <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft.  
  
3.  Ziehen Sie eine <xref:System.Windows.Forms.GroupBox> -Steuerelement aus der **Toolbox** auf das Formular.  
  
4.  Ändern Sie den Wert von der <xref:System.Windows.Forms.GroupBox> des Steuerelements <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft durch Erweitern der <xref:System.Windows.Forms.Control.Padding%2A> Eintrag in der **Eigenschaften** Fenster und der Einstellung der <xref:System.Windows.Forms.Padding.All%2A> -Eigenschaft auf 10.  
  
5.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** in die <xref:System.Windows.Forms.GroupBox> Steuerelement.  
  
6.  Verschieben der <xref:System.Windows.Forms.Button> in der Nähe des rechten Rands des Steuerelements die <xref:System.Windows.Forms.GroupBox> steuern, bis eine Ausrichtungslinie angezeigt wird. Verschieben der <xref:System.Windows.Forms.Button> -Steuerelement innerhalb der <xref:System.Windows.Forms.GroupBox> -Steuerelement, und beachten Sie, wo die Ausrichtungslinien angezeigt werden.  
  
## <a name="aligning-to-grouped-controls"></a>Für gruppierte Steuerelemente ausrichten  
 Verwenden Sie Ausrichtungslinien, um gruppierte Steuerelemente auszurichten sowie Steuerelemente innerhalb einer <xref:System.Windows.Forms.GroupBox> Steuerelement.  
  
#### <a name="to-align-to-grouped-controls"></a>Um auf gruppierte Steuerelemente auszurichten.  
  
1.  Wählen Sie zwei der Steuerelemente auf dem Formular. Verschieben Sie die Auswahl, und beachten Sie die Ausrichtungslinien, die zwischen der Auswahl und die anderen Steuerelemente angezeigt werden.  
  
2.  Ziehen Sie eine <xref:System.Windows.Forms.GroupBox> -Steuerelement aus der **Toolbox** auf das Formular.  
  
3.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** in die <xref:System.Windows.Forms.GroupBox> Steuerelement.  
  
4.  Wählen Sie eine der der <xref:System.Windows.Forms.Button> steuert und bewegen sie den <xref:System.Windows.Forms.GroupBox> Steuerelement. Beachten Sie die Ausrichtungslinien, die an den Rändern des angezeigt werden die <xref:System.Windows.Forms.GroupBox> Steuerelement. Beachten Sie außerdem die Ausrichtungslinien, die an den Rändern des angezeigt werden die <xref:System.Windows.Forms.Button> von enthaltene der <xref:System.Windows.Forms.GroupBox> Steuerelement. Auch Unterstützung von Steuerelementen, die untergeordnete Elemente eines Containersteuerelements Ausrichtungslinien.  
  
## <a name="using-snaplines-to-place-a-control-by-outlining-its-size"></a>Verwenden von Ausrichtungslinien zum Platzieren eines Steuerelements durch seine Größe Gliedern  
 Mit Ausrichtungslinien können Sie ausrichten, die steuert, wann Sie sie in einem Formular platzieren Sie zuerst.  
  
#### <a name="to-use-snaplines-to-place-a-control-by-outlining-its-size"></a>So verwenden Sie Ausrichtungslinien, um ein Steuerelement zu platzieren, indem Sie seine Größe Gliedern  
  
1.  Klicken Sie in der **Toolbox**auf das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements. Ziehen Sie es nicht auf das Formular.  
  
2.  Bewegen Sie den Mauszeiger über der Form-Entwurfsoberfläche. Beachten Sie, dass der Mauszeiger die Form eines Fadenkreuzes annimmt, an das das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements angefügt ist. Beachten Sie außerdem die Ausrichtungslinien, die angezeigt, zum Vorschlagen von ausgerichteter Positionen für werden die <xref:System.Windows.Forms.Button> Steuerelement.  
  
3.  Klicken Sie, und halten Sie die Maustaste gedrückt.  
  
4.  Ziehen Sie den Mauszeiger, um das Formular aus. Beachten Sie, dass eine Gliederung gezeichnet wird, der angibt, der die Position und die Größe des Steuerelements.  
  
5.  Ziehen Sie den Mauszeiger, bis sie ein anderes Steuerelement im Formular ausgerichtet. Beachten Sie, dass eine Ausrichtungslinie angezeigt wird, um die Ausrichtung anzugeben.  
  
6.  Lassen Sie die Maustaste los. Das Steuerelement wird an der Position und Größe der Gliederung erkennbar erstellt.  
  
## <a name="using-snaplines-when-dragging-a-control-from-the-toolbox"></a>Mithilfe von Ausrichtungslinien beim Ziehen eines Steuerelements aus der Toolbox  
 Mit Ausrichtungslinien können Sie ausrichten steuert beim Ziehen sie aus der **Toolbox** auf das Formular.  
  
#### <a name="to-use-snaplines-when-dragging-a-control-from-the-toolbox"></a>So verwenden Sie Ausrichtungslinien beim Ziehen eines Steuerelements aus der Toolbox  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular, aber lassen Sie die Maustaste los nicht.  
  
2.  Bewegen Sie den Mauszeiger über der Form-Entwurfsoberfläche. Beachten Sie, dass der Mauszeiger, um anzugeben, die Position, an dem die neue <xref:System.Windows.Forms.Button> Steuerelement erstellt werden.  
  
3.  Ziehen Sie den Mauszeiger, um das Formular aus. Beachten Sie die Ausrichtungslinien, die angezeigt, zum Vorschlagen von ausgerichteter Positionen für werden die <xref:System.Windows.Forms.Button> Steuerelement. Suchen Sie eine Position, die mit anderen Steuerelementen ausgerichtet ist.  
  
4.  Lassen Sie die Maustaste los. Das Steuerelement wird an der Position der Ausrichtungslinien erkennbar erstellt.  
  
## <a name="resizing-controls-using-snaplines"></a>Ändern der Größe von Steuerelementen mithilfe von Ausrichtungslinien  
 Mit Ausrichtungslinien können Sie Steuerelemente auszurichten, während Sie ihre Größe ändern.  
  
#### <a name="to-resize-a-control-using-snaplines"></a>Um die Größe eines Steuerelements mithilfe von Ausrichtungslinien  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Ändern Sie die Größe der <xref:System.Windows.Forms.Button> Steuerelement, indem Eckziehpunkte auf einen der Ziehpunkte klicken und ziehen. Weitere Informationen finden Sie unter [Vorgehensweise: Ändern der Größe von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md).  
  
3.  Ziehen Sie den Ziehpunkt, bis eines der <xref:System.Windows.Forms.Button> Rändern des Steuerelements an ein anderes Steuerelement ausgerichtet ist. Beachten Sie, die eine Ausrichtungslinie angezeigt wird. Beachten Sie außerdem, dass die Position der Ausrichtungslinie erkennbar der Ziehpunkt ausgerichtet wird.  
  
4.  Ändern Sie die Größe der <xref:System.Windows.Forms.Button> in verschiedene Richtungen steuern und den Ziehpunkt zu anderen Steuerelementen ausrichten. Beachten Sie, wie die Ausrichtungslinien in verschiedenen Ausrichtungen an, dass Ausrichtung angezeigt werden.  
  
## <a name="aligning-a-label-to-a-controls-text"></a>Ausrichten von einer Bezeichnung, die Text eines Steuerelements  
 Einige Steuerelemente verfügen über eine Ausrichtungslinie zum Ausrichten von anderen Steuerelementen angezeigtem Text.  
  
#### <a name="to-align-a-label-to-a-controls-text"></a>Um eine Bezeichnung für den Text eines Steuerelements auszurichten.  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.TextBox> -Steuerelement aus der **Toolbox** auf das Formular. Beim Ablegen der <xref:System.Windows.Forms.TextBox> auf das Formular zu steuern, klicken Sie auf das Smarttag-Symbol und wählen Sie die **Text auf textBox1 festlegen** Option. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Ausführen allgemeine Aufgaben mithilfe von Smarttags auf Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md).  
  
2.  Ziehen Sie eine <xref:System.Windows.Forms.Label> -Steuerelement aus der **Toolbox** auf das Formular.  
  
3.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.AutoSize%2A>-Eigenschaft des <xref:System.Windows.Forms.Label>-Steuerelements in `true`. Beachten Sie, dass den Rändern des Steuerelements den Anzeigetext entsprechend angepasst werden.  
  
4.  Verschieben der <xref:System.Windows.Forms.Label> Steuerelement links neben der <xref:System.Windows.Forms.TextBox> zu steuern, damit es mit dem unteren Rand ausgerichtet ist die <xref:System.Windows.Forms.TextBox> Steuerelement. Beachten Sie die Ausrichtungslinien, die am unteren Rand von zwei Steuerelementen angezeigt wird.  
  
5.  Verschieben der <xref:System.Windows.Forms.Label> Steuerelement etwas nach oben, bis die <xref:System.Windows.Forms.Label> Text und die <xref:System.Windows.Forms.TextBox> Text ausgerichtet sind. Beachten Sie die unterschiedlich formatierte Ausrichtungslinie, die angezeigt wird, der angibt, wann die Textfelder beider Steuerelemente ausgerichtet sind, aus.  
  
## <a name="using-snaplines-with-keyboard-navigation"></a>Mithilfe von Ausrichtungslinien die Tastaturnavigation  
 Mit Ausrichtungslinien können Sie ausrichten, die steuert, wann Sie sie mithilfe der Pfeiltasten der Tastatur anordnen.  
  
#### <a name="to-use-snaplines-with-keyboard-navigation"></a>So verwenden Sie Ausrichtungslinien die Tastaturnavigation  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular. Fügen Sie ihn in der oberen linken Ecke des Formulars.  
  
2.  Drücken Sie STRG + nach-unten-Pfeil. Beachten Sie, dass das Steuerelement im Formular an die erste verfügbare horizontale Ausrichtungsposition verschoben wird.  
  
3.  Drücken Sie STRG + nach-unten-Pfeil, bis das Steuerelement den unteren Rand des Formulars erreicht. Beachten Sie die Positionen, die es einnimmt, wenn sie das Formular nach unten verschoben wird.  
  
4.  Drücken Sie STRG + nach-rechts-Pfeil. Beachten Sie, dass das Steuerelement über das Formular an die erste verfügbare vertikale Ausrichtungsposition verschoben wird.  
  
5.  Drücken Sie STRG + nach-rechts-Pfeil, bis das Steuerelement auf der Seite des Formulars erreicht. Beachten Sie die Positionen, die es einnimmt, wenn es über das Formular bewegen.  
  
6.  Verschieben Sie das Steuerelement auf dem Formular mit einer Kombination von Pfeiltasten. Beachten Sie die Positionen, die das Steuerelement belegt und die Ausrichtungslinien, die sie offen.  
  
7.  Drücken Sie UMSCHALT + beliebige Pfeiltaste, um die Größe der <xref:System.Windows.Forms.Button> -Steuerelements in Schritten von 1 Pixel.  
  
8.  Drücken Sie STRG + UMSCHALT + beliebige Pfeiltaste, um die Größe der <xref:System.Windows.Forms.Button> Steuerelement in Inkrementen von Ausrichtungslinie.  
  
## <a name="snaplines-and-layout-panels"></a>Ausrichtungslinien und LayoutPanel-Elemente  
 Ausrichtungslinien sind in Layoutbereichen deaktiviert.  
  
#### <a name="to-selectively-disable-snaplines"></a>Um Ausrichtungslinien selektiv zu deaktivieren.  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Doppelklicken Sie auf das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements in der **Toolbox**. Beachten Sie, dass ein neue Schaltflächen-Steuerelement in der <xref:System.Windows.Forms.TableLayoutPanel> ersten Zelle des Steuerelements.  
  
3.  Doppelklicken Sie auf die <xref:System.Windows.Forms.Button> Symbol "Steuerelement" in der **Toolbox** zweimal. Dies bewirkt, dass eine leere Zelle in der <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.  
  
4.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** in die leere Zelle von den <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement. Beachten Sie, die keine Ausrichtungslinien angezeigt werden.  
  
5.  Ziehen Sie die <xref:System.Windows.Forms.Button> Steuern von der <xref:System.Windows.Forms.TableLayoutPanel> steuern und bewegen sie den <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement. Beachten Sie, dass Ausrichtungslinien erneut angezeigt werden.  
  
## <a name="disabling-snaplines"></a>Deaktivieren von Ausrichtungslinien  
 Ausrichtungslinien sind standardmäßig aktiviert. Sie können Ausrichtungslinien selektiv deaktivieren, oder in der entwurfsumgebung deaktiviert werden.  
  
#### <a name="to-selectively-disable-snaplines"></a>Um Ausrichtungslinien selektiv zu deaktivieren.  
  
-   Drücken Sie die ALT-Taste, und zwar, verschieben ein Steuerelement, um das Formular.  
  
     Beachten Sie, dass keine Ausrichtungslinien angezeigt werden und das Steuerelement wird an alle potenziellen Ausrichtungspositionen nicht ausgerichtet.  
  
#### <a name="to-disable-snaplines-in-the-design-environment"></a>So deaktivieren Sie in der entwurfsumgebung Ausrichtungslinien  
  
1.  Aus der **Tools** öffnen Sie im Menü der **Optionen** (Dialogfeld). Öffnen Sie das Dialogfeld Windows Forms-Designer. Weitere Informationen finden Sie unter [Allgemein, Windows Forms-Designer, Optionen (Dialogfeld)](http://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834).  
  
2.  Wählen Sie die **allgemeine** Knoten. In der **Layoutmodus** Abschnitt, ändern Sie die Auswahl von **Ausrichtungslinien** auf **SnapToGrid**.  
  
3.  Klicken Sie auf OK, um die Einstellung zu übernehmen.  
  
4.  Wählen Sie ein Steuerelement im Formular aus, und bewegen sie die anderen Steuerelemente. Beachten Sie, dass keine Ausrichtungslinien angezeigt werden.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Ausrichtungslinien bieten eine intuitive Ausrichten von Steuerelementen auf dem Formular. Hier sind paar Vorschläge für weitere Experimente:  
  
-   Wiederholen Sie die Schachtelung einer <xref:System.Windows.Forms.GroupBox> Steuerelement innerhalb einer anderen <xref:System.Windows.Forms.GroupBox> Steuerelement. Stelle eine <xref:System.Windows.Forms.Button> innerhalb der untergeordneten Steuerelement <xref:System.Windows.Forms.GroupBox> -Steuerelement und ein anderes innerhalb des übergeordneten Elements <xref:System.Windows.Forms.GroupBox> Steuerelement. Verschieben der <xref:System.Windows.Forms.Button> Steuerelemente, um zu sehen, wie die Ausrichtungslinien Containergrenzen schneiden.  
  
-   Erstellen Sie eine Spalte des <xref:System.Windows.Forms.TextBox> Steuerelemente und entsprechende Spalte der <xref:System.Windows.Forms.Label> Steuerelemente. Legen Sie den Wert von der <xref:System.Windows.Forms.Label> Steuerelemente <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft `true`. Verwenden Sie Ausrichtungslinien, um das Verschieben der <xref:System.Windows.Forms.Label> steuert, sodass ihre angezeigte Text, mit dem Text in ausgerichtet ist der <xref:System.Windows.Forms.TextBox> Steuerelemente.  
  
 Informationen zur Gestaltung der Windows-Benutzeroberfläche finden Sie in das Buch *Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers* Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Design.Behavior.SnapLine>  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)  
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
