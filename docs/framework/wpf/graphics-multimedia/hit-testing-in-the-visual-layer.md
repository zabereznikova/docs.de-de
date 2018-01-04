---
title: Treffertests in der visuellen Ebene
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit testing functionality [WPF]
- visual layer [WPF], hit testing functionality
ms.assetid: b1a64b61-14be-4d75-b89a-5c67bebb2c7b
caps.latest.revision: "42"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f1bdecedece4581eaf8a010eddc0974e44fe88ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="hit-testing-in-the-visual-layer"></a>Treffertests in der visuellen Ebene
Dieses Thema enthält eine Übersicht über die Treffertestfunktionen der visuellen Ebene. Unterstützung für Treffertests können Sie bestimmen, ob ein Geometrie oder Punkt-Wert in den gerenderten Inhalt fällt eine <xref:System.Windows.Media.Visual>, sodass Sie Benutzeroberflächenverhalten z. B. ein Auswahlrechteck zum Auswählen mehrerer Objekte zu implementieren.  
  
 
  
<a name="hit_testing_scenarios"></a>   
## <a name="hit-testing-scenarios"></a>Treffertestszenarios  
 Die <xref:System.Windows.UIElement> -Klasse stellt die <xref:System.Windows.UIElement.InputHitTest%2A> -Methode, die Ihnen ermöglicht, ein Element mithilfe einer bestimmten Treffertest. In vielen Fällen die <xref:System.Windows.UIElement.InputHitTest%2A> Methode enthält die gewünschte Funktionalität für die Implementierung von Elementen testen. Es gibt jedoch mehrere Szenarios, bei denen es möglicherweise erforderlich ist, den Treffertest auf der visuellen Ebene zu implementieren.  
  
-   Treffertest für nicht-<xref:System.Windows.UIElement> Objekte: Dies gilt, wenn Sie die Tests nicht erreicht werden<xref:System.Windows.UIElement> Objekte, z. B. <xref:System.Windows.Media.DrawingVisual> oder Graphics-Objekten.  
  
-   Ein Treffertest unter Verwendung einer Geometrie: Dies gilt für Treffertests unter Verwendung eines Geometrieobjekts statt des Koordinatenwerts eines Punkts.  
  
-   Ein Treffertest für mehrere Objekte: Dies gilt fürs Treffertests für mehrere Objekte, wie z.B. überlappende Objekte. Sie können Ergebnisse für alle grafischen Elemente abrufen, die eine Geometrie oder einen Punkt kreuzen, nicht nur für das erste.  
  
-   Ignorieren von <xref:System.Windows.UIElement> Treffertests Richtlinie: Dies gilt, wenn Sie ignorieren möchten die <xref:System.Windows.UIElement> Treffertests Richtlinie, die berücksichtigt Faktoren wie gibt an, ob ein Element deaktiviert oder ausgeblendet ist.  
  
> [!NOTE]
>  Ein vollständiges Codebeispiel für einen Treffertest in der visuellen Ebene finden Sie unter [Beispiel für einen Treffertest mit DrawingVisuals](http://go.microsoft.com/fwlink/?LinkID=159994) und [Beispiel für einen Treffertest mit Win32-Interoperabilität](http://go.microsoft.com/fwlink/?LinkID=159995).  
  
<a name="hit_testing_support"></a>   
## <a name="hit-testing-support"></a>Unterstützung für den Treffertest  
 Der Zweck der <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Methoden in der <xref:System.Windows.Media.VisualTreeHelper> Klasse ist, um festzustellen, ob ein Geometrie oder Punkt-Koordinatenwert in den gerenderten Inhalt eines angegebenen Objekts, z. B. ein Steuerelement oder ein grafisches Element ist. Sie können beispielsweise den Treffertest verwenden um zu bestimmen, ob ein Mausklick innerhalb des umgebenden Rechtecks eines Objekts in die Geometrie eines Kreises fällt. Sie können auch die Standardimplementierung für den Treffertest überschreiben, um Ihre eigenen benutzerdefinierten Treffertestberechnungen durchzuführen.  
  
 Die folgende Abbildung zeigt die Beziehung zwischen dem Bereich eines nicht rechteckigen Objekts und seinem umschließenden Rechteck.  
  
 ![Diagramm eines gültigen treffertestbereich](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-visuals-hittest-1.png "wcpsdk_mmgraphics_visuals_hittest_1")  
Diagramm eines gültigen Treffertestbereichs  
  
<a name="hit_testing_and_z-order"></a>   
## <a name="hit-testing-and-z-order"></a>Treffertest und Z-Reihenfolge  
 Die visuelle Ebene für [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] unterstützt den Treffertest für alle Objekte unter einem Punkt oder einer Geometrie und nicht nur für das oberste Objekt. Die Ergebnisse werden in Z-Reihenfolge zurückgegeben. Jedoch das visuelle Objekt, das Sie als Parameter übergeben der <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Methode bestimmt, welcher Teil der visuellen Struktur, die ausgelöst werden, zu testen. Sie können einen Treffertest für die ganze visuelle Struktur oder einen beliebigen Teil davon durchführen.  
  
 In der folgenden Abbildung befindet sich das Kreisobjekt sowohl auf dem Quadrat als auch auf dem Dreieck. Wenn nur Treffertest für das visuelle Objekt Domänenmodus, dessen Wert der Z-Reihenfolge oberste ist, legen Sie die visuellen Treffertest-Enumeration zurückgegeben <xref:System.Windows.Media.HitTestResultBehavior.Stop> aus der <xref:System.Windows.Media.HitTestResultCallback> Treffertest Durchlauf nach dem ersten Element zu beenden.  
  
 ![Diagramm der z &#45; die Reihenfolge einer visuellen Struktur](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-visuals-hittest-2.png "wcpsdk_mmgraphics_visuals_hittest_2")  
Diagramm der Z-Reihenfolge einer visuellen Struktur  
  
 Wenn Sie alle visuellen Objekte unter einem bestimmten Zeitpunkt oder einer Geometrie auflisten möchten, zurück <xref:System.Windows.Media.HitTestResultBehavior.Continue> aus der <xref:System.Windows.Media.HitTestResultCallback>. Dies bedeutet, dass Sie den Treffertest sogar für vollständig von anderen Objekten überdeckte visuelle Objekte durchführen können. Weitere Informationen finden Sie im Beispielcode im Abschnitt „Verwenden eines Treffertest-Ergebnisrückrufs“.  
  
> [!NOTE]
>  Auch für transparente visuelle Objekte kann der Treffertest durchgeführt werden.  
  
<a name="using_default_hit_testing"></a>   
## <a name="using-default-hit-testing"></a>Verwenden des Standardtreffertests  
 Sie können ermitteln, ob sich ein Punkt innerhalb der Geometrie des visuellen Objekts, mit der <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Methode, um ein visuelles Objekt und einem Punkt-Koordinatenwert ab, für den Test anzugeben. Der visuelle Objektparameter identifiziert den Ausgangspunkt in der visuellen Struktur für die Treffertestsuche. Wenn in der visuellen Struktur ein visuelles Objekt gefunden wird, dessen Geometrie die Koordinate enthält, festgelegt ist die <xref:System.Windows.Media.HitTestResult.VisualHit%2A> Eigenschaft von einem <xref:System.Windows.Media.HitTestResult> Objekt. Die <xref:System.Windows.Media.HitTestResult> wird dann zurückgegeben, aus der <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Methode. Wenn der Punkt nicht mit der visuellen Unterstruktur enthalten ist, Sie erreicht werden, testen, <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> gibt `null`.  
  
> [!NOTE]
>  Der Standardtreffertest gibt immer das oberste Objekt in der Z-Reihenfolge zurück. Wenn Sie alle visuellen Objekte identifizieren möchten – auch diejenigen, die teilweise oder vollständig verdeckt sind –, verwenden Sie einen Treffertest-Ergebnisrückruf.  
  
 Der Koordinatenwert, Sie als der Point-Parameter für übergeben, die <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> -Methode relativ zu dem Koordinatenbereich des visuellen Objekts werden Sie Treffertest durchführen muss. Wenn Sie beispielsweise visuelle Objekte geschachtelt haben, die im übergeordneten Koordinatenraum bei (100, 100) definiert sind, entspricht der Treffertest eines untergeordneten visuellen Objekts bei (0, 0) dem Treffertest bei (100, 100) im übergeordneten Koordinatenraum.  
  
 Der folgende Code zeigt, wie Sie Ereignishandler für Maus Einrichten einer <xref:System.Windows.UIElement> -Objekt, das verwendet wird, um das Erfassen von Ereignissen für Treffertests.  
  
 [!code-csharp[HitTestingOverview#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[HitTestingOverview#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#100)]  
  
### <a name="how-the-visual-tree-affects-hit-testing"></a>Beeinflussung des Treffertests durch die visuelle Struktur  
 Der Startpunkt in der visuellen Struktur bestimmt, welche Objekte während der Treffertestenumeration der Objekte zurückgegeben werden. Wenn Sie für mehrere Objekte einen Treffertest durchführen möchten, muss das in der visuellen Struktur als Startpunkt verwendete Objekt das gemeinsame übergeordnete Element aller betroffenen Objekte sein. Wenn Sie beispielsweise sowohl für das Schaltflächenelement als auch für das visuelle Zeichnungsobjekt im folgenden Diagramm einen Treffertest durchführen möchten, müssen Sie den Startpunkt in der visuellen Struktur auf das gemeinsame übergeordnete Objekt für diese beiden Elemente festlegen. In diesem Fall ist das Canvas-Element das übergeordnete Objekt für das Schaltflächenelement und das visuelle Zeichnungsobjekt.  
  
 ![Diagramm der visuellen Strukturhierarchie](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-visuals-overview-01.gif "wcpsdk_mmgraphics_visuals_overview_01")  
Diagramm einer visuellen Strukturhierarchie  
  
> [!NOTE]
>  Die <xref:System.Windows.UIElement.IsHitTestVisible%2A> Eigenschaft ruft ab oder legt einen Wert, der deklariert, ob ein <xref:System.Windows.UIElement>-abgeleitetes Objekt als Treffertestergebnis von einem Teil des gerenderten Inhalts zurückgegeben werden kann. Dadurch haben Sie die Möglichkeit, selektiv Änderungen an der visuellen Struktur vorzunehmen, um zu bestimmen, welche visuellen Objekte an einem Treffertest beteiligt sind.  
  
<a name="using_a_hit_test_result_callback"></a>   
## <a name="using-a-hit-test-result-callback"></a>Verwenden eines Treffertest-Ergebnisrückrufs  
 Sie können alle visuellen Objekte in einer visuellen Struktur auflisten, deren Geometrie einen angegebenen Koordinatenwert enthält. Dadurch können Sie alle visuellen Objekte identifizieren, auch diejenigen, die teilweise oder vollständig von anderen visuellen Objekten verdeckt werden. Auflisten der visuellen Objekte in einem visuellen Struktur verwenden die <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Methode mit einem Treffertest-Rückruffunktion. Die Treffertest-Rückruffunktion wird vom System aufgerufen, wenn der von Ihnen angegebene Koordinatenwert in einem visuellen Objekt enthalten ist.  
  
 Während der Auflistung der Treffertestergebnisse sollten Sie keine Vorgänge ausführen, die die visuelle Struktur ändern. Das Hinzufügen oder Entfernen eines Objekts aus der visuellen Struktur, während diese durchlaufen wird, kann zu unvorhersehbarem Verhalten führen. Sie können problemlos ändern, die visuelle Struktur nach der <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> -Methode zurückkehrt. Sie möchten eine Datenstruktur bereitstellen, z. B. ein <xref:System.Collections.ArrayList>, um Werte während der Enumeration der Treffertest-Ergebnisse zu speichern.  
  
 [!code-csharp[HitTestingOverview#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#101)]
 [!code-vb[HitTestingOverview#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#101)]  
  
 Die Treffertest-Rückrufmethode definiert die Aktionen, die ausgeführt werden, wenn ein Treffertest für ein bestimmtes visuelles Objekt in der visuellen Struktur identifiziert wird. Nach dem Durchführen der Aktionen, die Sie zurückgeben einer <xref:System.Windows.Media.HitTestResultBehavior> Wert, der bestimmt, ob die Enumeration von anderen visuellen Objekten oder nicht fortgesetzt werden.  
  
 [!code-csharp[HitTestingOverview#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#102)]
 [!code-vb[HitTestingOverview#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#102)]  
  
> [!NOTE]
>  Die Auflistung der visuellen Objekttreffer erfolgt in Z-Reihenfolge. Das visuelle Objekt auf der obersten Z-Reihenfolgenebene ist das erste aufgelistete Objekt. Alle anderen visuellen Objekte werden absteigend gemäß der Z-Reihenfolge aufgelistet. Diese Auflistungsreihenfolge entspricht der Renderingreihenfolge der grafischen Elemente.  
  
 Sie können die Enumeration visueller Objekte in der Treffertest-Rückruffunktion jederzeit beenden, wird durch zurückgeben <xref:System.Windows.Media.HitTestResultBehavior.Stop>.  
  
 [!code-csharp[HitTestingOverview#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#103)]
 [!code-vb[HitTestingOverview#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#103)]  
  
<a name="using_a_hit_test_filter_callback"></a>   
## <a name="using-a-hit-test-filter-callback"></a>Verwenden eines Treffertestfilter-Rückrufs  
 Sie können einen optionalen Treffertestfilter verwenden, um die an die Treffertestergebnisse übergebenen Objekte zu begrenzen. Dadurch können Sie die Teile der visuellen Struktur ignorieren, die nicht in Ihren Treffertestergebnissen verarbeitet werden sollen. Um einem Treffertestfilter zu implementieren, definieren Sie eine Rückruffunktion der Treffertest-Filter und als Parameterwert übergeben, beim Aufrufen der <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Methode.  
  
 [!code-csharp[HitTestingOverview#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#104)]
 [!code-vb[HitTestingOverview#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#104)]  
  
 Wenn Sie nicht die optionalen Treffertest-Rückruffunktion angeben möchten, übergeben Sie eine `null` Wert als Parameter für die <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Methode.  
  
 [!code-csharp[HitTestingOverview#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#105)]
 [!code-vb[HitTestingOverview#105](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#105)]  
  
 ![Verzweigen einer visuellen Struktur mit einem Treffertestfilter](../../../../docs/framework/wpf/graphics-multimedia/media/filteredvisualtree-01.png "FilteredVisualTree_01")  
Reduzieren der Verzweigungen in einer visuellen Struktur  
  
 Mit der Treffertestfilter-Rückruffunktion können Sie alle visuellen Objekte auflisten, deren gerenderte Inhalte die von Ihnen angegebenen Koordinaten enthalten. Sie können jedoch auch bestimmte Verzweigungen der visuellen Struktur ignorieren, die im Rahmen Ihrer Treffertestergebnis-Rückruffunktion nicht verarbeitet werden sollen. Der Rückgabewert der Treffertestfilter-Rückruffunktion bestimmt, welcher Typ von Aktion von der Enumeration der visuellen Objekte ausgeführt werden soll. Angenommen, wenn der Rückgabewert <xref:System.Windows.Media.HitTestFilterBehavior.ContinueSkipSelfAndChildren>, können Sie das aktuelle visuelle Objekt und seine untergeordneten Elemente aus der Enumeration der Treffertest Ergebnisse löschen. Dies bedeutet, dass für die Treffertestergebnis-Rückruffunktion diese Objekte nicht in der Auflistung enthalten sind. Durch das Reduzieren der Verzweigungen in der visuellen Struktur von Objekten wird der Verarbeitungsaufwand während der Übergabe der Auflistung von Treffertestergebnissen verringert. Im folgenden Codebeispiel überspringt der Filter Bezeichnungen und ihre Nachfolgerelemente und führt für alle anderen Elemente Treffertests durch.  
  
 [!code-csharp[HitTestingOverview#106](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#106)]
 [!code-vb[HitTestingOverview#106](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#106)]  
  
> [!NOTE]
>  Der Treffertestfilter-Rückruf wird gelegentlich aufgerufen, wenn der Treffertestergebnis-Rückruf nicht aufgerufen wird.  
  
<a name="overriding_default_hit_testing"></a>   
## <a name="overriding-default-hit-testing"></a>Überschreiben des Standardtreffertests  
 Sie können ein visuelles Objekt standardmäßig Treffertests bei Unterstützung durch Außerkraftsetzen überschreiben die <xref:System.Windows.Media.Visual.HitTestCore%2A> Methode. Dies bedeutet, dass beim Aufrufen der <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> -Methode, die überschriebene Implementierung von <xref:System.Windows.Media.Visual.HitTestCore%2A> aufgerufen wird. Ihre überschriebene Methode wird aufgerufen, wenn sich ein Treffertest innerhalb des umgebenden Rechtecks für das visuelle Objekt befindet. Dies gilt auch dann, wenn die Koordinate außerhalb des gerenderten Inhalts des visuellen Objekts liegt.  
  
 [!code-csharp[HitTestingOverview#107](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#107)]
 [!code-vb[HitTestingOverview#107](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#107)]  
  
 Es kann vorkommen, dass Sie einen Treffertest sowohl für das umschließende Rechteck als auch für den gerenderten Inhalt eines visuellen Objekts durchführen möchten. Mithilfe der `PointHitTestParameters` Parameterwert in der überschriebenen <xref:System.Windows.Media.Visual.HitTestCore%2A> Methode als Parameter an die Basismethode <xref:System.Windows.Media.Visual.HitTestCore%2A>, können Sie Aktionen basierend auf einem Treffer des umschließenden Rechtecks für ein visuelles Objekt und führen Sie dann einen zweite Treffertest für das gerendert Inhalt des visuellen Objekts.  
  
 [!code-csharp[HitTestingOverview#108](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#108)]
 [!code-vb[HitTestingOverview#108](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#108)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>  
 <xref:System.Windows.Media.HitTestResult>  
 <xref:System.Windows.Media.HitTestResultCallback>  
 <xref:System.Windows.Media.HitTestFilterCallback>  
 <xref:System.Windows.UIElement.IsHitTestVisible%2A>  
 [Treffertests mit DrawingVisuals-Beispiel](http://go.microsoft.com/fwlink/?LinkID=159994)  
 [Treffertests mit Interoperation Win32-Beispiel](http://go.microsoft.com/fwlink/?LinkID=159995)  
 [Vorgehensweise: Treffertest für eine Geometrie in einem visuellen Objekt](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-geometry-in-a-visual.md)  
 [Treffertest mithilfe eines Win32-Hostcontainers](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-using-a-win32-host-container.md)
