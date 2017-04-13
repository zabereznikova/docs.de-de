---
title: "Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Steuerelemente [Windows Forms], Anordnen mit Ausrichtungslinien"
  - "SnapLine-Klasse, Exemplarische Vorgehensweisen"
  - "Ausrichtungslinien, Anordnen von Windows Forms-Steuerelementen"
  - "Windows Forms-Steuerelemente, Anordnen"
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien
Die präzise Platzierung von Steuerelementen auf dem Formular hat für viele Anwendungen einen hohen Stellenwert.  Der Windows Forms\-Designer bietet Ihnen hierfür zahlreiche Layouttools.  Eines der wichtigsten Tools ist das <xref:System.Windows.Forms.Design.Behavior.SnapLine>\-Feature.  
  
 Mithilfe von Ausrichtungslinien können Sie genau erkennen, wo Steuerelemente an anderen Steuerelementen ausgerichtet werden.  Darüber hinaus zeigen sie die laut den Richtlinien für die Windows\-Benutzeroberfläche empfohlenen Abstände für Ränder zwischen Steuerelementen.  Details finden Sie unter [User Interface Design and Development](http://go.microsoft.com/FWLink/?LinkId=83878).  
  
 Ausrichtungslinien erleichtern das Ausrichten von Steuerelementen und gewährleisten so ein professionelles Aussehen und Verhalten.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen eines Windows Forms\-Projekts  
  
-   Festlegen des Abstands und der Ausrichtung von Steuerelementen mithilfe von Ausrichtungslinien  
  
-   Ausrichten an Formular\- und Containerrändern  
  
-   Ausrichten an gruppierten Steuerelementen  
  
-   Verwenden von Ausrichtungslinien zum Platzieren eines Steuerelements durch Nachzeichnen seiner Größe  
  
-   Verwenden von Ausrichtungslinien beim Ziehen eines Steuerelements aus der Toolbox  
  
-   Ändern der Größe von Steuerelementen mithilfe von Ausrichtungslinien  
  
-   Ausrichten einer Bezeichnung am Text eines Steuerelements  
  
-   Verwenden von Ausrichtungslinien durch Tastaturnavigation  
  
-   Ausrichtungslinien und Layoutbereiche  
  
-   Deaktivieren von Ausrichtungslinien  
  
 Anschließend werden Sie verstehen, welche Rolle die Ausrichtungsfeatures für das Layout spielen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Erstellen des Projekts  
 Zunächst wird das Projekt erstellt und das Formular eingerichtet.  
  
#### So erstellen Sie das Projekt  
  
1.  Erstellen Sie ein Windows\-basiertes Anwendungsprojekt mit dem Namen "SnaplineExample".  Ausführliche Informationen finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Wählen Sie im Windows Forms\-Designer das Formular aus.  
  
## Festlegen des Abstands und der Ausrichtung von Steuerelementen mithilfe von Ausrichtungslinien  
 Ausrichtungslinien bieten Ihnen eine genaue und intuitive Möglichkeit, Steuerelemente auf dem Formular auszurichten.  Sie werden angezeigt, wenn Sie ein ausgewähltes Steuerelement oder mehrere ausgewählte Steuerelemente in die Nähe einer Position verschieben, an der sie an einem oder mehreren anderen Steuerelementen ausgerichtet würden.  Die Auswahl "fängt" die vorgeschlagene Position, während Sie sie an den anderen Steuerelementen vorbei verschieben.  
  
#### So ordnen Sie Steuerelemente mithilfe von Ausrichtungslinien an  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.Button>\-Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Verschieben Sie das <xref:System.Windows.Forms.Button>\-Steuerelement in die rechte untere Ecke des Formulars.  Beachten Sie die Ausrichtungslinien, die angezeigt werden, wenn sich das <xref:System.Windows.Forms.Button>\-Steuerelement dem unteren und rechten Rand des Formulars nähert.  Diese Ausrichtungslinien zeigen den empfohlenen Abstand zwischen den Rändern des Steuerelements und denen des Formulars an.  
  
3.  Verschieben Sie das <xref:System.Windows.Forms.Button>\-Steuerelement um die Ränder des Formulars herum, und beachten Sie, wo die Ausrichtungslinien angezeigt werden.  Wenn Sie fertig sind, verschieben Sie das <xref:System.Windows.Forms.Button>\-Steuerelement in die Nähe des Formularmittelpunkts.  
  
4.  Ziehen Sie ein weiteres <xref:System.Windows.Forms.Button>\-Steuerelement aus der **Toolbox** auf das Formular.  
  
5.  Verschieben Sie das zweite <xref:System.Windows.Forms.Button>\-Steuerelement, bis es nahezu auf der gleichen Höhe wie das erste ist.  Beachten Sie die Ausrichtungslinie, die an der Textbasislinie beider Schaltflächen angezeigt wird. Beachten Sie außerdem, dass das Steuerelement, das Sie verschieben, eine Position fängt, die exakt auf der gleichen Höhe wie das andere Steuerelement liegt.  
  
6.  Verschieben Sie das zweite <xref:System.Windows.Forms.Button>\-Steuerelement, bis es direkt über dem ersten positioniert ist.  Beachten Sie die Ausrichtungslinien, die an den linken und rechten Rändern beider Schaltflächen angezeigt werden. Beachten Sie außerdem, dass das Steuerelement, das Sie verschieben, eine Position fängt, die exakt auf der gleichen Höhe wie das andere Steuerelement liegt.  
  
7.  Wählen Sie eines der <xref:System.Windows.Forms.Button>\-Steuerelemente aus, und verschieben Sie es in die Nähe des jeweils anderen, bis sie sich beinahe berühren.  Beachten Sie die Ausrichtungslinie, die zwischen ihnen angezeigt wird.  Dies ist der empfohlene Abstand zwischen den Rändern der Steuerelemente.  Beachten Sie außerdem, dass das Steuerelement, das Sie verschieben, diese Position fängt.  
  
8.  Ziehen Sie zwei <xref:System.Windows.Forms.Panel>\-Steuerelemente aus der **Toolbox** auf das Formular.  
  
9. Verschieben Sie eines der <xref:System.Windows.Forms.Panel>\-Steuerelemente, bis es nahezu auf der gleichen Höhe wie das erste ist.  Beachten Sie die Ausrichtungslinien, die an den oberen und unteren Rändern beider Steuerelemente angezeigt werden. Beachten Sie außerdem, dass das Steuerelement, das Sie verschieben, eine Position fängt, die exakt auf der gleichen Höhe wie das andere Steuerelement liegt.  
  
## Ausrichten an Formular\- und Containerrändern  
 Ausrichtungslinien unterstützen Sie dabei, Steuerelemente an Formular\- und Containerrändern konsistent auszurichten.  
  
#### So richten Sie Steuerelemente an Formular\- und Containerrändern aus  
  
1.  Wählen Sie eines der <xref:System.Windows.Forms.Button>\-Steuerelemente aus, und verschieben Sie es in die Nähe des rechten Rands des Formulars, bis eine Ausrichtungslinie angezeigt wird.  Der Abstand der Ausrichtungslinie vom rechten Rand entspricht der Summe der Werte für die <xref:System.Windows.Forms.Control.Margin%2A>\-Eigenschaft des Steuerelements und die <xref:System.Windows.Forms.Control.Padding%2A>\-Eigenschaft des Formulars.  
  
> [!NOTE]
>  Wenn die <xref:System.Windows.Forms.Control.Padding%2A>\-Eigenschaft des Formulars auf 0,0,0,0 festgelegt ist, weist der Windows Forms\-Designer dem Formular den gespiegelten <xref:System.Windows.Forms.Control.Padding%2A>\-Wert 9,9,9,9 zu.  Zum Überschreiben dieses Verhaltens weisen Sie der Eigenschaft einen anderen Wert als 0,0,0,0 zu.  
  
1.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Margin%2A>\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements, indem Sie den <xref:System.Windows.Forms.Control.Margin%2A>\-Eintrag im **Eigenschaftenfenster** erweitern und die <xref:System.Windows.Forms.Padding.All%2A>\-Eigenschaft auf 0 festlegen.  Ausführliche Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Windows Forms\-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize\-Eigenschaft](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md).  
  
2.  Verschieben Sie das <xref:System.Windows.Forms.Button>\-Steuerelement in die Nähe des rechten Rands des Formulars, bis eine Ausrichtungslinie angezeigt wird.  Dieser Abstand wird nun durch den Wert der <xref:System.Windows.Forms.Control.Padding%2A>\-Eigenschaft des Formulars bestimmt.  
  
3.  Ziehen Sie ein <xref:System.Windows.Forms.GroupBox>\-Steuerelement aus der **Toolbox** auf das Formular.  
  
4.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Padding%2A>\-Eigenschaft des <xref:System.Windows.Forms.GroupBox>\-Steuerelements, indem Sie den <xref:System.Windows.Forms.Control.Padding%2A>\-Eintrag im **Eigenschaftenfenster** erweitern und die <xref:System.Windows.Forms.Padding.All%2A>\-Eigenschaft auf 10 festlegen.  
  
5.  Ziehen Sie ein <xref:System.Windows.Forms.Button>\-Steuerelement aus der **Toolbox** in das <xref:System.Windows.Forms.GroupBox>\-Steuerelement.  
  
6.  Verschieben Sie das <xref:System.Windows.Forms.Button>\-Steuerelement in die Nähe des rechten Rands des <xref:System.Windows.Forms.GroupBox>\-Steuerelements, bis eine Ausrichtungslinie angezeigt wird.  Verschieben Sie das <xref:System.Windows.Forms.Button>\-Steuerelement innerhalb des <xref:System.Windows.Forms.GroupBox>\-Steuerelements, und beachten Sie, wo die Ausrichtungslinien angezeigt werden.  
  
## Ausrichten an gruppierten Steuerelementen  
 Mit Ausrichtungslinien können Sie gruppierte Steuerelemente sowie Steuerelemente innerhalb eines <xref:System.Windows.Forms.GroupBox>\-Steuerelements ausrichten.  
  
#### So richten Sie an gruppierten Steuerelementen aus  
  
1.  Wählen Sie zwei der Steuerelemente auf dem Formular aus.  Verschieben Sie die Auswahl, und beachten Sie die Ausrichtungslinien, die zwischen der Auswahl und den anderen Steuerelementen angezeigt werden.  
  
2.  Ziehen Sie ein <xref:System.Windows.Forms.GroupBox>\-Steuerelement aus der **Toolbox** auf das Formular.  
  
3.  Ziehen Sie ein <xref:System.Windows.Forms.Button>\-Steuerelement aus der **Toolbox** in das <xref:System.Windows.Forms.GroupBox>\-Steuerelement.  
  
4.  Wählen Sie eines der <xref:System.Windows.Forms.Button>\-Steuerelemente aus, und verschieben Sie es um das <xref:System.Windows.Forms.GroupBox>\-Steuerelement.  Beachten Sie die Ausrichtungslinien, die an den Rändern des <xref:System.Windows.Forms.GroupBox>\-Steuerelements angezeigt werden.  Beachten Sie außerdem die Ausrichtungslinien, die an den Rändern des <xref:System.Windows.Forms.Button>\-Steuerelements angezeigt werden, das im <xref:System.Windows.Forms.GroupBox>\-Steuerelement enthalten ist.  Steuerelemente, die untergeordnete Elemente eines Containersteuerelements sind, unterstützen ebenfalls Ausrichtungslinien.  
  
## Verwenden von Ausrichtungslinien zum Platzieren eines Steuerelements durch Nachzeichnen seiner Größe  
 Ausrichtungslinien unterstützen Sie dabei, Steuerelemente auszurichten, wenn Sie sie erstmals auf einem Formular platzieren.  
  
#### So verwenden Sie Ausrichtungslinien zum Platzieren eines Steuerelements durch Nachzeichnen seiner Größe  
  
1.  Klicken Sie in der **Toolbox** auf das Symbol für das <xref:System.Windows.Forms.Button>\-Steuerelement.  Ziehen Sie es nicht auf das Formular.  
  
2.  Verschieben Sie den Mauszeiger über die Entwurfsoberfläche des Formulars.  Beachten Sie, dass sich der Zeiger zu einem Fadenkreuz mit angefügtem Symbol des <xref:System.Windows.Forms.Button>\-Steuerelements ändert.  Beachten Sie außerdem die Ausrichtungslinien, die angezeigt werden, um ausgerichtete Positionen für das <xref:System.Windows.Forms.Button>\-Steuerelement vorzuschlagen.  
  
3.  Halten Sie die Maustaste gedrückt.  
  
4.  Ziehen Sie den Mauszeiger um das Formular.  Beachten Sie, dass eine Kontur gezeichnet wird, die die Position und die Größe des Steuerelements angibt.  
  
5.  Ziehen Sie den Mauszeiger, bis es an einem anderen Steuerelement auf dem Formular ausgerichtet wird.  Beachten Sie, dass eine Ausrichtungslinie angezeigt wird.  
  
6.  Lassen Sie die Maustaste los.  Das Steuerelement wird an der Position und mit der Größe erstellt, die durch die Kontur vorgegeben werden.  
  
## Verwenden von Ausrichtungslinien beim Ziehen eines Steuerelements aus der Toolbox  
 Ausrichtungslinien unterstützen Sie dabei, Steuerelemente auszurichten, wenn Sie sie aus der **Toolbox** auf das Formular ziehen.  
  
#### So verwenden Sie Ausrichtungslinien beim Ziehen eines Steuerelements aus der Toolbox  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.Button>\-Steuerelement aus der **Toolbox** auf das Formular, ohne anschließend die Maustaste loszulassen.  
  
2.  Verschieben Sie den Mauszeiger über die Entwurfsoberfläche des Formulars.  Beachten Sie, dass der Mauszeiger die Position angibt, an der das neue <xref:System.Windows.Forms.Button>\-Steuerelement erstellt wird.  
  
3.  Ziehen Sie den Mauszeiger um das Formular.  Beachten Sie die Ausrichtungslinien, die angezeigt werden, um ausgerichtete Positionen für das <xref:System.Windows.Forms.Button>\-Steuerelement vorzuschlagen.  Suchen Sie eine Position, die an anderen Steuerelementen ausgerichtet ist.  
  
4.  Lassen Sie die Maustaste los.  Das Steuerelement wird an der von den Ausrichtungslinien angegebenen Position erstellt.  
  
## Ändern der Größe von Steuerelementen mithilfe von Ausrichtungslinien  
 Ausrichtungslinien unterstützen Sie dabei, Steuerelemente auszurichten, während Sie ihre Größe ändern.  
  
#### So ändern Sie die Größe eines Steuerelements mithilfe von Ausrichtungslinien  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.Button>\-Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Ändern Sie die Größe des <xref:System.Windows.Forms.Button>\-Steuerelements, indem Sie auf einen der Eckziehpunkte klicken und bei gedrückter Maustaste ziehen.  Ausführliche Informationen finden Sie unter [Gewusst wie: Ändern der Größe von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md).  
  
3.  Ziehen Sie den Ziehpunkt, bis einer der Ränder des <xref:System.Windows.Forms.Button>\-Steuerelements an einem anderen Steuerelement ausgerichtet ist.  Beachten Sie, dass eine Ausrichtungslinie angezeigt wird.  Beachten Sie außerdem, dass der Ziehpunkt die von der Ausrichtungslinie angegebene Position fängt.  
  
4.  Ändern Sie die Größe des <xref:System.Windows.Forms.Button>\-Steuerelements in verschiedene Richtungen, und richten Sie den Ziehpunkt an verschiedenen Steuerelementen aus.  Beachten Sie, wie die Ausrichtungslinien in verschiedenen Ausrichtungen angezeigt werden.  
  
## Ausrichten einer Bezeichnung am Text eines Steuerelements  
 Einige Steuerelemente verfügen über eine Ausrichtungslinie, um andere Steuerelemente am angezeigten Text auszurichten.  
  
#### So richten Sie eine Bezeichnung am Text eines Steuerelements aus  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.TextBox>\-Steuerelement aus der **Toolbox** auf das Formular.  Wenn Sie das <xref:System.Windows.Forms.TextBox>\-Steuerelement auf dem Formular einfügen, klicken Sie auf das Smarttagsymbol, und wählen Sie die Option **Text auf textBox1 festlegen**.  Ausführliche Informationen finden Sie unter [Exemplarische Vorgehensweise: Ausführen von häufigen Aufgaben mit Smarttags auf Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md).  
  
2.  Ziehen Sie ein <xref:System.Windows.Forms.Label>\-Steuerelement aus der **Toolbox** auf das Formular.  
  
3.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft des <xref:System.Windows.Forms.Label>\-Steuerelements in `true`.  Beachten Sie, dass die Ränder des Steuerelements so angepasst werden, dass der Text darin angezeigt wird.  
  
4.  Verschieben Sie das <xref:System.Windows.Forms.Label>\-Steuerelement links neben das <xref:System.Windows.Forms.TextBox>\-Steuerelement, sodass es am unteren Rand des <xref:System.Windows.Forms.TextBox>\-Steuerelements ausgerichtet ist.  Beachten Sie die Ausrichtungslinie, die an den unteren Rändern der beiden Steuerelemente angezeigt wird.  
  
5.  Verschieben Sie das <xref:System.Windows.Forms.Label>\-Steuerelement etwas nach oben, bis der <xref:System.Windows.Forms.Label>\-Text und der <xref:System.Windows.Forms.TextBox>\-Text ausgerichtet sind.  Beachten Sie die anders dargestellte Ausrichtungslinie, die angibt, wann die Textfelder beider Steuerelemente ausgerichtet sind.  
  
## Verwenden von Ausrichtungslinien durch Tastaturnavigation  
 Ausrichtungslinien unterstützen Sie dabei, Steuerelemente auszurichten, wenn Sie sie mit den Pfeiltasten der Tastatur anordnen.  
  
#### So verwenden Sie Ausrichtungslinien durch Tastaturnavigation  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.Button>\-Steuerelement aus der **Toolbox** auf das Formular.  Platzieren Sie es in der oberen linken Ecke des Formulars.  
  
2.  Drücken Sie STRG\+NACH\-UNTEN\-PFEIL.  Beachten Sie, dass das Steuerelement im Formular nach unten an die erste verfügbare horizontale Ausrichtungsposition verschoben wird.  
  
3.  Drücken Sie STRG\+NACH\-UNTEN\-PFEIL, bis das Steuerelement das Ende des Formulars erreicht.  Beachten Sie die Positionen, die es einnimmt, wenn es auf dem Formular nach unten verschoben wird.  
  
4.  Drücken Sie STRG\+NACH\-RECHTS\-PFEIL.  Beachten Sie, dass das Steuerelement im Formular nach rechts an die erste verfügbare vertikale Ausrichtungsposition verschoben wird.  
  
5.  Drücken Sie STRG\+NACH\-RECHTS\-PFEIL, bis das Steuerelement den rechten Rand des Formulars erreicht.  Beachten Sie die Positionen, die es einnimmt, wenn es auf dem Formular nach rechts verschoben wird.  
  
6.  Verschieben Sie das Steuerelement mit verschiedenen Pfeiltasten auf dem Formular.  Beachten Sie die Positionen, die das Steuerelement einnimmt, sowie die dabei angezeigten Ausrichtungslinien.  
  
7.  Drücken Sie UMSCHALT\+beliebige Pfeiltaste, um die Größe des <xref:System.Windows.Forms.Button>\-Steuerelements in Schritten von einem Pixel zu ändern.  
  
8.  Drücken Sie STRG\+UMSCHALT\+beliebige Pfeiltaste, um die Größe des <xref:System.Windows.Forms.Button>\-Steuerelements in Ausrichtungslinienschritten zu ändern.  
  
## Ausrichtungslinien und Layoutbereiche  
 Ausrichtungslinien sind innerhalb der Layoutbereiche deaktiviert.  
  
#### So deaktivieren Sie Ausrichtungslinien gezielt  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Doppelklicken Sie auf das <xref:System.Windows.Forms.Button>\-Steuerelementsymbol in der **Toolbox**.  Beachten Sie, dass ein neues Schaltflächensteuerelement in der ersten Zelle des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements angezeigt wird.  
  
3.  Doppelklicken Sie noch zweimal auf das <xref:System.Windows.Forms.Button>\-Steuerelementsymbol in der **Toolbox**.  Dadurch verbleibt eine leere Zelle im <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement.  
  
4.  Ziehen Sie ein <xref:System.Windows.Forms.Button>\-Steuerelement aus der **Toolbox** in die leere Zelle des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements.  Beachten Sie, dass keine Ausrichtungslinien angezeigt werden.  
  
5.  Ziehen Sie das <xref:System.Windows.Forms.Button>\-Steuerelement aus dem <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement, und verschieben Sie es um das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement.  Beachten Sie, dass wieder Ausrichtungslinien angezeigt werden.  
  
## Deaktivieren von Ausrichtungslinien  
 Ausrichtungslinien sind standardmäßig aktiviert.  Sie können Ausrichtungslinien gezielt oder in der Entwurfsumgebung deaktivieren.  
  
#### So deaktivieren Sie Ausrichtungslinien gezielt  
  
-   Drücken Sie die ALT\-TASTE, während Sie ein Steuerelement auf dem Formular verschieben.  
  
     Beachten Sie, dass keine Ausrichtungslinien angezeigt werden und das Steuerelement keine potenziellen Ausrichtungspositionen fängt.  
  
#### So deaktivieren Sie Ausrichtungslinien in der Entwurfsumgebung  
  
1.  Öffnen Sie im Menü **Extras** das Dialogfeld **Optionen**.  Öffnen Sie das Dialogfeld Windows Forms\-Designer.  Ausführliche Informationen finden Sie unter [General, Windows Forms Designer, Options Dialog Box](http://msdn.microsoft.com/de-de/8dd170af-72f0-4212-b04b-034ceee92834).  
  
2.  Wählen Sie den Knoten **Allgemein** aus.  Ändern Sie im Abschnitt **Layoutmodus** die Auswahl von **SnapLines** in **SnapToGrid**.  
  
3.  Klicken Sie auf OK, um die Einstellung zu übernehmen.  
  
4.  Wählen Sie ein Steuerelement auf dem Formular aus, und verschieben Sie es um die anderen Steuerelemente.  Beachten Sie, dass keine Ausrichtungslinien angezeigt werden.  
  
## Nächste Schritte  
 Ausrichtungslinien bieten eine intuitive Möglichkeit, Steuerelemente auf dem Formular auszurichten.  Hier einige Vorschläge:  
  
-   Versuchen Sie, ein <xref:System.Windows.Forms.GroupBox>\-Steuerelement in einem anderen <xref:System.Windows.Forms.GroupBox>\-Steuerelement zu verschachteln.  Platzieren Sie ein <xref:System.Windows.Forms.Button>\-Steuerelement im untergeordneten <xref:System.Windows.Forms.GroupBox>\-Steuerelement und ein weiteres im übergeordneten <xref:System.Windows.Forms.GroupBox>\-Steuerelement.  Verschieben Sie die <xref:System.Windows.Forms.Button>\-Steuerelemente, um zu sehen, wie die Ausrichtungslinien Containergrenzen schneiden.  
  
-   Erstellen Sie eine Spalte mit <xref:System.Windows.Forms.TextBox>\-Steuerelementen und eine entsprechende Spalte mit <xref:System.Windows.Forms.Label>\-Steuerelementen.  Legen Sie den Wert der <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft des <xref:System.Windows.Forms.Label>\-Steuerelements auf `true` fest.  Verschieben Sie <xref:System.Windows.Forms.Label>\-Steuerelemente mithilfe von Ausrichtungslinien, sodass der darin enthaltene Text an dem Text in den <xref:System.Windows.Forms.TextBox>\-Steuerelementen ausgerichtet wird.  
  
 Informationen zum Windows\-Benutzeroberflächenentwurf finden Sie im Buch *Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers*, Microsoft Press, Redmond, WA, 1999.  \(USBN: 0\-7356\-0566\-1\).  
  
## Siehe auch  
 <xref:System.Windows.Forms.Design.Behavior.SnapLine>   
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)   
 [Exemplarische Vorgehensweise: Anordnen von Windows Forms\-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize\-Eigenschaft](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)   
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)