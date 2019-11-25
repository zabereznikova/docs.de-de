---
title: Implementieren einer Dispose-Methode
ms.date: 04/07/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- garbage collection, Dispose method
ms.assetid: eb4e1af0-3b48-4fbc-ad4e-fc2f64138bf9
ms.openlocfilehash: 0583329ae75fa54cf000212479895ccebdbd30d8
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74142055"
---
# <a name="implementing-a-dispose-method"></a>Implementieren einer Dispose-Methode

Sie implementieren eine <xref:System.IDisposable.Dispose%2A>-Methode, um nicht verwaltete Ressourcen freizugeben, die von Ihrer Anwendung verwendet werden. Der .NET-Garbage Collector ordnet nicht verwalteten Arbeitsspeicher weder zu noch gibt er diesen frei.  
  
Das Muster für das Verwerfen eines Objekts, [Dispose-Muster](implementing-dispose.md) genannt, legt die Ordnung für die Lebensdauer eines Objekts fest. Das Dispose-Muster wird nur für Objekte verwendet, die auf nicht verwaltete Ressourcen zugreifen, wie etwa Datei- und Pipehandles, Registrierungshandles, Wait-Handles oder Zeiger auf Blöcke nicht verwalteten Speichers. Dies liegt daran, dass der Garbage Collector beim Freigeben nicht verwendeter verwalteter Objekte sehr effizient ist, nicht verwaltete Objekt jedoch nicht freigeben kann.  
  
Das Dispose-Muster weist zwei Varianten auf:  
  
- Sie umschließen jede nicht verwaltete Ressource, die ein Typ verwendet, in einem SafeHandle (also in einer von <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> abgeleiteten Klasse). In diesem Fall implementieren Sie die <xref:System.IDisposable>-Schnittstelle und eine zusätzliche `Dispose(Boolean)`-Methode. Dies ist die empfohlene Variante und erfordert nicht das Überschreiben der <xref:System.Object.Finalize%2A?displayProperty=nameWithType>-Methode.  
  
  > [!NOTE]
  > Der <xref:Microsoft.Win32.SafeHandles?displayProperty=nameWithType>-Namespace stellt einen Satz von Klassen bereit, die von <xref:System.Runtime.InteropServices.SafeHandle> abgeleitet werden und im Abschnitt [Verwenden von SafeHandles](#SafeHandles) aufgeführt sind. Wenn Sie keine Klasse finden können, die Ihre nicht verwaltete Ressource freigeben kann, können Sie eine eigene Unterklasse von <xref:System.Runtime.InteropServices.SafeHandle> implementieren.  
  
- Sie implementieren die <xref:System.IDisposable>-Schnittstelle und eine zusätzliche `Dispose(Boolean)`-Methode, und Sie überschreiben auch die <xref:System.Object.Finalize%2A?displayProperty=nameWithType>-Methode. Sie müssen <xref:System.Object.Finalize%2A> überschreiben, um sicherzustellen, dass nicht verwaltete Ressourcen verworfen werden, wenn die <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>-Implementierung nicht von einem Consumer Ihres Typs aufgerufen wird. Wenn Sie das unter dem vorherigen Aufzählungspunkt beschriebene empfohlene Verfahren anwenden, führt die <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>-Klasse dies für Sie durch.  
  
Um sicherzustellen, dass Ressourcen immer entsprechend bereinigt werden, sollte eine <xref:System.IDisposable.Dispose%2A>-Methode auch mehrmals aufgerufen werden können, ohne eine Ausnahme auszulösen.  
  
Das Codebeispiel für die <xref:System.GC.KeepAlive%2A?displayProperty=nameWithType>-Methode veranschaulicht, wie durch agressive Garbage Collection die Ausführung eines Finalizers bewirkt werden kann, während ein Member des freigegebenen Objekts noch ausgeführt wird. Es empfiehlt sich, die <xref:System.GC.KeepAlive%2A>-Methode am Ende einer längeren <xref:System.IDisposable.Dispose%2A>-Methode aufzurufen.  
  
<a name="Dispose2"></a>
## <a name="dispose-and-disposeboolean"></a>Dispose() und Dispose(Boolean)  

Die <xref:System.IDisposable>-Schnittstelle erfordert die Implementierung einer einzelnen parameterlosen Methode, <xref:System.IDisposable.Dispose%2A>. Für das Dispose-Muster müssen jedoch zwei `Dispose`-Methoden implementiert werden:  
  
- Eine öffentliche, nicht virtuelle (`NonInheritable` in Visual Basic) <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>-Implementierung, die keine Parameter aufweist.  
  
- Eine geschützte, virtuelle (`Overridable` in Visual Basic) `Dispose`-Methode mit der folgenden Signatur:  
  
  [!code-csharp[Conceptual.Disposable#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#8)]
  [!code-vb[Conceptual.Disposable#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#8)]  
  
### <a name="the-dispose-overload"></a>Die Dispose() Überladung

Da die öffentliche, nicht virtuelle (`NonInheritable` in Visual Basic), parameterlose `Dispose`-Methode von einem Consumer des Typs aufgerufen wird, besteht ihr Zweck darin, nicht verwaltete Ressourcen freizugeben und anzugeben, dass der Finalizer, sofern vorhanden, nicht ausgeführt werden muss. Daher weist sie eine Standardimplementierung auf:  
  
[!code-csharp[Conceptual.Disposable#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#7)]
[!code-vb[Conceptual.Disposable#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#7)]  
  
Die `Dispose`-Methode führt die Bereinigung aller Objekte aus, damit der Garbage Collector nicht mehr die <xref:System.Object.Finalize%2A?displayProperty=nameWithType>-Überschreibung der Objekte aufrufen muss. Daher verhindert der Aufruf der <xref:System.GC.SuppressFinalize%2A>-Methode, dass der Garbage Collector den Finalizer ausführt. Wenn der Typ keinen Finalizer aufweist, bleibt der Aufruf von <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> ohne Auswirkungen. Beachten Sie, dass die tatsächliche Arbeit des Freigebens nicht verwalteter Ressourcen durch die zweite Überladung der `Dispose`-Methode ausgeführt wird.  
  
### <a name="the-disposeboolean-overload"></a>Die Dispose(Boolean) Überladung

In der zweiten Überladung ist der *disposing*-Parameter ein <xref:System.Boolean>, der angibt, ob der Methodenaufruf von einer <xref:System.IDisposable.Dispose%2A>-Methode (der Wert ist `true`) oder von einem Finalizer (der Wert ist `false`) stammt.  
  
Der Text der Methode besteht aus zwei Codeblöcken:  
  
- Ein Block, der nicht verwaltete Ressourcen freigibt. Dieser Block wird unabhängig vom Wert des `disposing`-Parameters ausgeführt.  
  
- Ein bedingter Block, der verwaltete Ressourcen freigibt. Dieser Block wird ausgeführt, wenn der Wert von `disposing` gleich `true` ist. Die verwalteten Ressourcen, die freigegeben werden, können Folgendes umfassen:  
  
  **Verwaltete Objekte, die <xref:System.IDisposable> implementieren.** Der bedingte Block kann verwendet werden, um deren <xref:System.IDisposable.Dispose%2A>-Implementierung aufzurufen. Wenn Sie ein SafeHandle verwendet haben, um die nicht verwaltete Ressource einschließen, sollten Sie die <xref:System.Runtime.InteropServices.SafeHandle.Dispose%28System.Boolean%29?displayProperty=nameWithType>-Implementierung hier aufrufen.  
  
  **Verwaltete Objekte, die viel Arbeitsspeicher belegen oder knappe Ressourcen nutzen.** Durch die explizite Freigabe in der `Dispose`-Methode werden diese Objekte schneller freigegeben, als wenn sie vom Garbage Collector nicht deterministisch freigegeben werden würden.  
  
Wenn der Methodenaufruf von einem Finalizer stammt (das heißt, *disposing* ist `false`), wird nur der Code ausgeführt, der nicht verwaltete Ressourcen freigibt. Die Reihenfolge, in der der Garbage Collector verwaltete Objekte während des Abschlusses zerstört, ist nicht definiert. Durch Aufrufen dieser `Dispose`-Überladung mit dem Wert `false` wird daher verhindert, dass der Finalizer versucht, verwaltete Ressourcen freizugeben, die möglicherweise bereits freigegeben wurden.  
  
## <a name="implementing-the-dispose-pattern-for-a-base-class"></a>Implementieren des Dispose-Musters für eine Basisklasse

Wenn Sie das Dispose-Muster für eine Basisklasse implementieren, müssen Sie Folgendes bereitstellen:  
  
> [!IMPORTANT]
> Sie sollten dieses Muster für alle Basisklassen implementieren, die <xref:System.IDisposable.Dispose> implementieren und nicht `sealed` (`NotInheritable` in Visual Basic) sind.  
  
- Eine <xref:System.IDisposable.Dispose%2A>-Implementierung, die die `Dispose(Boolean)`-Methode aufruft.  
  
- Eine `Dispose(Boolean)`-Methode, die die eigentliche Arbeit des Freigebens von Ressourcen ausführt.  
  
- Entweder eine von <xref:System.Runtime.InteropServices.SafeHandle> abgeleitete Klasse, die die nicht verwaltete Ressource einschließt (empfohlen) oder eine Überschreibung der <xref:System.Object.Finalize%2A?displayProperty=nameWithType>-Methode. Die <xref:System.Runtime.InteropServices.SafeHandle>-Klasse stellt einen Finalizer bereit, wodurch Sie keinen programmieren müssen.  
  
Im Folgenden finden Sie das allgemeine Muster für die Implementierung des Dispose-Musters für eine Basisklasse, die ein SafeHandle verwendet.  
  
[!code-csharp[System.IDisposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base1.cs#3)]
[!code-vb[System.IDisposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base1.vb#3)]  
  
> [!NOTE]
> Im vorherigen Beispiel wird ein <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>-Objekt zum Veranschaulichen des Musters verwendet; stattdessen kann auch ein beliebiges anderes von <xref:System.Runtime.InteropServices.SafeHandle> abgeleitetes Objekt verwendet werden. Beachten Sie, dass im Beispiel das <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>-Objekt nicht ordnungsgemäß instanziiert wird.  
  
Im Folgenden finden Sie das allgemeine Muster für die Implementierung des Dispose-Musters für eine Basisklasse, die <xref:System.Object.Finalize%2A?displayProperty=nameWithType> überschreibt.  
  
[!code-csharp[System.IDisposable#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base2.cs#5)]
[!code-vb[System.IDisposable#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base2.vb#5)]  
  
> [!NOTE]
> In C# überschreiben Sie <xref:System.Object.Finalize%2A?displayProperty=nameWithType> durch Definieren eines [Destruktors](../../csharp/programming-guide/classes-and-structs/destructors.md).  
  
## <a name="implementing-the-dispose-pattern-for-a-derived-class"></a>Implementieren des Dispose-Musters für eine abgeleitete Klasse

Eine Klasse, die von einer Klasse abgeleitet ist, die die <xref:System.IDisposable>-Schnittstelle implementiert, sollte <xref:System.IDisposable> nicht implementieren, da die Basisklassenimplementierung von <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> von den abgeleiteten Klassen geerbt wird. Zum Freigeben von Ressourcen einer abgeleiteten Klasse stellen Sie stattdessen Folgendes bereit:  
  
- Eine `protected Dispose(Boolean)`-Methode, die die Basisklassenmethode überschreibt und die eigentliche Freigabe der Ressourcen der abgeleiteten Klasse durchführt. Diese Methode sollte auch die `Dispose(Boolean)`-Methode der Basisklasse aufrufen und ihren disposing-Status für das Argument übergeben.  
  
- Entweder eine von <xref:System.Runtime.InteropServices.SafeHandle> abgeleitete Klasse, die die nicht verwaltete Ressource einschließt (empfohlen) oder eine Überschreibung der <xref:System.Object.Finalize%2A?displayProperty=nameWithType>-Methode. Die <xref:System.Runtime.InteropServices.SafeHandle>-Klasse stellt einen Finalizer bereit, wodurch Sie keinen programmieren müssen. Wenn Sie einen Finalizer bereitstellen, sollte er die `Dispose(Boolean)`-Überladung mit einem *disposing*-Argument mit dem Wert `false` aufrufen.  
  
Im Folgenden finden Sie das allgemeine Muster für das Implementieren des Dispose-Musters für eine abgeleitete Klasse, die ein SafeHandle verwendet:  
  
[!code-csharp[System.IDisposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived1.cs#4)]
[!code-vb[System.IDisposable#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived1.vb#4)]  
  
> [!NOTE]
> Im vorherigen Beispiel wird ein <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>-Objekt zum Veranschaulichen des Musters verwendet; stattdessen kann auch ein beliebiges anderes von <xref:System.Runtime.InteropServices.SafeHandle> abgeleitetes Objekt verwendet werden. Beachten Sie, dass im Beispiel das <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>-Objekt nicht ordnungsgemäß instanziiert wird.  
  
Im Folgenden finden Sie das allgemeine Muster für das Implementieren des Dispose-Musters für eine abgeleitete Klasse, die <xref:System.Object.Finalize%2A?displayProperty=nameWithType> überschreibt:  
  
[!code-csharp[System.IDisposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived2.cs#6)]
[!code-vb[System.IDisposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived2.vb#6)]  
  
> [!NOTE]
> In C# überschreiben Sie <xref:System.Object.Finalize%2A?displayProperty=nameWithType> durch Definieren eines [Destruktors](../../csharp/programming-guide/classes-and-structs/destructors.md).  
  
<a name="SafeHandles"></a>   
## <a name="using-safe-handles"></a>Verwenden von SafeHandles

Das Schreiben von Code für den Finalizer eines Objekts ist eine komplexe Aufgabe, die Probleme verursachen kann, wenn sie nicht ordnungsgemäß gelöst wird. Daher wird empfohlen, <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>-Objekte zu erstellen, anstatt einen Finalizer zu implementieren.  
  
Von der <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>-Klasse abgeleitete Klassen vereinfachen Probleme mit der Objektlebensdauer, indem sie Handles ohne Unterbrechung zuweisen und freigeben. Sie enthalten einen kritischen Finalizer, der auf jeden Fall ausgeführt wird, während eine Anwendungsdomäne entladen wird. Weitere Informationen zu den Vorteilen bei der Verwendung von SafeHandle finden Sie unter <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>. Die folgenden abgeleiteten Klassen im <xref:Microsoft.Win32.SafeHandles>-Namespace stellen SafeHandles bereit:  
  
- Die Klasse <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>, <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedFileHandle> und <xref:Microsoft.Win32.SafeHandles.SafePipeHandle>, für Dateien, Speicherabbilddateien und Pipes.  
  
- Die <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle>-Klasse, für Speicheransichten.  
  
- Die Klassen <xref:Microsoft.Win32.SafeHandles.SafeNCryptKeyHandle>, <xref:Microsoft.Win32.SafeHandles.SafeNCryptProviderHandle> und <xref:Microsoft.Win32.SafeHandles.SafeNCryptSecretHandle>, für Kryptografiekonstrukte.  
  
- Die <xref:Microsoft.Win32.SafeHandles.SafeRegistryHandle>-Klasse, für Registrierungsschlüssel.  
  
- Die <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle>-Klasse, für Wait-Handles.  
  
<a name="base"></a>   
## <a name="using-a-safe-handle-to-implement-the-dispose-pattern-for-a-base-class"></a>Verwenden eines SafeHandles zum Implementieren des Dispose-Musters für eine Basisklasse

Das folgende Beispiel zeigt das Dispose-Muster für eine Basisklasse, `DisposableStreamResource`, die ein SafeHandle verwendet, um nicht verwaltete Ressourcen zu kapseln. Es definiert eine `DisposableResource`-Klasse, die ein <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> verwendet, um ein <xref:System.IO.Stream>-Objekt zu umschließen, das eine offene Datei darstellt. Die `DisposableResource`-Methode enthält auch eine einzelne Eigenschaft, `Size`, die die Gesamtzahl von Bytes im Dateistream zurückgibt.  
  
[!code-csharp[Conceptual.Disposable#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/base1.cs#9)]
[!code-vb[Conceptual.Disposable#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/base1.vb#9)]  
  
<a name="derived"></a>   
## <a name="using-a-safe-handle-to-implement-the-dispose-pattern-for-a-derived-class"></a>Verwenden eines SafeHandles zum Implementieren des Dispose-Musters für eine abgeleitete Klasse

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
- [Vorgehensweise: Definieren und Verarbeiten von Klassen und Strukturen (C++/CLI)](/cpp/dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli)
- [Dispose-Muster](implementing-dispose.md)
