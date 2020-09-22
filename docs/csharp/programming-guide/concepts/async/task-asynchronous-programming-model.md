---
title: Das aufgabenbasierte asynchrone Programmiermodell mit async und await (C#)
description: In diesem Artikel wird die Verwendung der aufgabenbasierten asynchronen Programmierung erläutert. Dabei handelt es sich um einen vereinfachten Ansatz für die asynchrone Programmierung in C#.
ms.date: 08/19/2020
ms.assetid: 9bcf896a-5826-4189-8c1a-3e35fa08243a
ms.openlocfilehash: 1014e38dcb3e2c4f56c8b3f3dade9bdbff3abd27
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556036"
---
# <a name="task-asynchronous-programming-model"></a>Aufgabenbasiertes asynchrones Programmiermodell

Sie können Leistungsengpässe vermeiden und die Reaktionsfähigkeit der Anwendung insgesamt verbessern, indem Sie asynchrone Programmierung verwenden. Allerdings können herkömmliche Verfahren zum Schreiben von asynchronen Anwendungen kompliziert sein, weshalb es schwierig ist, diese Anwendungen zu schreiben, zu debuggen und zu verwalten.

[C# 5](../../../whats-new/csharp-version-history.md#c-version-50) führte den vereinfachten Ansatz der asynchronen Programmierung ein, der die asynchrone Unterstützung in .NET Framework 4.5 und höher, .NET Core sowie in der Windows-Runtime nutzt. Der Compiler übernimmt die schwierige Arbeit, die zuvor vom Entwickler ausgeführt wurde, und die Anwendung behält eine logische Struktur bei, die synchronem Code ähnelt. So erhalten Sie alle Vorteile der asynchronen Programmierung mit einem Bruchteil des Aufwands.

Dieses Thema enthält eine Übersicht über die Verwendungsmöglichkeiten der asynchronen Programmierung sowie Links zu Supportthemen, die weitere Informationen und Beispiele enthalten.

## <a name="async-improves-responsiveness"></a><a name="BKMK_WhentoUseAsynchrony"></a> Async verbessert die Reaktionsfähigkeit

Asynchronie ist wesentlich für potenziell blockierende Aktivitäten, z.B. Webzugriff. Der Zugriff auf eine Webressource ist manchmal langsam oder verzögert. Wenn eine solche Aktivität innerhalb eines synchronen Prozesses blockiert wird, muss die gesamte Anwendung warten. In einem asynchronen Prozess kann die Anwendung mit anderer Arbeit fortfahren, die nicht von der Webressource abhängig ist, bis die potenziell blockierende Aufgabe beendet ist.

In der folgenden Tabelle werden typische Bereichen angezeigt, in denen die asynchrone Programmierung die Reaktionsfähigkeit verbessert. Die aufgelisteten APIs von .NET und der Windows-Runtime enthalten Methoden, die die asynchrone Programmierung unterstützen.

| Anwendungsbereich | .NET-Typen mit asynchronen Methoden | Windows-Runtime-Typen mit asynchronen Methoden |
|--|--|--|
| Webzugriff | <xref:System.Net.Http.HttpClient> | <xref:Windows.Web.Http.HttpClient?displayProperty=nameWithType> <br> <xref:Windows.Web.Syndication.SyndicationClient> |
| Arbeiten mit Dateien | <xref:System.Text.Json.JsonSerializer> <br> <xref:System.IO.StreamReader> <br> <xref:System.IO.StreamWriter> <br> <xref:System.Xml.XmlReader> <br> <xref:System.Xml.XmlWriter> | <xref:Windows.Storage.StorageFile> |
| Arbeiten mit Bildern |  | <xref:Windows.Media.Capture.MediaCapture> <br> <xref:Windows.Graphics.Imaging.BitmapEncoder> <br> <xref:Windows.Graphics.Imaging.BitmapDecoder> |
| WCF-Programmierung | [Synchrone und asynchrone Vorgänge](../../../../framework/wcf/synchronous-and-asynchronous-operations.md) |  |

Asynchronität erweist sich als besonders nützlich bei Prozessen, die durch den UI-Thread ausgeführt werden, da sämtliche auf die Benutzeroberfläche bezogenen Aktivitäten sich gemeinhin diesen Thread teilen. Ist ein Prozess in einer synchronen Anwendung blockiert, werden alle blockiert. Die Anwendung reagiert nicht mehr, und Sie denken möglicherweise, es sei ein Fehler aufgetreten, wenn die Anwendung tatsächlich nur wartet.

Wenn Sie asynchrone Methoden verwenden, reagiert die Anwendung weiterhin auf die Benutzeroberfläche. Sie können beispielsweise die Fenstergröße ändern, das Fenster minimieren oder die Anwendung schließen, wenn Sie nicht warten möchten, bis sie fertig ist.

Durch den auf Asynchronie basierenden Ansatz wird eine Entsprechung für die automatische Übertragung an die Liste der Optionen hinzugefügt, die beim Entwerfen von asynchronen Vorgängen zur Auswahl stehen. Sie erhalten also alle Vorteile der herkömmlichen asynchronen Programmierung, der Aufwand des Entwicklers ist jedoch wesentlich geringer.

## <a name="async-methods-are-easy-to-write"></a><a name="BKMK_HowtoWriteanAsyncMethod"></a> Das Schreiben asynchroner Methoden ist einfach

Die Schlüsselwörter [async](../../../language-reference/keywords/async.md) und [await](../../../language-reference/operators/await.md) in C# sind das Kernstück der asynchronen Programmierung. Durch Verwendung dieser beiden Schlüsselwörter können Sie mithilfe von .NET Framework-, .NET Core- oder Windows-Runtime-Ressourcen asynchrone Methoden fast genauso einfach erstellen wie synchrone Methoden. Asynchrone Methoden, die Sie unter Verwendung des Schlüsselworts `async` definieren, werden als *async-Methoden* bezeichnet.

Das folgende Beispiel zeigt eine Async-Methode. Fast der gesamte Code sollte Ihnen bekannt vorkommen.

Ein vollständiges WPF-Beispiel (Windows Presentation Foundation) können Sie unter [Asynchrones Programmieren mit async und await in C#](/samples/dotnet/samples/async-and-await-cs) herunterladen.

:::code language="csharp" source="snippets/access-web/Program.cs" id="ControlFlow":::

Sie können dem vorherigen Beispiel mehrere Methoden entnehmen. Starten Sie mit der Methodensignatur. Sie enthält den `async`-Modifizierer. Der Rückgabetyp lautet `Task<int>` (weitere Optionen finden Sie im Abschnitt „Rückgabetypen“). Der Methodenname endet auf `Async`. Im Text der Methode gibt `GetStringAsync` einen `Task<string>`-Wert zurück. Das bedeutet, dass Sie `string` (`contents`) erhalten, wenn Sie auf die Aufgabe warten (`await`). Bevor Sie auf die Aufgabe warten, können Sie Arbeiten ausführen, die nicht auf einem `string`-Wert von `GetStringAsync` basieren.

Achten Sie besonders auf den `await`-Operator. `GetUrlContentLengthAsync` wird angehalten:

- `GetUrlContentLengthAsync` kann erst fortgesetzt werden, wenn `getStringTask` abgeschlossen ist.
- In der Zwischenzeit wird die Steuerung an den Aufrufer von `GetUrlContentLengthAsync` zurückgegeben.
- Die Steuerung wird hier wieder aufgenommen, sobald `getStringTask` abgeschlossen ist.
- Der `await`-Operator ruft nun das `string`-Ergebnis von `getStringTask` ab.

Die return-Anweisung gibt ein ganzzahliges Ergebnis an. Alle Methoden, die auf `GetUrlContentLengthAsync` warten, rufen den Längenwert ab.

Wenn für `GetUrlContentLengthAsync` zwischen dem Aufrufen von `GetStringAsync` und dem Warten auf die Beendigung keine Arbeit ansteht, können Sie den Code durch Aufrufen und Warten in der folgenden Anweisung vereinfachen.

```csharp
string contents = await client.GetStringAsync("https://docs.microsoft.com/dotnet");
```

Die folgenden Merkmale fassen zusammen, wodurch das vorherige Beispiel sich als asynchrone Methode auszeichnet:

- Die Methodensignatur enthält einen `async`-Modifizierer.
- Der Name einer Async-Methode endet mit dem Suffix "Async".
- Der Rückgabetyp ist einer der folgenden Typen:

  - <xref:System.Threading.Tasks.Task%601>, wenn die Methode über eine return-Anweisung verfügt, in der der Operand dem Typ `TResult` angehört.
  - <xref:System.Threading.Tasks.Task>, wenn die Methode keine return-Anweisung hat oder eine return-Anweisung ohne Operanden hat.
  - `void`, wenn Sie einen asynchronen Ereignishandler schreiben.
  - Jeder andere Typ, der über eine `GetAwaiter`-Methode verfügt (ab C# 7.0).

  Weitere Informationen finden Sie im Abschnitt [Rückgabetypen und -parameter](#BKMK_ReturnTypesandParameters).

- Die Methode umfasst normalerweise mindestens einen `await`-Ausdruck, der einen Punkt kennzeichnet, an dem die Methode erst nach Abschluss des erwarteten asynchronen Vorgangs fortgesetzt werden kann. In der Zwischenzeit wird die Methode angehalten, und die Steuerung kehrt zum Aufrufer der Methode zurück. Im nächsten Abschnitt dieses Themas wird veranschaulicht, was am Unterbrechungspunkt geschieht.

In Asynch-Methoden verwenden Sie die bereitgestellten Schlüsselwörter und Typen, um die gewünschten Aktionen anzugeben. Der Compiler übernimmt den Rest, er verfolgt auch, was geschehen muss, wenn die Steuerung zu einem await-Punkt in einer angehaltenen Methode zurückkehrt. Einige Routinenprozesse, beispielsweise Schleifen und Ausnahmebehandlung, sind im herkömmlichen asynchronen Code möglicherweise schwierig zu handhaben. In einer Async-Methode schreiben Sie diese Elemente fast so wie in einer synchronen Lösung, und das Problem ist gelöst.

Weitere Informationen zur Asynchronität in vorherigen Versionen von .NET Framework finden Sie unter [TPL und herkömmliche asynchrone .NET Framework-Programmierung](../../../../standard/parallel-programming/tpl-and-traditional-async-programming.md).

## <a name="what-happens-in-an-async-method"></a><a name="BKMK_WhatHappensUnderstandinganAsyncMethod"></a> Was geschieht in einer asynchronen Methode?

Bei der asynchronen Programmierung ist es sehr wichtig zu verstehen, wie die Ablaufsteuerung von Methode zu Methode springt. In dem folgenden Diagramm werden Sie durch den Prozess geführt:

:::image type="content" source="media/task-asynchronous-programming-model/navigation-trace-async-program.png" alt-text="Ablaufnavigation der asynchronen Ablaufsteuerung" lightbox="media/task-asynchronous-programming-model/navigation-trace-async-program.png":::

Die Zahlen in diesem Diagramm entsprechen den folgenden Schritten, die initiiert werden, wenn eine aufrufende Methode die asynchrone Methode aufruft.

1. Eine aufrufende Methode ruft die asynchrone Methode `GetUrlContentLengthAsync` auf und wartet auf sie.

1. `GetUrlContentLengthAsync` erstellt eine <xref:System.Net.Http.HttpClient>-Instanz und ruft die asynchrone Methode <xref:System.Net.Http.HttpClient.GetStringAsync%2A> auf, um den Inhalt einer Website als Zeichenfolge herunterzuladen.

1. In `GetStringAsync` geschieht etwas, durch das die Ausführung angehalten wird. Möglicherweise muss gewartet werden, bis eine Website heruntergeladen oder eine andere blockierende Aktivität ausgeführt wurde. Um blockierende Ressourcen zu vermeiden, übergibt die Methode `GetStringAsync` die Steuerung an ihren Aufrufer `GetUrlContentLengthAsync`.

     `GetStringAsync` gibt <xref:System.Threading.Tasks.Task%601> zurück, wobei `TResult` eine Zeichenfolge ist. `GetUrlContentLengthAsync` weist der `getStringTask`-Variablen die Aufgabe zu. Die Aufgabe stellt den laufenden Prozess für den Aufruf von `GetStringAsync` dar, mit der Festlegung, dass bei Abschluss der Arbeit ein tatsächlicher Zeichenfolgenwert erzeugt wurde.

1. Da `getStringTask` noch nicht abgewartet wurde, kann `GetUrlContentLengthAsync` mit anderer Arbeit fortfahren, die nicht vom Endergebnis von `GetStringAsync` abhängt. Diese Aufgaben werden durch einen Aufruf der synchronen Methode `DoIndependentWork` dargestellt.

1. `DoIndependentWork` ist eine synchrone Methode, die ihre Arbeit ausführt und zu ihrem Aufrufer zurückkehrt.

1. Für `GetUrlContentLengthAsync` steht keine Arbeit mehr an, die die Methode ohne ein Ergebnis von `getStringTask` ausführen kann. `GetUrlContentLengthAsync` möchte als Nächstes die Länge der heruntergeladenen Zeichenfolge berechnen und zurückgeben, aber die Methode kann diesen Wert erst berechnen, wenn sie über die Zeichenfolge verfügt.

    Daher verwendet `GetUrlContentLengthAsync` einen await-Operator, um die Ausführung anzuhalten und die Steuerung an die Methode zu übergeben, von der `GetUrlContentLengthAsync` aufgerufen wurde. `GetUrlContentLengthAsync` gibt ein `Task<int>`-Element an den Aufrufer zurück. Die Aufgabe stellt eine Zusicherung dar, ein Ganzzahlergebnis zu erzeugen, das die Länge der heruntergeladenen Zeichenfolge ist.

    > [!NOTE]
    > Wenn `GetStringAsync` (und daher `getStringTask`) abgeschlossen ist, bevor `GetUrlContentLengthAsync` darauf wartet, verbleibt die Steuerung bei `GetUrlContentLengthAsync`. Der Aufwand des Anhaltens und der Rückkehr zu `GetUrlContentLengthAsync` wäre überflüssig, wenn der aufgerufene asynchrone Prozess `getStringTask` bereits abgeschlossen ist und `GetUrlContentLengthAsync` nicht auf das Endergebnis warten muss.

    In der aufrufenden Methode wird das Verarbeitungsmuster fortgesetzt. Der Aufrufer führt möglicherweise andere Arbeit aus, die nicht von dem Ergebnis von `GetUrlContentLengthAsync` abhängt, bevor er auf dieses Ergebnis wartet, oder der Aufrufer wartet sofort auf das Ergebnis. Die aufrufende Methode wartet auf `GetUrlContentLengthAsync`, und `GetUrlContentLengthAsync` wartet auf `GetStringAsync`.

1. `GetStringAsync` wird abgeschlossen und erstellt ein Zeichenfolgenergebnis. Das Zeichenfolgenergebnis wird von dem Aufruf `GetStringAsync` nicht auf die Art zurückgegeben, die Sie möglicherweise erwarten. (Beachten Sie, dass die Methode bereits in Schritt 3 eine Aufgabe zurückgegeben hat.) Stattdessen wird das Zeichenfolgenergebnis in dem Task gespeichert, der den Abschluss der Methode darstellt: `getStringTask`. Der await-Operator ruft das Ergebnis von `getStringTask` ab. Die Zuweisungsanweisung weist `contents` das abgerufene Ergebnis zu.

1. Wenn `GetUrlContentLengthAsync` über das Zeichenfolgenergebnis verfügt, kann die Methode die Länge der Zeichenfolge berechnen. Dann ist die Arbeit von `GetUrlContentLengthAsync` auch abgeschlossen, und der wartende Ereignishandler kann fortfahren. Im vollständigen Beispiel am Ende des Themas können Sie überprüfen, ob der Ereignishandler den Wert des Längenergebnisses abruft und druckt.
Wenn die asynchrone Programmierung für Sie neu ist, nehmen Sie sich einen Moment Zeit, um den Unterschied zwischen synchronem und asynchronem Verhalten zu untersuchen. Eine synchrone Methode kehrt zum Aufrufer zurück, wenn ihre Arbeit abgeschlossen ist (Schritt 5). Eine asynchrone Methode hingegen gibt einen Aufgabenwert zurück, wenn die Verarbeitung angehalten wird (Schritt 3 und 6). Wenn die asynchrone Methode schließlich ihre Arbeit abgeschlossen hat, wird die Aufgabe als abgeschlossen markiert und das Ergebnis ggf. in der Aufgabe gespeichert.

## <a name="api-async-methods"></a><a name="BKMK_APIAsyncMethods"></a> API-Async-Methoden

Sie fragen sich möglicherweise, wo Methoden wie `GetStringAsync` zu finden sind, die die asynchrone Programmierung unterstützen. .NET Framework 4.5 oder höher und .NET Core enthalten viele Member, die mit `async` und `await` funktionieren. Sie können sie am Suffix „Async“ erkennen, das an den Membernamen angefügt wird, sowie am Rückgabetyp <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601>. Beispielsweise enthält die `System.IO.Stream`-Klasse Methoden wie <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.ReadAsync%2A> und <xref:System.IO.Stream.WriteAsync%2A> sowie die synchronen Methoden <xref:System.IO.Stream.CopyTo%2A>, <xref:System.IO.Stream.Read%2A> und <xref:System.IO.Stream.Write%2A>.

Die Windows-Runtime enthält außerdem viele Methoden, die Sie mit `async` und `await` in Windows-Apps verwenden können. Weitere Informationen finden Sie unter [Threading and async programming](/windows/uwp/threading-async/) (Threading und asynchrone Programmierung) für die UWP-Entwicklung, [Asynchronous programming (Windows Store apps)](/previous-versions/windows/apps/hh464924(v=win.10)) (Asynchrone Programmierung für Windows Store-Apps) und [Quickstart: Calling asynchronous APIs in C# or Visual Basic](/previous-versions/windows/apps/hh452713(v=win.10)) (Schnellstart: Aufrufen von asynchronen APIs in C# oder Visual Basic), wenn Sie frühere Versionen der Windows-Runtime verwenden.

## <a name="threads"></a><a name="BKMK_Threads"></a> Threads

Async-Methoden sollen nicht blockierende Vorgänge sein. Ein `await`-Ausdruck in einer asynchronen Methode blockiert den aktuellen Thread nicht, während der Task, auf den gewartet wurde, ausgeführt wird. Stattdessen registriert der Ausdruck den Rest der Methode als Fortsetzung und gibt die Steuerung an den Aufrufer der Async-Methode zurück.

Durch die Schlüsselwörter `async` und `await` werden keine zusätzlichen Threads erstellt. Async-Methoden erfordern kein Multithreading, da eine Async-Methode nicht in einem eigenen Thread ausgeführt wird. Die Methode wird im aktuellen Synchronisierungskontext ausgeführt und verwendet Zeit im Thread nur, wenn sie aktiv ist. Sie können <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> zur Verschiebung CPU-gebundener Arbeit in einen Hintergrundthread verwenden, aber ein Hintergrundthread nützt nichts bei einem Prozess, der wartet, dass Ergebnisse zur Verfügung gestellt werden.

Der auf Asynchronie basierende Ansatz der asynchronen Programmierung ist vorhandenen Ansätzen in nahezu jedem Fall vorzuziehen. Insbesondere eignet sich dieser Ansatz besser für E/A-gebundene Vorgänge als die <xref:System.ComponentModel.BackgroundWorker>-Klasse, da der Code einfacher und kein Schutz vor Racebedingungen erforderlich ist. In Kombination mit der Methode <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> eignet sich die asynchrone Programmierung besser als <xref:System.ComponentModel.BackgroundWorker> für CPU-gebundene Vorgänge, da die asynchrone Programmierung Koordinationsdetails der Ausführung des Codes von der Arbeit trennt, die `Task.Run` an den Threadpool überträgt.

## <a name="async-and-await"></a><a name="BKMK_AsyncandAwait"></a> „async“ und „await“

Wenn Sie angeben, dass eine Methode eine asynchrone Methode ist, indem Sie den [async](../../../language-reference/keywords/async.md)-Modifizierer verwenden, aktivieren Sie die folgenden zwei Funktionen.

- Die markierte async-Methode kann [await](../../../language-reference/operators/await.md) verwenden, um Unterbrechungspunkte festzulegen. Der `await`-Operator informiert den Compiler, dass die Async-Methode erst über diesen Punkt hinaus fortgesetzt werden kann, wenn der abgewartete asynchrone Prozess abgeschlossen ist. In der Zwischenzeit kehrt die Steuerung zum Aufrufer der Async-Methode zurück.

     Die Unterbrechung einer async-Methode bei einem `await`-Ausdruck stellt keine Beendigung der Methode dar, und `finally`-Blöcke werden nicht ausgeführt.

- Auf die markierte Async-Methode können auch Methoden warten, die sie aufrufen.

Eine asynchrone Methode enthält in der Regel mindestens ein Vorkommen eines `await`-Operators, die Abwesenheit von `await`-Ausdrücken verursacht jedoch keinen Compilerfehler. Wenn eine asynchrone Methode keinen `await`-Operator verwendet, um einen Unterbrechungspunkt zu markieren, wird die Methode ungeachtet des `async`-Modifizierers wie eine synchrone Methode ausgeführt. Der Compiler gibt eine Warnung für solche Methoden aus.

`async` und `await` sind kontextbezogene Schlüsselwörter. Weitere Informationen und Beispiele finden Sie unter den folgenden Themen:

- [async](../../../language-reference/keywords/async.md)
- [await](../../../language-reference/operators/await.md)

## <a name="return-types-and-parameters"></a><a name="BKMK_ReturnTypesandParameters"></a> Rückgabetypen und Parameter

Eine async-Methode gibt normalerweise eine <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> zurück. Innerhalb einer async-Methode wird ein `await`-Operator auf einen Task angewendet, der in einem Aufruf einer anderen async-Methode zurückgegeben wurde.

Geben Sie <xref:System.Threading.Tasks.Task%601> als Rückgabetyp an, wenn die Methode eine [`return`](../../../language-reference/keywords/return.md)-Anweisung enthält, die einen Operanden vom Typ `TResult` angibt.

Sie verwenden <xref:System.Threading.Tasks.Task> als Rückgabetyp, wenn die Methode keine return-Anweisung hat oder über eine return-Anweisung verfügt, die keinen Operanden zurückgibt.

Ab C# 7.0 können Sie auch andere Rückgabetypen angeben, vorausgesetzt, der Typ enthält eine `GetAwaiter`-Methode. Ein Beispiel eines solchen Typs ist <xref:System.Threading.Tasks.ValueTask%601>. Er ist im NuGet-Paket [System.Threading.Tasks.Extension](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) verfügbar.

Im folgenden Beispiel wird gezeigt, wie Sie eine Methode deklarieren und aufrufen, die <xref:System.Threading.Tasks.Task%601> oder <xref:System.Threading.Tasks.Task> zurückgibt:

```csharp
async Task<int> GetTaskOfTResultAsync()
{
    int hours = 0;
    await Task.Delay(0);

    return hours;
}


Task<int> returnedTaskTResult = GetTaskOfTResultAsync();
int intResult = await returnedTaskTResult;
// Single line
// int intResult = await GetTaskOfTResultAsync();

async Task GetTaskAsync()
{
    await Task.Delay(0);
    // No return statement needed
}

Task returnedTask = GetTaskAsync();
await returnedTask;
// Single line
await GetTaskAsync();
```

Jede zurückgegebene Aufgabe stellt derzeit ausgeführte Arbeit dar. Eine Aufgabe kapselt Informationen über den Zustand des asynchronen Prozesses und schließlich entweder das Endergebnis aus dem Prozess oder die Ausnahme, die durch einen Prozessfehler verursacht wird.

Eine asynchrone Methode kann auch den Rückgabetyp `void` aufweisen. Dieser Rückgabetyp wird hauptsächlich zum Definieren von Ereignishandlern verwendet, wobei ein `void`-Rückgabetyp erforderlich ist. Asynchrone Ereignishandler dienen häufig als Ausgangspunkt für asynchrone Programme.

Auf eine asynchrone Methode, die einen `void`-Rückgabetyp aufweist, kann nicht gewartet werden, und der Aufrufer einer Methode, die „void“ zurückgibt, kann keine Ausnahmen abfangen, die von der Methode ausgelöst werden.

Eine asynchrone Methode kann keine [in](../../../language-reference/keywords/in-parameter-modifier.md)-, [ref](../../../language-reference/keywords/ref.md)- oder [out](../../../language-reference/keywords/out-parameter-modifier.md)-Parameter deklarieren. Die Methode kann jedoch Methoden aufrufen, die solche Parameter aufweisen. Genauso kann eine async-Methode keinen Wert nach Verweis zurückgeben, obwohl sie Methoden mit ref-Rückgabewerten aufrufen kann.

Weitere Informationen und Beispiele finden Sie unter [Asynchrone Rückgabetypen (C#)](async-return-types.md). Weitere Informationen zum Abfangen von Ausnahmen in async-Methoden finden Sie unter [try-catch](../../../language-reference/keywords/try-catch.md).

Asynchrone APIs in der Windows-Runtime-Programmierung weisen einen der folgenden Rückgabetypen auf, die Tasks ähnlich sind:

- <xref:Windows.Foundation.IAsyncOperation%601>, was <xref:System.Threading.Tasks.Task%601> entspricht.
- <xref:Windows.Foundation.IAsyncAction>, was <xref:System.Threading.Tasks.Task> entspricht.
- <xref:Windows.Foundation.IAsyncActionWithProgress%601>
- <xref:Windows.Foundation.IAsyncOperationWithProgress%602>

## <a name="naming-convention"></a><a name="BKMK_NamingConvention"></a> Benennungskonvention

Üblicherweise sollten die Namen von Methoden, die in der Regel awaitable-Typen zurückgeben (z. B. `Task`, `Task<T>`, `ValueTask`, `ValueTask<T>`), auf „Async“ enden. Methoden, die einen asynchronen Vorgang starten, aber keinen awaitable-Typ zurückgeben, sollten nicht auf „Async“ enden, sondern mit „Begin“, „Start“ oder einem ähnlichen Verb beginnen, sodass eindeutig ist, dass diese Methode nicht das Ergebnis des Vorgangs zurückgibt bzw. auslöst.

Sie können die Konvention ignorieren, wenn ein Ereignis, eine Basisklasse oder ein Schnittstellenvertrag einen anderen Namen vorsieht. Beispielsweise sollten Sie allgemeine Ereignishandler wie `OnButtonClick` nicht umbenennen.

## <a name="related-topics-and-samples-visual-studio"></a><a name="BKMK_RelatedTopics"></a> Verwandte Themen und Beispiele (Visual Studio)

| Titel | Beschreibung | Beispiel |
|--|--|--|
| [Vorgehensweise: Paralleles Erstellen mehrerer Webanforderungen mit async und await (C#)](./index.md) | Veranschaulicht, wie mehrere Aufgaben gleichzeitig gestartet werden. | [Async Sample: Make Multiple Web Requests in Parallel](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e) (Asynchrones Beispiel: Paralleles Erstellen mehrerer Webanforderungen) |
| [Asynchrone Rückgabetypen (C#)](async-return-types.md) | Es werden die Typen veranschaulicht, die asynchrone Methoden zurückgeben können, und es wird erklärt, wann die einzelnen Typen geeignet sind. |  |
| Abbrechen von Aufgaben mit einem Abbruchtoken als Signalisierungsmechanismus | Zeigt, wie die folgenden Funktionen der asynchronen Lösung hinzugefügt werden:<br><br> - [Abbrechen einer Aufgabenliste (C#)](cancel-an-async-task-or-a-list-of-tasks.md)<br>- [Abbrechen von Aufgaben nach einem bestimmten Zeitraum (C#)](cancel-async-tasks-after-a-period-of-time.md)<br>- [Verarbeiten asynchroner Aufgaben nach Abschluss (C#)](start-multiple-async-tasks-and-process-them-as-they-complete.md) |  |
| [Verwenden von Async für den Dateizugriff (C#)](using-async-for-file-access.md) | Listet die Vorteile der Verwendung von "async" und "await" für den Zugriff auf Dateien auf und veranschaulicht sie. |  |
| [Aufgabenbasiertes asynchrones Muster](../../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) | In diesem Artikel wird ein asynchrones Muster beschrieben. Dieses Muster basiert auf den Typen <xref:System.Threading.Tasks.Task> und <xref:System.Threading.Tasks.Task%601>. |  |
| [Videos zur asynchronen Programmierung auf Channel 9](https://channel9.msdn.com/search?term=async%20&type=All#pubDate=year&ch9Search&lang-en=en) | Stellt Links zu einer Vielzahl von Videos über die asynchrone Programmierung bereit. |  |

## <a name="see-also"></a>Siehe auch

- [async](../../../language-reference/keywords/async.md)
- [await](../../../language-reference/operators/await.md)
- [Asynchrone Programmierung](../../../async.md)
- [Async (Übersicht)](../../../../standard/async.md)
