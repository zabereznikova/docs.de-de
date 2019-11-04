---
title: Leitfaden zur Verwendung von Memory<T> und Span<T>
ms.date: 10/01/2018
helpviewer_keywords:
- Memory&lt;T&gt; and Span&lt;T&gt; best practices
- using Memory&lt;T&gt; and Span&lt;T&gt;
ms.openlocfilehash: 0a614f628faa98be778c627573e4dddc462c9107
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121963"
---
# <a name="memoryt-and-spant-usage-guidelines"></a>Leitfaden zur Verwendung von Memory\<T> und Span\<T>

.NET Core enthält eine Reihe von Typen, die eine beliebige zusammenhängende Speicherregion darstellen. .NET Core 2.0 hat <xref:System.Span%601> und <xref:System.ReadOnlySpan%601> eingeführt. Dabei handelt es sich um einfache Speicherpuffer, die durch verwalteten oder nicht verwalteten Speicher gesichert werden können. Da diese Typen nur im Stapel gespeichert werden können, sind sie für eine Reihe von Szenarien ungeeignet. Hierzu zählen unter anderem asynchrone Methodenaufrufe. .NET Core 2.1 fügt eine Reihe von zusätzlichen Typen hinzu, einschließlich <xref:System.Memory%601>, <xref:System.ReadOnlyMemory%601>, <xref:System.Buffers.IMemoryOwner%601> und <xref:System.Buffers.MemoryPool%601>. Wie <xref:System.Span%601> kann auch <xref:System.Memory%601> und die verwandten Typen durch verwalteten und nicht verwalteten Speicher gesichert werden. Im Gegensatz zu <xref:System.Span%601> kann <xref:System.Memory%601> im verwalteten Heap gespeichert werden.

Sowohl <xref:System.Span%601> als auch <xref:System.Memory%601> sind Puffer von strukturierten Daten, die in Pipelines verwendet werden können. Das heißt, sie sind so konzipiert, dass ein Teil oder alle Daten effizient an Komponenten in der Pipeline übergeben werden können, die sie verarbeiten und optional den Puffer modifizieren können. Da <xref:System.Memory%601> und die zugehörigen Typen von mehreren Komponenten oder von mehreren Threads aufgerufen werden können, ist es wichtig, dass Entwickler einige Standardnutzungsrichtlinien befolgen, um robusten Code zu generieren.

## <a name="owners-consumers-and-lifetime-management"></a>Besitzer, Consumer und Verwaltung der Lebensdauer

Da Puffer zwischen APIs ausgetauscht werden können und auf Puffer manchmal über mehrere Threads zugegriffen werden kann, ist es wichtig, die Lebensdauerverwaltung zu berücksichtigen. Es gibt drei grundlegende Konzepte:

- **Besitz**. Der Besitzer einer Pufferinstanz ist für das die Verwaltung der Lebensdauer verantwortlich, einschließlich der Zerstörung des Puffers, wenn er nicht mehr in Gebrauch ist. Alle Puffer haben nur einen einzigen Besitzer. Im Allgemeinen ist der Besitzer die Komponente, die den Puffer erstellt hat, oder die den Puffer von einer Factory erhalten hat. Der Besitz kann auch übertragen werden; **Komponente-A** kann die Kontrolle über den Puffer an **Komponente-B** abgeben, wobei **Komponente-A** den Puffer nicht mehr verwenden darf, und **Komponente-B** wird für die Zerstörung des Puffers verantwortlich, wenn er nicht mehr verwendet wird.

- **Verbrauch**. Der Consumer einer Pufferinstanz darf die Pufferinstanz nutzen, indem er aus ihr liest und eventuell in sie schreibt. Puffer können jeweils einen Consumer haben, es sei denn, es ist ein externer Synchronisationsmechanismus vorgesehen. Beachten Sie, dass der aktive Consumer eines Puffers nicht unbedingt der Besitzer des Puffers ist.

- **Leasedauer**. Die Leasedauer ist die Zeitspanne, in der eine bestimmte Komponente als Consumer des Puffers zugelassen wird.

Im folgenden Pseudocodebeispiel werden diese drei Konzepte veranschaulicht. Es beinhaltet eine `Main`-Methode, die einen <xref:System.Memory%601>-Puffer vom Typ <xref:System.Char> instanziiert, die `WriteInt32ToBuffer`-Methode aufruft, um die Zeichenfolgendarstellung einer ganzen Zahl in den Puffer zu schreiben, und dann die `DisplayBufferToConsole`-Methode aufruft, um den Wert des Puffers anzuzeigen.

```csharp
using System;

class Program
{
    // Write 'value' as a human-readable string to the output buffer.
    void WriteInt32ToBuffer(int value, Buffer buffer);

    // Display the contents of the buffer to the console.
    void DisplayBufferToConsole(Buffer buffer);

    // Application code
    static void Main()
    {
        var buffer = CreateBuffer();
        try
        {
            int value = Int32.Parse(Console.ReadLine());
            WriteInt32ToBuffer(value, buffer);
            DisplayBufferToConsole(buffer);
        }
        finally
        {
            buffer.Destroy();
        }
    }
}
```

Die `Main`-Methode erstellt den Puffer (in diesem Fall eine <xref:System.Span%601>-Instanz) und damit seinen Besitzer. Daher ist `Main` dafür verantwortlich, den Puffer zu zerstören, wenn er nicht mehr verwendet wird. Dies geschieht durch Aufrufen der <xref:System.Span%601.Clear?displayProperty=nameWithType> Methode des Puffers. (Die <xref:System.Span%601.Clear>-Methode löscht hier tatsächlich den Speicher des Puffers; die <xref:System.Span%601>-Struktur verfügt über keine Methode, die den Puffer zerstört.)

Der Puffer hat zwei Consumer: `WriteInt32ToBuffer` und `DisplayBufferToConsole`. Es gibt immer nur jeweils einen Consumer (zuerst `WriteInt32ToBuffer`, dann `DisplayBufferToConsole`), und keiner der Consumer besitzt den Puffer. Beachten Sie auch, dass „Consumer“ in diesem Zusammenhang keine schreibgeschützte Ansicht des Puffers impliziert; Consumer können den Inhalt des Puffers ändern, wie `WriteInt32ToBuffer`, wenn sie eine Lese-/Schreibansicht des Puffers erhalten.

Die `WriteInt32ToBuffer`-Methode verfügt über eine Leasedauer (kann den Puffer zwischen dem Start des Methodenaufrufs und der Zeit, die die Methode zurückgibt, verbrauchen). Ebenso hat `DisplayBufferToConsole` eine Leasingdauer für den Puffer, während er ausgeführt wird, und die Leasedauer wird freigegeben, wenn die Methode entladen wird. (Es gibt keine API für die Leaseverwaltung; eine „Leasedauer“ ist nur ein Konzept.)

## <a name="memoryt-and-the-ownerconsumer-model"></a>Memory\<T > und das Besitzer/Consumer-Modell

Wie im Abschnitt [Besitzer, Consumer und Verwaltung der Lebensdauer](#owners-consumers-and-lifetime-management) beschrieben, hat ein Puffer immer einen Besitzer. .NET Core unterstützt zwei Besitzmodelle:

- Ein Modell, das alleinigen Besitz unterstützt. Ein Puffer hat einen einzigen Besitzer für seine gesamte Lebensdauer.

- Ein Modell, das die Besitzübertragung unterstützt. Der Besitz eines Puffers kann von seinem ursprünglichen Besitzer (seinem Ersteller) auf eine andere Komponente übertragen werden, die dann für die Lebensdauerverwaltung des Puffers verantwortlich ist. Dieser Besitzer kann seinerseits den Besitz auf eine andere Komponente übertragen, und so weiter.

Sie verwenden die <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>-Schnittstelle, um den Besitz eines Puffers explizit zu verwalten. <xref:System.Buffers.IMemoryOwner%601> unterstützt beide Besitzmodelle. Die Komponente, die einen Verweis <xref:System.Buffers.IMemoryOwner%601> hat, besitzt den Puffer. Das folgende Beispiel verwendet eine <xref:System.Buffers.IMemoryOwner%601?>-Instanz, um den Besitz eines <xref:System.Memory%601>-Puffers anzugeben.

[!code-csharp[ownership](~/samples/snippets/standard/buffers/memory-t/owner/owner.cs)]

Wir können dieses Beispiel auch mit dem [`using`](../../csharp/language-reference/keywords/using-statement.md) schreiben:

[!code-csharp[ownership-using](~/samples/snippets/standard/buffers/memory-t/owner-using/owner-using.cs)]

In diesem Code:

- Die `Main`-Methode enthält den Verweis auf die <xref:System.Buffers.IMemoryOwner%601>-Instanz, sodass die `Main`-Methode der Besitzer des Puffers ist.

- Die `WriteInt32ToBuffer`- und `DisplayBufferToConsole`-Methode akzeptieren <xref:System.Memory%601> als öffentliche API. Daher sind sie der Consumer des Puffers. Und sie können ihn nur jeweils einzeln verbrauchen.

Obwohl die `WriteInt32ToBuffer`-Methode dazu bestimmt ist, einen Wert in den Puffer zu schreiben, ist die `DisplayBufferToConsole`-Methode dies nicht. Um dies anzugeben, hätte sie ein Argument vom Typ <xref:System.ReadOnlyMemory%601> akzeptieren können. Weitere Informationen zu <xref:System.ReadOnlyMemory%601> finden Sie unter [Regel 2: ReadOnlySpan\<T> oder ReadOnlyMemory\<T> verwenden, wenn der Puffer schreibgeschützt sein soll](#rule-2).

### <a name="ownerless-memoryt-instances"></a>Memory\<T>-Instanzen ohne Besitzer

Sie können einen <xref:System.Memory%601>-Instanz ohne die Verwendung von <xref:System.Buffers.IMemoryOwner%601> erstellen. In diesem Fall ist der Besitz des Puffers eher implizit als explizit, und es wird nur das Einzelbesitzermodell unterstützt. Gehen Sie dafür so vor:

- Direkter Aufruf eines der <xref:System.Memory%601>-Konstruktoren, Übergabe eines `T[]`, wie im folgenden Beispiel.

- Aufrufen der [String.AsMemory](xref:System.MemoryExtensions.AsMemory(System.String))-Erweiterungsmethode zur Erstellung einer `ReadOnlyMemory<char>`-Instanz.

[!code-csharp[ownerless-memory](~/samples/snippets/standard/buffers/memory-t/ownerless/ownerless.cs)]

Die Methode, die die <xref:System.Memory%601>-Instanz initial erstellt, ist der implizite Besitzer des Puffers. Der Besitz kann nicht auf eine andere Komponente übertragen werden, da es keine <xref:System.Buffers.IMemoryOwner%601>-Instanz gibt, die die Übertragung vereinfacht. (Alternativ ist es auch vorstellbar, dass der Garbage Collector der Runtime den Puffer besitzt und alle Methoden nur den Puffer verbrauchen.)

## <a name="usage-guidelines"></a>Verwendungsrichtlinien

Da ein Speicherblock einen Besitzer hat, aber an mehrere Komponenten übergeben werden soll, von denen einige gleichzeitig auf einem bestimmten Speicherblock arbeiten können, ist es wichtig, Richtlinien für die Verwendung von <xref:System.Memory%601> und <xref:System.Span%601> festzulegen.  Richtlinien sind aus folgendem Grund erforderlich:

- Es ist möglich, dass eine Komponente einen Verweis auf einen Speicherblock behält, nachdem sein Besitzer ihn freigegeben hat.

- Es ist möglich, dass eine Komponente gleichzeitig mit einer anderen Komponente auf einem Puffer arbeitet, wodurch die Daten im Puffer beschädigt werden.

- Durch die Stapelzuordnung von <xref:System.Span%601> wird zwar die Leistung optimiert und <xref:System.Span%601> zum bevorzugten Typ für den Betrieb auf einem Speicherblock, aber auch <xref:System.Span%601> einigen bedeutenden Einschränkungen unterworfen. Es ist wichtig zu wissen, wann einen <xref:System.Span%601> und wann <xref:System.Memory%601> verwenden sollten.

Nachfolgend finden Sie unsere Empfehlungen für den erfolgreichen Einsatz von <xref:System.Memory%601> und den verwandten Typen. Beachten Sie, dass die Richtlinien, die für <xref:System.Memory%601> und <xref:System.Span%601> gelten, auch für <xref:System.ReadOnlyMemory%601> und <xref:System.ReadOnlySpan%601> gelten, sofern nicht ausdrücklich anders angegeben.

**Regel 1: Für eine synchrone API Span\<T> anstelle von Memory\<T> als Parameter verwenden, wenn möglich.**

<xref:System.Span%601> ist vielseitiger als <xref:System.Memory%601> und kann eine größere Anzahl von zusammenhängenden Speicherpuffern darstellen. <xref:System.Span%601> bietet außerdem eine bessere Leistung als <xref:System.Memory%601>. Schließlich können Sie die <xref:System.Memory%601.Span?displayProperty=nameWithType>-Eigenschaft verwenden, um eine <xref:System.Memory%601>-Instanz in eine <xref:System.Span%601>-Instanz zu konvertieren, obwohl eine Span\<T>-in-Memory\<T>-Konvertierung nicht möglich ist. Wenn Ihre Aufrufer also eine <xref:System.Memory%601>-Instanz haben, können sie Ihre Methoden trotzdem mit <xref:System.Span%601>-Parametern aufrufen.

Die Verwendung eines Parameters vom Typ <xref:System.Span%601> anstelle von Typ <xref:System.Memory%601> unterstützt Sie auch dabei, eine korrekte Implementierung einer konsumierenden Methode zu schreiben. Die Kompilierzeit wird automatisch überprüft, um sicherzustellen, dass Sie nicht versuche, nach Ablauf der Leasedauer auf den Puffer zuzugreifen (weitere Informationen dazu im weiteren Verlauf).

Manchmal müssen Sie einen <xref:System.Memory%601>-Parameter anstelle eines <xref:System.Span%601>-Parameters verwenden, auch wenn Sie vollständig synchron sind. Vielleicht akzeptiert eine API, von der Sie abhängen, nur <xref:System.Memory%601>-Argumente. Dies ist in Ordnung, aber beachten Sie die Vor- und Nachteile, die bei der synchronen Verwendung von <xref:System.Memory%601> auftreten.

<a name="rule-2" />

**Regel 2: ReadOnlySpan\<T> oder ReadOnlyMemory\<T> verwenden, wenn der Puffer schreibgeschützt sein soll.**

In den früheren Beispielen liest die `DisplayBufferToConsole`-Methode nur aus dem Puffer und ändert den Inhalt des Puffers nicht. Die Methodensignatur sollte wie folgt geändert werden.

```csharp
void DisplayBufferToConsole(ReadOnlyMemory<char> buffer);
```

Wenn wir diese Regel und Regel 1 kombinieren, können wir die Methodensignatur wie folgt umschreiben:

```csharp
void DisplayBufferToConsole(ReadOnlySpan<char> buffer);
```

Die `DisplayBufferToConsole`-Methode funktioniert nun mit praktisch jedem denkbaren Puffertyp: `T[]`, Speicher, der mit [stackalloc](../../csharp/language-reference/operators/stackalloc.md) zugewiesen wurde, und so weiter. Sie können einen <xref:System.String> sogar direkt übergeben!

**Regel 3: Wenn Ihre Methode Memory\<T> akzeptiert und `void` zurückgibt, dürfen Sie die Memory\<T>-Instanz nicht verwenden, nachdem Ihre Methode ein Ergebnis zurückgegeben hat.**

Dies bezieht sich auf das bereits erwähnte Konzept der „Leasedauer“. Die Leasedauer für eine Methode auf der <xref:System.Memory%601>-Instanz, die „void“ zurückgibt, beginnt, wenn die Methode aufgerufen wird, und endet, wenn die Methode beendet wird. Schauen Sie sich das folgende Beispiel an, in dem basierend auf der Eingabe von der Konsole ein `Log` aufgerufen wird.

[!code-csharp[void-returning](~/samples/snippets/standard/buffers/memory-t/void-returning/void-returning.cs#1)]

Wenn `Log` eine vollständig synchrone Methode ist, verhält sich dieser Code wie erwartet, da es zu einem bestimmten Zeitpunkt nur einen aktiven Verbraucher der Speicherinstanz gibt.
Aber stellen Sie sich vor, `Log` hat stattdessen diese Implementierung.

```csharp
// !!! INCORRECT IMPLEMENTATION !!!
static void Log(ReadOnlyMemory<char> message)
{
    // Run in background so that we don't block the main thread while performing IO.
    Task.Run(() =>
    {
        StreamWriter sw = File.AppendText(@".\input-numbers.dat");
        sw.WriteLine(message);
    });
}
```

In dieser Implementierung verstößt `Log` gegen die Leasedauer, weil immer noch versucht wird, die <xref:System.Memory%601>-Instanz im Hintergrund zu verwenden, nachdem die ursprüngliche Methode zurückgegeben wurde. Die `Main`-Methode könnte den Puffer verändern, während `Log` versucht, aus ihm zu lesen. Das könnte zu einer Datenbeschädigung führen.

Es gibt mehrere Möglichkeiten, dieses Problem zu lösen:

- Die `Log`-Methode kann <xref:System.Threading.Tasks.Task> anstelle von `void` zurückgeben, wie es bei der folgenden Implementierung der `Log`-Methode der Fall ist.

   [!code-csharp[task-returning](~/samples/snippets/standard/buffers/memory-t/task-returning2/task-returning2.cs#1)]

- `Log` kann stattdessen wie folgt implementiert werden:

   [!code-csharp[defensive-copy](~/samples/snippets/standard/buffers/memory-t/task-returning/task-returning.cs#1)]

**Regel 4: Wenn Ihre Methode Memory\<T> akzeptiert und einen Task zurückgibt, dürfen Sie die Memory\<T>-Instanz nicht verwenden, nachdem der Task in einen Endzustand übergeht.**

Dies ist nur die asynchrone Variante von Regel 3. Die `Log`-Methode aus dem früheren Beispiel kann wie folgt geschrieben werden, um dieser Regel zu entsprechen:

[!code-csharp[task-returning-async](~/samples/snippets/standard/buffers/memory-t/void-returning-async/void-returning-async.cs#1)]

Hier bedeutet „Endzustand“, dass der Task in einen abgeschlossenen, fehlerhaften oder abgebrochenen Zustand übergeht. Anders ausgedrückt bedeutet „Endzustand“ „alles, was das Warten auf das Auslösen oder Fortsetzen der Ausführung verursachen würde“.

Diese Anleitung gilt für Methoden, die <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask%601> oder einen ähnlichen Typen zurückgeben würden.

**Regel 5: Wenn Ihr Konstruktor Memory\<T> als Parameter akzeptiert, werden Instanzmethoden auf dem konstruierten Objekt als Consumer der Memory\<T>-Instanz angenommen.**

Betrachten Sie das folgende Beispiel:

```csharp
class OddValueExtractor
{
    public OddValueExtractor(ReadOnlyMemory<int> input);
    public bool TryReadNextOddValue(out int value);
}

void PrintAllOddValues(ReadOnlyMemory<int> input)
{
    var extractor = new OddValueExtractor(input);
    while (extractor.TryReadNextOddValue(out int value))
    {
      Console.WriteLine(value);
    }
}
```

Hier akzeptiert der `OddValueExtractor`-Konstruktor `ReadOnlyMemory<int>` als Konstruktorparameter, sodass der Konstruktor selbst ein Consumer der `ReadOnlyMemory<int>`-Instanz ist, und alle Instanzmethoden auf dem zurückgegebenen Wert sind auch Consumer der ursprünglichen `ReadOnlyMemory<int>`-Instanz. Das bedeutet, dass `TryReadNextOddValue` die `ReadOnlyMemory<int>`-Instanz verbraucht, obwohl die Instanz nicht direkt an die `TryReadNextOddValue`-Methode übergeben wird.

**Regel 6: Wenn Sie eine einstellbare Memory\<T>-typisierte Eigenschaft (oder eine gleichwertige Instanzmethode) für Ihren Typ haben, werden Instanzmethoden auf diesem Objekt als Consumer der Memory\<T>-Instanz angenommen.**

Dies ist eigentlich nur eine Variante der Regel 5. Diese Regel existiert, weil davon ausgegangen wird, dass Property Setter oder gleichwertige Methoden ihre Eingaben erfassen und beibehalten, sodass Instanzmethoden auf demselben Objekt den erfassten Zustand verwenden können.

Das folgende Beispiel löst diese Regel aus:

```csharp
class Person
{
    // Settable property.
    public Memory<char> FirstName { get; set; }

    // alternatively, equivalent "setter" method
    public SetFirstName(Memory<char> value);

    // alternatively, a public settable field
    public Memory<char> FirstName;
}
```

**Regel 7: Wenn Sie einen IMemoryOwner\<T> Verweis haben, müssen Sie ihn irgendwann verwerfen oder den Besitz übertragen (aber nicht beides).**

Da eine <xref:System.Memory%601>-Instanz entweder durch verwalteten oder nicht verwalteten Speicher gesichert werden kann, muss der Besitzer <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> aufrufen, wenn die Arbeit an der <xref:System.Memory%601>-Instanz abgeschlossen ist. Alternativ kann der Besitzer die Besitzrechte an der <xref:System.Buffers.IMemoryOwner%601>-Instanz auf eine andere Komponente übertragen, wobei die erwerbende Komponente dann für den Aufruf von <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> zum gegebenen Zeitpunkt (mehr dazu später) verantwortlich ist.

Wenn die <xref:System.Buffers.MemoryPool%601.Dispose%2A>-Methode nicht aufgerufen wird, kann dies zu nicht verwalteten Speicherverlusten oder anderen Leistungseinbußen führen.

Diese Regel gilt auch für Code, der Factorymethoden wie <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType> aufruft. Der Aufrufer wird zum Besitzer des zurückgegebenen <xref:System.Buffers.IMemoryOwner%601> und ist verantwortlich für das Verwerfen der Instanz, wenn sie beendet ist.

**Regel 8: Wenn Sie einen IMemoryOwner\<T>-Parameter in Ihrer API-Oberfläche haben, akzeptieren Sie den Besitz dieser Instanz.**

Die Annahme einer Instanz dieses Typs signalisiert, dass Ihre Komponente beabsichtigt, den Besitz dieser Instanz zu übernehmen. Ihre Komponente ist für das ordnungsgemäße Verwerfen gemäß Regel 7 verantwortlich.

Jede Komponente, die den Besitz der <xref:System.Buffers.IMemoryOwner%601>-Instanz auf eine andere Komponente überträgt, sollte diese Instanz nach Abschluss des Methodenaufrufs nicht mehr verwenden.

> [!IMPORTANT]
> Wenn Ihr Konstruktor <xref:System.Buffers.IMemoryOwner%601> als Parameter akzeptiert, sollte sein Typ <xref:System.IDisposable> implementieren, und Ihre <xref:System.IDisposable.Dispose%2A>-Methode sollte <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> aufrufen.

**Regel 9: Wenn Sie eine synchrone P/Invoke-Methode umschließen, sollte Ihre API Span\<T> als Parameter akzeptieren.**

Gemäß Regel 1 ist <xref:System.Span%601> im Allgemeinen der richtige Typ für synchrone APIs. Sie können <xref:System.Span%601>-Instanzen über das Schlüsselwort [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) anheften, wie im folgenden Beispiel.

```csharp
using System.Runtime.InteropServices;

[DllImport(...)]
private static extern unsafe int ExportedMethod(byte* pbData, int cbData);

public unsafe int ManagedWrapper(Span<byte> data)
{
    fixed (byte* pbData = &MemoryMarshal.GetReference(data))
    {
        int retVal = ExportedMethod(pbData, data.Length);

        /* error checking retVal goes here */

        return retVal;
    }
}
```

Im vorherigen Beispiel kann `pbData` Null sein, wenn beispielsweise der Eingangs-Span-Wert leer ist. Wenn die exportierte Methode unbedingt erfordert, dass `pbData` nicht Null ist, auch wenn `cbData` 0 ist, kann die Methode wie folgt implementiert werden:

```csharp
public unsafe int ManagedWrapper(Span<byte> data)
{
    fixed (byte* pbData = &MemoryMarshal.GetReference(data))
    {
        byte dummy = 0;
        int retVal = ExportedMethod((pbData != null) ? pbData : &dummy, data.Length);

        /* error checking retVal goes here */

        return retVal;
    }
}
```

**Regel 10: Wenn Sie eine synchrone P/Invoke-Methode umschließen, sollte Ihre API Memory\<T> als Parameter akzeptieren.**

Da Sie das Schlüsselwort [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) nicht über asynchrone Vorgänge hinweg verwenden können, verwenden Sie die <xref:System.Memory%601.Pin%2A?displayProperty=nameWithType>-Methode, um <xref:System.Memory%601>-Instanzen anzuheften, unabhängig von der Art des zusammenhängenden Speichers, den die Instanz repräsentiert. Das folgende Beispiel zeigt, wie man diese API verwendet, um einen asynchronen P/Invoke-Aufruf durchzuführen.

```csharp
using System.Runtime.InteropServices;

[UnmanagedFunctionPointer(...)]
private delegate void OnCompletedCallback(IntPtr state, int result);

[DllImport(...)]
private static extern unsafe int ExportedAsyncMethod(byte* pbData, int cbData, IntPtr pState, IntPtr lpfnOnCompletedCallback);

private static readonly IntPtr _callbackPtr = GetCompletionCallbackPointer();

public unsafe Task<int> ManagedWrapperAsync(Memory<byte> data)
{
    // setup
    var tcs = new TaskCompletionSource<int>();
    var state = new MyCompletedCallbackState
    {
        Tcs = tcs
    };
    var pState = (IntPtr)GCHandle.Alloc(state);

    var memoryHandle = data.Pin();
    state.MemoryHandle = memoryHandle;

    // make the call
    int result;
    try
    {
        result = ExportedAsyncMethod((byte*)memoryHandle.Pointer, data.Length, pState, _callbackPtr);
    }
    catch
    {
        ((GCHandle)pState).Free(); // cleanup since callback won't be invoked
        memoryHandle.Dispose();
        throw;
    }

    if (result != PENDING)
    {
        // Operation completed synchronously; invoke callback manually
        // for result processing and cleanup.
        MyCompletedCallbackImplementation(pState, result);
    }

    return tcs.Task;
}

private static void MyCompletedCallbackImplementation(IntPtr state, int result)
{
    GCHandle handle = (GCHandle)state;
    var actualState = (MyCompletedCallbackState)state;
    handle.Free();
    actualState.MemoryHandle.Dispose();

    /* error checking result goes here */

    if (error)
    {
        actualState.Tcs.SetException(...);
    }
    else
    {
        actualState.Tcs.SetResult(result);
    }
}

private static IntPtr GetCompletionCallbackPointer()
{
    OnCompletedCallback callback = MyCompletedCallbackImplementation;
    GCHandle.Alloc(callback); // keep alive for lifetime of application
    return Marshal.GetFunctionPointerForDelegate(callback);
}

private class MyCompletedCallbackState
{
    public TaskCompletionSource<int> Tcs;
    public MemoryHandle MemoryHandle;
}
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Memory%601?displayProperty=nameWithType>
- <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>
- <xref:System.Span%601?displayProperty=nameWithType>
