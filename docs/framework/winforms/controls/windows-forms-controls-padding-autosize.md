---
title: "Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 797a432bb8cfd3af3b5f030be8f71c78a1a393e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-laying-out-windows-forms-controls-with-padding-margins-and-the-autosize-property"></a>Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft
Die präzise Platzierung von Steuerelementen auf dem Formular hat für viele Anwendungen einen hohen Stellenwert. Die **Windows Forms-Designer** bietet Ihnen viele Layouttools, um dies zu erreichen. Drei der wichtigsten sind die <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>, und <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaften, die auf alle Windows Forms-Steuerelemente vorhanden sind.  
  
 Die <xref:System.Windows.Forms.Control.Margin%2A>-Eigenschaft definiert den Bereich um das Steuerelement, durch den andere Steuerelemente einen bestimmten Abstand von den Rändern des Steuerelements einhalten müssen.  
  
 Die <xref:System.Windows.Forms.Control.Padding%2A>-Eigenschaft definiert den Bereich innerhalb eines Steuerelements, durch den der Inhalt des Steuerelements (z. B. der Wert seiner <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft) einen bestimmten Abstand von den Rändern des Steuerelements einhalten muss.  
  
 Die folgende Abbildung zeigt die <xref:System.Windows.Forms.Control.Padding%2A>-Eigenschaft und die <xref:System.Windows.Forms.Control.Margin%2A>-Eigenschaft für ein Steuerelement.  
  
 ![Ränder und Abstände bei Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")  
  
 Die <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft weist ein Steuerelement an, seine Größe automatisch an seinen Inhalt angepasst. Es wird nicht seine kleiner sein als der Wert der ursprünglichen Größe <xref:System.Windows.Forms.Control.Size%2A> -Eigenschaft, und es wird der Wert der berücksichtigen seine <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen eines Windows Forms-Projekts  
  
-   Festlegen von Rändern für Ihre Steuerelemente  
  
-   Festlegen der Auffüllung für Ihre Steuerelemente  
  
-   Automatisches Anpassen der Größe Ihrer Steuerelemente  
  
 Wenn Sie diese Aufgaben durchgearbeitet haben, besitzen Sie ein Verständnis für die Rolle, die diese wichtigen Layoutfunktionen spielen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Ausreichende Berechtigungen zum Erstellen und Ausführen von Windows Forms-Anwendungsprojekten auf dem Computer, auf dem Visual Studio installiert ist.  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.  
  
#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
1.  Erstellen einer **Windows-Anwendung** Projekt mit der Bezeichnung `LayoutExample`. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) .  
  
2.  Wählen Sie das Formular in der **Windows Forms-Designer**.  
  
## <a name="setting-margins-for-your-controls"></a>Festlegen von Rändern für Ihre Steuerelemente  
 Sie können den Standardabstand zwischen den Steuerelementen mithilfe Festlegen der <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft. Wenn Sie ein Steuerelement verschieben genug, um ein anderes Steuerelement zu schließen, wird eine Ausrichtungslinie, die die Ränder für die beiden Steuerelemente angezeigt werden. Das Steuerelement, das Sie verschieben möchten, wird auch an den Abstand von den Rändern definierten ausgerichtet.  
  
#### <a name="to-arrange-controls-on-your-form-using-the-margin-property"></a>Anordnen von Steuerelementen auf dem Formular mithilfe der Margin-Eigenschaft  
  
1.  Ziehen Sie zwei <xref:System.Windows.Forms.Button> -Steuerelemente aus der **Toolbox** auf das Formular.  
  
2.  Wählen Sie eine von der <xref:System.Windows.Forms.Button> -Steuerelemente sowie die in der Nähe der anderen zu verschieben, bis sie fast berühren.  
  
     Beachten Sie die Ausrichtungslinie, die zwischen ihnen angezeigt wird. Dieser Abstand wird die Summe der beiden Steuerelemente <xref:System.Windows.Forms.Control.Margin%2A> Werte. Das Steuerelement, das Sie verschieben möchten, wird dieser Abstand ausgerichtet. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
3.  Ändern der <xref:System.Windows.Forms.Control.Margin%2A> -Eigenschaft eines der Steuerelemente erweitern die <xref:System.Windows.Forms.Control.Margin%2A> Eintrag in der **Eigenschaften** Fenster und die Einstellung der <xref:System.Windows.Forms.Padding.All%2A> Eigenschaft bis 20.  
  
4.  Wählen Sie eine der der <xref:System.Windows.Forms.Button> -Steuerelemente sowie die in der Nähe der anderen zu verschieben.  
  
     Der Ausrichtungslinie steuern länger ist die Summe der Werte für Ränder definieren und, dass das Steuerelement mit einem größeren Abstand von den anderen ausgerichtet wird.  
  
5.  Ändern der <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft des ausgewählten Steuerelements durch Erweitern der <xref:System.Windows.Forms.Control.Margin%2A> Eintrag in der **Eigenschaften** Fenster und die Einstellung der <xref:System.Windows.Forms.Padding.Top%2A> Eigenschaft bis 5.  
  
6.  Bewegen Sie des ausgewählten Steuerelements unter dem anderen Steuerelement, und beachten Sie, dass die Ausrichtungslinie kürzer ist. Bewegen Sie des ausgewählten Steuerelements auf der linken Seite eines anderen Steuerelements, und beachten Sie, dass der Ausrichtungslinie den Wert aus Schritt 4 beibehält.  
  
7.  Legen Sie alle Aspekte von der <xref:System.Windows.Forms.Control.Margin%2A> -Eigenschaft, <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A>, um unterschiedliche Werte, oder Sie können alle auf den gleichen Wert mit Festlegen der <xref:System.Windows.Forms.Padding.All%2A> Eigenschaft.  
  
## <a name="setting-padding-for-your-controls"></a>Festlegen der Auffüllung für Ihre Steuerelemente  
 Um die genaue Layout für Ihre Anwendung erforderliche zu erreichen, werden die Steuerelemente häufig untergeordneten Steuerelemente enthalten. Wenn Sie den Abstand des Rahmens des untergeordneten Steuerelements auf das übergeordnete Steuerelement Rahmen angeben möchten, verwenden Sie des übergeordnete Steuerelements <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft in Verbindung mit des untergeordneten Steuerelements <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft. Die <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft wird auch verwendet, um den Abstand des Inhalts eines Steuerelements zu steuern (z. B. eine <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft) zu seinen Rändern.  
  
#### <a name="to-arrange-controls-on-your-form-using-padding"></a>Anordnen von Steuerelementen auf dem Formular mithilfe der Auffüllung  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.AutoSize%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in `true`.  
  
3.  Ändern der <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft durch Erweitern der <xref:System.Windows.Forms.Control.Padding%2A> Eintrag in der **Eigenschaften** Fenster und die Einstellung der <xref:System.Windows.Forms.Padding.All%2A> Eigenschaft bis 5.  
  
     Das Steuerelement wird erweitert, um Raum für die neue Auffüllung bereitzustellen.  
  
4.  Ziehen Sie eine <xref:System.Windows.Forms.GroupBox> -Steuerelement aus der **Toolbox** auf das Formular. Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** in die <xref:System.Windows.Forms.GroupBox> Steuerelement. Position der <xref:System.Windows.Forms.Button> steuern, daher ist es schließt bündig mit der rechten unteren Ecke des der <xref:System.Windows.Forms.GroupBox> Steuerelement.  
  
     Beachten Sie die Ausrichtungslinien, die als angezeigt werden die <xref:System.Windows.Forms.Button> Steuerelement nähert sich dem unteren und rechten Rahmen der <xref:System.Windows.Forms.GroupBox> Steuerelement. Diese Ausrichtungslinien entsprechen den <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft von der <xref:System.Windows.Forms.Button>.  
  
5.  Ändern der <xref:System.Windows.Forms.GroupBox> des Steuerelements <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft durch Erweitern der <xref:System.Windows.Forms.Control.Padding%2A> Eintrag in der **Eigenschaften** Fenster und der Einstellung der <xref:System.Windows.Forms.Padding.All%2A> Eigenschaft bis 20.  
  
6.  Wählen Sie die <xref:System.Windows.Forms.Button> -Steuerelement innerhalb der <xref:System.Windows.Forms.GroupBox> steuern und verschieben Sie sie an der Mitte des der <xref:System.Windows.Forms.GroupBox>.  
  
     Die Ausrichtungslinien angezeigt werden mit einem größeren Abstand von den Rändern des der <xref:System.Windows.Forms.GroupBox> Steuerelement. Dieser Abstand wird die Summe der <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft und die <xref:System.Windows.Forms.GroupBox> des Steuerelements <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft.  
  
## <a name="automatically-sizing-your-controls"></a>Automatisches Anpassen der Größe Ihrer Steuerelemente  
 In einigen Anwendungen wird die Größe eines Steuerelements identisch zur Laufzeit nicht zur Entwurfszeit vorlag. Der Text, der eine <xref:System.Windows.Forms.Button> -Steuerelement, z. B. möglicherweise ausgeführt werden aus einer Datenbank, und seine Länge wird nicht im Voraus bekannt sein.  
  
 Wenn die <xref:System.Windows.Forms.Control.AutoSize%2A> -Eigenschaftensatz auf `true`, wird die Größe des Steuerelements selbst zum jeweiligen Inhalt. Weitere Informationen finden Sie unter [Übersicht über die AutoSize-Eigenschaft](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
#### <a name="to-arrange-controls-on-your-form-using-the-autosize-property"></a>Anordnen von Steuerelementen auf dem Formular mithilfe der AutoSize-Eigenschaft  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.AutoSize%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in `true`.  
  
3.  Ändern der <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Text%2A> -Eigenschaft auf "**Schaltfläche befindet sich eine lange Zeichenfolge für seine Texteigenschaft**."  
  
     Wenn Sie die Änderung zu übernehmen die <xref:System.Windows.Forms.Button> Steuerelement angepasst, damit der neue Text passt.  
  
4.  Ziehen Sie ein weiteres <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular.  
  
5.  Ändern der <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Text%2A> -Eigenschaft auf "**Schaltfläche befindet sich eine lange Zeichenfolge für seine Texteigenschaft.**"  
  
     Wenn Sie die Änderung zu übernehmen die <xref:System.Windows.Forms.Button> Steuerelement ändert die Größe nicht selbst, und der Text wird am rechten Rand des Steuerelements abgeschnitten.  
  
6.  Ändern der <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft durch Erweitern der <xref:System.Windows.Forms.Control.Padding%2A> Eintrag in der **Eigenschaften** Fenster und die Einstellung der <xref:System.Windows.Forms.Padding.All%2A> Eigenschaft bis 5.  
  
     Der Text in das Steuerelement innere wird auf allen vier Seiten abgeschnitten.  
  
7.  Ändern der <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft `true`.  
  
     Die <xref:System.Windows.Forms.Button> Steuerelements angepasst, damit die gesamte Zeichenfolge enthält. Darüber hinaus Auffüllung zwischen dem Text hinzugefügt wurde verursacht die <xref:System.Windows.Forms.Button> Steuerelement in alle vier Richtungen erweitern.  
  
8.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular. Positionieren Sie es in der Nähe der rechten unteren Ecke des Formulars.  
  
9. Ändern Sie den Wert der <xref:System.Windows.Forms.Control.AutoSize%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuerelements in `true`.  
  
10. Legen Sie die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft <xref:System.Windows.Forms.AnchorStyles.Right>, <xref:System.Windows.Forms.AnchorStyles.Bottom>.  
  
11. Ändern der <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Text%2A> -Eigenschaft auf "**Schaltfläche befindet sich eine lange Zeichenfolge für seine Texteigenschaft.**"  
  
     Wenn Sie die Änderung zu übernehmen die <xref:System.Windows.Forms.Button> Steuerelement passt sich an der linken Seite. Automatische größenanpassung im Allgemeinen wird die Größe eines Steuerelements in die entgegengesetzte Richtung erhöhen die <xref:System.Windows.Forms.Control.Anchor%2A> Einstellung der Eigenschaft.  
  
## <a name="autosize-and-autosizemode-properties"></a>AutoSize und AutoSizeMode-Eigenschaft  
 Einige Steuerelemente unterstützen die `AutoSizeMode` -Eigenschaft, die eine präzisere Kontrolle über das automatische Größenanpassungsverhalten eines Steuerelements enthält.  
  
#### <a name="to-use-the-autosizemode-property"></a>Verwenden Sie die AutoSizeMode-Eigenschaft  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.Panel> -Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Legen Sie den Wert, der die <xref:System.Windows.Forms.Panel> des Steuerelements <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft `true`.  
  
3.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** in die <xref:System.Windows.Forms.Panel> Steuerelement.  
  
4.  Ort der <xref:System.Windows.Forms.Button> in der Nähe der rechten unteren Ecke des Steuerelements die <xref:System.Windows.Forms.Panel> Steuerelement.  
  
5.  Wählen Sie die <xref:System.Windows.Forms.Panel> steuern, und ziehen Sie den unteren rechten Ziehpunkt. Ändern Sie die Größe der <xref:System.Windows.Forms.Panel> Steuerelement größere und kleinere befinden.  
  
    > [!NOTE]
    >  Sie können beliebig ändern die <xref:System.Windows.Forms.Panel> -Steuerelement, aber Sie können keine Ändern der Größe kleiner als die Position des der <xref:System.Windows.Forms.Button> die unteren rechten Ecke des Steuerelements. Dieses Verhalten wird angegeben, indem der Wert von der `AutoSizeMode` Eigenschaft, die <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>.  
  
6.  Legen Sie den Wert, der die <xref:System.Windows.Forms.Panel> des Steuerelements `AutoSizeMode` Eigenschaft <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>.  
  
     Die <xref:System.Windows.Forms.Panel> -Steuerelement passt sich zum Umschließen der <xref:System.Windows.Forms.Button> Steuerelement. Kann nicht geändert werden die <xref:System.Windows.Forms.Panel> Steuerelement.  
  
7.  Ziehen Sie die <xref:System.Windows.Forms.Button> in Richtung der oberen linken Ecke des Steuerelements die <xref:System.Windows.Forms.Panel> Steuerelement.  
  
     Die <xref:System.Windows.Forms.Panel> Registerkartensteuerelements der <xref:System.Windows.Forms.Button> neue Position des Steuerelements.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Es gibt zahlreiche Layoutfunktionen zum Anordnen von Steuerelementen in Windows Forms-Anwendungen. Hier sind einige Kombinationen, die Sie ausprobieren können:  
  
-   Erstellen eines Formulars mit einem <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md). Ändern Sie die Werte der <xref:System.Windows.Forms.TableLayoutPanel> des Steuerelements <xref:System.Windows.Forms.Control.Padding%2A> -Eigenschaft, als auch die <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft der untergeordneten Steuerelemente.  
  
-   Wiederholen Sie die gleiche Experiment mit einem <xref:System.Windows.Forms.FlowLayoutPanel> Steuerelement. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).  
  
-   Experimentieren Sie mit dem Andocken von untergeordneten Steuerelementen in einem <xref:System.Windows.Forms.Panel> Steuerelement. Die <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft ist eine allgemeinere Realisierung der der <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> -Eigenschaft, und Sie können vorgegebene selbst, dass dies der Fall ist, verlegen Sie ein untergeordnetes Steuerelement einer <xref:System.Windows.Forms.Panel> Steuerelement und Festlegen des untergeordneten Steuerelements <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Fill>. Legen Sie die <xref:System.Windows.Forms.Panel> des Steuerelements <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft verschiedene Werte und beobachten Sie die Auswirkung.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Control.AutoSize%2A>  
 <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>  
 <xref:System.Windows.Forms.Control.Margin%2A>  
 <xref:System.Windows.Forms.Control.Padding%2A>  
 [Übersicht über die AutoSize-Eigenschaft](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
