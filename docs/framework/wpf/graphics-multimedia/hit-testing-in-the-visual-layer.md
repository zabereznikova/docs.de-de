---
title: Treffertests in der visuellen Ebene
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit testing functionality [WPF]
- visual layer [WPF], hit testing functionality
ms.assetid: b1a64b61-14be-4d75-b89a-5c67bebb2c7b
ms.openlocfilehash: d4d304353e91147c57297dcc4525759ff1474b4f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186401"
---
# <a name="hit-testing-in-the-visual-layer"></a>Treffertests in der visuellen Ebene
Dieses Thema enthält eine Übersicht über die Treffertestfunktionen der visuellen Ebene. Mit der Treffertestunterstützung können Sie bestimmen, ob eine Geometrie <xref:System.Windows.Media.Visual>oder ein Punktwert innerhalb des gerenderten Inhalts einer liegt, sodass Sie das Verhalten der Benutzeroberfläche implementieren können, z. B. ein Auswahlrechteck, um mehrere Objekte auszuwählen.  

<a name="hit_testing_scenarios"></a>
## <a name="hit-testing-scenarios"></a>Treffertestszenarios  
 Die <xref:System.Windows.UIElement> Klasse <xref:System.Windows.UIElement.InputHitTest%2A> stellt die Methode bereit, mit der Sie testen gegen ein Element mithilfe eines bestimmten Koordinatenwerts treffen können. In vielen Fällen <xref:System.Windows.UIElement.InputHitTest%2A> bietet die Methode die gewünschte Funktionalität zum Implementieren von Treffertests von Elementen. Es gibt jedoch mehrere Szenarios, bei denen es möglicherweise erforderlich ist, den Treffertest auf der visuellen Ebene zu implementieren.  
  
- Treffertests für<xref:System.Windows.UIElement> Nicht-Objekte: Dies gilt,<xref:System.Windows.UIElement> wenn Sie <xref:System.Windows.Media.DrawingVisual> auf das Testen von Nicht-Objekten, z. B. Grafikobjekten, treffen.  
  
- Ein Treffertest unter Verwendung einer Geometrie: Dies gilt für Treffertests unter Verwendung eines Geometrieobjekts statt des Koordinatenwerts eines Punkts.  
  
- Ein Treffertest für mehrere Objekte: Dies gilt fürs Treffertests für mehrere Objekte, wie z.B. überlappende Objekte. Sie können Ergebnisse für alle grafischen Elemente abrufen, die eine Geometrie oder einen Punkt kreuzen, nicht nur für das erste.  
  
- Ignorieren <xref:System.Windows.UIElement> der Treffertestrichtlinie: Dies gilt, wenn Sie die Treffertestrichtlinie ignorieren müssen, bei der <xref:System.Windows.UIElement> Faktoren wie deaktiviert oder unsichtbar berücksichtigt werden.  
  
> [!NOTE]
> Ein vollständiges Codebeispiel für einen Treffertest in der visuellen Ebene finden Sie unter [Beispiel für einen Treffertest mit DrawingVisuals](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual) und [Beispiel für einen Treffertest mit Win32-Interoperabilität](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting).  
  
<a name="hit_testing_support"></a>
## <a name="hit-testing-support"></a>Unterstützung für den Treffertest  
 Der Zweck <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> der Methoden <xref:System.Windows.Media.VisualTreeHelper> in der Klasse besteht darin, zu bestimmen, ob sich ein Geometrie- oder Punktkoordinatenwert innerhalb des gerenderten Inhalts eines bestimmten Objekts befindet, z. B. eines Steuerelements oder Grafikelements. Sie können beispielsweise den Treffertest verwenden um zu bestimmen, ob ein Mausklick innerhalb des umgebenden Rechtecks eines Objekts in die Geometrie eines Kreises fällt. Sie können auch die Standardimplementierung für den Treffertest überschreiben, um Ihre eigenen benutzerdefinierten Treffertestberechnungen durchzuführen.  
  
 Die folgende Abbildung zeigt die Beziehung zwischen dem Bereich eines nicht rechteckigen Objekts und seinem umschließenden Rechteck.  
  
 ![Diagramm eines gültigen Treffertestbereichs](./media/wcpsdk-mmgraphics-visuals-hittest-1.png "wcpsdk_mmgraphics_visuals_hittest_1")  
Diagramm eines gültigen Treffertestbereichs  
  
<a name="hit_testing_and_z-order"></a>
## <a name="hit-testing-and-z-order"></a>Treffertest und Z-Reihenfolge  
 Die visuelle Ebene für [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] unterstützt den Treffertest für alle Objekte unter einem Punkt oder einer Geometrie und nicht nur für das oberste Objekt. Die Ergebnisse werden in Z-Reihenfolge zurückgegeben. Das visuelle Objekt, das Sie als <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Parameter an die Methode übergeben, bestimmt jedoch, welcher Teil der visuellen Struktur getestet wird. Sie können einen Treffertest für die ganze visuelle Struktur oder einen beliebigen Teil davon durchführen.  
  
 In der folgenden Abbildung befindet sich das Kreisobjekt sowohl auf dem Quadrat als auch auf dem Dreieck. Wenn Sie nur daran interessiert sind, das visuelle Objekt zu testen, dessen Wert für die Z-Reihenfolge <xref:System.Windows.Media.HitTestResultCallback> am obersten Wert ist, können Sie die visuelle Treffertest-Enumeration so einstellen, dass sie von der zurückkehrt, um die Treffertestdurchquerung nach dem ersten Element zu <xref:System.Windows.Media.HitTestResultBehavior.Stop> beenden.  
  
 ![Diagramm der Z&#45;Reihenfolge in einer visuellen Struktur](./media/wcpsdk-mmgraphics-visuals-hittest-2.png "wcpsdk_mmgraphics_visuals_hittest_2")  
Diagramm der Z-Reihenfolge einer visuellen Struktur  
  
 Wenn Sie alle visuellen Objekte unter einem bestimmten Punkt <xref:System.Windows.Media.HitTestResultBehavior.Continue> oder <xref:System.Windows.Media.HitTestResultCallback>einer bestimmten Geometrie aufzählen möchten, kehren Sie aus dem zurück. Dies bedeutet, dass Sie den Treffertest sogar für vollständig von anderen Objekten überdeckte visuelle Objekte durchführen können. Weitere Informationen finden Sie im Beispielcode im Abschnitt „Verwenden eines Treffertest-Ergebnisrückrufs“.  
  
> [!NOTE]
> Auch für transparente visuelle Objekte kann der Treffertest durchgeführt werden.  
  
<a name="using_default_hit_testing"></a>
## <a name="using-default-hit-testing"></a>Verwenden des Standardtreffertests  
 Sie können ermitteln, ob sich ein Punkt innerhalb der <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Geometrie eines visuellen Objekts befindet, indem Sie die Methode zum Angeben eines visuellen Objekts und eines Punktkoordinatenwerts verwenden, mit dem getestet werden soll. Der visuelle Objektparameter identifiziert den Ausgangspunkt in der visuellen Struktur für die Treffertestsuche. Wenn ein visuelles Objekt in der visuellen Struktur gefunden wird, deren Geometrie die Koordinate enthält, wird es auf die <xref:System.Windows.Media.HitTestResult.VisualHit%2A> Eigenschaft eines <xref:System.Windows.Media.HitTestResult> Objekts festgelegt. Der <xref:System.Windows.Media.HitTestResult> wird dann <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> von der Methode zurückgegeben. Wenn der Punkt nicht in der visuellen Unterstruktur <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> `null`enthalten ist, die Sie beim Testen drücken, wird zurückgegeben.  
  
> [!NOTE]
> Der Standardtreffertest gibt immer das oberste Objekt in der Z-Reihenfolge zurück. Wenn Sie alle visuellen Objekte identifizieren möchten – auch diejenigen, die teilweise oder vollständig verdeckt sind –, verwenden Sie einen Treffertest-Ergebnisrückruf.  
  
 Der Koordinatenwert, den Sie als <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Punktparameter für die Methode übergeben, muss relativ zum Koordinatenraum des visuellen Objekts sein, auf das Sie beim Testen treffen. Wenn Sie beispielsweise visuelle Objekte geschachtelt haben, die im übergeordneten Koordinatenraum bei (100, 100) definiert sind, entspricht der Treffertest eines untergeordneten visuellen Objekts bei (0, 0) dem Treffertest bei (100, 100) im übergeordneten Koordinatenraum.  
  
 Der folgende Code zeigt, wie Mausereignishandler <xref:System.Windows.UIElement> für ein Objekt eingerichtet werden, das zum Erfassen von Ereignissen verwendet wird, die für Treffertests verwendet werden.  
  
 [!code-csharp[HitTestingOverview#100](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[HitTestingOverview#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#100)]  
  
### <a name="how-the-visual-tree-affects-hit-testing"></a>Beeinflussung des Treffertests durch die visuelle Struktur  
 Der Startpunkt in der visuellen Struktur bestimmt, welche Objekte während der Treffertestenumeration der Objekte zurückgegeben werden. Wenn Sie für mehrere Objekte einen Treffertest durchführen möchten, muss das in der visuellen Struktur als Startpunkt verwendete Objekt das gemeinsame übergeordnete Element aller betroffenen Objekte sein. Wenn Sie beispielsweise sowohl für das Schaltflächenelement als auch für das visuelle Zeichnungsobjekt im folgenden Diagramm einen Treffertest durchführen möchten, müssen Sie den Startpunkt in der visuellen Struktur auf das gemeinsame übergeordnete Objekt für diese beiden Elemente festlegen. In diesem Fall ist das Canvas-Element das übergeordnete Objekt für das Schaltflächenelement und das visuelle Zeichnungsobjekt.  
  
 ![Diagramm einer visuellen Strukturhierarchie](./media/wcpsdk-mmgraphics-visuals-overview-01.gif "wcpsdk_mmgraphics_visuals_overview_01")  
Diagramm einer visuellen Strukturhierarchie  
  
> [!NOTE]
> Die <xref:System.Windows.UIElement.IsHitTestVisible%2A> Eigenschaft ruft einen Wert ab <xref:System.Windows.UIElement>oder legt ihn fest, der deklariert, ob ein -derived-Objekt möglicherweise als Treffertestergebnis aus einem Teil des gerenderten Inhalts zurückgegeben werden kann. Dadurch haben Sie die Möglichkeit, selektiv Änderungen an der visuellen Struktur vorzunehmen, um zu bestimmen, welche visuellen Objekte an einem Treffertest beteiligt sind.  
  
<a name="using_a_hit_test_result_callback"></a>
## <a name="using-a-hit-test-result-callback"></a>Verwenden eines Treffertest-Ergebnisrückrufs  
 Sie können alle visuellen Objekte in einer visuellen Struktur auflisten, deren Geometrie einen angegebenen Koordinatenwert enthält. Dadurch können Sie alle visuellen Objekte identifizieren, auch diejenigen, die teilweise oder vollständig von anderen visuellen Objekten verdeckt werden. Um visuelle Objekte in einer visuellen <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Struktur aufzuzählen, verwenden Sie die Methode mit einer Treffertestrückruffunktion. Die Treffertest-Rückruffunktion wird vom System aufgerufen, wenn der von Ihnen angegebene Koordinatenwert in einem visuellen Objekt enthalten ist.  
  
 Während der Auflistung der Treffertestergebnisse sollten Sie keine Vorgänge ausführen, die die visuelle Struktur ändern. Das Hinzufügen oder Entfernen eines Objekts aus der visuellen Struktur, während diese durchlaufen wird, kann zu unvorhersehbarem Verhalten führen. Sie können die visuelle Struktur <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> sicher ändern, nachdem die Methode zurückgegeben wurde. Sie können eine Datenstruktur bereitstellen, <xref:System.Collections.ArrayList>z. B. eine , um Werte während der Aufzählung der Treffertestergebnisse zu speichern.  
  
 [!code-csharp[HitTestingOverview#101](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#101)]
 [!code-vb[HitTestingOverview#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#101)]  
  
 Die Treffertest-Rückrufmethode definiert die Aktionen, die ausgeführt werden, wenn ein Treffertest für ein bestimmtes visuelles Objekt in der visuellen Struktur identifiziert wird. Nachdem Sie die Aktionen ausgeführt <xref:System.Windows.Media.HitTestResultBehavior> haben, geben Sie einen Wert zurück, der bestimmt, ob die Aufzählung anderer visueller Objekte fortgesetzt werden soll oder nicht.  
  
 [!code-csharp[HitTestingOverview#102](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#102)]
 [!code-vb[HitTestingOverview#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#102)]  
  
> [!NOTE]
> Die Auflistung der visuellen Objekttreffer erfolgt in Z-Reihenfolge. Das visuelle Objekt auf der obersten Z-Reihenfolgenebene ist das erste aufgelistete Objekt. Alle anderen visuellen Objekte werden absteigend gemäß der Z-Reihenfolge aufgelistet. Diese Auflistungsreihenfolge entspricht der Renderingreihenfolge der grafischen Elemente.  
  
 Sie können die Aufzählung visueller Objekte jederzeit in der Erfolgstestrückruffunktion beenden, indem Sie <xref:System.Windows.Media.HitTestResultBehavior.Stop>zurückgeben.  
  
 [!code-csharp[HitTestingOverview#103](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#103)]
 [!code-vb[HitTestingOverview#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#103)]  
  
<a name="using_a_hit_test_filter_callback"></a>
## <a name="using-a-hit-test-filter-callback"></a>Verwenden eines Treffertestfilter-Rückrufs  
 Sie können einen optionalen Treffertestfilter verwenden, um die an die Treffertestergebnisse übergebenen Objekte zu begrenzen. Dadurch können Sie die Teile der visuellen Struktur ignorieren, die nicht in Ihren Treffertestergebnissen verarbeitet werden sollen. Um einen Treffertestfilter zu implementieren, definieren Sie eine Treffertestfilterrückruffunktion und <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> übergeben sie beim Aufrufen der Methode als Parameterwert.  
  
 [!code-csharp[HitTestingOverview#104](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#104)]
 [!code-vb[HitTestingOverview#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#104)]  
  
 Wenn Sie die optionale Treffertestfilterrückruffunktion nicht angeben `null` möchten, übergeben <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Sie einen Wert als Parameter für die Methode.  
  
 [!code-csharp[HitTestingOverview#105](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#105)]
 [!code-vb[HitTestingOverview#105](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#105)]  
  
 ![Bereinigen einer visuellen Struktur mithilfe eines Treffertestfilters](./media/filteredvisualtree-01.png "FilteredVisualTree_01")  
Reduzieren der Verzweigungen in einer visuellen Struktur  
  
 Mit der Treffertestfilter-Rückruffunktion können Sie alle visuellen Objekte auflisten, deren gerenderte Inhalte die von Ihnen angegebenen Koordinaten enthalten. Sie können jedoch auch bestimmte Verzweigungen der visuellen Struktur ignorieren, die im Rahmen Ihrer Treffertestergebnis-Rückruffunktion nicht verarbeitet werden sollen. Der Rückgabewert der Treffertestfilter-Rückruffunktion bestimmt, welcher Typ von Aktion von der Enumeration der visuellen Objekte ausgeführt werden soll. Wenn Sie z. B. <xref:System.Windows.Media.HitTestFilterBehavior.ContinueSkipSelfAndChildren>den Wert zurückgeben, können Sie das aktuelle visuelle Objekt und seine untergeordneten Objekte aus der Aufzählung der Treffertestergebnisse entfernen. Dies bedeutet, dass für die Treffertestergebnis-Rückruffunktion diese Objekte nicht in der Auflistung enthalten sind. Durch das Reduzieren der Verzweigungen in der visuellen Struktur von Objekten wird der Verarbeitungsaufwand während der Übergabe der Auflistung von Treffertestergebnissen verringert. Im folgenden Codebeispiel überspringt der Filter Bezeichnungen und ihre Nachfolgerelemente und führt für alle anderen Elemente Treffertests durch.  
  
 [!code-csharp[HitTestingOverview#106](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#106)]
 [!code-vb[HitTestingOverview#106](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#106)]  
  
> [!NOTE]
> Der Treffertestfilter-Rückruf wird gelegentlich aufgerufen, wenn der Treffertestergebnis-Rückruf nicht aufgerufen wird.  
  
<a name="overriding_default_hit_testing"></a>
## <a name="overriding-default-hit-testing"></a>Überschreiben des Standardtreffertests  
 Sie können die standardmäßige Treffertestunterstützung eines visuellen <xref:System.Windows.Media.Visual.HitTestCore%2A> Objekts überschreiben, indem Sie die Methode überschreiben. Dies bedeutet, dass <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> beim Aufrufen der <xref:System.Windows.Media.Visual.HitTestCore%2A> Methode die überschriebene Implementierung von aufgerufen wird. Ihre überschriebene Methode wird aufgerufen, wenn sich ein Treffertest innerhalb des umgebenden Rechtecks für das visuelle Objekt befindet. Dies gilt auch dann, wenn die Koordinate außerhalb des gerenderten Inhalts des visuellen Objekts liegt.  
  
 [!code-csharp[HitTestingOverview#107](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#107)]
 [!code-vb[HitTestingOverview#107](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#107)]  
  
 Es kann vorkommen, dass Sie einen Treffertest sowohl für das umschließende Rechteck als auch für den gerenderten Inhalt eines visuellen Objekts durchführen möchten. Wenn Sie `PointHitTestParameters` den Parameterwert <xref:System.Windows.Media.Visual.HitTestCore%2A> in der überschriebenen <xref:System.Windows.Media.Visual.HitTestCore%2A>Methode als Parameter für die Basismethode verwenden, können Sie Aktionen basierend auf einem Treffer des umgebenden Rechtecks eines visuellen Objekts ausführen und dann einen zweiten Treffertest für den gerenderten Inhalt des visuellen Objekts durchführen.  
  
 [!code-csharp[HitTestingOverview#108](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#108)]
 [!code-vb[HitTestingOverview#108](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#108)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>
- <xref:System.Windows.Media.HitTestResult>
- <xref:System.Windows.Media.HitTestResultCallback>
- <xref:System.Windows.Media.HitTestFilterCallback>
- <xref:System.Windows.UIElement.IsHitTestVisible%2A>
- [Beispiel für Treffertests mit DarwingVisuals](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual)
- [Beispiel für Treffertests mit Win32-Interoperabilität](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)
- [Vorgehensweise: Treffertest für eine Geometrie in einem visuellen Objekt](how-to-hit-test-geometry-in-a-visual.md)
- [Treffertest mithilfe eines Win32-Hostcontainers](how-to-hit-test-using-a-win32-host-container.md)
