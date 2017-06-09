---
title: "Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abst&#228;nden, R&#228;ndern und der AutoSize-Eigenschaft | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Margin.Bottom"
  - "Margin.Left"
  - "Margin.Top"
  - "Margin.All"
  - "Margin.Right"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "AutoSize-Eigenschaft, Exemplarische Vorgehensweisen"
  - "Layout [Windows Forms], Ränder und Abstand"
  - "Margin-Eigenschaft [Windows Forms], Exemplarische Vorgehensweisen"
  - "Padding-Eigenschaft [Windows Forms], Exemplarische Vorgehensweisen"
  - "Exemplarische Vorgehensweisen [Windows Forms], Layout"
  - "Windows Forms, Layout"
ms.assetid: f8ae2a6b-db13-4630-8e25-d104091205c7
caps.latest.revision: 28
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 28
---
# Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abst&#228;nden, R&#228;ndern und der AutoSize-Eigenschaft
Die präzise Platzierung von Steuerelementen auf dem Formular hat für viele Anwendungen einen hohen Stellenwert.  Der **Windows Forms\-Designer** bietet Ihnen hierfür zahlreiche Layouttools.  Drei der wichtigsten Tools sind die Eigenschaften <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A> und <xref:System.Windows.Forms.Control.AutoSize%2A>, über die jedes Windows Forms\-Steuerelement verfügt.  
  
 Die <xref:System.Windows.Forms.Control.Margin%2A>\-Eigenschaft definiert den Bereich um das Steuerelement, durch den andere Steuerelemente in einem bestimmten Abstand von den Rändern des Steuerelements entfernt bleiben.  
  
 Die <xref:System.Windows.Forms.Control.Padding%2A>\-Eigenschaft definiert den Bereich innerhalb eines Steuerelements, durch den der Inhalt des Steuerelements \(z. B. der Wert seiner <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft\) in einem bestimmten Abstand von den Rändern des Steuerelements entfernt bleibt.  
  
 Die folgende Abbildung zeigt die <xref:System.Windows.Forms.Control.Padding%2A>\-Eigenschaft und die <xref:System.Windows.Forms.Control.Margin%2A>\-Eigenschaft für ein Steuerelement.  
  
 ![Ränder und Abstände bei Windows Forms&#45;Steuerelementen](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS\_WinFormPadMargin")  
  
 Die <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft weist ein Steuerelement an, seine Größe automatisch an seinen Inhalt anzupassen.  Seine Größe entspricht jedoch mindestens dem Wert der ursprünglichen <xref:System.Windows.Forms.Control.Size%2A>\-Eigenschaft. Außerdem wird bei der Anpassung der Wert der <xref:System.Windows.Forms.Control.Padding%2A>\-Eigenschaft berücksichtigt.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen eines Windows Forms\-Projekts  
  
-   Festlegen von Rändern für die Steuerelemente  
  
-   Festlegen eines Abstands für die Steuerelemente  
  
-   Automatisches Anpassen der Größe der Steuerelemente  
  
 Anschließend werden Sie verstehen, welche Rolle diese wichtigen Layoutfeatures spielen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Vorbereitungsmaßnahmen  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Ausreichende Berechtigungen zum Erstellen und Ausführen von Windows Forms\-Anwendungsprojekten auf dem Computer, auf dem Visual Studio installiert ist.  
  
## Erstellen des Projekts  
 Zunächst wird das Projekt erstellt und das Formular eingerichtet.  
  
#### So erstellen Sie das Projekt  
  
1.  Erstellen Sie ein Projekt vom Typ **Windows\-Anwendung** mit dem Namen `LayoutExample`.  Weitere Informationen finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Wählen Sie im **Windows Forms\-Designer** das Formular aus.  
  
## Festlegen von Rändern für die Steuerelemente  
 Sie können den standardmäßigen Abstand zwischen den Steuerelementen mithilfe der <xref:System.Windows.Forms.Control.Margin%2A>\-Eigenschaft festlegen.  Wenn Sie ein Steuerelement nahe genug an ein anderes Steuerelement verschieben, wird eine Ausrichtungslinie angezeigt, die die Ränder zwischen den beiden Steuerelement angibt.  Das Steuerelement, das Sie verschieben, wird ebenfalls mit dem von den Rändern definierten Abstand ausgerichtet.  
  
#### So ordnen Sie Steuerelemente auf dem Formular mithilfe der Margin\-Eigenschaft an  
  
1.  Ziehen Sie zwei <xref:System.Windows.Forms.Button>\-Steuerelemente aus der **Toolbox** auf das Formular.  
  
2.  Wählen Sie eines der <xref:System.Windows.Forms.Button>\-Steuerelemente aus, und verschieben Sie es in die Nähe des jeweils anderen, bis sie sich beinahe berühren.  
  
     Beachten Sie die Ausrichtungslinie, die zwischen ihnen angezeigt wird.  Dieser Abstand entspricht der Summe der <xref:System.Windows.Forms.Control.Margin%2A>\-Werte der beiden Steuerelemente.  Das Steuerelement, das Sie verschieben, wird mit diesem Abstand ausgerichtet.  Ausführliche Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
3.  Ändern Sie die <xref:System.Windows.Forms.Control.Margin%2A>\-Eigenschaft eines der beiden Steuerelemente, indem Sie den <xref:System.Windows.Forms.Control.Margin%2A>\-Eintrag im **Eigenschaftenfenster** erweitern und die <xref:System.Windows.Forms.Padding.All%2A>\-Eigenschaft auf 20 festlegen.  
  
4.  Wählen Sie eines der <xref:System.Windows.Forms.Button>\-Steuerelemente aus, und verschieben Sie es in die Nähe des anderen.  
  
     Die Ausrichtungslinie, die die Summer der Werte für die Ränder definiert, ist länger, d. h., das Steuerelement wird mit einem größeren Abstand zum anderen Steuerelement ausgerichtet.  
  
5.  Ändern Sie die <xref:System.Windows.Forms.Control.Margin%2A>\-Eigenschaft des ausgewählten Steuerelements, indem Sie den <xref:System.Windows.Forms.Control.Margin%2A>\-Eintrag im **Eigenschaftenfenster** erweitern und die <xref:System.Windows.Forms.Padding.Top%2A>\-Eigenschaft auf 5 festlegen.  
  
6.  Verschieben Sie das ausgewählte Steuerelement unter das andere Steuerelement, und beachten Sie, dass die Ausrichtungslinie kürzer ist.  Verschieben Sie das ausgewählte Steuerelement links neben das andere Steuerelement, und beobachten Sie, dass die Ausrichtungslinie den Wert aus Schritt 4 beibehält.  
  
7.  Sie können für alle Aspekte der <xref:System.Windows.Forms.Control.Margin%2A>\-Eigenschaft, d. h. für <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A> und <xref:System.Windows.Forms.Padding.Bottom%2A>, verschiedene Werte festlegen oder mit der <xref:System.Windows.Forms.Padding.All%2A>\-Eigenschaft für alle denselben Wert festlegen.  
  
## Festlegen eines Abstands für die Steuerelemente  
 Um das für die Anwendung erforderliche präzise Layout zu erreichen, enthalten die Steuerelemente häufig untergeordnete Steuerelemente.  Wenn Sie den Abstand zwischen den Rändern des untergeordneten Steuerelements und den Rändern des übergeordneten Steuerelements festlegen möchten, verwenden Sie die <xref:System.Windows.Forms.Control.Padding%2A>\-Eigenschaft des übergeordneten Steuerelements zusammen mit der <xref:System.Windows.Forms.Control.Margin%2A>\-Eigenschaft des untergeordneten Steuerelements.  Die <xref:System.Windows.Forms.Control.Padding%2A>\-Eigenschaft wird außerdem verwendet, um den Abstand des Inhalts eines Steuerelements \(z. B. die <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft eines <xref:System.Windows.Forms.Button>\-Steuerelements\) zu seinen Rändern zu steuern.  
  
#### So ordnen Sie Steuerelemente auf dem Formular mithilfe des Abstands an  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.Button>\-Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements in `true`.  
  
3.  Ändern Sie die <xref:System.Windows.Forms.Control.Padding%2A>\-Eigenschaft, indem Sie den <xref:System.Windows.Forms.Control.Padding%2A>\-Eintrag im **Eigenschaftenfenster** erweitern und die <xref:System.Windows.Forms.Padding.All%2A>\-Eigenschaft auf 5 festlegen.  
  
     Das Steuerelement wird gemäß dem neuen Abstand erweitert.  
  
4.  Ziehen Sie ein <xref:System.Windows.Forms.GroupBox>\-Steuerelement aus der **Toolbox** auf das Formular.  Ziehen Sie ein <xref:System.Windows.Forms.Button>\-Steuerelement aus der **Toolbox** in das <xref:System.Windows.Forms.GroupBox>\-Steuerelement.  Positionieren Sie das <xref:System.Windows.Forms.Button>\-Steuerelement so, dass es an der rechten unteren Ecke des <xref:System.Windows.Forms.GroupBox>\-Steuerelements ausgerichtet ist.  
  
     Beachten Sie die Ausrichtungslinien, die angezeigt werden, wenn sich das <xref:System.Windows.Forms.Button>\-Steuerelement dem unteren und rechten Rand des <xref:System.Windows.Forms.GroupBox>\-Steuerelements nähert.  Diese Ausrichtungslinien entsprechen der <xref:System.Windows.Forms.Control.Margin%2A>\-Eigenschaft des <xref:System.Windows.Forms.Button>.  
  
5.  Ändern Sie die <xref:System.Windows.Forms.Control.Padding%2A>\-Eigenschaft des <xref:System.Windows.Forms.GroupBox>\-Steuerelements, indem Sie den <xref:System.Windows.Forms.Control.Padding%2A>\-Eintrag im **Eigenschaftenfenster** erweitern und die <xref:System.Windows.Forms.Padding.All%2A>\-Eigenschaft auf 20 festlegen.  
  
6.  Wählen Sie das <xref:System.Windows.Forms.Button>\-Steuerelement innerhalb des <xref:System.Windows.Forms.GroupBox>\-Steuerelements aus, und verschieben Sie es in Richtung der Mitte des <xref:System.Windows.Forms.GroupBox>\-Steuerelements.  
  
     Die Ausrichtungslinien werden mit einem größeren Abstand von den Rändern des <xref:System.Windows.Forms.GroupBox>\-Steuerelements angezeigt.  Dieser Abstand entspricht der Summe der <xref:System.Windows.Forms.Control.Margin%2A>\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements und der <xref:System.Windows.Forms.Control.Padding%2A>\-Eigenschaft des <xref:System.Windows.Forms.GroupBox>\-Steuerelements.  
  
## Automatisches Anpassen der Größe der Steuerelemente  
 In einigen Anwendungen ist die Größe eines Steuerelements zur Laufzeit nicht dieselbe wie zur Entwurfszeit.  Der Text eines <xref:System.Windows.Forms.Button>\-Steuerelements kann beispielsweise aus einer Datenbank abgerufen werden, ohne dass seine Länge vorab bekannt ist.  
  
 Wenn die <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft auf `true` festgelegt ist, passt sich die Größe des Steuerelements an seinen Inhalt an.  Weitere Informationen finden Sie unter [Übersicht über die AutoSize\-Eigenschaft](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
#### So ordnen Sie Steuerelemente auf dem Formular mithilfe der AutoSize\-Eigenschaft an  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.Button>\-Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements in `true`.  
  
3.  Ändern Sie die <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements in "This button has a long string for its Text property".  
  
     Wenn Sie die Änderung anwenden, passt sich die Größe des <xref:System.Windows.Forms.Button>\-Steuerelements an den neuen Text an.  
  
4.  Ziehen Sie ein weiteres <xref:System.Windows.Forms.Button>\-Steuerelement aus der **Toolbox** auf das Formular.  
  
5.  Ändern Sie die <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements in "This button has a long string for its Text property".  
  
     Wenn Sie die Änderung anwenden, passt sich die Größe des <xref:System.Windows.Forms.Button>\-Steuerelements nicht an, und der Text wird am rechten Rand des Steuerelements abgeschnitten.  
  
6.  Ändern Sie die <xref:System.Windows.Forms.Control.Padding%2A>\-Eigenschaft, indem Sie den <xref:System.Windows.Forms.Control.Padding%2A>\-Eintrag im **Eigenschaftenfenster** erweitern und die <xref:System.Windows.Forms.Padding.All%2A>\-Eigenschaft auf 5 festlegen.  
  
     Der Text innerhalb des Steuerelements wird an allen vier Seiten abgeschnitten.  
  
7.  Ändern Sie die <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements in `true`.  
  
     Die Größe des <xref:System.Windows.Forms.Button>\-Steuerelements passt sich an die Zeichenfolge an, sodass es diese vollständig umschließt.  Zudem wurde um den Text herum ein Abstand hinzugefügt, wodurch das <xref:System.Windows.Forms.Button>\-Steuerelement in alle vier Richtungen erweitert wird.  
  
8.  Ziehen Sie ein <xref:System.Windows.Forms.Button>\-Steuerelement aus der **Toolbox** auf das Formular.  Positionieren Sie es in der Nähe der rechten unteren Ecke des Formulars.  
  
9. Ändern Sie den Wert der <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements in `true`.  
  
10. Legen Sie die <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements auf <xref:System.Windows.Forms.AnchorStyles> und <xref:System.Windows.Forms.AnchorStyles> fest.  
  
11. Ändern Sie die <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements in "This button has a long string for its Text property".  
  
     Wenn Sie die Änderung anwenden, passt sich die Größe des <xref:System.Windows.Forms.Button>\-Steuerelements nach links an.  Im Allgemeinen bewirkt die automatische Größenanpassung, dass sich die Größe eines Steuerelements in entgegengesetzter Richtung zur Einstellung der <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaft erhöht.  
  
## AutoSize\-Eigenschaft und AutoSizeMode\-Eigenschaft  
 Einige Steuerelemente unterstützen die `AutoSizeMode`\-Eigenschaft, mit der Sie die automatische Anpassung eines Steuerelements genauer steuern können.  
  
#### So verwenden Sie die AutoSizeMode\-Eigenschaft  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.Panel>\-Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Legen Sie den Wert der <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft des <xref:System.Windows.Forms.Panel>\-Steuerelements auf `true` fest.  
  
3.  Ziehen Sie ein <xref:System.Windows.Forms.Button>\-Steuerelement aus der **Toolbox** in das <xref:System.Windows.Forms.Panel>\-Steuerelement.  
  
4.  Platzieren Sie das <xref:System.Windows.Forms.Button>\-Steuerelement in der Nähe der rechten unteren Ecke des <xref:System.Windows.Forms.Panel>\-Steuerelements.  
  
5.  Wählen Sie das <xref:System.Windows.Forms.Panel>\-Steuerelement aus, und klicken Sie auf den rechten unteren Ziehpunkt.  Vergrößern oder verkleinern Sie das <xref:System.Windows.Forms.Panel>\-Steuerelement.  
  
    > [!NOTE]
    >  Sie können die Größe des <xref:System.Windows.Forms.Panel>\-Steuerelements bis zur Position der rechten unteren Ecke des <xref:System.Windows.Forms.Button>\-Steuerelements beliebig ändern.  Dieses Verhalten wird vom Standardwert der `AutoSizeMode`\-Eigenschaft festgelegt, d. h. von <xref:System.Windows.Forms.AutoSizeMode>.  
  
6.  Legen Sie den Wert der `AutoSizeMode`\-Eigenschaft des <xref:System.Windows.Forms.Panel>\-Steuerelements auf <xref:System.Windows.Forms.AutoSizeMode> fest.  
  
     Die Größe des <xref:System.Windows.Forms.Panel>\-Steuerelements passt sich so an, dass es das <xref:System.Windows.Forms.Button>\-Steuerelement umgibt.  Sie können die Größe des <xref:System.Windows.Forms.Panel>\-Steuerelements nicht ändern.  
  
7.  Ziehen Sie das <xref:System.Windows.Forms.Button>\-Steuerelement in die linke obere Ecke des <xref:System.Windows.Forms.Panel>\-Steuerelements.  
  
     Die Größe des <xref:System.Windows.Forms.Panel>\-Steuerelements passt sich an die neue Position des <xref:System.Windows.Forms.Button>\-Steuerelements an.  
  
## Nächste Schritte  
 Es gibt zahlreiche weitere Layoutfeatures zum Anordnen von Steuerelementen in Windows Forms\-Anwendungen.  Probieren Sie beispielsweise folgende Kombinationen aus:  
  
-   Erstellen Sie ein Formular mithilfe eines <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements.  Ausführliche Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).  Versuchen Sie, die Werte der <xref:System.Windows.Forms.Control.Padding%2A>\-Eigenschaft des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements sowie die <xref:System.Windows.Forms.Control.Margin%2A>\-Eigenschaft der untergeordneten Steuerelemente zu ändern.  
  
-   Versuchen Sie dies mit einem <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelement.  Ausführliche Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).  
  
-   Docken Sie untergeordnete Steuerelemente in einem <xref:System.Windows.Forms.Panel>\-Steuerelement an.  Die <xref:System.Windows.Forms.Control.Padding%2A>\-Eigenschaft ist eine allgemeinere Variante der <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>\-Eigenschaft. Sie können sich hiervon überzeugen, indem Sie ein untergeordnetes Steuerelement in ein <xref:System.Windows.Forms.Panel>\-Steuerelement einfügen und die <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft des untergeordneten Steuerelements auf <xref:System.Windows.Forms.DockStyle> festlegen.  Legen Sie die <xref:System.Windows.Forms.Control.Padding%2A>\-Eigenschaft des <xref:System.Windows.Forms.Panel>\-Steuerelements auf verschiedene Werte fest, und beachten Sie die Auswirkung.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Control.AutoSize%2A>   
 <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>   
 <xref:System.Windows.Forms.Control.Margin%2A>   
 <xref:System.Windows.Forms.Control.Padding%2A>   
 [Übersicht über die AutoSize\-Eigenschaft](../../../../docs/framework/winforms/controls/autosize-property-overview.md)   
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)   
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)