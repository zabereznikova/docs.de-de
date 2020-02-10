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
ms.openlocfilehash: b1887afd19407898d8de1d92252e29778899fb89
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095189"
---
# <a name="freezable-objects-overview"></a>Übersicht über Freezable-Objekte

In diesem Thema wird beschrieben, wie <xref:System.Windows.Freezable>-Objekte effektiv verwendet und erstellt werden, die spezielle Funktionen zur Verbesserung der Anwendungsleistung bereitstellen. Beispiele für frei wählbare Objekte sind Pinsel, Stifte, Transformationen, Geometrien und Animationen.

<a name="whatisafreezable"></a>

## <a name="what-is-a-freezable"></a>Was ist ein frei wählbarer?

Ein <xref:System.Windows.Freezable> ist ein spezieller Objekttyp, der zwei Zustände aufweist: nicht fixiert und fixiert. Wenn das Objekt nicht fixiert ist, verhält sich ein <xref:System.Windows.Freezable> wie ein beliebiges anderes Objekt. Wenn Sie eingefroren ist, kann eine <xref:System.Windows.Freezable> nicht mehr geändert werden.

Ein <xref:System.Windows.Freezable> stellt ein <xref:System.Windows.Freezable.Changed> Ereignis bereit, mit dem Beobachter über Änderungen am Objekt benachrichtigt werden können. Das Einfrieren einer <xref:System.Windows.Freezable> kann die Leistung verbessern, da Sie keine Ressourcen mehr für Änderungs Benachrichtigungen aufwenden muss. Eine fixierte <xref:System.Windows.Freezable> kann auch Thread übergreifend freigegeben werden, während eine nicht fixierte <xref:System.Windows.Freezable> nicht.

Obwohl die <xref:System.Windows.Freezable>-Klasse viele Anwendungen enthält, sind die meisten <xref:System.Windows.Freezable> Objekte in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] mit dem Grafik Subsystem verknüpft.

Die <xref:System.Windows.Freezable>-Klasse vereinfacht die Verwendung bestimmter Grafiksystem Objekte und kann dabei helfen, die Anwendungsleistung zu verbessern. Beispiele für Typen, die von <xref:System.Windows.Freezable> erben, sind die Klassen <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>und <xref:System.Windows.Media.Geometry>. Da Sie nicht verwaltete Ressourcen enthalten, muss das System diese Objekte auf Änderungen überwachen und dann die entsprechenden nicht verwalteten Ressourcen aktualisieren, wenn Änderungen am ursprünglichen Objekt vorgenommen werden. Selbst wenn Sie ein Grafiksystem Objekt nicht tatsächlich ändern, muss das System trotzdem einige Ressourcen für die Überwachung des Objekts aufwenden, falls Sie es ändern.

Nehmen Sie beispielsweise an, Sie erstellen einen <xref:System.Windows.Media.SolidColorBrush> Pinsel und verwenden ihn, um den Hintergrund einer Schaltfläche zu zeichnen.

[!code-csharp[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
[!code-vb[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]

Wenn die Schaltfläche gerendert wird, verwendet das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Grafik-unter System die Informationen, die Sie angegeben haben, um eine Gruppe von Pixeln zu zeichnen, um die Darstellung einer Schaltfläche zu erstellen. Obwohl Sie einen Pinsel mit voll Tonfarbe verwendet haben, um zu beschreiben, wie die Schaltfläche gezeichnet werden soll, führt der Pinsel mit voll Tonfarbe das Zeichnen nicht aus. Das Grafiksystem generiert schnelle, Low-Level-Objekte für die Schaltfläche und den Pinsel, und es handelt sich um die Objekte, die auf dem Bildschirm tatsächlich angezeigt werden.

Wenn Sie den Pinsel ändern, müssten diese Objekte auf niedriger Ebene erneut generiert werden. Die auffüllbare Klasse bietet einem Pinsel die Möglichkeit, die entsprechenden generierten Objekte auf niedriger Ebene zu finden und bei Änderungen zu aktualisieren. Wenn diese Fähigkeit aktiviert ist, wird der Pinsel als "nicht eingefroren" bezeichnet.

Mit der <xref:System.Windows.Freezable.Freeze%2A>-Methode eines frei wählbaren s können Sie diese selbst Aktualisierungs Fähigkeit deaktivieren. Mit dieser Methode können Sie den Pinsel als "eingefroren" oder als nicht änderbar festlegen.

> [!NOTE]
> Nicht jedes frei wählbare Objekt kann eingefroren werden. Um das Auslösen eines <xref:System.InvalidOperationException>zu vermeiden, überprüfen Sie den Wert der <xref:System.Windows.Freezable.CanFreeze%2A>-Eigenschaft des frei wählbaren Objekts, um zu bestimmen, ob er eingefroren werden kann, bevor versucht wird, ihn zu fixieren

[!code-csharp[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
[!code-vb[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]

Wenn Sie nicht mehr die Möglichkeit haben, eine frei wählbare zu ändern, bietet das Einfrieren Leistungsvorteile. Wenn Sie in diesem Beispiel den Pinsel fixieren würden, muss das Grafiksystem nicht mehr auf Änderungen überwachen. Das Grafiksystem kann auch andere Optimierungen vornehmen, da es weiß, dass sich der Pinsel nicht ändert.

> [!NOTE]
> Aus Gründen der praktische Arbeit bleiben frei wählbare Objekte nicht fixiert, es sei denn, Sie fixieren Sie explizit.

<a name="frozenfreezables"></a>

## <a name="using-freezables"></a>Verwenden von frei wählbaren Elementen

Die Verwendung eines nicht fixierten, nicht fixierbaren Objekts ähnelt der Verwendung eines beliebigen anderen Objekt Typs. Im folgenden Beispiel wird die Farbe einer <xref:System.Windows.Media.SolidColorBrush> von Gelb in rot geändert, nachdem Sie verwendet wurde, um den Hintergrund einer Schaltfläche zu zeichnen. Das Grafiksystem arbeitet im Hintergrund, um die Schaltfläche automatisch von Gelb in rot zu ändern, wenn der Bildschirm das nächste Mal aktualisiert wird.

[!code-csharp[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
[!code-vb[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]

### <a name="freezing-a-freezable"></a>Einfrieren eines frei wählbaren

Um einen <xref:System.Windows.Freezable> nicht änderbar zu machen, nennen Sie dessen <xref:System.Windows.Freezable.Freeze%2A>-Methode. Wenn Sie ein Objekt fixieren, das frei wählbare Objekte enthält, werden diese Objekte ebenfalls eingefroren. Wenn Sie z. b. eine <xref:System.Windows.Media.PathGeometry>fixieren, werden die darin enthaltenen Abbildungen und Segmente ebenfalls eingefroren.

Ein frei wählbares **kann nicht** eingefroren werden, wenn Folgendes zutrifft:

- Sie verfügt über animierte oder Daten gebundene Eigenschaften.

- Sie verfügt über Eigenschaften, die von einer dynamischen Ressource festgelegt werden. (Weitere Informationen zu dynamischen Ressourcen finden Sie in den [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md) .)

- Sie enthält <xref:System.Windows.Freezable> untergeordneten Objekten, die nicht eingefroren werden können.

Wenn diese Bedingungen falsch sind und Sie die <xref:System.Windows.Freezable>nicht ändern möchten, sollten Sie diese fixieren, um die zuvor beschriebenen Leistungsvorteile zu erhalten.

Nachdem Sie die <xref:System.Windows.Freezable.Freeze%2A>-Methode eines frei wählbaren aufgerufen haben, kann Sie nicht mehr geändert werden. Der Versuch, ein fixierte Objekt zu ändern, bewirkt, dass eine <xref:System.InvalidOperationException> ausgelöst wird. Der folgende Code löst eine Ausnahme aus, da versucht wird, den Pinsel zu ändern, nachdem er eingefroren wurde.

[!code-csharp[freezablesample_procedural#ExceptionExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
[!code-vb[freezablesample_procedural#ExceptionExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]

Um zu vermeiden, dass diese Ausnahme ausgelöst wird, können Sie die <xref:System.Windows.Freezable.IsFrozen%2A>-Methode verwenden, um zu bestimmen, ob ein <xref:System.Windows.Freezable> eingefroren ist.

[!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
[!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]

Im vorangehenden Codebeispiel wurde mit der <xref:System.Windows.Freezable.Clone%2A>-Methode eine änderbare Kopie von einem fixierten-Objekt erstellt. Im nächsten Abschnitt wird das Klonen ausführlicher erläutert.

> [!NOTE]
> Da eine fixierte freisetzbare nicht animiert werden kann, erstellt das Animationssystem automatisch änderbare Klone von fixierten <xref:System.Windows.Freezable> Objekten, wenn Sie versuchen, Sie mit einem <xref:System.Windows.Media.Animation.Storyboard>zu animieren. Um den durch das Klonen verursachten Leistungs Aufwand zu vermeiden, lassen Sie ein Objekt nicht fixiert, wenn Sie es animieren möchten. Weitere Informationen zur Animation mit Storyboards finden Sie in der [Übersicht über Storyboards](../graphics-multimedia/storyboards-overview.md).

### <a name="freezing-from-markup"></a>Einfrieren von Markup

Um ein im Markup deklariertes <xref:System.Windows.Freezable> Objekt zu fixieren, verwenden Sie das `PresentationOptions:Freeze`-Attribut. Im folgenden Beispiel wird ein <xref:System.Windows.Media.SolidColorBrush> als Seiten Ressource deklariert und fixiert. Sie wird dann verwendet, um den Hintergrund einer Schaltfläche festzulegen.

[!code-xaml[FreezableSample#FreezeFromMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]

Um das `Freeze`-Attribut zu verwenden, müssen Sie den Präsentations Optionen-Namespace zuordnen: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`. `PresentationOptions` ist das empfohlene Präfix für die Zuordnung dieses Namespace:

```xaml
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"
```

Da nicht alle XAML-Reader dieses Attribut erkennen, empfiehlt es sich, das [MC: Ignorable-Attribut](mc-ignorable-attribute.md) zu verwenden, um das `Presentation:Freeze` Attribut als Ignorable zu markieren:

```xaml
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
mc:Ignorable="PresentationOptions"
```

Weitere Informationen finden Sie auf der Seite " [MC: Ignorable Attribute](mc-ignorable-attribute.md) ".

### <a name="unfreezing-a-freezable"></a>"Einfrieren" eines frei wählbaren

Nachdem Sie eingefroren ist, kann ein <xref:System.Windows.Freezable> nie geändert oder nicht eingefroren werden. Sie können jedoch einen nicht fixierten Klon mithilfe der <xref:System.Windows.Freezable.Clone%2A>-oder <xref:System.Windows.Freezable.CloneCurrentValue%2A>-Methode erstellen.

Im folgenden Beispiel wird der Hintergrund der Schaltfläche mit einem Pinsel festgelegt, und der Pinsel wird dann fixiert. Eine nicht fixierte Kopie wird aus dem Pinsel mithilfe der <xref:System.Windows.Freezable.Clone%2A>-Methode erstellt. Der Klon wird geändert und verwendet, um den Hintergrund der Schaltfläche von Gelb in rot zu ändern.

[!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
[!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]

> [!NOTE]
> Unabhängig davon, welche Klon Methode Sie verwenden, werden Animationen nie in den neuen <xref:System.Windows.Freezable>kopiert.

Die Methoden <xref:System.Windows.Freezable.Clone%2A> und <xref:System.Windows.Freezable.CloneCurrentValue%2A> ergeben Tiefe Kopien der frei wählbaren. Wenn das freisetzbare Objekt andere fixierte, freisetzbare Objekte enthält, werden diese auch geklont und als änderbar festgelegt. Wenn Sie z. b. eine fixierte <xref:System.Windows.Media.PathGeometry> Klonen, damit Sie geändert werden kann, werden die darin enthaltenen Abbildungen und Segmente ebenfalls kopiert und als änderbar festgelegt.

<a name="createyourownfreezableclass"></a>

## <a name="creating-your-own-freezable-class"></a>Erstellen einer eigenen, frei wählbaren Klasse

Eine Klasse, die von <xref:System.Windows.Freezable> abgeleitet wird, erhält die folgenden Funktionen.

- Sonderzustände: schreibgeschützt (fixiert) und beschreibbar.

- Thread Sicherheit: eine fixierte <xref:System.Windows.Freezable> kann über mehrere Threads hinweg gemeinsam genutzt werden.

- Ausführliche Änderungs Benachrichtigung: im Gegensatz zu anderen <xref:System.Windows.DependencyObject>s bieten frei wählbare Objekte Änderungs Benachrichtigungen, wenn sich untergeordnete Eigenschaftswerte ändern.

- Einfaches Klonen: die Klasse, die frei wählbar ist, hat bereits mehrere Methoden implementiert, die Tiefe Klone ergeben.

Ein <xref:System.Windows.Freezable> ist ein Typ von <xref:System.Windows.DependencyObject>und verwendet daher das Abhängigkeits Eigenschaften System. Die Klasseneigenschaften müssen keine Abhängigkeits Eigenschaften sein, aber die Verwendung von Abhängigkeits Eigenschaften verringert die Menge an Code, den Sie schreiben müssen, da die <xref:System.Windows.Freezable> Klasse mit Abhängigkeits Eigenschaften entworfen wurde. Weitere Informationen zum Abhängigkeits Eigenschafts System finden Sie unter [Übersicht über Abhängigkeits Eigenschaften](dependency-properties-overview.md).

Jede <xref:System.Windows.Freezable> Unterklasse muss die <xref:System.Windows.Freezable.CreateInstanceCore%2A>-Methode überschreiben. Wenn Ihre Klasse Abhängigkeits Eigenschaften für alle Ihre Daten verwendet, sind Sie fertig.

Wenn Ihre Klasse Datenelemente für nicht-Abhängigkeits Eigenschaften enthält, müssen Sie auch die folgenden Methoden überschreiben:

- <xref:System.Windows.Freezable.CloneCore%2A>

- <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>

- <xref:System.Windows.Freezable.GetAsFrozenCore%2A>

- <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>

- <xref:System.Windows.Freezable.FreezeCore%2A>

Außerdem müssen Sie die folgenden Regeln für den Zugriff auf und das Schreiben von Datenmembern beachten, die keine Abhängigkeits Eigenschaften sind:

- Zum Anfang einer API, die nicht-Abhängigkeits eigenschaftendatenmember liest, wird die <xref:System.Windows.Freezable.ReadPreamble%2A>-Methode aufgerufen.

- Zum Anfang einer API, die nicht-Abhängigkeits eigenschaftendatenmember schreibt, wird die <xref:System.Windows.Freezable.WritePreamble%2A>-Methode aufgerufen. (Nachdem Sie <xref:System.Windows.Freezable.WritePreamble%2A> in einer API aufgerufen haben, müssen Sie keinen zusätzlichen Aufruf an <xref:System.Windows.Freezable.ReadPreamble%2A> tätigen, wenn Sie auch nicht-Abhängigkeits eigenschaftendatenmember lesen.)

- Ruft die <xref:System.Windows.Freezable.WritePostscript%2A>-Methode auf, bevor Methoden beendet werden, die in Datenelemente ohne Abhängigkeits Eigenschaften schreiben.

Wenn die Klasse nicht-Abhängigkeits Eigenschafts Datenmember enthält, die <xref:System.Windows.DependencyObject>-Objekten sind, müssen Sie auch die <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A>-Methode jedes Mal, wenn Sie einen ihrer Werte ändern, auch dann aufzurufen, wenn Sie den-Member auf `null`festlegen.

> [!NOTE]
> Es ist sehr wichtig, dass Sie jede <xref:System.Windows.Freezable> Methode, die Sie überschreiben, mit einem-Befehl der Basis Implementierung beginnen.

Ein Beispiel für eine benutzerdefinierte <xref:System.Windows.Freezable>-Klasse finden Sie im Beispiel für eine [Benutzerdefinierte Animation](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation).

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Freezable>
- [Benutzerdefiniertes Animationsbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
