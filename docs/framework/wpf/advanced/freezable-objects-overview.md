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
ms.openlocfilehash: 79c539bd0117c712670601b7498c490fca76090e
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610518"
---
# <a name="freezable-objects-overview"></a>Übersicht über Freezable-Objekte
In diesem Thema wird beschrieben, wie effektiv verwenden und erstellen Sie <xref:System.Windows.Freezable> -Objekte, die spezielle Funktionen bereitstellen, die Leistung der Anwendung verbessern können. Beispiele für freezable-Objekte sind Pinsel, Stifte, Transformationen, Geometrien und Animationen.  
  
<a name="whatisafreezable"></a>   
## <a name="what-is-a-freezable"></a>Was ist ein Freezable-Objekt?  
 Ein <xref:System.Windows.Freezable> ist ein spezieller Typ des Objekts, das zwei Status: nicht fixiert und fixiert. Wenn nicht fixiert ist, eine <xref:System.Windows.Freezable> angezeigt wie jedes andere Objekt verhält. Wenn fixiert, eine <xref:System.Windows.Freezable> können nicht mehr geändert werden.  
  
 Ein <xref:System.Windows.Freezable> bietet eine <xref:System.Windows.Freezable.Changed> Ereignis, um den Beobachter über Änderungen an das Objekt zu benachrichtigen. Sperren einer <xref:System.Windows.Freezable> kann dessen Leistung verbessern, da sie nicht mehr zum Ausgeben von Ressourcen für änderungsbenachrichtigungen muss. Ein fixiertes <xref:System.Windows.Freezable> kann auch übergreifend für Threads, während eine nicht fixierte <xref:System.Windows.Freezable> nicht möglich.  
  
 Obwohl die <xref:System.Windows.Freezable> -Klasse verfügt über viele Anwendungen, die meisten <xref:System.Windows.Freezable> Objekte im [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] beziehen sich auf das untergeordnete Grafiksystem.  
  
 Die <xref:System.Windows.Freezable> Klasse erleichtert es, bestimmte Systemobjekte Grafiken zu verwenden und die Anwendungsleistung verbessern können. Beispiele für Typen, die von erben <xref:System.Windows.Freezable> enthalten die <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>, und <xref:System.Windows.Media.Geometry> Klassen. Da sie nicht verwaltete Ressourcen enthalten, muss das System diese Objekte für die Änderungen zu überwachen und aktualisieren Sie dann ihre entsprechenden nicht verwalteten Ressourcen aus, wenn es eine Änderung auf das ursprüngliche Objekt. Auch wenn Sie ein Grafikobjekt für das System tatsächlich nicht ändern können, muss das System dennoch einige ihrer Ressourcen, die Überwachung des Objekts, sorgfältig Bedenken für den Fall, dass Sie es ändern.  
  
 Nehmen wir beispielsweise an, die Sie erstellen eine <xref:System.Windows.Media.SolidColorBrush> Pinsel aus, und verwenden, um den Hintergrund einer Schaltfläche zu zeichnen.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]  
  
 Wenn die Schaltfläche mit der gerendert wird, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] untergeordnete-Grafiksystem verwendet die Informationen, die Sie angegeben haben, um eine Gruppe von Pixel, um die Darstellung einer Schaltfläche erstellen zu zeichnen. Obwohl Sie einen Pinsel mit Volltonfarbe verwendet, um beschreiben, wie die Schaltfläche gezeichnet werden soll, nicht Ihre Pinsel mit Volltonfarbe tatsächlich gezeichnet werden soll. Das Grafiksystem generiert schnelle, Low-Level-Objekte für die Schaltfläche und der Pinsel, und die Objekte, die tatsächlich auf dem Bildschirm angezeigt werden kann.  
  
 Würden Sie den Pinsel ändern, müssten die Low-Level-Objekte erneut generiert werden. Die freezable-Klasse ist, was einem Pinsel bietet die Möglichkeit, die entsprechenden generierten, Low-Level-Objekten zu suchen und diese aktualisieren, wenn sich diese ändern. Wenn diese Funktion aktiviert ist, gilt der Pinsel als "nicht fixierten."  
  
 Eine Freezable Objekts <xref:System.Windows.Freezable.Freeze%2A> Methode können Sie diese selbstaktualisierung Fähigkeit zu deaktivieren. Sie können diese Methode verwenden, um den Pinsel zu "fixierte", oder als nicht änderbar fest.  
  
> [!NOTE]
>  Nicht jede Freezable-Objekts kann fixiert werden. Auslösen von vermeiden einer <xref:System.InvalidOperationException>, überprüfen Sie den Wert von Freezable-Objekts <xref:System.Windows.Freezable.CanFreeze%2A> Eigenschaft, um zu bestimmen, ob sie eingefroren werden kann, bevor Sie versuchen, ihn einfrieren.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]  
  
 Wenn Sie nicht mehr einem Freezable-Objekt ändern müssen, bietet das Fixieren Leistungsvorteile. Würden Sie den Pinsel in diesem Beispiel zu fixieren, würde das Grafiksystem nicht mehr benötigen, um diese Änderungen zu überwachen. Das Grafiksystem kann auch andere Optimierungen vornehmen, da er weiß, dass der Pinsel nicht ändern.  
  
> [!NOTE]
>  Der Einfachheit halber bleiben freezable-Objekte nicht fixierten, es sei denn, Sie explizit fixieren.  
  
<a name="frozenfreezables"></a>   
## <a name="using-freezables"></a>Verwenden von Freezable-Objekte  
 Verwenden eine nicht fixierte ist wie jede andere Art von Objekt Freezable-Objekts. Im folgenden Beispiel die Farbe des eine <xref:System.Windows.Media.SolidColorBrush> von Gelb zu Rot geändert wird, nach der Verwendung den Hintergrund einer Schaltfläche gezeichnet. Das Grafiksystem arbeitet im Hintergrund automatisch die Schaltfläche mit den von Gelb zu rot der nächsten Anmeldung ändern, wenn der Bildschirm aktualisiert wird.  
  
 [!code-csharp[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
 [!code-vb[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]  
  
### <a name="freezing-a-freezable"></a>Das Fixieren eines Freezable-Objekts  
 Zu einem <xref:System.Windows.Freezable> nicht änderbar ist, rufen Sie die <xref:System.Windows.Freezable.Freeze%2A> Methode. Wenn Sie ein Objekt, die von freezable-Objekte enthält fixieren, werden diese Objekte auch fixiert. Angenommen, Sie Einfrieren eine <xref:System.Windows.Media.PathGeometry>, die Abbildungen und Segmente, die es enthält würde zu fixiert werden.  
  
 Eine Freezable **kann nicht** fixiert werden, wenn eine der folgenden Bedingungen zutrifft:  
  
- Es verfügt über animierte oder datengebundene Eigenschaften.  
  
- Er verfügt über Eigenschaften, die von einer dynamischen Ressource festgelegt. (Finden Sie unter den [XAML-Ressourcen](xaml-resources.md) für Weitere Informationen zu dynamischen Ressourcen.)  
  
- Es enthält <xref:System.Windows.Freezable> untergeordnete Objekte, die nicht fixiert werden können.  
  
 Wenn diese Bedingungen "false sind", und Sie nicht beabsichtigen, ändern Sie die <xref:System.Windows.Freezable>, und Sie darauf, um die Leistungsvorteile, die zuvor beschriebenen erhalten fixieren sollten.  
  
 Wenn Sie eine Freezable Objekts aufrufen <xref:System.Windows.Freezable.Freeze%2A> -Methode kann nicht mehr geändert werden. Versucht, ein fixiertes Objekt bewirkt, dass ein <xref:System.InvalidOperationException> ausgelöst wird. Der folgende Code eine Ausnahme auslöst, da wir versuchen, den Pinsel ändern, nachdem es eingefroren ist.  
  
 [!code-csharp[freezablesample_procedural#ExceptionExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
 [!code-vb[freezablesample_procedural#ExceptionExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]  
  
 Um zu vermeiden, diese Ausnahme auslöst, können Sie die <xref:System.Windows.Freezable.IsFrozen%2A> Methode, um zu bestimmen, ob eine <xref:System.Windows.Freezable> eingefroren ist.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 Im vorherigen Codebeispiel, erfolgte eine änderbare Kopie eines fixierten Objekts mit der <xref:System.Windows.Freezable.Clone%2A> Methode. Im nächste Abschnitt noch ausführlicher Informationen zum Klonen.  
  
 **Hinweis** da einen fixierten Freezable-Objekt kann nicht animiert werden kann, das Animationssystem erstellt automatisch änderbare Klone von fixierten <xref:System.Windows.Freezable> Objekte, wenn Sie versuchen, die sie animieren eine <xref:System.Windows.Media.Animation.Storyboard>. Um die Leistung Mehraufwand durch Klonen verursachte auszuschließen, lassen Sie ein Objekt, das nicht fixiert ist, wenn Sie beabsichtigen, die sie animieren. Weitere Informationen über das Animieren mit Storyboards finden Sie unter den [Übersicht über Storyboards](../graphics-multimedia/storyboards-overview.md).  
  
### <a name="freezing-from-markup"></a>Einfrieren von Markup  
 So fixieren Sie einen <xref:System.Windows.Freezable> Objekt deklariert im Markup, das Sie verwenden die `PresentationOptions:Freeze` Attribut. Im folgenden Beispiel eine <xref:System.Windows.Media.SolidColorBrush> als Seitenressource deklariert und fixiert ist. Es wird dann verwendet, um den Hintergrund einer Schaltfläche festzulegen.  
  
 [!code-xaml[FreezableSample#FreezeFromMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]  
  
 Verwenden der `Freeze` -Attribut, müssen Sie auf den Namespace der Präsentation Optionen zuordnen: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`. `PresentationOptions` ist das empfohlene Präfix für die Zuordnung von diesem Namespace:  
  
```  
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"   
```  
  
 Da nicht alle XAML-Leser dieses Attribut erkannt wird, wird empfohlen, dass Sie verwenden die [Mc: Ignorable-Attribut](mc-ignorable-attribute.md) markieren die `Presentation:Freeze` als ignorierbar Attribut:  
  
```  
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
mc:Ignorable="PresentationOptions"  
```  
  
 Weitere Informationen finden Sie unter den [Mc: Ignorable-Attribut](mc-ignorable-attribute.md) Seite.  
  
### <a name="unfreezing-a-freezable"></a>"Aufheben der Fixierung von" einem Freezable-Objekt  
 Einmal fixiert ist, eine <xref:System.Windows.Freezable> können nicht geändert und nicht fixiert ist; Sie können jedoch mit einen nicht fixierten Klon erstellen die <xref:System.Windows.Freezable.Clone%2A> oder <xref:System.Windows.Freezable.CloneCurrentValue%2A> Methode.  
  
 Im folgenden Beispiel des Hintergrunds der Schaltfläche mit einem Pinsel festgelegt ist, und klicken Sie dann den Pinsel eingefroren ist. Eine nicht fixierte Kopie des Pinsels mit erfolgt die <xref:System.Windows.Freezable.Clone%2A> Methode. Der Klon wird geändert und verwendet, um den Hintergrund der Schaltfläche von Gelb zu Rot zu ändern.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
> [!NOTE]
>  Unabhängig davon, welche Clone-Methode, die Sie verwenden, Animationen nie in die neue kopiert werden <xref:System.Windows.Freezable>.  
  
 Die <xref:System.Windows.Freezable.Clone%2A> und <xref:System.Windows.Freezable.CloneCurrentValue%2A> Methoden erzeugt tiefe Kopien von Freezable-Objekts. Freezable-Objekts Weitere fixierte freezable-Objekte enthält, werden sie auch geklont und änderbaren vorgenommen werden soll. Wenn Sie ein fixiertes klonen, z. B. <xref:System.Windows.Media.PathGeometry> damit geändert werden können, die Abbildungen und Segmente, die es enthält auch kopiert und geändert werden vorgenommen.  
  
<a name="createyourownfreezableclass"></a>   
## <a name="creating-your-own-freezable-class"></a>Erstellen einer eigenen Freezable-Klasse  
 Eine abgeleitete Klasse <xref:System.Windows.Freezable> erhält die folgenden Features.  
  
- Besondere Zustände: eine schreibgeschützt (fixiert) und einen beschreibbaren Status.  
  
- Threadsicherheit: ein fixiertes <xref:System.Windows.Freezable> über Threads freigegeben werden können.  
  
- Detaillierte änderungsbenachrichtigung: Im Gegensatz zu anderen <xref:System.Windows.DependencyObject>s, angeben Freezable-Objekte von änderungsbenachrichtigungen an, wenn untergeordnete Eigenschaftswerte ändern.  
  
- Klonen einfach: die Freezable-Klasse verfügt über mehrere Methoden, die tiefe Klone erstellen bereits implementiert.  
  
 Ein <xref:System.Windows.Freezable> ist eine Art von <xref:System.Windows.DependencyObject>, und daher verwendet das Abhängigkeitseigenschaftensystem. Ihre Klasseneigenschaften müssen Abhängigkeitseigenschaften sein, aber die Verwendung von Abhängigkeitseigenschaften reduziert die Menge des Codes, die Sie schreiben da, müssen die <xref:System.Windows.Freezable> Klasse wurde entwickelt, mit Abhängigkeitseigenschaften Bedenken. Weitere Informationen zu das Abhängigkeitseigenschaftensystem, finden Sie unter den [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md).  
  
 Jede <xref:System.Windows.Freezable> Unterklasse überschreiben, muss die <xref:System.Windows.Freezable.CreateInstanceCore%2A> Methode. Wenn Ihre Klasse Abhängigkeitseigenschaften für alle ihre Daten verwendet werden, sind Sie fertig.  
  
 Wenn Ihre Klasse ohne Abhängigkeitseigenschaft-Datenmember enthält, müssen Sie auch die folgenden Methoden überschreiben:  
  
- <xref:System.Windows.Freezable.CloneCore%2A>  
  
- <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>  
  
- <xref:System.Windows.Freezable.GetAsFrozenCore%2A>  
  
- <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>  
  
- <xref:System.Windows.Freezable.FreezeCore%2A>  
  
 Sie müssen auch beachten, dass für den Zugriff auf und Schreiben von Datenmembern, die keine Abhängigkeitseigenschaften sind die folgenden Regeln:  
  
- Am Anfang jeder [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] , ohne Abhängigkeitseigenschaft die Datenmember liest, rufen Sie die <xref:System.Windows.Freezable.ReadPreamble%2A> Methode.  
  
- Rufen Sie am Anfang jeder API, die nicht als Abhängigkeitseigenschaft Datenmember schreibt, die <xref:System.Windows.Freezable.WritePreamble%2A> Methode. (Nachdem Sie aufgerufen haben <xref:System.Windows.Freezable.WritePreamble%2A> in einer API müssen Sie keine stellen einen zusätzlichen Aufruf <xref:System.Windows.Freezable.ReadPreamble%2A> , wenn Sie auch ohne Abhängigkeiten eigenschaftsdatenmember lesen.)  
  
- Rufen Sie die <xref:System.Windows.Freezable.WritePostscript%2A> Methode vor dem Beenden der Methoden, die auf nicht-Abhängigkeitseigenschaft Datenmember zu schreiben.  
  
 Wenn Ihre Klasse nicht Abhängigkeitseigenschaften Datenelemente enthält, sind <xref:System.Windows.DependencyObject> Objekte, Sie müssen auch aufrufen, die <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> Methode jedes Mal, die Sie die Werte, ändern auch wenn Sie das Element festlegen können, auf `null`.  
  
> [!NOTE]
>  Es ist sehr wichtig, dass Sie jede nun <xref:System.Windows.Freezable> Methode, die Sie durch einen Aufruf der basisimplementierung überschreiben.  
  
 Ein Beispiel für eine benutzerdefinierte <xref:System.Windows.Freezable> Klasse, finden Sie unter den [Beispiel für die benutzerdefinierte Animation](https://go.microsoft.com/fwlink/?LinkID=159981).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Freezable>
- [Benutzerdefiniertes Animationsbeispiel](https://go.microsoft.com/fwlink/?LinkID=159981)
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
