---
title: 'Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with TableLayoutPanel
- TableLayoutPanel control [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d474885e-12cc-4ab7-b997-2a23a643049b
ms.openlocfilehash: 769a8a5b60c6b963619b79526a7d1ee59af3ba33
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43773971"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel"></a>Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel
Einige Anwendungen erfordern ein Formular mit einem Layout, das sich selbst entsprechend neu anordnet, wenn sich die Größe des Formulars oder des Inhalts ändert. Wenn Sie ein dynamisches Layout benötigen und <xref:System.Windows.Forms.Control.Layout> -Ereignisse nicht explizit im Code verarbeiten möchten, ziehen Sie die Verwendung eines Layoutbereichs in Erwägung.  
  
 Das <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement und das <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement stellen intuitive Verfahren zum Anordnen von Steuerelementen auf Formularen dar. Beide bieten die Möglichkeit, die relativen Positionen der in ihnen enthaltenen untergeordneten Steuerelemente automatisch und konfigurierbar zu steuern, und beide stellen dynamische Layoutfunktionen zur Laufzeit zur Verfügung, sodass sie Größe und Position von untergeordneten Steuerelementen ändern können, wenn sich die Abmessungen des übergeordneten Formulars ändern. Layoutbereiche können in Layoutbereichen geschachtelt werden, um die Realisierung raffinierter Benutzeroberflächen zu ermöglichen.  
  
 Das <xref:System.Windows.Forms.FlowLayoutPanel> ordnet seinen Inhalt in einer bestimmten Flussrichtung an: horizontal oder vertikal. Dieser Inhalt kann von einer Zeile zur nächsten oder von einer Spalte zur nächsten umbrochen werden. Alternativ kann dieser Inhalt abgeschnitten werden, statt dass er umbrochen wird. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).  
  
 Die <xref:System.Windows.Forms.TableLayoutPanel> ordnet seinen Inhalt in einem Raster, und bietet eine auf die HTML-ähnliche Funktionalität \<Tabelle > Element. Die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement ermöglicht es Ihnen, Steuerelemente in einem Rasterlayout platziert werden, ohne dass Sie die genaue Position der einzelnen Steuerelemente angeben. Seine Zellen sind in Zeilen und Spalten angeordnet, und diese können verschiedene Größen haben. Zellen können in Zeilen und Spalten zusammengeführt werden. Zellen können alles enthalten, einem Formular enthalten und Verhalten sich in den meisten anderen Punkten, die als Container kann.  
  
 Die <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement bietet auch eine proportionale Größenänderung-Funktion zur Laufzeit, damit das Layout problemlos ändern kann, wie Ihre Formulars geändert wird. Dadurch wird die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement eignet sich gut für Zwecke, z. B. Dateneingabeformularen und lokalisierter Anwendungen. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: erstellen ein Formular, das in Windows für die Dateneingabe](https://msdn.microsoft.com/library/e193b4fc-912a-4917-b036-b76c7a6f58ab) und [Exemplarische Vorgehensweise: Erstellen einer lokalisierbaren Windows Forms](https://msdn.microsoft.com/library/c5240b6e-aaca-4286-9bae-778a416edb9c).  
  
 Im Allgemeinen sollten Sie nicht verwenden eine <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement als Container für das gesamte Layout. Verwendung <xref:System.Windows.Forms.TableLayoutPanel> Steuerelemente, um Teile des Layouts proportionale Größenänderung von Fenstern annimmt Funktionen bereitzustellen.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen eines Windows Forms-Projekts  
  
-   Anordnen von Steuerelementen in Zeilen und Spalten  
  
-   Festlegen von Zeilen- und Spalteneigenschaften  
  
-   Überspannen von Zeilen und Spalten mit einem Steuerelement  
  
-   Automatische Behandlung von Überläufen  
  
-   Einfügen von Steuerelementen durch Doppelklicken in der Toolbox  
  
-   Einfügen eines Steuerelements durch Zeichnen seiner Kontur  
  
-   Erneutes Zuweisen von vorhandenen Steuerelementen zu einem anderen übergeordneten Element  
  
 Wenn Sie diese Aufgaben durchgearbeitet haben, besitzen Sie ein Verständnis für die Rolle, die diese wichtigen Layoutfunktionen spielen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.  
  
#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
1.  Erstellen Sie eine Windows-Anwendungsprojekt mit dem Namen "TableLayoutPanelExample". Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) .  
  
2.  Wählen Sie das Formular in der **Windows** **Formulardesigner**.  
  
## <a name="arranging-controls-in-rows-and-columns"></a>Anordnen von Steuerelementen in Zeilen und Spalten  
 Die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement ermöglicht es Ihnen einfach anordnen von Steuerelementen in Zeilen und Spalten.  
  
#### <a name="to-arrange-controls-in-rows-and-columns-using-a-tablelayoutpanel"></a>Anordnen von Steuerelementen in Zeilen und Spalten, die mithilfe von TableLayoutPanel  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular. Beachten Sie, dass standardmäßig die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement enthält vier Zellen.  
  
2.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** in die <xref:System.Windows.Forms.TableLayoutPanel> steuern, und legen Sie es in eine der Zellen. Beachten Sie, dass die <xref:System.Windows.Forms.Button> Steuerelement wird erstellt, in der Zelle, die Sie ausgewählt haben.  
  
3.  Ziehen Sie drei weitere <xref:System.Windows.Forms.Button> -Steuerelemente aus der **Toolbox** in die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement, sodass jede Zelle über eine Schaltfläche enthält.  
  
4.  Ziehen Sie den vertikalen Ziehpunkt zwischen den beiden Spalten aus, und verschieben Sie sie auf der linken Seite. Beachten Sie, dass die <xref:System.Windows.Forms.Button> Steuerelemente in der ersten Spalte werden auf eine kleinere Breite, während die Größe der Größe der <xref:System.Windows.Forms.Button> Steuerelemente in der zweiten Spalte bleibt unverändert.  
  
5.  Ziehen Sie den vertikalen Ziehpunkt zwischen den beiden Spalten aus, und verschieben Sie sie auf der rechten Seite. Beachten Sie, dass die <xref:System.Windows.Forms.Button> while-Steuerelemente in der ersten Spalte zurückgeben, um ihre ursprüngliche Größe der <xref:System.Windows.Forms.Button> Steuerelemente in der zweiten Spalte nach rechts verschoben werden.  
  
6.  Verschieben Sie den horizontalen Ziehpunkt oben und unten, um die Auswirkungen auf die Steuerelemente im Bereich finden Sie unter.  
  
## <a name="positioning-controls-within-cells-using-docking-and-anchoring"></a>Positionieren von Steuerelementen in Zellen, die durch Andocken und Verankern  
 Das Verankerungsverhalten von untergeordneten Steuerelementen in einem <xref:System.Windows.Forms.TableLayoutPanel> weicht vom Verhalten in anderen Containersteuerelementen. Das Andockverhalten des untergeordneten Steuerelemente ist identisch mit anderen Containersteuerelementen.  
  
#### <a name="positioning-controls-within-cells"></a>Positionieren von Steuerelementen in Zellen  
  
1.  Wählen Sie die erste <xref:System.Windows.Forms.Button> Steuerelement. Legen Sie den Wert seiner <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill>fest. Beachten Sie, dass die <xref:System.Windows.Forms.Button> Steuerelement wird erweitert, um die Zelle ausfüllt.  
  
2.  Wählen Sie eine der anderen <xref:System.Windows.Forms.Button> Steuerelemente. Legen Sie den Wert seiner <xref:System.Windows.Forms.Control.Anchor%2A> -Eigenschaft auf <xref:System.Windows.Forms.AnchorStyles.Right>fest. Beachten Sie, dass es verschoben wird, sodass die rechte Rahmen in der Nähe von den rechten Rand der Zelle ist. Der Abstand zwischen den Rändern ist die Summe der <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Margin%2A> -Eigenschaft und des Bereichs <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft.  
  
3.  Ändern Sie den Wert, der die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft <xref:System.Windows.Forms.AnchorStyles.Right> und <xref:System.Windows.Forms.AnchorStyles.Left>. Beachten Sie, die das Steuerelement an die Breite der Zelle angepasst wird, mit der <xref:System.Windows.Forms.Control.Margin%2A> und <xref:System.Windows.Forms.Control.Padding%2A> Werte berücksichtigt.  
  
4.  Wiederholen Sie die Schritte 2 und 3 für die <xref:System.Windows.Forms.AnchorStyles.Top> und <xref:System.Windows.Forms.AnchorStyles.Bottom> Stile.  
  
## <a name="setting-row-and-column-properties"></a>Festlegen von Zeilen- und Spalteneigenschaften  
 Sie können die einzelne Eigenschaften von Zeilen und Spalten festlegen, mit der <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> und <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> Sammlungen.  
  
#### <a name="to-set-row-and-column-properties"></a>Zum Festlegen von Eigenschaften für Zeilen- und  
  
1.  Wählen Sie die <xref:System.Windows.Forms.TableLayoutPanel> steuern, der **Windows Forms-Designer**.  
  
2.  In der **Eigenschaften** Windows, öffnen die <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> Auflistung, indem Sie auf die Auslassungspunkte (![VisualStudioEllipsesButton-bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) Schaltfläche neben der **Spalten** Eintrag.  
  
3.  Die erste Spalte auswählen und ändern Sie den Wert, der die <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> Eigenschaft <xref:System.Windows.Forms.SizeType.AutoSize>. Klicken Sie auf **OK** um die Änderung anzunehmen. Beachten Sie, dass die Breite der ersten Spalte reduziert wird, entsprechend der <xref:System.Windows.Forms.Button> Steuerelement. Beachten Sie außerdem, dass die Breite der Spalte nicht geändert werden kann.  
  
4.  In der **Eigenschaften** geöffnete Fenster die <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> Auflistung, und wählen Sie die erste Spalte. Ändern Sie den Wert, der die <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> Eigenschaft <xref:System.Windows.Forms.SizeType.Percent>. Klicken Sie auf **OK** um die Änderung anzunehmen. Ändern der Größe der <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement auf einer größeren Breite aus, und beachten Sie, dass die Breite der ersten Spalte erweitert. Ändern der Größe der <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement auf eine kleinere Breite aus, und beachten Sie, dass die Schaltflächen in der ersten Spalte an die Größe die Zelle angepasst werden. Beachten Sie außerdem, dass die Breite der Spalte geändert werden.  
  
5.  In der **Eigenschaften** geöffnete Fenster die <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> Auflistung, und wählen Sie alle aufgelisteten Spalten. Legen Sie den Wert von jedem <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> Eigenschaft <xref:System.Windows.Forms.SizeType.Percent>. Klicken Sie auf **OK** um die Änderung anzunehmen. Wiederholen Sie diesen Schritt mit der <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> Auflistung.  
  
6.  Einen der Ziehpunkte zur Größenänderung Ecke, und Ändern der Größe der Breite und die Höhe der <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement. Beachten Sie, die die Zeilen und Spalten, als angepasst werden die <xref:System.Windows.Forms.TableLayoutPanel> größenänderungen des Steuerelements. Beachten Sie außerdem, dass die Zeilen und Spalten mit veränderbarer Größe, mit der horizontalen und vertikalen Ziehpunkten sind.  
  
## <a name="spanning-rows-and-columns-with-a-control"></a>Überspannen von Zeilen und Spalten mit einem Steuerelement  
 Die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement fügt mehrere neue Eigenschaften für Steuerelemente zur Entwurfszeit. Zwei dieser Eigenschaften sind `RowSpan` und `ColumnSpan`. Sie können diese Eigenschaften verwenden, ein Steuerelement Spanne mehr als eine Zeile oder Spalte vornehmen.  
  
#### <a name="to-span-rows-and-columns-with-a-control"></a>Zeilen und Spalten mit einem Steuerelement umfassen.  
  
1.  Wählen Sie die <xref:System.Windows.Forms.Button> -Steuerelement in der ersten Zeile und ersten Spalte.  
  
2.  In der **Eigenschaften** Windows, ändern Sie den Wert, der die `ColumnSpan` Eigenschaft **2**. Beachten Sie, dass die <xref:System.Windows.Forms.Button> Steuerelement ausfüllt, der ersten Spalte und die zweite Spalte. Beachten Sie auch als eine zusätzliche Zeile hinzugefügt wurde, um diese Änderung zu berücksichtigen.  
  
3.  Wiederholen Sie Schritt 2 für die `RowSpan` Eigenschaft.  
  
## <a name="inserting-controls-by-double-clicking-them-in-the-toolbox"></a>Einfügen von Steuerelementen durch Doppelklicken in der Toolbox  
 Sie können Auffüllen Ihrer <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement durch Doppelklicken auf die Steuerelemente in der **Toolbox**.  
  
#### <a name="to-insert-controls-by-double-clicking-in-the-toolbox"></a>So fügen Sie Steuerelemente durch Doppelklicken in der Toolbox ein  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Doppelklicken Sie auf das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements in der **Toolbox**. Beachten Sie, dass ein neue Schaltflächen-Steuerelement in der <xref:System.Windows.Forms.TableLayoutPanel> ersten Zelle des Steuerelements.  
  
3.  Doppelklicken Sie in der **Toolbox**auf verschiedene weitere Steuerelemente. Beachten Sie, dass die neuen Steuerelemente nacheinander im werden die <xref:System.Windows.Forms.TableLayoutPanel> freien Zellen des Steuerelements. Beachten Sie, dass die <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement erweitert wird, um die neuen Steuerelemente zu ermöglichen, wenn keine Zellen öffnen verfügbar sind.  
  
## <a name="automatic-handling-of-overflows"></a>Automatische Behandlung von Überläufen  
 Beim Einfügen von Steuerelementen in der <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement, können Sie leere Zellen ausführen, für neue Steuerelemente. Die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement behandelt diese Situation durch Erhöhen der Anzahl von Zellen.  
  
#### <a name="to-observe-automatic-handling-of-overflows"></a>Beobachten Sie automatische Behandlung von Überläufen  
  
1.  Treten weiterhin leere Zellen in der <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement, fügen Sie weiterhin neue <xref:System.Windows.Forms.Button> steuert, bis die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement ist voll.  
  
2.  Nach der <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement voll ist, doppelklicken Sie auf die <xref:System.Windows.Forms.Button> Symbol in der **Toolbox** , fügen Sie einen anderen <xref:System.Windows.Forms.Button> Steuerelement. Beachten Sie, dass die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement erstellt neue Zellen für das neue Steuerelement. Fügen Sie einige weitere Steuerelemente, und beobachten Sie das Verhalten der größenanpassung.  
  
3.  Ändern Sie den Wert der <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A>-Eigenschaft des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements in <xref:System.Windows.Forms.TableLayoutPanelGrowStyle.FixedSize>. Doppelklicken Sie auf die <xref:System.Windows.Forms.Button> Symbol in der **Toolbox** einzufügende <xref:System.Windows.Forms.Button> steuert, bis die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement ist voll. Doppelklicken Sie auf die <xref:System.Windows.Forms.Button> Symbol in der **Toolbox** erneut aus. Beachten Sie, dass Sie eine Fehlermeldung aus der **Windows Forms-Designer** Sie darüber informiert, dass zusätzliche Zeilen und Spalten können nicht erstellt werden.  
  
## <a name="inserting-a-control-by-drawing-its-outline"></a>Einfügen eines Steuerelements durch Zeichnen seiner Kontur  
 Sie können ein Steuerelement in Einfügen einer <xref:System.Windows.Forms.TableLayoutPanel> steuern und seine Größe angeben, indem Sie in einer Zelle seine Kontur zeichnen.  
  
#### <a name="to-insert-a-control-by-drawing-its-outline"></a>So fügen Sie ein Steuerelement ein, indem Sie seine Kontur zeichnen  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Klicken Sie in der **Toolbox**auf das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements. Ziehen Sie es nicht auf das Formular.  
  
3.  Bewegen Sie den Mauszeiger über die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement. Beachten Sie, dass der Mauszeiger die Form eines Fadenkreuzes annimmt, an das das Symbol des <xref:System.Windows.Forms.Button> -Steuerelements angefügt ist.  
  
4.  Klicken Sie, und halten Sie die Maustaste gedrückt.  
  
5.  Ziehen Sie den Mauszeiger, um die Kontur des <xref:System.Windows.Forms.Button> -Steuerelements zu zeichnen. Wenn Sie mit der Größe zufrieden sind, geben Sie die Maustaste frei. Beachten Sie, dass die <xref:System.Windows.Forms.Button> Steuerelement wird erstellt, in der Zelle, in dem Sie die Kontur des Steuerelements gezeichnet haben.  
  
## <a name="multiple-controls-within-cells-are-not-permitted"></a>Mehrere Steuerelemente in Zellen sind nicht zulässig.  
 Die <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement kann nur ein untergeordnetes Steuerelement pro Zelle enthalten.  
  
#### <a name="to-demonstrate-that-multiple-controls-within-cells-are-not-permitted"></a>Um zu veranschaulichen, dass mehrere Steuerelemente in Zellen nicht zulässig sind.  
  
-   Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** in die <xref:System.Windows.Forms.TableLayoutPanel> steuern, und legen Sie es in eine Zelle belegt. Beachten Sie, dass die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement lässt nicht zum Löschen der <xref:System.Windows.Forms.Button> Steuerelement in die gefüllte Zelle.  
  
## <a name="swapping-controls"></a>Austauschen von Steuerelementen  
 Die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement können Sie Steuerelemente in zwei verschiedenen Zellen auszutauschen.  
  
#### <a name="to-swap-controls"></a>Austauschen von Steuerelementen  
  
-   Ziehen Sie eines der der <xref:System.Windows.Forms.Button> Steuerelemente über eine gefüllte Zelle, und platzieren auf einem anderen gefüllte Zelle. Beachten Sie, dass die beiden Steuerelemente, die aus einer Zelle in die andere verschoben werden.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Mithilfe einer Kombination aus Layoutbereichen und Steuerelementen können Sie ein komplexes Layout verwirklichen. Hier sind paar Vorschläge für weitere Experimente:  
  
-   Versuchen Sie es ändern der Größe eines der <xref:System.Windows.Forms.Button> Steuerelementen zu einem größeren und beobachten Sie die Auswirkung auf das Layout.  
  
-   Fügen Sie eine Auswahl mehrerer Steuerelemente in der <xref:System.Windows.Forms.TableLayoutPanel> steuern, und beachten Sie, wie die Steuerelemente eingefügt werden.  
  
-   Layoutbereiche können andere Layoutbereiche enthalten. Experimentieren Sie mit dem Ablegen eines <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelements auf dem vorhandenen Steuerelement.  
  
-   Andocken der <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement an das übergeordnete Formular. Ändern Sie die Größe des Formulars, und beobachten Sie die Auswirkung auf das Layout.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [Microsoft Windows-Benutzererfahrung, Official Guidelines for User Interface Developers and Designers. Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1)](https://www.microsoft.com/mspress/southpacific/books/book11588.htm)  
 [Exemplarische Vorgehensweise: Erstellen eines in der Größe veränderbaren Windows Forms für die Dateneingabe](https://msdn.microsoft.com/library/e193b4fc-912a-4917-b036-b76c7a6f58ab)  
 [Exemplarische Vorgehensweise: Erstellen einer lokalisierbaren Windows Formulars](https://msdn.microsoft.com/library/c5240b6e-aaca-4286-9bae-778a416edb9c)  
 [Empfohlene Vorgehensweisen für das TableLayoutPanel-Steuerelement](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)  
 [Übersicht über die AutoSize-Eigenschaft](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [Gewusst wie: Andocken von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)  
 [Gewusst wie: Verankern von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)  
 [Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)
