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
ms.openlocfilehash: 05cd3c27430146f575c23011f53995aa07aaf99e
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991495"
---
# <a name="freezable-objects-overview"></a>Übersicht über Freezable-Objekte

In diesem Thema wird beschrieben, wie Sie- <xref:System.Windows.Freezable> Objekte effektiv verwenden und erstellen können, die spezielle Funktionen zur Verbesserung der Anwendungsleistung bereitstellen. Beispiele für frei wählbare Objekte sind Pinsel, Stifte, Transformationen, Geometrien und Animationen.

<a name="whatisafreezable"></a>

## <a name="what-is-a-freezable"></a>Was ist ein frei wählbarer?

Ein <xref:System.Windows.Freezable> ist ein spezieller Objekttyp, der zwei Zustände aufweist: nicht fixiert und fixiert. Wenn das Objekt nicht fixiert <xref:System.Windows.Freezable> ist, verhält sich wie ein beliebiges anderes Objekt. Wenn Sie eingefroren ist <xref:System.Windows.Freezable> , kann eine nicht mehr geändert werden.

Ein <xref:System.Windows.Freezable> stellt ein <xref:System.Windows.Freezable.Changed> -Ereignis bereit, um Beobachter über Änderungen am-Objekt zu benachrichtigen. Das Einfrieren <xref:System.Windows.Freezable> einer kann die Leistung verbessern, da Sie keine Ressourcen mehr für Änderungs Benachrichtigungen aufwenden muss. Ein fixierter kann auch Thread übergreifend freigegeben werden, während ein nicht fixiertist.<xref:System.Windows.Freezable> <xref:System.Windows.Freezable>

Obwohl die <xref:System.Windows.Freezable> -Klasse über viele Anwendungen verfügt <xref:System.Windows.Freezable> , sind [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] die meisten Objekte in mit dem Grafik-unter System verknüpft.

Die <xref:System.Windows.Freezable> -Klasse vereinfacht die Verwendung bestimmter Grafiksystem Objekte und kann dabei helfen, die Anwendungsleistung zu verbessern. Beispiele für Typen, die von <xref:System.Windows.Freezable> erben, <xref:System.Windows.Media.Brush>sind <xref:System.Windows.Media.Transform>die Klassen <xref:System.Windows.Media.Geometry> , und. Da Sie nicht verwaltete Ressourcen enthalten, muss das System diese Objekte auf Änderungen überwachen und dann die entsprechenden nicht verwalteten Ressourcen aktualisieren, wenn Änderungen am ursprünglichen Objekt vorgenommen werden. Selbst wenn Sie ein Grafiksystem Objekt nicht tatsächlich ändern, muss das System trotzdem einige Ressourcen für die Überwachung des Objekts aufwenden, falls Sie es ändern.

Nehmen Sie beispielsweise an, Sie <xref:System.Windows.Media.SolidColorBrush> erstellen einen Pinsel und verwenden ihn, um den Hintergrund einer Schaltfläche zu zeichnen.

[!code-csharp[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
[!code-vb[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]

Wenn die Schaltfläche gerendert [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird, verwendet das Grafik Subsystem die Informationen, die Sie angegeben haben, um eine Gruppe von Pixeln zu zeichnen, um die Darstellung einer Schaltfläche zu erstellen. Obwohl Sie einen Pinsel mit voll Tonfarbe verwendet haben, um zu beschreiben, wie die Schaltfläche gezeichnet werden soll, führt der Pinsel mit voll Tonfarbe das Zeichnen nicht aus. Das Grafiksystem generiert schnelle, Low-Level-Objekte für die Schaltfläche und den Pinsel, und es handelt sich um die Objekte, die auf dem Bildschirm tatsächlich angezeigt werden.

Wenn Sie den Pinsel ändern, müssten diese Objekte auf niedriger Ebene erneut generiert werden. Die auffüllbare Klasse bietet einem Pinsel die Möglichkeit, die entsprechenden generierten Objekte auf niedriger Ebene zu finden und bei Änderungen zu aktualisieren. Wenn diese Fähigkeit aktiviert ist, wird der Pinsel als "nicht eingefroren" bezeichnet.

Mit der- <xref:System.Windows.Freezable.Freeze%2A> Methode können Sie diese selbst Aktualisierungs Fähigkeit deaktivieren. Mit dieser Methode können Sie den Pinsel als "eingefroren" oder als nicht änderbar festlegen.

> [!NOTE]
> Nicht jedes frei wählbare Objekt kann eingefroren werden. Um zu vermeiden, <xref:System.InvalidOperationException>dass ein ausgelöst wird, überprüfen Sie den Wert <xref:System.Windows.Freezable.CanFreeze%2A> der-Eigenschaft des frei wählbaren Objekts, um zu bestimmen, ob er eingefroren werden kann, bevor versucht wird, ihn

[!code-csharp[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
[!code-vb[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]

Wenn Sie nicht mehr die Möglichkeit haben, eine frei wählbare zu ändern, bietet das Einfrieren Leistungsvorteile. Wenn Sie in diesem Beispiel den Pinsel fixieren würden, muss das Grafiksystem nicht mehr auf Änderungen überwachen. Das Grafiksystem kann auch andere Optimierungen vornehmen, da es weiß, dass sich der Pinsel nicht ändert.

> [!NOTE]
> Aus Gründen der praktische Arbeit bleiben frei wählbare Objekte nicht fixiert, es sei denn, Sie fixieren Sie explizit.

<a name="frozenfreezables"></a>

## <a name="using-freezables"></a>Verwenden von frei wählbaren Elementen

Die Verwendung eines nicht fixierten, nicht fixierbaren Objekts ähnelt der Verwendung eines beliebigen anderen Objekt Typs. Im folgenden Beispiel <xref:System.Windows.Media.SolidColorBrush> wird die Farbe eines von Gelb in rot geändert, nachdem es verwendet wurde, um den Hintergrund einer Schaltfläche zu zeichnen. Das Grafiksystem arbeitet im Hintergrund, um die Schaltfläche automatisch von Gelb in rot zu ändern, wenn der Bildschirm das nächste Mal aktualisiert wird.

[!code-csharp[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
[!code-vb[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]

### <a name="freezing-a-freezable"></a>Einfrieren eines frei wählbaren

Um eine <xref:System.Windows.Freezable> nicht änderbar zu machen, wird die <xref:System.Windows.Freezable.Freeze%2A> zugehörige-Methode aufgerufen. Wenn Sie ein Objekt fixieren, das frei wählbare Objekte enthält, werden diese Objekte ebenfalls eingefroren. Wenn Sie z. b. ein <xref:System.Windows.Media.PathGeometry>fixieren, werden die darin enthaltenen Abbildungen und Segmente ebenfalls eingefroren.

Ein frei wählbares **kann nicht** eingefroren werden, wenn Folgendes zutrifft:

- Sie verfügt über animierte oder Daten gebundene Eigenschaften.

- Sie verfügt über Eigenschaften, die von einer dynamischen Ressource festgelegt werden. (Weitere Informationen zu dynamischen Ressourcen finden Sie in den [XAML-Ressourcen](xaml-resources.md) .)

- Sie enthält <xref:System.Windows.Freezable> untergeordnete Objekte, die nicht eingefroren werden können.

Wenn diese Bedingungen falsch sind und Sie nicht beabsichtigen, die <xref:System.Windows.Freezable>zu ändern, sollten Sie diese fixieren, um die zuvor beschriebenen Leistungsvorteile zu erhalten.

Nachdem Sie die- <xref:System.Windows.Freezable.Freeze%2A> Methode einer frei wählbaren Methode aufgerufen haben, kann Sie nicht mehr geändert werden. Der Versuch, ein fixierte Objekt zu <xref:System.InvalidOperationException> ändern, bewirkt, dass eine ausgelöst wird. Der folgende Code löst eine Ausnahme aus, da versucht wird, den Pinsel zu ändern, nachdem er eingefroren wurde.

[!code-csharp[freezablesample_procedural#ExceptionExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
[!code-vb[freezablesample_procedural#ExceptionExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]

Um zu vermeiden, dass diese Ausnahme ausgelöst wird, <xref:System.Windows.Freezable.IsFrozen%2A> können Sie mithilfe der- <xref:System.Windows.Freezable> Methode bestimmen, ob ein eingefroren ist.

[!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
[!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]

Im vorangehenden Codebeispiel wurde mit der <xref:System.Windows.Freezable.Clone%2A> -Methode eine änderbare Kopie von einem fixierten-Objekt erstellt. Im nächsten Abschnitt wird das Klonen ausführlicher erläutert.

> [!NOTE]
> Da eine fixierte freisetzbare nicht animiert werden kann, erstellt das Animationssystem automatisch änderbare Klone von <xref:System.Windows.Freezable> fixierten Objekten, wenn Sie versuchen, Sie mit einem <xref:System.Windows.Media.Animation.Storyboard>zu animieren. Um den durch das Klonen verursachten Leistungs Aufwand zu vermeiden, lassen Sie ein Objekt nicht fixiert, wenn Sie es animieren möchten. Weitere Informationen zur Animation mit Storyboards finden Sie in der [Übersicht über Storyboards](../graphics-multimedia/storyboards-overview.md).

### <a name="freezing-from-markup"></a>Einfrieren von Markup

Um ein <xref:System.Windows.Freezable> im Markup deklariertes-Objekt zu fixieren, `PresentationOptions:Freeze` verwenden Sie das-Attribut. Im folgenden Beispiel wird eine <xref:System.Windows.Media.SolidColorBrush> als Seiten Ressource deklariert und fixiert. Sie wird dann verwendet, um den Hintergrund einer Schaltfläche festzulegen.

[!code-xaml[FreezableSample#FreezeFromMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]

Um das `Freeze` -Attribut zu verwenden, müssen Sie den Präsentations Optionen-Namespace `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`zuordnen:. `PresentationOptions`ist das empfohlene Präfix für die Zuordnung dieses Namespace:

```xaml
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"
```

Da nicht alle XAML-Reader dieses Attribut erkennen, empfiehlt es sich, das [MC: Ignorable-Attribut](mc-ignorable-attribute.md) zu verwenden, `Presentation:Freeze` um das Attribut als Ignorable zu markieren:

```xaml
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
mc:Ignorable="PresentationOptions"
```

Weitere Informationen finden Sie auf der Seite " [MC: Ignorable Attribute](mc-ignorable-attribute.md) ".

### <a name="unfreezing-a-freezable"></a>"Einfrieren" eines frei wählbaren

Nachdem Sie eingefroren ist <xref:System.Windows.Freezable> , kann eine nie geändert oder nicht fixiert werden. Sie können jedoch einen nicht fixierten Klon mithilfe <xref:System.Windows.Freezable.Clone%2A> der <xref:System.Windows.Freezable.CloneCurrentValue%2A> -oder-Methode erstellen.

Im folgenden Beispiel wird der Hintergrund der Schaltfläche mit einem Pinsel festgelegt, und der Pinsel wird dann fixiert. Eine nicht fixierte Kopie wird mithilfe der <xref:System.Windows.Freezable.Clone%2A> -Methode aus dem Pinsel erstellt. Der Klon wird geändert und verwendet, um den Hintergrund der Schaltfläche von Gelb in rot zu ändern.

[!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
[!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]

> [!NOTE]
> Unabhängig davon, welche Klon Methode Sie verwenden, werden Animationen nie in den neuen <xref:System.Windows.Freezable>kopiert.

Die <xref:System.Windows.Freezable.Clone%2A> - <xref:System.Windows.Freezable.CloneCurrentValue%2A> Methode und die-Methode ergeben Tiefe Kopien der frei wählbaren. Wenn das freisetzbare Objekt andere fixierte, freisetzbare Objekte enthält, werden diese auch geklont und als änderbar festgelegt. Wenn Sie z. b. ein <xref:System.Windows.Media.PathGeometry> -Element Klonen, um es änderbar zu machen, werden die darin enthaltenen Abbildungen und Segmente ebenfalls kopiert und als änderbar festgelegt.

<a name="createyourownfreezableclass"></a>

## <a name="creating-your-own-freezable-class"></a>Erstellen einer eigenen, frei wählbaren Klasse

Eine Klasse, die von <xref:System.Windows.Freezable> abgeleitet wird, erhält die folgenden Funktionen.

- Sonderzustände: schreibgeschützt (fixiert) und beschreibbar.

- Thread Sicherheit: eine <xref:System.Windows.Freezable> fixierte kann über mehrere Threads gemeinsam genutzt werden.

- Ausführliche Änderungs Benachrichtigung: Im Gegensatz <xref:System.Windows.DependencyObject>zu anderen s bieten frei wählbare Objekte Änderungs Benachrichtigungen, wenn sich untergeordnete Eigenschaftswerte ändern.

- Einfaches Klonen: die Klasse, die frei wählbar ist, hat bereits mehrere Methoden implementiert, die Tiefe Klone ergeben.

Ein <xref:System.Windows.Freezable> ist ein Typ von <xref:System.Windows.DependencyObject>und verwendet daher das Abhängigkeits Eigenschaften System. Die Klasseneigenschaften müssen keine Abhängigkeits Eigenschaften sein, aber die Verwendung von Abhängigkeits Eigenschaften verringert die Menge an Code, den Sie schreiben müssen <xref:System.Windows.Freezable> , da die-Klasse mit den Abhängigkeits Eigenschaften entworfen wurde. Weitere Informationen zum Abhängigkeits Eigenschafts System finden Sie unter [Übersicht über Abhängigkeits Eigenschaften](dependency-properties-overview.md).

Jede <xref:System.Windows.Freezable> Unterklasse muss die <xref:System.Windows.Freezable.CreateInstanceCore%2A> -Methode überschreiben. Wenn Ihre Klasse Abhängigkeits Eigenschaften für alle Ihre Daten verwendet, sind Sie fertig.

Wenn Ihre Klasse Datenelemente für nicht-Abhängigkeits Eigenschaften enthält, müssen Sie auch die folgenden Methoden überschreiben:

- <xref:System.Windows.Freezable.CloneCore%2A>

- <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>

- <xref:System.Windows.Freezable.GetAsFrozenCore%2A>

- <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>

- <xref:System.Windows.Freezable.FreezeCore%2A>

Außerdem müssen Sie die folgenden Regeln für den Zugriff auf und das Schreiben von Datenmembern beachten, die keine Abhängigkeits Eigenschaften sind:

- Zum Anfang einer API, die Datenmember ohne Abhängigkeits Eigenschaften liest, wird die <xref:System.Windows.Freezable.ReadPreamble%2A> -Methode aufgerufen.

- Zum Anfang einer API, die nicht-Abhängigkeits eigenschaftendatenmember schreibt, <xref:System.Windows.Freezable.WritePreamble%2A> wird die-Methode aufgerufen. (Nachdem Sie in einer <xref:System.Windows.Freezable.WritePreamble%2A> API aufgerufen haben, müssen Sie keinen zusätzlichen Aufruf von <xref:System.Windows.Freezable.ReadPreamble%2A> durchführen, wenn Sie auch nicht-Abhängigkeits eigenschaftendatenmember lesen.)

- Ruft die <xref:System.Windows.Freezable.WritePostscript%2A> -Methode auf, bevor Methoden beendet werden, die in Datenelemente ohne Abhängigkeits Eigenschaften schreiben.

Wenn die Klasse nicht-Abhängigkeits Eigenschafts Datenmember enthält, <xref:System.Windows.DependencyObject> die Objekte sind, müssen Sie auch <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> die-Methode jedes Mal, wenn Sie einen ihrer Werte ändern, auch dann aufzurufen, `null`Wenn Sie den-Member auf festlegen.

> [!NOTE]
> Es ist sehr wichtig, dass Sie jede <xref:System.Windows.Freezable> Methode, die Sie überschreiben, mit einem-Befehl der Basis Implementierung starten.

Ein Beispiel für eine benutzerdefinierte <xref:System.Windows.Freezable> Klasse finden Sie im Beispiel für eine [Benutzerdefinierte Animation](https://go.microsoft.com/fwlink/?LinkID=159981).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Freezable>
- [Benutzerdefiniertes Animationsbeispiel](https://go.microsoft.com/fwlink/?LinkID=159981)
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
