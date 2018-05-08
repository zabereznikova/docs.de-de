---
title: Übersicht über Freezable-Objekte
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], description
- unfreezing Freezable objects [WPF]
- classes [WPF], Freezable
ms.assetid: 89c71692-4f43-4057-b611-67c6a8a863a2
ms.openlocfilehash: d3b9f6f7af22b2a846f4ee34e8d4d00bb032fd69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="freezable-objects-overview"></a>Übersicht über Freezable-Objekte
In diesem Thema wird beschrieben, wie effektiv verwenden und erstellen <xref:System.Windows.Freezable> Objekte, die spezielle Funktionen bereitstellen, die Leistung der Anwendung verbessern können. Beispiele für freezable-Objekte sind Pinsel, Stifte, Transformationen, Geometrien und Animationen.  
  
<a name="whatisafreezable"></a>   
## <a name="what-is-a-freezable"></a>Was ist ein Freezable?  
 Ein <xref:System.Windows.Freezable> ist eine besondere Art von Objekt, das zwei Zustände verfügt: nicht fixiert und fixiert. Wenn nicht fixiert ist, eine <xref:System.Windows.Freezable> angezeigt wird, verhält sich wie ein anderes Objekt. Wenn fixiert, eine <xref:System.Windows.Freezable> kann nicht mehr geändert werden.  
  
 Ein <xref:System.Windows.Freezable> bietet eine <xref:System.Windows.Freezable.Changed> Ereignis, um den Beobachter über alle Änderungen auf das Objekt zu benachrichtigen. Das Fixieren von einem <xref:System.Windows.Freezable> kann die Leistung verbessern, da er nicht mehr benötigt, Ressourcen für änderungsbenachrichtigungen ausgeben. Ein fixiertes <xref:System.Windows.Freezable> können ebenfalls freigegeben werden, während eine nicht fixierte threadübergreifend <xref:System.Windows.Freezable> nicht möglich.  
  
 Obwohl die <xref:System.Windows.Freezable> Klasse hat zahlreiche Anwendungsmöglichkeiten, die meisten <xref:System.Windows.Freezable> Objekte im [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] beziehen sich auf das Teilsystem Grafiken.  
  
 Die <xref:System.Windows.Freezable> Klasse erleichtert es, bestimmte Systemobjekte Grafiken verwenden und die Anwendungsleistung verbessern können. Beispiele für Typen, die von erben <xref:System.Windows.Freezable> enthalten die <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>, und <xref:System.Windows.Media.Geometry> Klassen. Da sie nicht verwaltete Ressourcen enthalten, muss das System diese Objekte für die Änderungen überwachen und aktualisieren Sie dann ihre entsprechenden nicht verwalteten Ressourcen aus, wenn eine Änderung auf das ursprüngliche Objekt. Auch wenn Sie ein Grafikobjekt-System tatsächlich nicht ändern können, muss das System noch einige seiner Ressourcen, die Überwachung des Objekts verbringen für den Fall, dass Sie es ändern.  
  
 Nehmen wir beispielsweise an, die Sie erstellen eine <xref:System.Windows.Media.SolidColorBrush> Pinsel und verwenden, um den Hintergrund einer Schaltfläche zu zeichnen.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]  
  
 Wenn die Schaltfläche gerendert wird, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Graphics-Teilsystem verwendet die Informationen, die Sie bereitgestellt haben, um eine Gruppe von Pixel, erstellen Sie die Darstellung einer Schaltfläche zu zeichnen. Obwohl einen Pinsel mit Volltonfarbe verwenden, die beschreiben, wie die Schaltfläche gezeichnet werden soll, nicht Ihre Pinsel mit Volltonfarbe tatsächlich gezeichnet werden soll. Grafiksystem generiert schnelle, Low-Level-Objekte für die Schaltfläche und die Pinsel und jene Objekte, die tatsächlich auf dem Bildschirm angezeigt werden kann.  
  
 Würden Sie den Pinsel ändern möchten, müssten diese Objekte auf niedriger Ebene erneut generiert werden. Die freezable-Klasse ist, was einem Pinsel bietet die Möglichkeit, ihre entsprechenden generierten, Low-Level-Objekten zu suchen und diese aktualisieren, wenn sich ändert. Wenn diese Funktion aktiviert ist, gilt der Pinsel, der als "aufgetaut".  
  
 Eine freezable des <xref:System.Windows.Freezable.Freeze%2A> Methode ermöglicht es Ihnen, diese selbstaktualisierung Fähigkeit zu deaktivieren. Sie können diese Methode verwenden, um den Pinsel zu "fixierte", oder als nicht änderbar fest.  
  
> [!NOTE]
>  Nicht jedes Objekt Freezable kann fixiert werden. Zur Vermeidung Auslösen einer <xref:System.InvalidOperationException>, überprüfen Sie den Wert des Freezable-Objekts <xref:System.Windows.Freezable.CanFreeze%2A> Eigenschaft, um zu bestimmen, ob er fixiert werden kann, bevor Sie versuchen, die sie fixieren.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]  
  
 Wenn Sie nicht mehr eine freezable ändern müssen, bietet das Fixieren Leistungsvorteile. Würden Sie den Pinsel in diesem Beispiel zu fixieren, müssten die Grafiksystem nicht mehr für die Änderungen zu überwachen. Grafiksystem kann auch andere Optimierungen vornehmen, da er weiß, dass der Pinsel nicht ändert.  
  
> [!NOTE]
>  Der Einfachheit halber bleiben freezable-Objekte nicht fixierten, es sei denn, Sie explizit fixieren.  
  
<a name="frozenfreezables"></a>   
## <a name="using-freezables"></a>Verwenden von Freezable-Objekte  
 Verwenden eine nicht fixierte ist wie die Verwendung eines Objekts eines anderen Typs freezable. Im folgenden Beispiel wird die Farbe des eine <xref:System.Windows.Media.SolidColorBrush> von Gelb zu Rot geändert wird, nachdem er verwendet wird, um den Hintergrund einer Schaltfläche zu zeichnen. Die Grafiksystem funktioniert im Hintergrund automatisch die Schaltfläche von Gelb zu rot das nächste Mal geändert, wenn, das der Bildschirm aktualisiert wird.  
  
 [!code-csharp[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
 [!code-vb[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]  
  
### <a name="freezing-a-freezable"></a>Das Fixieren von einem Freezable  
 Vornehmen einer <xref:System.Windows.Freezable> nicht änderbar ist, rufen Sie die <xref:System.Windows.Freezable.Freeze%2A> Methode. Fixieren Sie ein Objekt, das freezable-Objekte enthält, werden diese Objekte ebenfalls fixiert. Angenommen, Sie Einfrieren eine <xref:System.Windows.Media.PathGeometry>, die Abbildungen und Segmente, die es enthält würde zu fixiert werden.  
  
 Eine Freezable **kann nicht** fixiert werden, wenn keines der folgenden erfüllt sind:  
  
-   Es verfügt über animierte oder datengebundene Eigenschaften.  
  
-   Sie verfügt über Eigenschaften, die von einer dynamischen Ressource festgelegt. (Finden Sie unter der [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md) für Weitere Informationen zu dynamischen Ressourcen.)  
  
-   Er enthält <xref:System.Windows.Freezable> untergeordnete Objekte, die nicht fixiert werden können.  
  
 Wenn diese Bedingungen "false sind", und Sie nicht beabsichtigen, ändern Sie die <xref:System.Windows.Freezable>, und Sie darauf, um die Leistungsvorteile, die zuvor beschriebenen erhalten fixieren sollten.  
  
 Nachdem Sie eine Freezable Objekts aufrufen <xref:System.Windows.Freezable.Freeze%2A> -Methode kann nicht mehr geändert werden. Bei dem Versuch, ein fixierter ändern-Objekt Ursachen eine <xref:System.InvalidOperationException> ausgelöst wird. Der folgende Code eine Ausnahme auslöst, weil wir versuchen, den Pinsel zu ändern, nachdem es eingefroren ist.  
  
 [!code-csharp[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
 [!code-vb[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]  
  
 Um zu vermeiden, diese Ausnahme auslösen, können Sie die <xref:System.Windows.Freezable.IsFrozen%2A> Methode, um zu bestimmen, ob eine <xref:System.Windows.Freezable> eingefroren ist.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 Im vorherigen Codebeispiel wurde versucht eine änderbare Kopie einer fixierten Objekt mit der <xref:System.Windows.Freezable.Clone%2A> Methode. Im nächste Abschnitt erläutert ausführlich das Klonen.  
  
 **Hinweis** da ein fixiertes freezable nicht animiert werden kann, erstellt das Animationssystem automatisch änderbare Klone von fixierten <xref:System.Windows.Freezable> Objekte, wenn Sie versuchen, die sie mit dem animiert werden soll eine <xref:System.Windows.Media.Animation.Storyboard>. Um die Leistung durch das Klonen Mehraufwand verursacht zu vermeiden, lassen Sie ein Objekt, das nicht fixiert ist, wenn Sie beabsichtigen, die es dem animiert werden soll. Weitere Informationen über Animationen mit Storyboards finden Sie unter der [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
### <a name="freezing-from-markup"></a>Einfrieren von Markup  
 So fixieren Sie einen <xref:System.Windows.Freezable> Objekt im Markup deklariert wurde, verwenden Sie die `PresentationOptions:Freeze` Attribut. Im folgenden Beispiel eine <xref:System.Windows.Media.SolidColorBrush> als Seitenressource deklariert und fixiert. Es wird dann verwendet, um den Hintergrund einer Schaltfläche festzulegen.  
  
 [!code-xaml[FreezableSample#FreezeFromMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]  
  
 Verwenden der `Freeze` -Attribut, müssen Sie auf den Namespace der Präsentation Optionen zuordnen: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`. `PresentationOptions` ist die empfohlene Präfix für die Zuordnung dieses Namespaces.  
  
```  
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"   
```  
  
 Da nicht alle XAML-Readern dieses Attribut nicht erkennen, wird empfohlen, die Sie verwenden die [Mc: Ignorierbares Attribut](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) zum Kennzeichnen der `Presentation:Freeze` ignorierbares Attribut:  
  
```  
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
mc:Ignorable="PresentationOptions"  
```  
  
 Weitere Informationen finden Sie unter der [Mc: Ignorierbares Attribut](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) Seite.  
  
### <a name="unfreezing-a-freezable"></a>"Fixierung" eine Freezable  
 Einmal fixiert, eine <xref:System.Windows.Freezable> nie geändert oder aufgetaut; Sie können jedoch mit einen nicht fixierten Klon erstellen die <xref:System.Windows.Freezable.Clone%2A> oder <xref:System.Windows.Freezable.CloneCurrentValue%2A> Methode.  
  
 Im folgenden Beispiel Hintergrund der Schaltfläche mit einem Pinsel festgelegt ist, und klicken Sie dann den Pinsel eingefroren ist. Eine nicht fixierte Kopie des Pinsels mithilfe der <xref:System.Windows.Freezable.Clone%2A> Methode. Der Klon wird geändert und verwendet, um den Hintergrund der Schaltfläche von Gelb zu Rot zu ändern.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
> [!NOTE]
>  Unabhängig davon, welche Clone-Methode, die Sie verwenden, Animationen nie in die neue kopiert werden <xref:System.Windows.Freezable>.  
  
 Die <xref:System.Windows.Freezable.Clone%2A> und <xref:System.Windows.Freezable.CloneCurrentValue%2A> Methoden erzeugen tiefe Kopien des Freezable-Objekts. Wenn die freezable Weitere fixierte freezable-Objekte enthält, sind sie auch geklont und änderbaren vorgenommen. Wenn Sie ein fixierter Klonen z. B. <xref:System.Windows.Media.PathGeometry> zum verändern zu können, die Abbildungen und Segmente, die es enthält auch kopiert und änderbare vorgenommen.  
  
<a name="createyourownfreezableclass"></a>   
## <a name="creating-your-own-freezable-class"></a>Erstellen eine eigene Freezable-Klasse  
 Eine Klasse, die abgeleitet <xref:System.Windows.Freezable> erhält die folgenden Features.  
  
-   Besondere Zustände: ein schreibgeschützter (fixiert) und einen beschreibbaren Status.  
  
-   Threadsicherheit: ein fixierter <xref:System.Windows.Freezable> über Threads freigegeben werden können.  
  
-   Detaillierte änderungsbenachrichtigung: im Gegensatz zu anderen <xref:System.Windows.DependencyObject>s, bieten Freezable-Objekte änderungsbenachrichtigungen an, wenn untergeordnete Eigenschaftswerte zu verändern.  
  
-   Einfache Klonen: Freezable-Klasse verfügt über mehrere Methoden, die tiefe Klone erstellen bereits implementiert.  
  
 Ein <xref:System.Windows.Freezable> ist eine Art von <xref:System.Windows.DependencyObject>, und verwendet daher Abhängigkeitseigenschaftensystem. Die Klasseneigenschaften müssen keine Abhängigkeitseigenschaften sein, aber mithilfe von Abhängigkeitseigenschaften reduziert die Menge an Code, die Sie schreiben, da müssen die <xref:System.Windows.Freezable> Klasse mit Abhängigkeitseigenschaften Bedenken entwickelt wurde. Weitere Informationen zu Abhängigkeitseigenschaftensystem, finden Sie unter der [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
 Jede <xref:System.Windows.Freezable> Unterklasse überschreiben, muss die <xref:System.Windows.Freezable.CreateInstanceCore%2A> Methode. Wenn Ihre Klasse Abhängigkeitseigenschaften für alle ihre Daten verwendet werden, sind Sie nicht mehr benötigen.  
  
 Wenn Ihre Klasse nicht Abhängigkeitseigenschaft-Datenmember enthält, müssen Sie auch die folgenden Methoden überschreiben:  
  
-   <xref:System.Windows.Freezable.CloneCore%2A>  
  
-   <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>  
  
-   <xref:System.Windows.Freezable.GetAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.FreezeCore%2A>  
  
 Sie müssen auch beachten, dass für den Zugriff auf und Schreiben in Datenmember, die nicht Abhängigkeitseigenschaften sind die folgenden Regeln:  
  
-   Am Anfang eines beliebigen [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] , ohne Abhängigkeiten Eigenschaftenmember Daten liest, rufen Sie die <xref:System.Windows.Freezable.ReadPreamble%2A> Methode.  
  
-   Rufen Sie am Anfang jeder API, die nicht Abhängigkeitseigenschaft Datenmember schreibt die <xref:System.Windows.Freezable.WritePreamble%2A> Methode. (Sobald Sie aufgerufen haben <xref:System.Windows.Freezable.WritePreamble%2A> in einer [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)], Sie müssen einen zusätzlichen Aufruf stellen <xref:System.Windows.Freezable.ReadPreamble%2A> , wenn Sie auch ohne Abhängigkeiten eigenschaftsdatenmember lesen.)  
  
-   Rufen Sie die <xref:System.Windows.Freezable.WritePostscript%2A> -Methode vor dem Beenden von Methoden, die in nicht Abhängigkeitseigenschaft Datenmember schreiben.  
  
 Wenn Ihre Klasse nicht Abhängigkeitseigenschaft Datenmember enthält, sind <xref:System.Windows.DependencyObject> Objekte aufweist, müssen Sie auch Aufrufen der <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> Methode bei jeder Änderung auf Verhältnis der Werte, auch wenn Sie auf das Element festlegen `null`.  
  
> [!NOTE]
>  Es ist sehr wichtig, dass Sie jede beginnen <xref:System.Windows.Freezable> Methode, die Sie außer Kraft, durch die basisimplementierung aufrufen setzen.  
  
 Ein Beispiel eines benutzerdefinierten <xref:System.Windows.Freezable> Klasse, finden Sie unter der [benutzerdefinierten Animation Sample](http://go.microsoft.com/fwlink/?LinkID=159981).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Freezable>  
 [Benutzerdefiniertes Animationsbeispiel](http://go.microsoft.com/fwlink/?LinkID=159981)  
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
