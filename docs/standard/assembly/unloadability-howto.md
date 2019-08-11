---
title: Verwenden und Debuggen von Assemblyentladbarkeit in .NET Core
description: Erfahren Sie, wie Sie entladbaren AssemblyLoadContext zum Laden und Entladen von verwalteten Assemblys verwenden und wie Sie Probleme beheben können, die den Erfolg des Entladevorgangs verhindern.
author: janvorli
ms.author: janvorli
ms.date: 02/05/2019
ms.openlocfilehash: a3ba2c2809aedd0af03ec965089f8779c430a335
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/19/2019
ms.locfileid: "68671245"
---
# <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a><span data-ttu-id="0da88-103">Verwenden und Debuggen von Assemblyentladbarkeit in .NET Core</span><span class="sxs-lookup"><span data-stu-id="0da88-103">How to use and debug assembly unloadability in .NET Core</span></span>

<span data-ttu-id="0da88-104">Ab .NET Core 3.0 wird die Möglichkeit unterstützt, eine Gruppe von Assemblys zu laden und später zu entladen.</span><span class="sxs-lookup"><span data-stu-id="0da88-104">Starting with .NET Core 3.0, the ability to load and later unload a set of assemblies is supported.</span></span> <span data-ttu-id="0da88-105">In .NET Framework wurden benutzerdefinierte App-Domänen zu diesem Zweck verwendet, .NET Core unterstützt jedoch nur eine einzelne App-Standarddomäne.</span><span class="sxs-lookup"><span data-stu-id="0da88-105">In .NET Framework, custom app domains were used for this purpose, but .NET Core only supports a single default app domain.</span></span>

<span data-ttu-id="0da88-106">.NET Core 3.0 und höhere Versionen unterstützen Entladbarkeit über <xref:System.Runtime.Loader.AssemblyLoadContext>.</span><span class="sxs-lookup"><span data-stu-id="0da88-106">.NET Core 3.0 and later versions support unloadability through <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="0da88-107">Sie können eine Gruppe von Assemblys in einen entladbaren `AssemblyLoadContext` laden, Methoden in ihnen ausführen oder sie einfach mithilfe von Reflektion untersuchen und schließlich den `AssemblyLoadContext` entladen.</span><span class="sxs-lookup"><span data-stu-id="0da88-107">You can load a set of assemblies into a collectible `AssemblyLoadContext`, execute methods in them or just inspect them using reflection, and finally unload the `AssemblyLoadContext`.</span></span> <span data-ttu-id="0da88-108">Dadurch werden die Assemblys entladen, die in diesen `AssemblyLoadContext` geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="0da88-108">That unloads the assemblies loaded into that `AssemblyLoadContext`.</span></span>

<span data-ttu-id="0da88-109">Es gibt einen bemerkenswerten Unterschied zwischen dem Entladen mithilfe von `AssemblyLoadContext` und der Verwendung von AppDomains.</span><span class="sxs-lookup"><span data-stu-id="0da88-109">There's one noteworthy difference between the unloading using `AssemblyLoadContext` and using AppDomains.</span></span> <span data-ttu-id="0da88-110">Mit AppDomains wird das Entladen erzwungen.</span><span class="sxs-lookup"><span data-stu-id="0da88-110">With AppDomains, the unloading is forced.</span></span> <span data-ttu-id="0da88-111">Zum Zeitpunkt der Entladung werden beispielsweise alle Threads abgebrochen, die in der Zielanwendungsdomäne ausgeführt werden, und verwaltete COM-Objekte werden gelöscht, die in der Ziel-AppDomain erstellt wurden. Mit `AssemblyLoadContext` ist den Entladevorgang „kooperativ“.</span><span class="sxs-lookup"><span data-stu-id="0da88-111">At the unload time, all threads running in the target AppDomain are aborted, managed COM objects created in the target AppDomain are destroyed, etc. With `AssemblyLoadContext`, the unload is "cooperative".</span></span> <span data-ttu-id="0da88-112">Durch Aufrufen der <xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType>-Methode wird der Entladevorgang nur initiiert.</span><span class="sxs-lookup"><span data-stu-id="0da88-112">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType> method just initiates the unloading.</span></span> <span data-ttu-id="0da88-113">Das Entladen wird abgeschlossen, nachdem die folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="0da88-113">The unloading finishes after:</span></span>

- <span data-ttu-id="0da88-114">Es gibt keine Threads, die über Methoden aus den Assemblys in ihren Aufruflisten verfügen, die in den `AssemblyLoadContext` geladen werden.</span><span class="sxs-lookup"><span data-stu-id="0da88-114">No threads have methods from the assemblies loaded into the `AssemblyLoadContext` on their call stacks.</span></span>
- <span data-ttu-id="0da88-115">Auf keinen der Typen aus den in den `AssemblyLoadContext` geladenen Assemblys, auf keine Instanzen dieser Typen und auf keine der Assemblys selbst außerhalb des `AssemblyLoadContext` wird durch Folgendes verwiesen:</span><span class="sxs-lookup"><span data-stu-id="0da88-115">None of the types from the assemblies loaded into the `AssemblyLoadContext`, instances of those types and the assemblies themselves outside of the `AssemblyLoadContext` are referenced by:</span></span>
  - <span data-ttu-id="0da88-116">Verweise außerhalb des `AssemblyLoadContext`, ausgenommen schwache Verweise (<xref:System.WeakReference> oder <xref:System.WeakReference%601>).</span><span class="sxs-lookup"><span data-stu-id="0da88-116">References outside of the `AssemblyLoadContext`, except of weak references (<xref:System.WeakReference> or <xref:System.WeakReference%601>).</span></span>
  - <span data-ttu-id="0da88-117">Starke GC-Handles (<xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Normal></span><span class="sxs-lookup"><span data-stu-id="0da88-117">Strong GC handles (<xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Normal></span></span> <span data-ttu-id="0da88-118">oder <xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Pinned>) von innerhalb und außerhalb des `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="0da88-118">or <xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Pinned>) from both inside and outside of the `AssemblyLoadContext`.</span></span>

## <a name="using-collectible-assemblyloadcontext"></a><span data-ttu-id="0da88-119">Verwenden des entladbaren AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="0da88-119">Using collectible AssemblyLoadContext</span></span>

<span data-ttu-id="0da88-120">Dieser Abschnitt enthält ein detailliertes schrittweises Tutorial, das eine einfache Möglichkeit zeigt, eine .NET Core-Anwendung in einen entladbaren `AssemblyLoadContext` zu laden, ihren Einstiegspunkt auszuführen und sie dann zu entladen.</span><span class="sxs-lookup"><span data-stu-id="0da88-120">This section contains a detailed step-by-step tutorial that shows a simple way to load a .NET Core application into a collectible `AssemblyLoadContext`, execute its entry point, and then unload it.</span></span> <span data-ttu-id="0da88-121">Das vollständige Beispiel finden Sie unter <https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading>.</span><span class="sxs-lookup"><span data-stu-id="0da88-121">You can find a complete sample at <https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading>.</span></span>

### <a name="create-a-collectible-assemblyloadcontext"></a><span data-ttu-id="0da88-122">Erstellen eines entladbaren AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="0da88-122">Create a collectible AssemblyLoadContext</span></span>

<span data-ttu-id="0da88-123">Sie müssen die Klasse von <xref:System.Runtime.Loader.AssemblyLoadContext> ableiten und ihre <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType>-Methode überladen.</span><span class="sxs-lookup"><span data-stu-id="0da88-123">You need to derive your class from the <xref:System.Runtime.Loader.AssemblyLoadContext> and overload its <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="0da88-124">Diese Methode löst Verweise auf alle Assemblys auf, die Abhängigkeiten von in diesen `AssemblyLoadContext` geladenen Assemblys sind.</span><span class="sxs-lookup"><span data-stu-id="0da88-124">That method resolves references to all assemblies that are dependencies of assemblies loaded into that `AssemblyLoadContext`.</span></span>
<span data-ttu-id="0da88-125">Der folgende Code ist ein Beispiel für den einfachsten benutzerdefinierten `AssemblyLoadContext`:</span><span class="sxs-lookup"><span data-stu-id="0da88-125">The following code is an example of the simplest custom `AssemblyLoadContext`:</span></span>

[!code-csharp[Simple custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/simple_example.cs#1)]

<span data-ttu-id="0da88-126">Wie Sie sehen können, gibt die `Load`-Methode `null` zurück.</span><span class="sxs-lookup"><span data-stu-id="0da88-126">As you can see, the `Load` method returns `null`.</span></span> <span data-ttu-id="0da88-127">Dies bedeutet, dass alle Abhängigkeitsassemblys in den Standardkontext geladen werden und der neue Kontext nur die Assemblys enthält, die explizit in ihn geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="0da88-127">That means that all the dependency assemblies are loaded into the default context, and the new context contains only the assemblies explicitly loaded into it.</span></span>

<span data-ttu-id="0da88-128">Wenn Sie einige oder alle Abhängigkeiten in den `AssemblyLoadContext` laden möchten, können Sie `AssemblyDependencyResolver` in der `Load`-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="0da88-128">If you want to load some or all of the dependencies into the `AssemblyLoadContext` too, you can use the `AssemblyDependencyResolver` in the `Load` method.</span></span> <span data-ttu-id="0da88-129">`AssemblyDependencyResolver` löst die Assemblynamen mithilfe der Datei *.deps.json*, die im Verzeichnis der in den Kontext geladenen Hauptassembly enthalten ist, in absolute Assemblydateipfade auf und verwendet Assemblydateien in diesem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0da88-129">The `AssemblyDependencyResolver` resolves the assembly names to absolute assembly file paths using the *.deps.json* file contained in the directory of the main assembly loaded into the context and using assembly files in that directory.</span></span>

[!code-csharp[Advanced custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/complex_assemblyloadcontext.cs)]

### <a name="use-a-custom-collectible-assemblyloadcontext"></a><span data-ttu-id="0da88-130">Verwenden eines benutzerdefinierten entladbaren AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="0da88-130">Use a custom collectible AssemblyLoadContext</span></span>

<span data-ttu-id="0da88-131">In diesem Abschnitt wird davon ausgegangen, dass die einfachere Version von `TestAssemblyLoadContext` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0da88-131">This section assumes the simpler version of the `TestAssemblyLoadContext` is being used.</span></span>

<span data-ttu-id="0da88-132">Sie können eine Instanz des benutzerdefinierten `AssemblyLoadContext` erstellen und eine Assembly wie folgt in diesen laden:</span><span class="sxs-lookup"><span data-stu-id="0da88-132">You can create an instance of the custom `AssemblyLoadContext` and load an assembly into it as follows:</span></span>

[!code-csharp[Part 1](~/samples/snippets/standard/assembly/unloading/simple_example.cs#3)]

<span data-ttu-id="0da88-133">Für jede der Assemblys, auf die von der geladenen Assembly verwiesen wird, wird die `TestAssemblyLoadContext.Load`-Methode aufgerufen, sodass der `TestAssemblyLoadContext` entscheiden kann, von wo die Assembly abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="0da88-133">For each of the assemblies referenced by the loaded assembly, the `TestAssemblyLoadContext.Load` method is called so that the `TestAssemblyLoadContext` can decide where to get the assembly from.</span></span> <span data-ttu-id="0da88-134">In unserem Fall wird `null` zurückgegeben, um anzugeben, dass sie in den Standardkontext aus Speicherorten geladen werden soll, die die Runtime zum Laden von Assemblys standardmäßig verwendet.</span><span class="sxs-lookup"><span data-stu-id="0da88-134">In our case, it returns `null` to indicate that it should be loaded into the default context from locations that the runtime uses to load assemblies by default.</span></span>

<span data-ttu-id="0da88-135">Da nun eine Assembly geladen wurde, können Sie eine Methode daraus ausführen.</span><span class="sxs-lookup"><span data-stu-id="0da88-135">Now that an assembly was loaded, you can execute a method from it.</span></span> <span data-ttu-id="0da88-136">Führen Sie die `Main`-Methode aus:</span><span class="sxs-lookup"><span data-stu-id="0da88-136">Run the `Main` method:</span></span>

[!code-csharp[Part 2](~/samples/snippets/standard/assembly/unloading/simple_example.cs#4)]

<span data-ttu-id="0da88-137">Nachdem die `Main`-Methode abgeschlossen wurde, können Sie das Entladen einleiten, indem Sie entweder die `Unload`-Methode für den benutzerdefinierten `AssemblyLoadContext` aufrufen oder den Verweis auf den `AssemblyLoadContext` entfernen:</span><span class="sxs-lookup"><span data-stu-id="0da88-137">After the `Main` method returns, you can initiate unloading by either calling the `Unload` method on the custom `AssemblyLoadContext` or getting rid of the reference you have to the `AssemblyLoadContext`:</span></span>

[!code-csharp[Part 3](~/samples/snippets/standard/assembly/unloading/simple_example.cs#5)]

<span data-ttu-id="0da88-138">Dies reicht aus, um die Testassembly zu entladen.</span><span class="sxs-lookup"><span data-stu-id="0da88-138">This is sufficient to unload the test assembly.</span></span> <span data-ttu-id="0da88-139">Bringen wird all dies in einer separaten, nicht inlinefähigen Methode zusammen, um sicherzustellen, dass `TestAssemblyLoadContext`, `Assembly` und `MethodInfo` (der `Assembly.EntryPoint`) nicht durch Stackslotverweise (reale oder durch JIT eingeführte lokale Variablen) aktiv gehalten werden.</span><span class="sxs-lookup"><span data-stu-id="0da88-139">Let's actually put all of this into a separate non-inlineable method to ensure that the `TestAssemblyLoadContext`, `Assembly`, and `MethodInfo` (the `Assembly.EntryPoint`) can't be kept alive by stack slot references (real- or JIT-introduced locals).</span></span> <span data-ttu-id="0da88-140">Dies könnte den `TestAssemblyLoadContext` aktiv lassen und das Entladen verhindern.</span><span class="sxs-lookup"><span data-stu-id="0da88-140">That could keep the `TestAssemblyLoadContext` alive and prevent the unload.</span></span>

<span data-ttu-id="0da88-141">Geben Sie außerdem einen schwachen Verweis auf den `AssemblyLoadContext` zurück, damit Sie ihn später verwenden können, um den Abschluss des Entladevorgangs zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="0da88-141">Also, return a weak reference to the `AssemblyLoadContext` so that you can use it later to detect unload completion.</span></span>

[!code-csharp[Part 4](~/samples/snippets/standard/assembly/unloading/simple_example.cs#2)]

<span data-ttu-id="0da88-142">Nun können Sie diese Funktion ausführen, um die Assembly zu laden, auszuführen und zu entladen.</span><span class="sxs-lookup"><span data-stu-id="0da88-142">Now you can run this function to load, execute, and unload the assembly.</span></span>

[!code-csharp[Part 5](~/samples/snippets/standard/assembly/unloading/simple_example.cs#6)]

<span data-ttu-id="0da88-143">Das Entladen wird jedoch nicht sofort beendet.</span><span class="sxs-lookup"><span data-stu-id="0da88-143">However, the unload doesn't complete immediately.</span></span> <span data-ttu-id="0da88-144">Wie bereits erwähnt, verwendet der Vorgang GC, um alle Objekte aus der Testassembly zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="0da88-144">As previously mentioned, it relies on the GC to collect all the objects from the test assembly.</span></span> <span data-ttu-id="0da88-145">In vielen Fällen ist es nicht erforderlich, auf den Abschluss des Entladevorgangs zu warten.</span><span class="sxs-lookup"><span data-stu-id="0da88-145">In many cases, it isn't necessary to wait for the unload completion.</span></span> <span data-ttu-id="0da88-146">Es gibt jedoch Fälle, in denen es nützlich zu wissen ist, dass der Entladevorgang abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="0da88-146">However, there are cases where it's useful to know that the unload has finished.</span></span> <span data-ttu-id="0da88-147">Beispielsweise, wenn Sie die Assemblydatei löschen möchten, die vom Datenträger in den benutzerdefinierten `AssemblyLoadContext` geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="0da88-147">For example, you may want to delete the assembly file that was loaded into the custom `AssemblyLoadContext` from disk.</span></span> <span data-ttu-id="0da88-148">In einem solchen Fall kann der folgende Codeausschnitt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0da88-148">In such a case, the following code snippet can be used.</span></span> <span data-ttu-id="0da88-149">Er löst eine GC aus und wartet auf ausstehende Finalizer in einer Schleife, bis der schwache Verweis auf den benutzerdefinierten `AssemblyLoadContext` auf `null` festgelegt wurde, um anzugeben, dass das Zielobjekt entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="0da88-149">It triggers a GC and waits for pending finalizers in a loop until the weak reference to the custom `AssemblyLoadContext` is set to `null`, indicating the target object was collected.</span></span> <span data-ttu-id="0da88-150">Beachten Sie, dass in den meisten Fällen nur ein Durchlauf durch die Schleife erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="0da88-150">Note that in most cases, just one pass through the loop is required.</span></span> <span data-ttu-id="0da88-151">Für komplexere Fälle, in denen Objekte, die durch den im `AssemblyLoadContext` ausgeführten Code erstellt wurden, über Finalizer verfügen, sind möglicherweise weitere Durchgänge erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0da88-151">However, for more complex cases where objects created by the code running in the `AssemblyLoadContext` have finalizers, more passes may be needed.</span></span>

[!code-csharp[Part 6](~/samples/snippets/standard/assembly/unloading/simple_example.cs#7)]

### <a name="the-unloading-event"></a><span data-ttu-id="0da88-152">Das Unloading-Ereignis</span><span class="sxs-lookup"><span data-stu-id="0da88-152">The Unloading event</span></span>

<span data-ttu-id="0da88-153">In einigen Fällen kann es erforderlich sein, dass der Code, der in einen benutzerdefinierten `AssemblyLoadContext` geladen wird, einige Bereinigungsaufgaben durchführt, wenn das Entladen initiiert wird.</span><span class="sxs-lookup"><span data-stu-id="0da88-153">In some cases, it may be necessary for the code loaded into a custom `AssemblyLoadContext` to perform some cleanup when the unloading is initiated.</span></span> <span data-ttu-id="0da88-154">Beispielsweise kann es erforderlich sein, Threads anzuhalten und einige starke GC-Handles zu bereinigen. Das `Unloading`-Ereignis kann in solchen Fällen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0da88-154">For example, it may need to stop threads, clean up some strong GC handles, etc. The `Unloading` event can be used in such cases.</span></span> <span data-ttu-id="0da88-155">Ein Handler, der die erforderliche Bereinigung ausführt, kann mit diesem Ereignis verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="0da88-155">A handler that performs the necessary cleanup can be hooked to this event.</span></span>

### <a name="troubleshoot-unloadability-issues"></a><span data-ttu-id="0da88-156">Behandlung bei Problemen mit der Entladbarkeit</span><span class="sxs-lookup"><span data-stu-id="0da88-156">Troubleshoot unloadability issues</span></span>

<span data-ttu-id="0da88-157">Aufgrund der kooperativen Natur der Entladung kann leicht vergessen werden, dass Verweise die Objekte in einem entladbaren `AssemblyLoadContext` aktiv halten und das Entladen verhindern können.</span><span class="sxs-lookup"><span data-stu-id="0da88-157">Due to the cooperative nature of the unloading, it's easy to forget about references keeping the stuff in a collectible `AssemblyLoadContext` alive and preventing unload.</span></span> <span data-ttu-id="0da88-158">Hier ist eine Zusammenfassung der Objekte (einige davon nicht offensichtlich), die die Verweise enthalten können:</span><span class="sxs-lookup"><span data-stu-id="0da88-158">Here is a summary of things (some of them non-obvious) that can hold the references:</span></span>

- <span data-ttu-id="0da88-159">Reguläre Verweise, die außerhalb des entladbaren `AssemblyLoadContext` enthalten und in einem Stackslot oder einem Prozessorregister gespeichert sind (lokale Variablen von Methoden, entweder explizit durch den Benutzercode oder implizit durch JIT erstellt), eine statische Variable oder ein starkes/fixierendes GC-Handle und Transitivität, die auf Folgendes verweist:</span><span class="sxs-lookup"><span data-stu-id="0da88-159">Regular references held from outside of the collectible `AssemblyLoadContext`, stored in a stack slot or a processor register (method locals, either explicitly created by the user code or implicitly by the JIT), a static variable or a strong / pinning GC handle, and transitively pointing to:</span></span>
  - <span data-ttu-id="0da88-160">Eine Assembly, die in den entladbaren `AssemblyLoadContext` geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="0da88-160">An assembly loaded into the collectible `AssemblyLoadContext`.</span></span>
  - <span data-ttu-id="0da88-161">Ein Typ aus einer solchen Assembly.</span><span class="sxs-lookup"><span data-stu-id="0da88-161">A type from such an assembly.</span></span>
  - <span data-ttu-id="0da88-162">Eine Instanz eines Typs aus einer solchen Assembly.</span><span class="sxs-lookup"><span data-stu-id="0da88-162">An instance of a type from such an assembly.</span></span>
- <span data-ttu-id="0da88-163">Threads, die Code aus einer Assembly ausführen, die in den entladbaren `AssemblyLoadContext` geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="0da88-163">Threads running code from an assembly loaded into the collectible `AssemblyLoadContext`.</span></span>
- <span data-ttu-id="0da88-164">Instanzen von benutzerdefinierten, nicht entladbaren `AssemblyLoadContext`-Typen, die im entladbaren `AssemblyLoadContext` erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="0da88-164">Instances of custom non-collectible `AssemblyLoadContext` types created inside of the collectible `AssemblyLoadContext`</span></span>
- <span data-ttu-id="0da88-165">Ausstehende <xref:System.Threading.RegisteredWaitHandle>-Instanzen, bei denen Rückrufe auf Methoden im benutzerdefinierten `AssemblyLoadContext` festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="0da88-165">Pending <xref:System.Threading.RegisteredWaitHandle> instances with callbacks set to methods in the custom `AssemblyLoadContext`</span></span>

<span data-ttu-id="0da88-166">Hinweise zum Auffinden von Stackslots/Prozessorregistern, die ein Stammobjekt definieren:</span><span class="sxs-lookup"><span data-stu-id="0da88-166">Hints to find stack slot / processor register rooting an object:</span></span>

- <span data-ttu-id="0da88-167">Wenn Sie Ergebnisse eines Funktionsaufrufs direkt an eine andere Funktion übergeben, kann selbst dann ein Stamm erstellt werden, wenn keine vom Benutzer erstellte lokale Variable vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="0da88-167">Passing function call results directly to another function may create a root even though there is no user-created local variable.</span></span>
- <span data-ttu-id="0da88-168">Wenn zu irgendeinem Zeitpunkt in einer Methode ein Verweis auf ein Objekt verfügbar war, kann das JIT ggf. entscheiden, den Verweis in einem Stackslot/Prozessorregister so lange wie gewünscht in der aktuellen Funktion zu speichern.</span><span class="sxs-lookup"><span data-stu-id="0da88-168">If a reference to an object was available at any point in a method, the JIT might have decided to keep the reference in a stack slot / processor register for as long as it wants in the current function.</span></span>

## <a name="debug-unloading-issues"></a><span data-ttu-id="0da88-169">Debuggen von Problemen beim Entladen</span><span class="sxs-lookup"><span data-stu-id="0da88-169">Debug unloading issues</span></span>

<span data-ttu-id="0da88-170">Das Debuggen von Problemen beim Entladen kann mühsam sein.</span><span class="sxs-lookup"><span data-stu-id="0da88-170">Debugging issues with unloading can be tedious.</span></span> <span data-ttu-id="0da88-171">Es können Situationen eintreten, in denen Sie nicht wissen, was einen `AssemblyLoadContext` aktiv halten könnte, aber das Entladen schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="0da88-171">You can get into situations where you don't know what can be holding an `AssemblyLoadContext` alive, but the unload fails.</span></span>
<span data-ttu-id="0da88-172">Die beste Waffe bei einem solchen Problem ist WinDbg (LLDB unter Unix) mit dem SOS-Plug-In.</span><span class="sxs-lookup"><span data-stu-id="0da88-172">The best weapon to help with that is WinDbg (LLDB on Unix) with the SOS plugin.</span></span> <span data-ttu-id="0da88-173">Sie müssen herausfinden, was einen `LoaderAllocator`, der zu dem jeweiligen `AssemblyLoadContext` gehört, aktiv bleiben lässt.</span><span class="sxs-lookup"><span data-stu-id="0da88-173">You need to find what's keeping a `LoaderAllocator` belonging to the specific `AssemblyLoadContext` alive.</span></span>
<span data-ttu-id="0da88-174">Mit diesem Plug-In können Sie GC-Heapobjekte, ihre Hierarchien und Stämme überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0da88-174">This plugin allows you to look at GC heap objects, their hierarchies, and roots.</span></span>
<span data-ttu-id="0da88-175">Um das Plug-In in den Debugger zu laden, geben Sie den folgenden Befehl in der Debuggerbefehlszeile ein:</span><span class="sxs-lookup"><span data-stu-id="0da88-175">To load the plugin into the debugger, enter the following command in the debugger command line:</span></span>

<span data-ttu-id="0da88-176">In WinDbg (in WinDbg scheint dies automatisch beim Einstieg in die .NET Core-Anwendung zu geschehen):</span><span class="sxs-lookup"><span data-stu-id="0da88-176">In WinDbg (it seems WinDbg does that automatically when breaking into .NET Core application):</span></span>

```console
.loadby sos coreclr
```

<span data-ttu-id="0da88-177">In LLDB:</span><span class="sxs-lookup"><span data-stu-id="0da88-177">In LLDB:</span></span>

```console
plugin load /path/to/libsosplugin.so
```

<span data-ttu-id="0da88-178">Versuchen wir, ein Beispielprogramm zu debuggen, das Probleme beim Entladen hat.</span><span class="sxs-lookup"><span data-stu-id="0da88-178">Let's try to debug an example program that has problems with unloading.</span></span> <span data-ttu-id="0da88-179">Der Quellcode ist unten enthalten.</span><span class="sxs-lookup"><span data-stu-id="0da88-179">Source code is included below.</span></span> <span data-ttu-id="0da88-180">Wenn Sie ihn unter WinDbg ausführen, steigt das Programm direkt nach dem Versuch, den Erfolg des Entladevorgangs zu überprüfen, in den Debugger ein.</span><span class="sxs-lookup"><span data-stu-id="0da88-180">When you run it under WinDbg, the program breaks into the debugger right after attempting to check for the unload success.</span></span> <span data-ttu-id="0da88-181">Sie können dann mit der Suche nach den „Schuldigen“ beginnen.</span><span class="sxs-lookup"><span data-stu-id="0da88-181">You can then start looking for the culprits.</span></span>

<span data-ttu-id="0da88-182">Beachten Sie Folgendes: Wenn Sie mit LLDB unter UNIX debuggen, wird den SOS-Befehlen in den folgenden Beispielen kein `!` vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="0da88-182">Note that if you debug using LLDB on Unix, the SOS commands in the following examples don't have the `!` in front of them.</span></span>

```console
!dumpheap -type LoaderAllocator
```

<span data-ttu-id="0da88-183">Dieser Befehl sichert alle Objekte mit einem Typnamen, der `LoaderAllocator` enthält, aus dem GC-Heap.</span><span class="sxs-lookup"><span data-stu-id="0da88-183">This command dumps all objects with a type name containing `LoaderAllocator` that are in the GC heap.</span></span> <span data-ttu-id="0da88-184">Im Folgenden ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0da88-184">Here is an example:</span></span>

```console
         Address               MT     Size
000002b78000ce40 00007ffadc93a288       48     
000002b78000ceb0 00007ffadc93a218       24     

Statistics:
              MT    Count    TotalSize Class Name
00007ffadc93a218        1           24 System.Reflection.LoaderAllocatorScout
00007ffadc93a288        1           48 System.Reflection.LoaderAllocator
Total 2 objects
```

<span data-ttu-id="0da88-185">Überprüfen Sie im Abschnitt „Statistics“ unten die `MT` (`MethodTable`), die zu `System.Reflection.LoaderAllocator` gehört. Dies ist das Objekt, für das wir uns interessieren.</span><span class="sxs-lookup"><span data-stu-id="0da88-185">In the "Statistics:" part below, check the `MT` (`MethodTable`) belonging to the `System.Reflection.LoaderAllocator`, which is the object we care about.</span></span> <span data-ttu-id="0da88-186">Suchen Sie dann in der Liste am Anfang den Eintrag mit `MT`, der diesem Eintrag entspricht, und rufen Sie die Adresse des Objekts selbst ab.</span><span class="sxs-lookup"><span data-stu-id="0da88-186">Then in the list at the beginning, find the entry with `MT` matching that one and get the address of the object itself.</span></span> <span data-ttu-id="0da88-187">In unserem Fall lautet der Wert „000002b78000ce40“.</span><span class="sxs-lookup"><span data-stu-id="0da88-187">In our case, it is "000002b78000ce40"</span></span>

<span data-ttu-id="0da88-188">Nachdem wir nun die Adresse des `LoaderAllocator`-Objekts kennen, können wir einen anderen Befehl verwenden, um seine GC-Stämme zu finden.</span><span class="sxs-lookup"><span data-stu-id="0da88-188">Now that we know the address of the `LoaderAllocator` object, we can use another command to find its GC roots</span></span>

```console
!gcroot -all 0x000002b78000ce40 
```

<span data-ttu-id="0da88-189">Dieser Befehl sichert die Kette von Objektverweisen, die zur `LoaderAllocator`-Instanz führen.</span><span class="sxs-lookup"><span data-stu-id="0da88-189">This command dumps the chain of object references that lead to the `LoaderAllocator` instance.</span></span> <span data-ttu-id="0da88-190">Die Liste beginnt mit dem Stamm, bei dem es sich um die Entität handelt, die den `LoaderAllocator` aktiv hält und daher den Kern des Problems darstellt, das Sie debuggen.</span><span class="sxs-lookup"><span data-stu-id="0da88-190">The list starts with the root, which is the entity that keeps our `LoaderAllocator` alive and thus is the core of the problem you're debugging.</span></span> <span data-ttu-id="0da88-191">Der Stamm kann ein Stackslot, ein Prozessorregister, ein GC-Handle oder eine statische Variable sein.</span><span class="sxs-lookup"><span data-stu-id="0da88-191">The root can be a stack slot, a processor register, a GC handle, or a static variable.</span></span>

<span data-ttu-id="0da88-192">Hier ist ein Beispiel für die Ausgabe des `gcroot`-Befehls:</span><span class="sxs-lookup"><span data-stu-id="0da88-192">Here is an example of the output of the `gcroot` command:</span></span>

```console
Thread 4ac:
    000000cf9499dd20 00007ffa7d0236bc example.Program.Main(System.String[]) [E:\unloadability\example\Program.cs @ 70]
        rbp-20: 000000cf9499dd90
            ->  000002b78000d328 System.Reflection.RuntimeMethodInfo
            ->  000002b78000d1f8 System.RuntimeType+RuntimeTypeCache
            ->  000002b78000d1d0 System.RuntimeType
            ->  000002b78000ce40 System.Reflection.LoaderAllocator

HandleTable:
    000002b7f8a81198 (strong handle)
    -> 000002b78000d948 test.Test
    -> 000002b78000ce40 System.Reflection.LoaderAllocator

    000002b7f8a815f8 (pinned handle)
    -> 000002b790001038 System.Object[]
    -> 000002b78000d390 example.TestInfo
    -> 000002b78000d328 System.Reflection.RuntimeMethodInfo
    -> 000002b78000d1f8 System.RuntimeType+RuntimeTypeCache
    -> 000002b78000d1d0 System.RuntimeType
    -> 000002b78000ce40 System.Reflection.LoaderAllocator

Found 3 roots.
```

<span data-ttu-id="0da88-193">Nun müssen Sie herausfinden, wo sich der Stamm befindet, damit Sie das Problem beheben können.</span><span class="sxs-lookup"><span data-stu-id="0da88-193">Now you need to figure out where the root is located so you can fix it.</span></span> <span data-ttu-id="0da88-194">Im einfachsten Fall ist der Stamm ein Stackslot oder ein Prozessorregister.</span><span class="sxs-lookup"><span data-stu-id="0da88-194">The easiest case is when the root is a stack slot or a processor register.</span></span> <span data-ttu-id="0da88-195">In diesem Fall zeigt `gcroot` den Namen der Funktion an, deren Frame den Stamm und den Thread enthält, der diese Funktion ausführt.</span><span class="sxs-lookup"><span data-stu-id="0da88-195">In that case, the `gcroot` shows you the name of the function whose frame contains the root and the thread executing that function.</span></span> <span data-ttu-id="0da88-196">Ein schwieriger Fall liegt vor, wenn der Stamm eine statische Variable oder ein GC-Handle ist.</span><span class="sxs-lookup"><span data-stu-id="0da88-196">The difficult case is when the root is a static variable or a GC handle.</span></span> 

<span data-ttu-id="0da88-197">Im vorherigen Beispiel ist der erste Stamm eine lokale Variable vom Typ `System.Reflection.RuntimeMethodInfo`, die im Frame der Funktion `example.Program.Main(System.String[])` bei Adresse `rbp-20` gespeichert ist (`rbp` ist das Prozessorregister `rbp`, und -20 ist ein hexadezimaler Offset von diesem Register).</span><span class="sxs-lookup"><span data-stu-id="0da88-197">In the previous example, the first root is a local of type `System.Reflection.RuntimeMethodInfo` stored in the frame of the function `example.Program.Main(System.String[])` at address `rbp-20` (`rbp` is the processor register `rbp` and -20 is a hexadecimal offset from that register).</span></span>

<span data-ttu-id="0da88-198">Der zweite Stamm ist ein normales (starkes) `GCHandle`, das einen Verweis auf eine Instanz der `test.Test`-Klasse enthält.</span><span class="sxs-lookup"><span data-stu-id="0da88-198">The second root is a normal (strong) `GCHandle` that holds a reference to an instance of the `test.Test` class.</span></span> 

<span data-ttu-id="0da88-199">Der dritte Stamm ist ein fixiertes `GCHandle`.</span><span class="sxs-lookup"><span data-stu-id="0da88-199">The third root is a pinned `GCHandle`.</span></span> <span data-ttu-id="0da88-200">Dabei handelt es sich tatsächlich um eine statische Variable.</span><span class="sxs-lookup"><span data-stu-id="0da88-200">This one is actually a static variable.</span></span> <span data-ttu-id="0da88-201">Leider gibt es keine Möglichkeit, dies festzustellen.</span><span class="sxs-lookup"><span data-stu-id="0da88-201">Unfortunately, there is no way to tell.</span></span> <span data-ttu-id="0da88-202">Statische Variablen für Verweistypen werden in einem verwalteten Objektarray in internen Laufzeitstrukturen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0da88-202">Statics for reference types are stored in a managed object array in internal runtime structures.</span></span>

<span data-ttu-id="0da88-203">Ein weiterer Fall, der das Entladen eines `AssemblyLoadContext` verhindern kann: Wenn ein Thread über einen Frame einer Methode aus einer Assembly verfügt, die in den `AssemblyLoadContext` auf ihrem Stapel geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="0da88-203">Another case that can prevent unloading of an `AssemblyLoadContext` is when a thread has a frame of a method from an assembly loaded into the `AssemblyLoadContext` on its stack.</span></span> <span data-ttu-id="0da88-204">Sie können dies überprüfen, indem Sie die verwalteten Aufruflisten aller Threads sichern:</span><span class="sxs-lookup"><span data-stu-id="0da88-204">You can check that by dumping managed call stacks of all threads:</span></span>

```console
~*e !clrstack
```

<span data-ttu-id="0da88-205">Der Befehl bedeutet „Befehl `!clrstack` auf alle Threads anwenden“.</span><span class="sxs-lookup"><span data-stu-id="0da88-205">The command means "apply to all threads the `!clrstack` command".</span></span> <span data-ttu-id="0da88-206">Die folgende Abbildung zeigt die Ausgabe dieses Befehls für das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="0da88-206">The following is the output of that command for the example.</span></span> <span data-ttu-id="0da88-207">Leider bietet LLDB unter Unix keine Möglichkeit, einen Befehl auf alle Threads anzuwenden, sodass Sie die Threads manuell wechseln und den Befehl `clrstack` wiederholen müssen.</span><span class="sxs-lookup"><span data-stu-id="0da88-207">Unfortunately, LLDB on Unix doesn't have any way to apply a command to all threads, so you'll need to resort to manually switching threads and repeating the `clrstack` command.</span></span>
<span data-ttu-id="0da88-208">Ignorieren Sie alle Threads, bei denen der Debugger „Unable to walk the managed stack“ (Verwalteter Stapel kann nicht durchlaufen werden) anzeigt.</span><span class="sxs-lookup"><span data-stu-id="0da88-208">Ignore all threads where the debugger says "Unable to walk the managed stack."</span></span>

```console
OS Thread Id: 0x6ba8 (0)
        Child SP               IP Call Site
0000001fc697d5c8 00007ffb50d9de12 [HelperMethodFrame: 0000001fc697d5c8] System.Diagnostics.Debugger.BreakInternal()
0000001fc697d6d0 00007ffa864765fa System.Diagnostics.Debugger.Break()
0000001fc697d700 00007ffa864736bc example.Program.Main(System.String[]) [E:\unloadability\example\Program.cs @ 70]
0000001fc697d998 00007ffae5fdc1e3 [GCFrame: 0000001fc697d998] 
0000001fc697df28 00007ffae5fdc1e3 [GCFrame: 0000001fc697df28] 
OS Thread Id: 0x2ae4 (1)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x61a4 (2)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x7fdc (3)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x5390 (4)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x5ec8 (5)
        Child SP               IP Call Site
0000001fc70ff6e0 00007ffb5437f6e4 [DebuggerU2MCatchHandlerFrame: 0000001fc70ff6e0] 
OS Thread Id: 0x4624 (6)
        Child SP               IP Call Site
GetFrameContext failed: 1
0000000000000000 0000000000000000 
OS Thread Id: 0x60bc (7)
        Child SP               IP Call Site
0000001fc727f158 00007ffb5437fce4 [HelperMethodFrame: 0000001fc727f158] System.Threading.Thread.SleepInternal(Int32)
0000001fc727f260 00007ffb37ea7c2b System.Threading.Thread.Sleep(Int32)
0000001fc727f290 00007ffa865005b3 test.Program.ThreadProc() [E:\unloadability\test\Program.cs @ 17]
0000001fc727f2c0 00007ffb37ea6a5b System.Threading.Thread.ThreadMain_ThreadStart()
0000001fc727f2f0 00007ffadbc4cbe3 System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object)
0000001fc727f568 00007ffae5fdc1e3 [GCFrame: 0000001fc727f568] 
0000001fc727f7f0 00007ffae5fdc1e3 [DebuggerU2MCatchHandlerFrame: 0000001fc727f7f0] 

```

<span data-ttu-id="0da88-209">Wie Sie erkennen können, weist der letzte Thread `test.Program.ThreadProc()` auf.</span><span class="sxs-lookup"><span data-stu-id="0da88-209">As you can see, the last thread has `test.Program.ThreadProc()`.</span></span> <span data-ttu-id="0da88-210">Dabei handelt es sich um eine Funktion aus der Assembly, die in den `AssemblyLoadContext` geladen wird, sodass der `AssemblyLoadContext` aktiv bleibt.</span><span class="sxs-lookup"><span data-stu-id="0da88-210">This is a function from the assembly loaded into the `AssemblyLoadContext`, and so it keeps the `AssemblyLoadContext` alive.</span></span>

## <a name="example-source-with-unloadability-issues"></a><span data-ttu-id="0da88-211">Beispielquellcode mit Problemen bei der Entladbarkeit</span><span class="sxs-lookup"><span data-stu-id="0da88-211">Example source with unloadability issues</span></span>

<span data-ttu-id="0da88-212">Der folgende Code wird im vorherigen Debugbeispiel verwendet.</span><span class="sxs-lookup"><span data-stu-id="0da88-212">The following code is used in the previous debugging example.</span></span>

### <a name="main-testing-program"></a><span data-ttu-id="0da88-213">Haupttestprogramm</span><span class="sxs-lookup"><span data-stu-id="0da88-213">Main testing program</span></span>

[!code-csharp[Main testing program](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_main.cs)]

## <a name="program-loaded-into-the-testassemblyloadcontext"></a><span data-ttu-id="0da88-214">In den TestAssemblyLoadContext geladenes Programm</span><span class="sxs-lookup"><span data-stu-id="0da88-214">Program loaded into the TestAssemblyLoadContext</span></span>

<span data-ttu-id="0da88-215">Der folgende Code stellt die `test.dll` dar, die an die `ExecuteAndUnload`-Methode im Haupttestprogramm übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="0da88-215">The following code represents the `test.dll` passed to the `ExecuteAndUnload` method in the main testing program.</span></span>

[!code-csharp[Program loaded into the TestAssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_test.cs)]
