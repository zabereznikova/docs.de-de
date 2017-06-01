---
title: "Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel | Microsoft Docs"
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
  - "Steuerelemente [Windows Forms], Anordnen mit TableLayoutPanel"
  - "TableLayoutPanel-Steuerelement [Windows Forms], Exemplarische Vorgehensweisen"
  - "Windows Forms-Steuerelemente, Anordnen"
ms.assetid: d474885e-12cc-4ab7-b997-2a23a643049b
caps.latest.revision: 28
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 28
---
# Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel
Einige Anwendungen setzen ein Layout voraus, das bei Änderungen der Größe des Formulars oder des Inhalts automatisch angepasst wird.  Wenn Sie ein dynamisches Layout benötigen und keine <xref:System.Windows.Forms.Control.Layout>\-Ereignisse explizit im Code behandeln möchten, sollten Sie einen Layoutbereich verwenden.  
  
 Das <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelement und das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement bieten intuitive Möglichkeiten zum Anordnen von Steuerelementen auf dem Formular.  Mit beiden lassen sich die relativen Positionen untergeordneter Steuerelemente, die in ihnen enthalten sind, automatisch und konfigurierbar steuern. Außerdem bieten diese beiden Steuerelemente dynamische Layoutfeatures zur Laufzeit, mit denen die Größe und Position untergeordneter Steuerelemente an die Maße des übergeordneten Formulars angepasst werden können.  Layoutbereiche können in anderen Layoutbereichen verschachtelt sein, um anspruchsvolle Benutzeroberflächen zu ermöglichen.  
  
 Der Inhalt des <xref:System.Windows.Forms.FlowLayoutPanel> wird in einer bestimmten Flussrichtung angeordnet: horizontal oder vertikal.  Dieser Inhalt kann von einer Zeile zur nächsten oder von einer Spalte zur nächsten umbrochen werden.  Statt umbrochen zu werden, kann der Inhalt aber auch abgeschnitten werden.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).  
  
 Der Inhalt des <xref:System.Windows.Forms.TableLayoutPanel> ist in einem Raster angeordnet, dessen Funktionalität mit dem HTML\-Element \<table\> vergleichbar ist.  Das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement ermöglicht es Ihnen, Steuerelemente in einem Rasterlayout zu platzieren, ohne dass Sie die genaue Position der einzelnen Steuerelemente angeben müssen.  Die Zellen sind in Zeilen und Spalten angeordnet, die unterschiedliche Größen aufweisen können.  Zellen können zwischen Zeilen und Spalten zusammengeführt werden.  Sie können denselben Inhalt wie ein Formular enthalten und verhalten sich in den meisten anderen Beziehungen wie Container.  
  
 Das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement bietet zudem die Möglichkeit der proportionalen Größenanpassung zur Laufzeit, d. h., das Layout kann an die Größe des Formulars angepasst werden.  Dadurch eignet sich das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement speziell für Dateneingabeformulare und lokalisierte Anwendungen.  Weitere Informationen finden Sie unter [Walkthrough: Creating a Resizable Windows Form for Data Entry](http://msdn.microsoft.com/de-de/e193b4fc-912a-4917-b036-b76c7a6f58ab) und unter [Walkthrough: Creating a Localizable Windows Form](http://msdn.microsoft.com/de-de/c5240b6e-aaca-4286-9bae-778a416edb9c).  
  
 Im Allgemeinen sollten Sie kein <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement als Container für das gesamte Layout verwenden.  Verwenden Sie <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelemente, um für Teile des Layouts die proportionale Größenanpassung zu ermöglichen.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen eines Windows Forms\-Projekts  
  
-   Anordnen von Steuerelementen in Zeilen und Spalten  
  
-   Festlegen von Zeilen\- und Spalteneigenschaften  
  
-   Überspannen von Zeilen und Spalten mit einem Steuerelement  
  
-   Automatische Behandlung von Überläufen  
  
-   Einfügen von Steuerelementen durch Doppelklicken in der Toolbox  
  
-   Einfügen eines Steuerelements durch Zeichnen seiner Kontur  
  
-   Neuzuweisen von vorhandenen Steuerelementen zu einem anderen übergeordneten Steuerelement  
  
 Anschließend werden Sie verstehen, welche Rolle diese wichtigen Layoutfeatures spielen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Erstellen des Projekts  
 Zunächst wird das Projekt erstellt und das Formular eingerichtet.  
  
#### So erstellen Sie das Projekt  
  
1.  Erstellen Sie ein Windows\-Anwendungsprojekt mit dem Namen "TableLayoutPanelExample".  Weitere Informationen finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Wählen Sie im **Windows** **Forms\-Designer** das Formular aus.  
  
## Anordnen von Steuerelementen in Zeilen und Spalten  
 Das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement ermöglicht es Ihnen, Steuerelemente mühelos in Zeilen und Spalten anzuordnen.  
  
#### So ordnen Sie Steuerelemente mit TableLayoutPanel in Zeilen und Spalten an  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement aus der **Toolbox** auf das Formular.  Beachten Sie, dass das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement standardmäßig über vier Zellen verfügt.  
  
2.  Ziehen Sie ein <xref:System.Windows.Forms.Button>\-Steuerelement aus der **Toolbox** in das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement, und fügen Sie es in eine der Zellen ein.  Beachten Sie, dass das <xref:System.Windows.Forms.Button>\-Steuerelement innerhalb der Zelle erstellt wird, die Sie ausgewählt haben.  
  
3.  Ziehen Sie drei weitere <xref:System.Windows.Forms.Button>\-Steuerelemente aus der **Toolbox** in das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement, sodass jede Zelle über eine Schaltfläche verfügt.  
  
4.  Klicken Sie auf den vertikalen Ziehpunkt zwischen den beiden Spalten, und verschieben Sie ihn bei gedrückter Maustaste nach links.  Beachten Sie, dass die <xref:System.Windows.Forms.Button>\-Steuerelemente in der ersten Spalte schmaler werden, während die Größe der <xref:System.Windows.Forms.Button>\-Steuerelemente in der zweiten Spalte unverändert bleibt.  
  
5.  Klicken Sie auf den vertikalen Ziehpunkt zwischen den beiden Spalten, und verschieben Sie ihn bei gedrückter Maustaste nach rechts.  Beachten Sie, dass die <xref:System.Windows.Forms.Button>\-Steuerelemente in der ersten Spalte auf ihre ursprüngliche Größe zurückgesetzt werden, während die <xref:System.Windows.Forms.Button>\-Steuerelemente in der zweiten Spalte nach rechts verschoben werden.  
  
6.  Bewegen Sie den horizontalen Ziehpunkt nach oben und unten, um die Auswirkung auf die Steuerelemente im Bereich zu beobachten.  
  
## Positionieren von Steuerelementen in Zellen durch Andocken und Verankern  
 Das Ankerverhalten von untergeordneten Steuerelementen in einem <xref:System.Windows.Forms.TableLayoutPanel> unterscheidet sich vom Verhalten in anderen Containersteuerelementen.  Das Andockverhalten von untergeordneten Steuerelementen ist mit dem anderer Containersteuerelemente identisch.  
  
#### Positionieren von Steuerelementen in Zellen  
  
1.  Wählen Sie das erste <xref:System.Windows.Forms.Button>\-Steuerelement aus.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft in <xref:System.Windows.Forms.DockStyle>.  Beachten Sie, dass das <xref:System.Windows.Forms.Button>\-Steuerelement auf die Größe seiner Zelle erweitert wird.  
  
2.  Wählen Sie eines der anderen <xref:System.Windows.Forms.Button>\-Steuerelemente aus.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaft in <xref:System.Windows.Forms.AnchorStyles>.  Beachten Sie, dass es verschoben wird, sodass sich der rechte Rand in der Nähe des rechten Rands der Zelle befindet.  Der Abstand zwischen den Rändern entspricht der Summe der <xref:System.Windows.Forms.Control.Margin%2A>\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements und der <xref:System.Windows.Forms.Control.Padding%2A>\-Eigenschaft des Bereichs.  
  
3.  Ändern Sie den Wert der <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements in <xref:System.Windows.Forms.AnchorStyles> und <xref:System.Windows.Forms.AnchorStyles>.  Beachten Sie, dass das Steuerelement anhand der Werte für <xref:System.Windows.Forms.Control.Margin%2A> und <xref:System.Windows.Forms.Control.Padding%2A> an die Breite der Zelle angepasst wird.  
  
4.  Wiederholen Sie die Schritte 2 und 3 mit dem <xref:System.Windows.Forms.AnchorStyles>\-Stil und dem <xref:System.Windows.Forms.AnchorStyles>\-Stil.  
  
## Festlegen von Zeilen\- und Spalteneigenschaften  
 Sie können individuelle Eigenschaften von Zeilen und Spalten festlegen, indem Sie die <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A>\-Auflistung und die <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A>\-Auflistung verwenden.  
  
#### So legen Sie Zeilen\- und Spalteneigenschaften fest  
  
1.  Wählen Sie das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement im **Windows Forms\-Designer** aus.  
  
2.  Öffnen Sie im **Eigenschaftenfenster** die <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A>\-Auflistung, indem Sie auf die Schaltfläche mit den Auslassungszeichen \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) neben dem Eintrag **Spalten** klicken.  
  
3.  Wählen Sie die erste Spalte aus, und ändern Sie den Wert der <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A>\-Eigenschaft in <xref:System.Windows.Forms.SizeType>.  Klicken Sie auf **OK**, um die Änderung zu übernehmen.  Beachten Sie, dass die Breite der ersten Spalte an das <xref:System.Windows.Forms.Button>\-Steuerelement angepasst wird.  Beachten Sie außerdem, dass die Breite der Spalte nicht veränderbar ist.  
  
4.  Öffnen Sie im **Eigenschaftenfenster** die <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A>\-Auflistung, und wählen Sie die erste Spalte aus.  Ändern Sie den Wert der <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A>\-Eigenschaft in <xref:System.Windows.Forms.SizeType>.  Klicken Sie auf **OK**, um die Änderung zu übernehmen.  Vergrößern Sie die Breite des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements, und beachten Sie, dass die erste Spalte breiter wird.  Reduzieren Sie die Breite des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements, und beachten Sie, dass die Schaltflächen in der ersten Spalte an die Größe der Zelle angepasst werden.  Beachten Sie außerdem, dass die Breite der Spalte veränderbar ist.  
  
5.  Öffnen Sie im **Eigenschaftenfenster** die <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A>\-Auflistung, und wählen Sie alle aufgelisteten Spalten aus.  Legen Sie den Wert aller <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A>\-Eigenschaften auf <xref:System.Windows.Forms.SizeType> fest.  Klicken Sie auf **OK**, um die Änderung zu übernehmen.  Wiederholen Sie dies mit der <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A>\-Auflistung.  
  
6.  Klicken Sie auf einen der Eckziehpunkte, und ändern Sie bei gedrückter Maustaste sowohl die Breite als auch die Höhe des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements.  Beachten Sie, dass die Größe der Zeilen und Spalten mit der Größe des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements geändert wird.  Beachten Sie außerdem, dass die Größe der Zeilen und Spalten mit den horizontalen und vertikalen Ziehpunkten geändert werden kann.  
  
## Überspannen von Zeilen und Spalten mit einem Steuerelement  
 Das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement fügt Steuerelementen zur Entwurfszeit mehrere neue Eigenschaften hinzu.  Zwei dieser Eigenschaften sind `RowSpan` und `ColumnSpan`.  Sie können diese Eigenschaften verwenden, damit ein Steuerelement mehrere Zeilen und Spalten überspannt.  
  
#### So überspannen Sie Zeilen und Spalten mit einem Steuerelement  
  
1.  Wählen Sie das <xref:System.Windows.Forms.Button>\-Steuerelement in der ersten Zeile und Spalte aus.  
  
2.  Ändern Sie im **Eigenschaftenfenster** den Wert der `ColumnSpan`\-Eigenschaft in 2.  Beachten Sie, dass das <xref:System.Windows.Forms.Button>\-Steuerelement die erste Spalte und die zweite Spalte ausfüllt.  Beachten Sie außerdem, dass für diese Änderung eine zusätzliche Zeile hinzugefügt wurde.  
  
3.  Wiederholen Sie Schritt 2 für die `RowSpan`\-Eigenschaft.  
  
## Einfügen von Steuerelementen durch Doppelklicken in der Toolbox  
 Sie können das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement füllen, indem Sie in der **Toolbox** auf Steuerelemente doppelklicken.  
  
#### So fügen Sie Steuerelemente durch Doppelklicken in der Toolbox ein  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Doppelklicken Sie auf das <xref:System.Windows.Forms.Button>\-Steuerelementsymbol in der **Toolbox**.  Beachten Sie, dass ein neues Schaltflächensteuerelement in der ersten Zelle des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements angezeigt wird.  
  
3.  Doppelklicken Sie auf weitere Steuerelemente in der **Toolbox**.  Beachten Sie, dass die neuen Steuerelemente nacheinander in den freien Zellen des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements angezeigt werden.  Beachten Sie außerdem, dass das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement für die neuen Steuerelemente erweitert wird, wenn keine freien Zellen verfügbar sind.  
  
## Automatische Behandlung von Überläufen  
 Wenn Sie Steuerelemente in das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement einfügen, fehlen Ihnen möglicherweise leere Zellen für neue Steuerelemente.  Das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement behandelt diese Situation automatisch, indem es die Anzahl der Zellen erhöht.  
  
#### So erkennen Sie die automatische Behandlung von Überläufen  
  
1.  Wenn das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement noch leere Zellen enthält, fügen Sie weiterhin neue <xref:System.Windows.Forms.Button>\-Steuerelemente hinzu, bis das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement voll ist.  
  
2.  Wenn das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement voll ist, doppelklicken Sie auf das <xref:System.Windows.Forms.Button>\-Symbol in der **Toolbox**, um ein weiteres <xref:System.Windows.Forms.Button>\-Steuerelement einzufügen.  Beachten Sie, dass das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement neue Zellen für das neue Steuerelement erstellt.  Fügen Sie weitere Steuerelemente ein, und beachten Sie das Größenanpassungsverhalten.  
  
3.  Ändern Sie den Wert der <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A>\-Eigenschaft des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements in <xref:System.Windows.Forms.TableLayoutPanelGrowStyle>.  Doppelklicken Sie auf das <xref:System.Windows.Forms.Button>\-Symbol in der **Toolbox**, um <xref:System.Windows.Forms.Button>\-Steuerelemente einzufügen, bis das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement voll ist.  Doppelklicken Sie erneut auf das <xref:System.Windows.Forms.Button>\-Symbol in der **Toolbox**.  Beachten Sie, dass Sie eine Fehlermeldung vom **Windows Forms\-Designer** darüber erhalten, dass keine weiteren Zeilen und Spalten erstellt werden können.  
  
## Einfügen eines Steuerelements durch Zeichnen seiner Kontur  
 Sie können ein Steuerelement in ein <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement einfügen und seine Größe festlegen, indem Sie in einer Zelle seine Kontur zeichnen.  
  
#### So fügen Sie ein Steuerelement durch Zeichnen seiner Kontur ein  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Klicken Sie in der **Toolbox** auf das Symbol für das <xref:System.Windows.Forms.Button>\-Steuerelement.  Ziehen Sie es nicht auf das Formular.  
  
3.  Bewegen Sie den Mauszeiger über das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement.  Beachten Sie, dass sich der Zeiger zu einem Fadenkreuz mit angefügtem Symbol des <xref:System.Windows.Forms.Button>\-Steuerelements ändert.  
  
4.  Halten Sie die Maustaste gedrückt.  
  
5.  Ziehen Sie den Mauszeiger, um die Kontur des <xref:System.Windows.Forms.Button>\-Steuerelements zu zeichnen.  Wenn die gewünschte Größe erreicht ist, lassen Sie die Maustaste los.  Beachten Sie, dass das <xref:System.Windows.Forms.Button>\-Steuerelement in der Zelle erstellt wird, in der Sie die Kontur des Steuerelements gezeichnet haben.  
  
## Mehrere Steuerelemente in Zellen sind nicht erlaubt  
 Das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement kann nur ein untergeordnetes Steuerelement pro Zelle enthalten.  
  
#### So veranschaulichen Sie, dass mehrere Steuerelemente in Zellen nicht erlaubt sind  
  
-   Ziehen Sie ein <xref:System.Windows.Forms.Button>\-Steuerelement aus der **Toolbox** in das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement, und fügen Sie es in eine bereits gefüllte Zelle ein.  Beachten Sie, dass das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement Sie daran hindert, das <xref:System.Windows.Forms.Button>\-Steuerelement in die gefüllte Zelle einzufügen.  
  
## Austauschen von Steuerelementen  
 Das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement ermöglicht Ihnen, Steuerelemente in zwei verschiedenen Zellen auszutauschen.  
  
#### So tauschen Sie Steuerelemente aus  
  
-   Ziehen Sie eines der <xref:System.Windows.Forms.Button>\-Steuerelemente aus einer gefüllten Zelle auf eine andere gefüllte Zelle.  Beachten Sie, dass die beiden Steuerelemente von einer Zelle in die andere verschoben werden.  
  
## Nächste Schritte  
 Mit einer Kombination aus Layoutbereichen und Steuerelementen können Sie ein komplexes Layout erzielen.  Hier einige Vorschläge:  
  
-   Versuchen Sie, eines der <xref:System.Windows.Forms.Button>\-Steuerelemente zu vergrößern, und beachten Sie die Auswirkung auf das Layout.  
  
-   Fügen Sie eine Auswahl mehrerer Steuerelemente in das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement ein, und beachten Sie, wie die Steuerelemente eingefügt werden.  
  
-   Layoutbereiche können andere Layoutbereiche enthalten.  Fügen Sie probeweise ein <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement in das vorhandene Steuerelement ein.  
  
-   Docken Sie das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement am übergeordneten Formular an.  Passen Sie die Größe des Formulars an, und beachten Sie die Auswirkung auf das Layout.  
  
## Siehe auch  
 <xref:System.Windows.Forms.FlowLayoutPanel>   
 <xref:System.Windows.Forms.TableLayoutPanel>   
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)   
 [Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers. Redmond, WA: Microsoft Press, 1999. \(USBN: 0\-7356\-0566\-1\)](http://www.microsoft.com/mspress/southpacific/books/book11588.htm)   
 [Walkthrough: Creating a Resizable Windows Form for Data Entry](http://msdn.microsoft.com/de-de/e193b4fc-912a-4917-b036-b76c7a6f58ab)   
 [Walkthrough: Creating a Localizable Windows Form](http://msdn.microsoft.com/de-de/c5240b6e-aaca-4286-9bae-778a416edb9c)   
 [Empfohlene Vorgehensweisen für das TableLayoutPanel\-Steuerelement](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)   
 [Übersicht über die AutoSize\-Eigenschaft](../../../../docs/framework/winforms/controls/autosize-property-overview.md)   
 [Gewusst wie: Andocken von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)   
 [Gewusst wie: Verankern von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)   
 [Exemplarische Vorgehensweise: Anordnen von Windows Forms\-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize\-Eigenschaft](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)