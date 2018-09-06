---
title: 'Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with snaplines
- snaplines [Windows Forms], arranging Windows Forms controls
- SnapLine class [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
ms.openlocfilehash: 170b79f03515ab371f7013c267b28ba85dafd0f5
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43741839"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-snaplines"></a>Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien
Die präzise Platzierung von Steuerelementen auf dem Formular hat für viele Anwendungen einen hohen Stellenwert. Der Windows Forms-Designer bietet Ihnen viele Layouttools, um dies zu erreichen. Einer der wichtigsten Faktoren ist die <xref:System.Windows.Forms.Design.Behavior.SnapLine> Feature.  
  
 Mithilfe von Ausrichtungslinien können Sie genau, wo die Steuerelemente mit anderen Steuerelementen auszurichten. Darüber hinaus zeigen Sie die empfohlene Entfernung für die Ränder zwischen Steuerelementen, die gemäß den Richtlinien für Windows-Benutzeroberfläche. Weitere Informationen finden Sie unter [User Interface Design und Entwicklung](https://go.microsoft.com/FWLink/?LinkId=83878).  
  
 Ausrichtungslinien erleichtern Ihnen die Anpassung an Ihre Steuerelementen und gewährleisten, professionelles Aussehen und Verhalten (Aussehen und Verhalten).  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen eines Windows Forms-Projekts  
  
-   Abstand und Ausrichtung von Steuerelementen, die mithilfe von Ausrichtungslinien  
  
-   Ausrichten von Form und die Ränder des Containers  
  
-   Gruppierte Steuerelemente ausrichten  
  
-   Verwenden von Ausrichtungslinien zum Platzieren eines Steuerelements durch seine Größe Gliedern  
  
-   Mithilfe von Ausrichtungslinien beim Ziehen eines Steuerelements aus der Toolbox  
  
-   Ändern der Größe von Steuerelementen mithilfe von Ausrichtungslinien  
  
-   Ausrichten von einer Bezeichnung auf den Text eines Steuerelements  
  
-   Mithilfe von Ausrichtungslinien Tastaturnavigation  
  
-   Ausrichtungslinien und LayoutPanel-Elemente  
  
-   Deaktivieren von Ausrichtungslinien  
  
 Wenn Sie fertig sind, müssen Sie einen Überblick über die Rolle Layout durch die Ausrichtungslinien-Funktion.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.  
  
#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
1.  Erstellen Sie ein Windows-basierten Anwendung mit dem Namen "SnaplineExample" (**Datei** > **neu** > **Projekt**  >  **Visual C#-** oder **Visual Basic** > **Klassischer Desktop** > **Windows Forms-Anwendung**).  
  
2.  Wählen Sie das Formular im Formular-Designer.  
  
## <a name="spacing-and-aligning-controls-using-snaplines"></a>Abstand und Ausrichtung von Steuerelementen, die mithilfe von Ausrichtungslinien  
 Ausrichtungslinien bieten Ihnen eine präzise und intuitive Möglichkeit zum Ausrichten von Steuerelementen im Formular. Sie werden angezeigt, wenn Sie ein ausgewähltes Steuerelement oder Steuerelemente in der Nähe von einer Position verschieben, die an ein anderes Steuerelement oder eine Gruppe von Steuerelementen ausgerichtet würden. Ihre Auswahl wird die vorgeschlagene Position "eingerastet" werden, wie Sie es hinter die anderen Steuerelemente verschoben werden.  
  
#### <a name="to-arrange-controls-using-snaplines"></a>So ordnen Sie Steuerelemente mithilfe von Ausrichtungslinien an  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Verschieben der <xref:System.Windows.Forms.Button> Steuerelement auf der unteren rechten Ecke des Formulars. Beachten Sie die Ausrichtungslinien, die als angezeigt werden. die <xref:System.Windows.Forms.Button> -Steuerelement nähert, unteren und rechten Rand des Formulars. Diese Ausrichtungslinien zeigen die empfohlene Entfernung zwischen den Rahmenlinien des Steuerelements und dem Formular.  
  
3.  Verschieben der <xref:System.Windows.Forms.Button> Steuerelement rund um die Rahmen des Formulars und der Hinweis, in denen die Ausrichtungslinien angezeigt werden. Wenn Sie fertig sind, wechseln die <xref:System.Windows.Forms.Button> Steuerelement die Mitte des Formulars.  
  
4.  Ziehen Sie ein weiteres <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular.  
  
5.  Verschieben Sie das zweite <xref:System.Windows.Forms.Button> steuern, bis er fast mit der ersten Ebene ist. Beachten Sie die Ausrichtungslinie, die an die Text-Baseline der beiden Schaltflächen angezeigt, und beachten Sie, dass das Steuerelement, das Sie verschieben eine Position ausgerichtet wird, die genau mit dem anderen Steuerelement ist.  
  
6.  Verschieben Sie das zweite <xref:System.Windows.Forms.Button> steuern, bis es direkt über dem ersten positioniert ist. Beachten Sie die Ausrichtungslinien, die an den linken und rechten Rändern der beiden Schaltflächen angezeigt werden soll, und beachten Sie, dass das Steuerelement bewegt Snapsicherungen an eine Position, die genau mit dem anderen Steuerelement ausgerichtet ist.  
  
7.  Wählen Sie eine der der <xref:System.Windows.Forms.Button> steuert und verschieben Sie es in der Nähe der anderen, bis sie sich fast berühren. Beachten Sie die Ausrichtungslinie, die zwischen ihnen angezeigt wird. Diese Entfernung ist die empfohlene Entfernung zwischen den Rändern der Steuerelemente. Beachten Sie außerdem, dass das Steuerelement, das Sie verschieben, die an dieser Position ausgerichtet wird.  
  
8.  Ziehen Sie zwei <xref:System.Windows.Forms.Panel> -Steuerelemente aus der **Toolbox** auf das Formular.  
  
9. Verschieben Sie eine der der <xref:System.Windows.Forms.Panel> -Steuerelemente fort, bis es fast mit der ersten Ebene ist. Beachten Sie die Ausrichtungslinien, die an den oberen und unteren Rändern beider Steuerelemente angezeigt, und beachten Sie, dass das Steuerelement, das Sie verschieben eine Position ausgerichtet wird, die genau mit dem anderen Steuerelement ist.  
  
## <a name="aligning-to-form-and-container-margins"></a>Ausrichten von Form und die Ränder des Containers  
 Ausrichtungslinien können Sie das Formular und Container Rand auf konsistente Weise Ausrichten von Steuerelementen.  
  
#### <a name="to-align-controls-to-form-and-container-margins"></a>Zum Ausrichten von Steuerelementen, Form und Container Rand  
  
1.  Wählen Sie eine der der <xref:System.Windows.Forms.Button> steuert und verschieben Sie es in der Nähe der rechten Rand des Formulars, bis eine Ausrichtungslinie angezeigt wird. Der Abstand der Ausrichtungslinie vom rechten Rand ist die Summe des Steuerelements <xref:System.Windows.Forms.Control.Margin%2A> -Eigenschaft und des Formulars <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaftswerte.  
  
> [!NOTE]
>  Wenn des Formulars <xref:System.Windows.Forms.Control.Padding%2A> -Eigenschaftensatz auf 0,0,0,0, der Windows Forms-Designer weist dem Formular ein Shadowing <xref:System.Windows.Forms.Control.Padding%2A> Wert 9,9,9,9 zu. Um dieses Verhalten außer Kraft setzen, weisen Sie einen anderen Wert als 0,0,0,0.  
  
1.  Ändern Sie den Wert von der <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft durch Erweitern der <xref:System.Windows.Forms.Control.Margin%2A> Eintrag in der **Eigenschaften** Fenster und der Einstellung der <xref:System.Windows.Forms.Padding.All%2A> Eigenschaft auf 0. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von, Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md).  
  
2.  Verschieben der <xref:System.Windows.Forms.Button> Steuerelement in der Nähe der rechten Rand des Formulars bis eine Ausrichtungslinie angezeigt wird. Dieser Abstand wird jetzt durch den Wert des Formulars bestimmt <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft.  
  
3.  Ziehen Sie eine <xref:System.Windows.Forms.GroupBox> -Steuerelement aus der **Toolbox** auf das Formular.  
  
4.  Ändern Sie den Wert von der <xref:System.Windows.Forms.GroupBox> des Steuerelements <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft durch Erweitern der <xref:System.Windows.Forms.Control.Padding%2A> Eintrag in der **Eigenschaften** Fenster und der Einstellung der <xref:System.Windows.Forms.Padding.All%2A> Eigenschaft auf 10.  
  
5.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** in die <xref:System.Windows.Forms.GroupBox> Steuerelement.  
  
6.  Verschieben der <xref:System.Windows.Forms.Button> Steuerelement in der Nähe der rechte Rand des der <xref:System.Windows.Forms.GroupBox> steuern, bis eine Ausrichtungslinie angezeigt wird. Verschieben der <xref:System.Windows.Forms.Button> -Steuerelement innerhalb der <xref:System.Windows.Forms.GroupBox> Steuerelements, und beachten Sie, wo die Ausrichtungslinien angezeigt werden.  
  
## <a name="aligning-to-grouped-controls"></a>Gruppierte Steuerelemente ausrichten  
 Mithilfe von Ausrichtungslinien zum Ausrichten von gruppierter Steuerelementen sowie Steuerelemente in einem <xref:System.Windows.Forms.GroupBox> Steuerelement.  
  
#### <a name="to-align-to-grouped-controls"></a>Um auf gruppierte Steuerelemente auszurichten.  
  
1.  Wählen Sie zwei der Steuerelemente im Formular aus. Verschieben Sie die Auswahl, und beachten Sie die Ausrichtungslinien, die zwischen der Auswahl und den anderen Steuerelementen angezeigt werden.  
  
2.  Ziehen Sie eine <xref:System.Windows.Forms.GroupBox> -Steuerelement aus der **Toolbox** auf das Formular.  
  
3.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** in die <xref:System.Windows.Forms.GroupBox> Steuerelement.  
  
4.  Wählen Sie eine der der <xref:System.Windows.Forms.Button> steuert und verschieben Sie ihn der <xref:System.Windows.Forms.GroupBox> Steuerelement. Beachten Sie die Ausrichtungslinien, die an den Kanten des angezeigt werden. die <xref:System.Windows.Forms.GroupBox> Steuerelement. Beachten Sie außerdem die Ausrichtungslinien, die an den Kanten des angezeigt werden. die <xref:System.Windows.Forms.Button> von befindlichen Steuerelement ausgehend, die <xref:System.Windows.Forms.GroupBox> Steuerelement. Steuerelemente, die untergeordnete Elemente eines Containersteuerelements unterstützen auch Ausrichtungslinien an.  
  
## <a name="using-snaplines-to-place-a-control-by-outlining-its-size"></a>Verwenden von Ausrichtungslinien zum Platzieren eines Steuerelements durch seine Größe Gliedern  
 Mit Ausrichtungslinien können Sie ausrichten steuert, wenn Sie zuerst diese in einem Formular platzieren.  
  
#### <a name="to-use-snaplines-to-place-a-control-by-outlining-its-size"></a>So verwenden Sie Ausrichtungslinien, um ein Steuerelement zu platzieren, Gliedern von seiner Größe  
  
1.  Klicken Sie in der **Toolbox**auf das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements. Ziehen Sie es nicht auf das Formular.  
  
2.  Zeigen Sie den Mauszeiger auf die Formularentwurfsoberfläche. Beachten Sie, dass der Mauszeiger die Form eines Fadenkreuzes annimmt, an das das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements angefügt ist. Beachten Sie außerdem die Ausrichtungslinien, die angezeigt, zum Vorschlagen von ausgerichteter Positionen für werden die <xref:System.Windows.Forms.Button> Steuerelement.  
  
3.  Klicken Sie, und halten Sie die Maustaste gedrückt.  
  
4.  Ziehen Sie den Mauszeiger auf das Formular aus. Beachten Sie, dass eine Gliederung, der angibt, der die Position und die Größe des Steuerelements gezeichnet wird, an.  
  
5.  Ziehen Sie den Mauszeiger aus, bis sie mit einem anderen Steuerelement im Formular entspricht. Beachten Sie, dass eine Ausrichtungslinie angezeigt wird, um die Ausrichtung anzugeben.  
  
6.  Lassen Sie die Maustaste los. Das Steuerelement wird an die Position und Größe, angegeben durch die dokumentgliederung erstellt.  
  
## <a name="using-snaplines-when-dragging-a-control-from-the-toolbox"></a>Mithilfe von Ausrichtungslinien beim Ziehen eines Steuerelements aus der Toolbox  
 Ausrichtungslinien können Sie ausrichten, Steuerelemente, wenn Sie sie aus ziehen die **Toolbox** auf das Formular.  
  
#### <a name="to-use-snaplines-when-dragging-a-control-from-the-toolbox"></a>So verwenden Sie Ausrichtungslinien, wenn ein Steuerelement aus der Toolbox ziehen.  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular, jedoch werden keine Loslassen der Maustaste.  
  
2.  Zeigen Sie den Mauszeiger auf die Formularentwurfsoberfläche. Beachten Sie, dass der Zeiger ändert, um anzugeben, die Position, an dem das neue <xref:System.Windows.Forms.Button> Steuerelement erstellt werden.  
  
3.  Ziehen Sie den Mauszeiger auf das Formular aus. Beachten Sie die Ausrichtungslinien, die angezeigt, zum Vorschlagen von ausgerichteter Positionen für werden die <xref:System.Windows.Forms.Button> Steuerelement. Suchen Sie eine Position, die mit anderen Steuerelementen ausgerichtet ist.  
  
4.  Lassen Sie die Maustaste los. Das Steuerelement wird an der Position, die von den Ausrichtungslinien angegebenen erstellt.  
  
## <a name="resizing-controls-using-snaplines"></a>Ändern der Größe von Steuerelementen mithilfe von Ausrichtungslinien  
 Ausrichtungslinien können Sie Steuerelemente ausrichten, wie Sie ihre Größe zu ändern.  
  
#### <a name="to-resize-a-control-using-snaplines"></a>Zum Ändern der Größe eines Steuerelements mithilfe von Ausrichtungslinien  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Ändern der Größe der <xref:System.Windows.Forms.Button> Steuerelement Eckziehpunkte auf einen der Ziehpunkte klicken und ziehen. Weitere Informationen finden Sie unter [Vorgehensweise: Ändern der Größe von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md).  
  
3.  Ziehen Sie den Ziehpunkt, bis eines der <xref:System.Windows.Forms.Button> Rändern des Steuerelements mit einem anderen Steuerelement ausgerichtet wird. Beachten Sie, die eine Ausrichtungslinie angezeigt wird. Beachten Sie außerdem, dass die Position angegeben wird, von der Ausrichtungslinie der Ziehpunkt ausgerichtet wird.  
  
4.  Ändern der Größe der <xref:System.Windows.Forms.Button> in verschiedene Richtungen zu steuern, und richten Sie den Ziehpunkt für verschiedene Steuerelemente. Beachten Sie, wie die Ausrichtungslinien in verschiedenen Ausrichtungen, um die Ausrichtung anzugeben angezeigt werden.  
  
## <a name="aligning-a-label-to-a-controls-text"></a>Ausrichten von einer Bezeichnung auf den Text eines Steuerelements  
 Einige Steuerelemente verfügen über eine Ausrichtungslinien zum Ausrichten von anderen Steuerelementen angezeigten Text.  
  
#### <a name="to-align-a-label-to-a-controls-text"></a>Eine Bezeichnung für den Text eines Steuerelements ausgerichtet.  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.TextBox> -Steuerelement aus der **Toolbox** auf das Formular. Beim Ablegen der <xref:System.Windows.Forms.TextBox> steuern, auf das Formular, klicken Sie auf das Smarttag-Symbol aus, und wählen Sie die **Festlegen von Text in textBox1** Option. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Ausführen häufige Aufgaben mithilfe von Smarttags für Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md).  
  
2.  Ziehen Sie eine <xref:System.Windows.Forms.Label> -Steuerelement aus der **Toolbox** auf das Formular.  
  
3.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.AutoSize%2A>-Eigenschaft des <xref:System.Windows.Forms.Label>-Steuerelements in `true`. Beachten Sie, dass es sich bei den Rändern des Steuerelements angepasst werden, um den Text anpassen.  
  
4.  Verschieben der <xref:System.Windows.Forms.Label> Steuerelement auf der linken Seite von der <xref:System.Windows.Forms.TextBox> zu steuern, sodass es den unteren Rand ausgerichtet ist die <xref:System.Windows.Forms.TextBox> Steuerelement. Beachten Sie die Ausrichtungslinie, die an den unteren Rändern der beiden Steuerelemente angezeigt wird.  
  
5.  Verschieben der <xref:System.Windows.Forms.Label> Steuerelement etwas nach oben, bis die <xref:System.Windows.Forms.Label> Text und die <xref:System.Windows.Forms.TextBox> Text ausgerichtet sind. Beachten Sie die unterschiedlich formatierte Ausrichtungslinie, die angezeigt wird, der angibt, wann die Textfelder von beiden Steuerelementen ausgerichtet sind, ein.  
  
## <a name="using-snaplines-with-keyboard-navigation"></a>Mithilfe von Ausrichtungslinien Tastaturnavigation  
 Mit Ausrichtungslinien können Sie ausrichten steuert, wenn Sie sie mithilfe der Pfeiltasten der Tastatur angeordnet sind.  
  
#### <a name="to-use-snaplines-with-keyboard-navigation"></a>So verwenden Sie Ausrichtungslinien Tastaturnavigation  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular. Platzieren Sie es in der oberen linken Ecke des Formulars.  
  
2.  Drücken Sie STRG + nach-unten-Pfeil. Beachten Sie, dass das Steuerelement an die erste verfügbare horizontale Ausrichtungsposition im Formular nach unten verschoben wird.  
  
3.  Drücken Sie STRG + nach-unten-Pfeil, bis das Steuerelement den unteren Rand des Formulars erreicht. Beachten Sie die Positionen, die es einnimmt, wenn im Formular nach unten verschoben wird.  
  
4.  Drücken Sie STRG + nach-rechts-Pfeil. Beachten Sie, dass das Steuerelement über das Formular an die erste verfügbare vertikale Ausrichtungsposition verschoben wird.  
  
5.  Drücken Sie STRG + nach-rechts-Pfeil, bis das Steuerelement auf der Seite des Formulars erreicht. Beachten Sie die Positionen, die es einnimmt, wenn sie über das Formular verschoben.  
  
6.  Verschieben Sie das Steuerelement am Rand des Formulars wird mit einer Kombination von Pfeiltasten. Beachten Sie die Positionen, die das Steuerelement einnimmt und die Ausrichtungslinien, die sie gemeinsam mit.  
  
7.  Drücken Sie UMSCHALT + beliebige Pfeiltaste zum Ändern der Größe der <xref:System.Windows.Forms.Button> -Steuerelements in Schritten von 1 Pixel.  
  
8.  Drücken Sie STRG + UMSCHALT + beliebige Pfeiltaste zum Ändern der Größe der <xref:System.Windows.Forms.Button> Steuerelements in acht Inkrementen die Ausrichtungslinie.  
  
## <a name="snaplines-and-layout-panels"></a>Ausrichtungslinien und LayoutPanel-Elemente  
 Ausrichtungslinien sind in Layoutbereichen deaktiviert.  
  
#### <a name="to-selectively-disable-snaplines"></a>Um Ausrichtungslinien selektiv zu deaktivieren.  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Doppelklicken Sie auf das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements in der **Toolbox**. Beachten Sie, dass ein neue Schaltflächen-Steuerelement in der <xref:System.Windows.Forms.TableLayoutPanel> ersten Zelle des Steuerelements.  
  
3.  Doppelklicken Sie auf die <xref:System.Windows.Forms.Button> Symbol für Steuerelement in der **Toolbox** zwei weitere Male. Dadurch wird eine leere Zelle in der <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.  
  
4.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** in die leere Zelle ein, der die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement. Beachten Sie, die keine Ausrichtungslinien angezeigt werden.  
  
5.  Ziehen Sie die <xref:System.Windows.Forms.Button> steuern, von der <xref:System.Windows.Forms.TableLayoutPanel> steuern und verschieben Sie ihn der <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement. Beachten Sie, dass Ausrichtungslinien wieder angezeigt werden.  
  
## <a name="disabling-snaplines"></a>Deaktivieren von Ausrichtungslinien  
 Ausrichtungslinien sind standardmäßig aktiviert. Sie können Ausrichtungslinien selektiv deaktivieren, oder deaktivieren sie in der entwurfsumgebung.  
  
#### <a name="to-selectively-disable-snaplines"></a>Um Ausrichtungslinien selektiv zu deaktivieren.  
  
-   Drücken Sie die ALT-Taste, und zwar ein Steuerelement am Rand des Formulars verschieben.  
  
     Beachten Sie, dass keine Ausrichtungslinien angezeigt werden, und das Steuerelement wird an alle potenziellen Ausrichtungspositionen nicht ausgerichtet.  
  
#### <a name="to-disable-snaplines-in-the-design-environment"></a>So deaktivieren Sie die Ausrichtungslinien, die in der entwurfsumgebung  
  
1.  Von der **Tools** öffnen die **Optionen** Dialogfeld. Öffnen Sie im Dialogfeld Windows Forms-Designer. Weitere Informationen finden Sie unter [Allgemein, Windows Forms-Designer, Optionen (Dialogfeld)](https://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834).  
  
2.  Wählen Sie die **allgemeine** Knoten. In der **Layoutmodus** Abschnitt, ändern Sie die Auswahl von **Ausrichtungslinien** zu **SnapToGrid**.  
  
3.  Klicken Sie auf OK, um die Einstellung zu übernehmen.  
  
4.  Wählen Sie ein Steuerelement im Formular aus, und verschieben Sie ihn den anderen Steuerelementen. Beachten Sie, dass keine Ausrichtungslinien angezeigt werden.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Ausrichtungslinien bietet eine intuitive Möglichkeit Ausrichten von Steuerelementen im Formular. Hier sind paar Vorschläge für weitere Experimente:  
  
-   Testen der Schachtelungsebene einer <xref:System.Windows.Forms.GroupBox> Steuerelement innerhalb einer anderen <xref:System.Windows.Forms.GroupBox> Steuerelement. Stelle eine <xref:System.Windows.Forms.Button> Steuerelement innerhalb der untergeordneten <xref:System.Windows.Forms.GroupBox> -Steuerelement und ein anderes innerhalb des übergeordneten Elements <xref:System.Windows.Forms.GroupBox> Steuerelement. Verschieben der <xref:System.Windows.Forms.Button> Steuerelemente, um zu sehen, wie die Ausrichtungslinien Containergrenzen schneiden.  
  
-   Erstellen Sie eine Spalte des <xref:System.Windows.Forms.TextBox> Steuerelemente und eine entsprechende Spalte der <xref:System.Windows.Forms.Label> Steuerelemente. Legen Sie den Wert, der die <xref:System.Windows.Forms.Label> Steuerelemente <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft `true`. Verwenden Sie Ausrichtungslinien zum Verschieben der <xref:System.Windows.Forms.Label> steuert, sodass der Text in der angezeigten Text ausgerichtet ist die <xref:System.Windows.Forms.TextBox> Steuerelemente.  
  
 Informationen zum Entwurf der Benutzeroberfläche Windows finden Sie in das Buch *Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers* Redmond, WA, USA: Microsoft Press, 1999. (USBN: 0-7356-0566-1).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Design.Behavior.SnapLine>  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)  
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
