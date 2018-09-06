---
title: 'Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft'
ms.date: 03/30/2017
f1_keywords:
- Margin.Bottom
- Margin.Left
- Margin.Top
- Margin.All
- Margin.Right
helpviewer_keywords:
- Margin property [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], layout
- AutoSize property [Windows Forms], walkthroughs
- Padding property [Windows Forms], walkthroughs
- layout [Windows Forms], margins and padding
- Windows Forms, layout
ms.assetid: f8ae2a6b-db13-4630-8e25-d104091205c7
ms.openlocfilehash: 52bc75135e4f8cf5b9c1888b2ad9f5e278c1d6e2
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43882443"
---
# <a name="walkthrough-laying-out-windows-forms-controls-with-padding-margins-and-the-autosize-property"></a>Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft
Die präzise Platzierung von Steuerelementen auf dem Formular hat für viele Anwendungen einen hohen Stellenwert. Die **Windows Forms-Designer** bietet Ihnen viele Layouttools, um dies zu erreichen. Drei der wichtigsten Faktoren sind die <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>, und <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaften, die auf alle Windows Forms-Steuerelemente vorhanden sind.  
  
 Die <xref:System.Windows.Forms.Control.Margin%2A>-Eigenschaft definiert den Bereich um das Steuerelement, durch den andere Steuerelemente einen bestimmten Abstand von den Rändern des Steuerelements einhalten müssen.  
  
 Die <xref:System.Windows.Forms.Control.Padding%2A>-Eigenschaft definiert den Bereich innerhalb eines Steuerelements, durch den der Inhalt des Steuerelements (z. B. der Wert seiner <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft) einen bestimmten Abstand von den Rändern des Steuerelements einhalten muss.  
  
 Die folgende Abbildung zeigt die <xref:System.Windows.Forms.Control.Padding%2A>-Eigenschaft und die <xref:System.Windows.Forms.Control.Margin%2A>-Eigenschaft für ein Steuerelement.  
  
 ![Ränder und Abstände für Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")  
  
 Die <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft weist ein Steuerelement an, seine Größe automatisch an seinen Inhalt angepasst. Es wird nicht seine kleiner sein als der Wert der ursprünglichen Größe <xref:System.Windows.Forms.Control.Size%2A> -Eigenschaft, und es wird für den Wert des Kontos die <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen eines Windows Forms-Projekts  
  
-   Festlegen von Rändern für Ihre Steuerelemente  
  
-   Abstand für Ihre Steuerelemente festlegen  
  
-   Automatisches Anpassen der Größe der Steuerelemente  
  
 Wenn Sie diese Aufgaben durchgearbeitet haben, besitzen Sie ein Verständnis für die Rolle, die diese wichtigen Layoutfunktionen spielen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Berechtigt sind, können zum Erstellen und Ausführen von Windows Forms-Anwendungsprojekten auf dem Computer, auf dem Visual Studio installiert ist.  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.  
  
#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
1.  Erstellen Sie eine **Windows-Anwendung** -Projekt namens `LayoutExample`. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) .  
  
2.  Wählen Sie das Formular in der **Windows Forms-Designer**.  
  
## <a name="setting-margins-for-your-controls"></a>Festlegen von Rändern für Ihre Steuerelemente  
 Sie können den Standardabstand zwischen den Steuerelementen mithilfe Festlegen der <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft. Wenn Sie ein Steuerelement verschieben wird genug, um ein anderes Steuerelement zu schließen, einer Ausrichtungslinie, die die Ränder für die beiden Steuerelemente anzeigt. Das Steuerelement, das Sie verschieben möchten, wird auch der Entfernung, die von den Rändern definierten ausgerichtet.  
  
#### <a name="to-arrange-controls-on-your-form-using-the-margin-property"></a>Anordnen von Steuerelementen auf dem Formular mithilfe der Margin-Eigenschaft  
  
1.  Ziehen Sie zwei <xref:System.Windows.Forms.Button> -Steuerelemente aus der **Toolbox** auf das Formular.  
  
2.  Wählen Sie eine der der <xref:System.Windows.Forms.Button> steuert und verschieben Sie es in der Nähe der anderen, bis sie sich fast berühren.  
  
     Beachten Sie die Ausrichtungslinie, die zwischen ihnen angezeigt wird. Diese Entfernung ist die Summe der beiden Steuerelemente <xref:System.Windows.Forms.Control.Margin%2A> Werte. Das Steuerelement, das Sie verschieben möchten, wird dieser Abstand ausgerichtet. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
3.  Ändern der <xref:System.Windows.Forms.Control.Margin%2A> -Eigenschaft eines der Steuerelemente erweitern die <xref:System.Windows.Forms.Control.Margin%2A> Eintrag in der **Eigenschaften** Fenster und der Einstellung der <xref:System.Windows.Forms.Padding.All%2A> -Eigenschaft auf 20.  
  
4.  Wählen Sie eine der der <xref:System.Windows.Forms.Button> steuert und verschieben Sie es in der Nähe der anderen.  
  
     Der Ausrichtungslinie steuern länger ist die Summe der Werte für die Ränder definieren und das Steuerelement eine größere Entfernung aus den anderen ausgerichtet wird.  
  
5.  Ändern der <xref:System.Windows.Forms.Control.Margin%2A> -Eigenschaft des ausgewählten Steuerelements durch Erweitern der <xref:System.Windows.Forms.Control.Margin%2A> Eintrag in der **Eigenschaften** Fenster und der Einstellung der <xref:System.Windows.Forms.Padding.Top%2A> -Eigenschaft auf 5.  
  
6.  Verschieben Sie das ausgewählte Steuerelement unterhalb des Steuerelements anderen zu, und beachten Sie, dass die Ausrichtungslinie kürzer ist. Bewegen Sie des ausgewählten Steuerelements auf der linken Seite des anderen Steuerelements, und beachten Sie, dass die Ausrichtungslinie den Wert aus Schritt 4 werden beibehalten.  
  
7.  Können Sie festlegen, alle Aspekte von der <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A>, um unterschiedliche Werte, oder Sie können sie alle an den gleichen Wert festlegen die <xref:System.Windows.Forms.Padding.All%2A> Eigenschaft.  
  
## <a name="setting-padding-for-your-controls"></a>Abstand für Ihre Steuerelemente festlegen  
 Um das genaue Layout für Ihre Anwendung erforderliche zu erreichen, werden die Steuerelemente häufig untergeordneten Steuerelemente enthalten. Wenn Sie die Nähe des Rahmens des untergeordneten Steuerelements zu den übergeordneten Rahmen des Steuerelements angeben möchten, verwenden Sie des übergeordneten Steuerelements <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft in Verbindung mit des untergeordneten Steuerelements <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft. Die <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft wird auch verwendet, um den Abstand des Inhalts eines Steuerelements zu steuern (z. B. eine <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft) zu seinen Rändern.  
  
#### <a name="to-arrange-controls-on-your-form-using-padding"></a>Anordnen von Steuerelementen auf dem Formular mithilfe von Abständen  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.AutoSize%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in `true`.  
  
3.  Ändern der <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft durch Erweitern der <xref:System.Windows.Forms.Control.Padding%2A> Eintrag in der **Eigenschaften** Fenster und der Einstellung der <xref:System.Windows.Forms.Padding.All%2A> -Eigenschaft auf 5.  
  
     Das Steuerelement wird erweitert, um Raum für die neue Auffüllung bereitzustellen.  
  
4.  Ziehen Sie eine <xref:System.Windows.Forms.GroupBox> -Steuerelement aus der **Toolbox** auf das Formular. Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** in die <xref:System.Windows.Forms.GroupBox> Steuerelement. Position der <xref:System.Windows.Forms.Button> Steuerelement, sodass es bündig mit der rechten unteren Ecke der ist die <xref:System.Windows.Forms.GroupBox> Steuerelement.  
  
     Beachten Sie die Ausrichtungslinien, die als angezeigt werden. die <xref:System.Windows.Forms.Button> -Steuerelement nähert, unteren und rechten Rand des der <xref:System.Windows.Forms.GroupBox> Steuerelement. Diese Ausrichtungslinien entsprechen den <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft der <xref:System.Windows.Forms.Button>.  
  
5.  Ändern der <xref:System.Windows.Forms.GroupBox> des Steuerelements <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft durch Erweitern der <xref:System.Windows.Forms.Control.Padding%2A> Eintrag in der **Eigenschaften** Fenster und der Einstellung der <xref:System.Windows.Forms.Padding.All%2A> -Eigenschaft auf 20.  
  
6.  Wählen Sie die <xref:System.Windows.Forms.Button> -Steuerelement innerhalb der <xref:System.Windows.Forms.GroupBox> steuern und verschieben Sie es an der Mitte des der <xref:System.Windows.Forms.GroupBox>.  
  
     Die Ausrichtungslinien an eine größere Entfernung angezeigt werden, von den Rahmenlinien des der <xref:System.Windows.Forms.GroupBox> Steuerelement. Diese Entfernung ist die Summe der <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft und die <xref:System.Windows.Forms.GroupBox> des Steuerelements <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft.  
  
## <a name="automatically-sizing-your-controls"></a>Automatisches Anpassen der Größe der Steuerelemente  
 In einigen Anwendungen wird die Größe eines Steuerelements identisch zur Laufzeit nicht zur Entwurfszeit vorlag. Der Text, der eine <xref:System.Windows.Forms.Button> -Steuerelement, z. B. ergriffen werden aus einer Datenbank und die Länge wird nicht im Voraus bekannt sein.  
  
 Wenn die <xref:System.Windows.Forms.Control.AutoSize%2A> -Eigenschaftensatz auf `true`, wird die Größe des Steuerelements selbst an dessen Inhalt. Weitere Informationen finden Sie unter [Übersicht über die AutoSize-Eigenschaft](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
#### <a name="to-arrange-controls-on-your-form-using-the-autosize-property"></a>Anordnen von Steuerelementen auf dem Formular mithilfe der AutoSize-Eigenschaft  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.AutoSize%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in `true`.  
  
3.  Ändern der <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft "**der Schaltfläche befindet sich eine lange Zeichenfolge für seine Texteigenschaft**."  
  
     Wenn Sie die Änderung anwenden, die <xref:System.Windows.Forms.Button> Steuerelement seine Größe ändert sich entsprechend den neuen Text.  
  
4.  Ziehen Sie ein weiteres <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular.  
  
5.  Ändern der <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft "**der Schaltfläche befindet sich eine lange Zeichenfolge für die Text-Eigenschaft.**"  
  
     Wenn Sie die Änderung anwenden, die <xref:System.Windows.Forms.Button> Steuerelement selbst keine Größenänderung und der Text wird abgeschnitten, indem Sie den rechten Rand des Steuerelements.  
  
6.  Ändern der <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft durch Erweitern der <xref:System.Windows.Forms.Control.Padding%2A> Eintrag in der **Eigenschaften** Fenster und der Einstellung der <xref:System.Windows.Forms.Padding.All%2A> -Eigenschaft auf 5.  
  
     Der Text in des Steuerelements wird auf allen vier Seiten abgeschnitten.  
  
7.  Ändern der <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft `true`.  
  
     Die <xref:System.Windows.Forms.Button> Steuerelement angepasst, damit die gesamte Zeichenfolge enthält. Darüber hinaus Auffüllung rund um den Text hinzugefügt wurde verursacht die <xref:System.Windows.Forms.Button> Steuerelement erweitern in der alle vier Richtungen.  
  
8.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular. Positionieren Sie sie in der Nähe der unteren rechten Ecke des Formulars.  
  
9. Ändern Sie den Wert der <xref:System.Windows.Forms.Control.AutoSize%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in `true`.  
  
10. Legen Sie die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft <xref:System.Windows.Forms.AnchorStyles.Right>, <xref:System.Windows.Forms.AnchorStyles.Bottom>.  
  
11. Ändern der <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft "**der Schaltfläche befindet sich eine lange Zeichenfolge für die Text-Eigenschaft.**"  
  
     Wenn Sie die Änderung anwenden, die <xref:System.Windows.Forms.Button> Steuerelement passt sich die Größe der linken Seite. Im Allgemeinen automatische Größenänderung die Größe eines Steuerelements in der entgegengesetzten Richtung erhöhen die <xref:System.Windows.Forms.Control.Anchor%2A> Einstellung der Eigenschaft.  
  
## <a name="autosize-and-autosizemode-properties"></a>Automatisches Anpassen der Größe und AutoSizeMode-Eigenschaft  
 Einige Steuerelemente unterstützen das `AutoSizeMode` -Eigenschaft, die Ihnen eine präzisere Kontrolle über das automatische Größenanpassungsverhalten eines Steuerelements bietet.  
  
#### <a name="to-use-the-autosizemode-property"></a>Verwenden Sie die AutoSizeMode-Eigenschaft  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.Panel> -Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Legen Sie den Wert, der die <xref:System.Windows.Forms.Panel> des Steuerelements <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft `true`.  
  
3.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** in die <xref:System.Windows.Forms.Panel> Steuerelement.  
  
4.  Ort der <xref:System.Windows.Forms.Button> Steuerelement nahe der unteren rechten Ecke des der <xref:System.Windows.Forms.Panel> Steuerelement.  
  
5.  Wählen Sie die <xref:System.Windows.Forms.Panel> steuern, und klicken Sie auf den unteren rechten Ziehpunkt. Ändern der Größe der <xref:System.Windows.Forms.Panel> Steuerelement größere und kleinere sein.  
  
    > [!NOTE]
    >  Sie können beliebig ändern der <xref:System.Windows.Forms.Panel> -Steuerelement, aber Sie können nicht die Größe kleiner ist als die Position des der <xref:System.Windows.Forms.Button> die untere rechte Ecke des Steuerelements. Dieses Verhalten wird angegeben, indem der Wert von der `AutoSizeMode` Eigenschaft, die <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>.  
  
6.  Legen Sie den Wert, der die <xref:System.Windows.Forms.Panel> des Steuerelements `AutoSizeMode` Eigenschaft <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>.  
  
     Die <xref:System.Windows.Forms.Panel> -Steuerelement passt sich zum Umschließen der <xref:System.Windows.Forms.Button> Steuerelement. Sie können nicht die Größe der <xref:System.Windows.Forms.Panel> Steuerelement.  
  
7.  Ziehen Sie die <xref:System.Windows.Forms.Button> Steuerelement auf der linken oberen Ecke des der <xref:System.Windows.Forms.Panel> Steuerelement.  
  
     Die <xref:System.Windows.Forms.Panel> Steuerelement seine Größe ändert, um die <xref:System.Windows.Forms.Button> neue Position des Steuerelements.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Es gibt viele andere Layoutfeatures für das Anordnen von Steuerelementen in Ihrer Windows Forms-Anwendungen. Hier sind einige Kombinationen, die Sie ausprobieren können:  
  
-   Erstellen eines Formulars mit einem <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md). Versuchen Sie es ändern der Werte von der <xref:System.Windows.Forms.TableLayoutPanel> des Steuerelements <xref:System.Windows.Forms.Control.Padding%2A> -Eigenschaft, als auch die <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft der untergeordneten Steuerelemente.  
  
-   Versuchen Sie es der gleichen Experiment mit einem <xref:System.Windows.Forms.FlowLayoutPanel> Steuerelement. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).  
  
-   Experimentieren Sie mit Andocken von untergeordneten Steuerelementen in einem <xref:System.Windows.Forms.Panel> Steuerelement. Die <xref:System.Windows.Forms.Control.Padding%2A> -Eigenschaft ist eine allgemeinere Variante von der <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> -Eigenschaft, und Sie können zu erfüllen selbst, dass dies der Fall ist, indem Sie Sie in ein untergeordnetes Steuerelement einfügen einer <xref:System.Windows.Forms.Panel> Steuerelement und Festlegen des untergeordneten Steuerelements <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Fill>. Legen Sie die <xref:System.Windows.Forms.Panel> des Steuerelements <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft verschiedene Werte und beobachten Sie die Auswirkung.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Control.AutoSize%2A>  
 <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>  
 <xref:System.Windows.Forms.Control.Margin%2A>  
 <xref:System.Windows.Forms.Control.Padding%2A>  
 [Übersicht über die AutoSize-Eigenschaft](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
