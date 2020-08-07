---
title: Implementieren einer Dispose-Methode
description: In diesem Artikel erfahren Sie, wie Sie die Dispose-Methode implementieren, die nicht verwaltete Ressourcen freigibt, die von Ihrem Code in .NET verwendet werden.
ms.date: 05/27/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- garbage collection, Dispose method
ms.assetid: eb4e1af0-3b48-4fbc-ad4e-fc2f64138bf9
ms.openlocfilehash: 4f0cc9b88947d60638057ca83adb7f2e141c5d14
ms.sourcegitcommit: 7499bdb428d63ed0e19e97f54d3d576c41598659
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2020
ms.locfileid: "87455739"
---
# <a name="implement-a-dispose-method"></a>Implementieren einer Dispose-Methode

Die Implementierung der <xref:System.IDisposable.Dispose%2A>-Methode ist hauptsächlich für die Freigabe nicht verwalteter Ressourcen bestimmt. Beim Arbeiten mit Instanzmembern, die <xref:System.IDisposable>-Implementierungen sind, werden <xref:System.IDisposable.Dispose%2A>-Aufrufe häufig weitergegeben. Es gibt weitere Gründe für die Implementierung von <xref:System.IDisposable.Dispose%2A>, wie beispielsweise das Freigeben von zugeordnetem Arbeitsspeicher, das Entfernen eines Elements, das einer Auflistung hinzugefügt wurde, oder das Signalisieren der Aufhebung einer abgerufenen Sperre.

Der [.NET-Garbage Collector](index.md) ordnet nicht verwalteten Arbeitsspeicher weder zu noch gibt er diesen frei. Das Muster für das Verwerfen eines Objekts, Dispose-Muster genannt, legt die Ordnung für die Lebensdauer eines Objekts fest. Das Dispose-Muster wird für Objekte verwendet, die die <xref:System.IDisposable>-Schnittstelle implementieren, und ist üblich bei der Interaktion mit Datei- und Pipehandles, Registrierungshandles, Wait-Handles oder Zeigern auf Blöcke nicht verwalteten Speichers. Dies liegt daran, dass der Garbage Collector nicht verwaltete Objekte nicht freigeben kann.

Um sicherzustellen, dass Ressourcen immer entsprechend bereinigt werden, sollte eine <xref:System.IDisposable.Dispose%2A>-Methode derart idempotent sein, dass sie mehrmals aufgerufen werden kann, ohne eine Ausnahme auszulösen. Außerdem sollten nachfolgende Aufrufe von <xref:System.IDisposable.Dispose%2A> nichts bewirken.

Das Codebeispiel für die <xref:System.GC.KeepAlive%2A?displayProperty=nameWithType>-Methode veranschaulicht, wie durch Garbage Collection die Ausführung eines Finalizers bewirkt werden kann, während ein nicht verwalteter Verweis auf das Objekt oder den Member weiterhin verwendet wird. Sie sollten <xref:System.GC.KeepAlive%2A?displayProperty=nameWithType> verwenden, damit das Objekt von Beginn der aktuellen Routine bis zum Zeitpunkt des Aufrufs dieser Methode von der Garbage Collection ausgenommen wird.

## <a name="safe-handles"></a>Sichere Handles

Das Schreiben von Code für den Finalizer eines Objekts ist eine komplexe Aufgabe, die Probleme verursachen kann, wenn sie nicht ordnungsgemäß gelöst wird. Daher wird empfohlen, <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>-Objekte zu erstellen, anstatt einen Finalizer zu implementieren.

Bei einem <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> handelt es sich um einen abstrakten verwalteten Typ, der einen <xref:System.IntPtr?displayProperty=nameWithType> umschließt, der eine nicht verwaltete Ressource identifiziert. Unter Windows könnte er ein Handle unter UNIX identifizieren, einen Dateideskriptor. Er bietet sämtliche erforderliche Logik, um sicherzustellen, dass diese Ressource einmalig und nur einmal freigegeben wird, wenn das `SafeHandle` verworfen wird oder alle Verweise auf das `SafeHandle` gelöscht wurden und die `SafeHandle`-Instanz abgeschlossen wurde.

<xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> ist eine abstrakte Basisklasse. Abgeleitete Klassen stellen bestimmte Instanzen für verschiedene Arten von Handles bereit. Diese abgeleiteten Klassen überprüfen, welche Werte für den <xref:System.IntPtr?displayProperty=nameWithType> als ungültig angesehen werden, und wie das Handle tatsächlich freigegeben werden soll. <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> wird z. B. von `SafeHandle` abgeleitet, um `IntPtrs` zu umschließen, die geöffnete Dateihandles/Deskriptoren identifizieren, und überschreibt die <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle?displayProperty=nameWithType>-Methode, um sie zu schließen (über die `close`-Funktion unter UNIX oder `CloseHandle`-Funktion unter Windows). Die meisten APIs in .NET-Bibliotheken, die eine nicht verwaltete Ressource erstellen, umschließen sie in einem `SafeHandle` und geben dieses `SafeHandle` bei Bedarf zurück, anstatt den Rohzeiger zu übergeben. In Situationen, in denen Sie mit einer nicht verwalteten Komponente interagieren und einen `IntPtr` für eine nicht verwaltete Ressource erhalten, können Sie einen eigenen `SafeHandle`-Typ erstellen, um sie zu umschließen. Daher müssen nur wenige Nicht-`SafeHandle`-Typen Finalizer implementieren. Die meisten Implementierungen von Dispose-Mustern schließen nur andere verwaltete Ressourcen ein, von denen einige möglicherweise `SafeHandle`s sind.

Die folgenden abgeleiteten Klassen im <xref:Microsoft.Win32.SafeHandles>-Namespace stellen SafeHandles bereit:

- Die Klasse <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>, <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedFileHandle> und <xref:Microsoft.Win32.SafeHandles.SafePipeHandle>, für Dateien, Speicherabbilddateien und Pipes.
- Die <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle>-Klasse, für Speicheransichten.
- Die Klassen <xref:Microsoft.Win32.SafeHandles.SafeNCryptKeyHandle>, <xref:Microsoft.Win32.SafeHandles.SafeNCryptProviderHandle> und <xref:Microsoft.Win32.SafeHandles.SafeNCryptSecretHandle>, für Kryptografiekonstrukte.
- Die <xref:Microsoft.Win32.SafeHandles.SafeRegistryHandle>-Klasse, für Registrierungsschlüssel.
- Die <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle>-Klasse, für Wait-Handles.

## <a name="dispose-and-disposebool"></a>Dispose() und Dispose(bool)

Die <xref:System.IDisposable>-Schnittstelle erfordert die Implementierung einer einzelnen parameterlosen Methode, <xref:System.IDisposable.Dispose%2A>. Außerdem sollte jede nicht versiegelte Klasse über eine zusätzliche `Dispose(bool)`-Überladungsmethode verfügen, die implementiert werden soll:

- Eine nicht virtuelle `public`-<xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>-Implementierung (`NonInheritable` in Visual Basic), die keine Parameter aufweist.

- Eine `protected virtual`-`Dispose`-Methode (`Overridable` in Visual Basic) mit der folgenden Signatur:

  [!code-csharp[Conceptual.Disposable#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#8)]
  [!code-vb[Conceptual.Disposable#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#8)]

  > [!IMPORTANT]
  > Der `disposing`-Parameter sollte `false` sein, wenn er von einem Finalizer aufgerufen wird, und `true`, wenn er von der <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>-Methode aufgerufen wird. Dies bedeutet, dass er `true` ist, wenn er deterministisch aufgerufen wird, und `false`, wenn er nicht deterministisch aufgerufen wird.

### <a name="the-dispose-method"></a>Die Dispose()-Methode

Da die nicht virtuelle, parameterlose `public`-`Dispose`-Methode (`NonInheritable` in Visual Basic) von einem Consumer des Typs aufgerufen wird, hat sie den Zweck, nicht verwaltete Ressourcen freizugeben, eine generelle Bereinigung durchzuführen und anzugeben, dass der Finalizer, sofern vorhanden, nicht ausgeführt werden muss. Das Freigeben des tatsächlichen Speichers, der einem verwalteten Objekt zugeordnet ist, ist immer die Domäne des [Garbage Collectors](index.md). Daher weist sie eine Standardimplementierung auf:

[!code-csharp[Conceptual.Disposable#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#7)]
[!code-vb[Conceptual.Disposable#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#7)]

Die `Dispose`-Methode führt die Bereinigung aller Objekte aus, damit der Garbage Collector nicht mehr die <xref:System.Object.Finalize%2A?displayProperty=nameWithType>-Überschreibung der Objekte aufrufen muss. Daher verhindert der Aufruf der <xref:System.GC.SuppressFinalize%2A>-Methode, dass der Garbage Collector den Finalizer ausführt. Wenn der Typ keinen Finalizer aufweist, bleibt der Aufruf von <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> ohne Auswirkungen. Beachten Sie, dass die tatsächliche Bereinigung durch die `Dispose(bool)`-Methodenüberladung ausgeführt wird.

### <a name="the-disposebool-method-overload"></a>Die Dispose(bool)-Methodenüberladung

In der Überladung ist der `disposing`-Parameter ein <xref:System.Boolean>-Wert, der angibt, ob der Methodenaufruf von einer <xref:System.IDisposable.Dispose%2A>-Methode (deren Wert `true` ist) oder einem Finalizer (dessen Wert `false` ist) stammt.

Der Text der Methode besteht aus zwei Codeblöcken:

- Ein Block, der nicht verwaltete Ressourcen freigibt. Dieser Block wird unabhängig vom Wert des `disposing`-Parameters ausgeführt.
- Ein bedingter Block, der verwaltete Ressourcen freigibt. Dieser Block wird ausgeführt, wenn der Wert von `disposing` gleich `true` ist. Die verwalteten Ressourcen, die freigegeben werden, können Folgendes umfassen:

  - **Verwaltete Objekte, die <xref:System.IDisposable> implementieren.** Der bedingte Block kann verwendet werden, um deren <xref:System.IDisposable.Dispose%2A>-Implementierung aufzurufen (Weitergeben von Dispose-Aufrufen). Wenn Sie eine abgeleitete Klasse von <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> verwendet haben, um die nicht verwaltete Ressource zu umschließen, sollten Sie hier die <xref:System.Runtime.InteropServices.SafeHandle.Dispose?displayProperty=nameWithType>-Implementierung aufrufen.

  - **Verwaltete Objekte, die viel Arbeitsspeicher belegen oder knappe Ressourcen nutzen.** Weisen Sie `null` Verweise auf große verwaltete Objekte zu, damit sie eher unerreichbar sind. So werden sie schneller freigegeben, als wenn sie nicht deterministisch freigegeben würden.

Wenn der Methodenaufruf von einem Finalizer stammt, wird nur der Code ausgeführt, der nicht verwaltete Ressourcen freigibt. Der Implementierer ist dafür verantwortlich, sicherzustellen, dass der falsche Pfad nicht mit verwalteten Objekten interagiert, die möglicherweise freigegeben wurden. Dies ist wichtig, da die Reihenfolge, in der der Garbage Collector verwaltete Objekte während der Finalisierung zerstört, nicht deterministisch ist.

## <a name="cascade-dispose-calls"></a>Weitergeben von Dispose-Aufrufen

Wenn die Klasse ein Feld oder eine Eigenschaft besitzt und dessen/deren Typ <xref:System.IDisposable> implementiert, sollte die enthaltende Klasse auch <xref:System.IDisposable> implementieren. Eine Klasse, die eine <xref:System.IDisposable>-Implementierung instanziiert und als Instanzmember speichert, ist auch für die Bereinigung verantwortlich. Dadurch wird sichergestellt, dass die verwerfbaren Typen, auf die verwiesen wird, die Möglichkeit erhalten, eine Bereinigung deterministisch mit der <xref:System.IDisposable.Dispose%2A>-Methode auszuführen. In diesem Beispiel ist die Klasse `sealed` (oder `NotInheritable` in Visual Basic).

[!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/disposable1.cs#1)]
[!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/disposable1.vb#1)]

## <a name="implement-the-dispose-pattern"></a>Implementieren des Dispose-Musters

Alle nicht versiegelten Klassen (oder nicht als `NotInheritable` geänderten Visual Basic-Klassen) sollten als potenzielle Basisklasse angesehen werden, da sie geerbt werden könnten. Wenn Sie das Dispose-Muster für eine potenzielle Basisklasse implementieren, müssen Sie Folgendes bereitstellen:

- Eine <xref:System.IDisposable.Dispose%2A>-Implementierung, die die `Dispose(bool)`-Methode aufruft.
- Eine `Dispose(bool)`-Methode, die die eigentliche Bereinigung ausführt.
- Entweder eine von <xref:System.Runtime.InteropServices.SafeHandle> abgeleitete Klasse, die die nicht verwaltete Ressource einschließt (empfohlen) oder eine Überschreibung der <xref:System.Object.Finalize%2A?displayProperty=nameWithType>-Methode. Die <xref:System.Runtime.InteropServices.SafeHandle>-Klasse stellt einen Finalizer bereit, sodass Sie ihn nicht selbst schreiben müssen.

> [!IMPORTANT]
> Es ist möglich, dass eine Basisklasse nur auf verwaltete Objekte verweist und das Dispose-Muster implementiert. In diesen Fällen ist ein Finalizer unnötig. Ein Finalizer ist nur erforderlich, wenn Sie direkt auf nicht verwaltete Ressourcen verweisen.

Im Folgenden finden Sie das allgemeine Muster für die Implementierung des Dispose-Musters für eine Basisklasse, die ein SafeHandle verwendet.

[!code-csharp[System.IDisposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base1.cs#3)]
[!code-vb[System.IDisposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base1.vb#3)]

> [!NOTE]
> Im vorherigen Beispiel wird ein <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>-Objekt zum Veranschaulichen des Musters verwendet; stattdessen kann auch ein beliebiges anderes von <xref:System.Runtime.InteropServices.SafeHandle> abgeleitetes Objekt verwendet werden. Beachten Sie, dass im Beispiel das <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>-Objekt nicht ordnungsgemäß instanziiert wird.

Im Folgenden finden Sie das allgemeine Muster für die Implementierung des Dispose-Musters für eine Basisklasse, die <xref:System.Object.Finalize%2A?displayProperty=nameWithType> überschreibt.

[!code-csharp[System.IDisposable#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base2.cs#5)]
[!code-vb[System.IDisposable#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base2.vb#5)]

> [!TIP]
> In C# erstellen Sie einen [Finalizer](../../csharp/programming-guide/classes-and-structs/destructors.md), indem Sie <xref:System.Object.Finalize%2A?displayProperty=nameWithType> überschreiben. In Visual Basic erfolgt dies mit `Protected Overrides Sub Finalize()`.

## <a name="implement-the-dispose-pattern-for-a-derived-class"></a>Implementieren des Dispose-Musters für eine abgeleitete Klasse

Eine Klasse, die von einer Klasse abgeleitet ist, die die <xref:System.IDisposable>-Schnittstelle implementiert, sollte <xref:System.IDisposable> nicht implementieren, da die Basisklassenimplementierung von <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> von den abgeleiteten Klassen geerbt wird. Zum Bereinigen einer abgeleiteten Klasse stellen Sie stattdessen Folgendes bereit:

- Eine `protected override void Dispose(bool)`-Methode, die die Basisklassenmethode überschreibt und die eigentliche Bereinigung der abgeleiteten Klasse durchführt. Diese Methode muss auch die `base.Dispose(bool)`-Methode (`MyBase.Dispose(bool)` in Visual Basic) der Basisklasse aufrufen und ihren disposing-Status für das Argument übergeben.
- Entweder eine von <xref:System.Runtime.InteropServices.SafeHandle> abgeleitete Klasse, die die nicht verwaltete Ressource einschließt (empfohlen) oder eine Überschreibung der <xref:System.Object.Finalize%2A?displayProperty=nameWithType>-Methode. Die <xref:System.Runtime.InteropServices.SafeHandle>-Klasse stellt einen Finalizer bereit, wodurch Sie keinen programmieren müssen. Wenn Sie einen Finalizer bereitstellen, muss er die `Dispose(bool)`-Überladung mit einem `disposing`-Argument mit dem Wert `false` aufrufen.

Im Folgenden finden Sie das allgemeine Muster für das Implementieren des Dispose-Musters für eine abgeleitete Klasse, die ein SafeHandle verwendet:

[!code-csharp[System.IDisposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived1.cs#4)]
[!code-vb[System.IDisposable#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived1.vb#4)]

> [!NOTE]
> Im vorherigen Beispiel wird ein <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>-Objekt zum Veranschaulichen des Musters verwendet; stattdessen kann auch ein beliebiges anderes von <xref:System.Runtime.InteropServices.SafeHandle> abgeleitetes Objekt verwendet werden. Beachten Sie, dass im Beispiel das <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>-Objekt nicht ordnungsgemäß instanziiert wird.

Im Folgenden finden Sie das allgemeine Muster für das Implementieren des Dispose-Musters für eine abgeleitete Klasse, die <xref:System.Object.Finalize%2A?displayProperty=nameWithType> überschreibt:

[!code-csharp[System.IDisposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived2.cs#6)]
[!code-vb[System.IDisposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived2.vb#6)]

## <a name="implement-the-dispose-pattern-with-safe-handles"></a>Implementieren des Dispose-Musters mit sicheren Handles

Das folgende Beispiel zeigt das Dispose-Muster für eine Basisklasse, `DisposableStreamResource`, die ein SafeHandle verwendet, um nicht verwaltete Ressourcen zu kapseln. Es definiert eine `DisposableStreamResource`-Klasse, die ein <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> verwendet, um ein <xref:System.IO.Stream>-Objekt zu umschließen, das eine offene Datei darstellt. Die Klasse enthält auch eine einzelne Eigenschaft, `Size`, die die Gesamtzahl von Bytes im Dateistream zurückgibt.

[!code-csharp[Conceptual.Disposable#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/base1.cs#9)]
[!code-vb[Conceptual.Disposable#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/base1.vb#9)]

## <a name="implement-the-dispose-pattern-for-a-derived-class-with-safe-handles"></a>Implementieren des Dispose-Musters für eine abgeleitete Klasse mit sicheren Handles

Das folgende Beispiel zeigt das Dispose-Muster für eine abgeleitete Klasse, `DisposableStreamResource2`, die von der `DisposableStreamResource`-Klasse erbt, die im vorherigen Beispiel dargestellt wurde. Die Klasse fügt eine zusätzliche Methode, `WriteFileInfo`, hinzu und verwendet ein <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>-Objekt, um das Handle der überschreibbaren Datei zu umschließen.

[!code-csharp[Conceptual.Disposable#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/derived1.cs#10)]
[!code-vb[Conceptual.Disposable#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/derived1.vb#10)]

## <a name="see-also"></a>Siehe auch

- <xref:System.GC.SuppressFinalize%2A>
- <xref:System.IDisposable>
- <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>
- <xref:Microsoft.Win32.SafeHandles>
- <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>
- [Definieren und Nutzen von Klassen und Strukturen (C++/CLI)](/cpp/dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli)
