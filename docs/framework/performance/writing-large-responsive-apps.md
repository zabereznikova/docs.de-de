---
title: Schreiben großer, reaktionsfähiger .NET Framework-Apps
description: Schreiben Sie große, reaktionsschnelle .net-apps oder apps, die große Datenmengen verarbeiten, z. b. Dateien oder Datenbanken.
ms.date: 03/30/2017
ms.assetid: 123457ac-4223-4273-bb58-3bc0e4957e9d
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 20b9f34595f8586eb5162715eb6b0df171f132a1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266843"
---
# <a name="writing-large-responsive-net-framework-apps"></a><span data-ttu-id="b7209-103">Schreiben großer, reaktionsfähiger .NET Framework-Apps</span><span class="sxs-lookup"><span data-stu-id="b7209-103">Writing Large, Responsive .NET Framework Apps</span></span>

<span data-ttu-id="b7209-104">In diesem Artikel werden Tipps zum Verbessern der Leistung von großen .NET Framework-Apps oder Apps bereitgestellt, die großen Datenmengen wie Dateien oder Datenbanken verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b7209-104">This article provides tips for improving the performance of large .NET Framework apps, or apps that process a large amount of data such as files or databases.</span></span> <span data-ttu-id="b7209-105">Die Tipps stammen aus dem Umschreiben der C#- und Visual Basic-Compiler in verwalteten Code, und dieser Artikel enthält mehrere reale Beispiele aus dem C#-Compiler.</span><span class="sxs-lookup"><span data-stu-id="b7209-105">These tips come from rewriting the C# and Visual Basic compilers in managed code, and this article includes several real examples from the C# compiler.</span></span>
  
<span data-ttu-id="b7209-106">.NET Framework ist sehr produktiv für das Erstellen von Apps.</span><span class="sxs-lookup"><span data-stu-id="b7209-106">The .NET Framework is highly productive for building apps.</span></span> <span data-ttu-id="b7209-107">Leistungsstarke und sichere Sprachen und eine umfassende Sammlung von Bibliotheken sorgen für eine sehr erfolgreiche Erstellung von Apps.</span><span class="sxs-lookup"><span data-stu-id="b7209-107">Powerful and safe languages and a rich collection of libraries make app building highly fruitful.</span></span> <span data-ttu-id="b7209-108">Aber mit großer Produktivität geht auch Verantwortung einher.</span><span class="sxs-lookup"><span data-stu-id="b7209-108">However, with great productivity comes responsibility.</span></span> <span data-ttu-id="b7209-109">Sie sollten die gesamte Leistung von .NET Framework nutzen, aber darauf vorbereitet sein, die Leistung Ihres Codes bei Bedarf abzustimmen.</span><span class="sxs-lookup"><span data-stu-id="b7209-109">You should use all the power of the .NET Framework, but be prepared to tune your code’s performance when needed.</span></span>
  
## <a name="why-the-new-compiler-performance-applies-to-your-app"></a><span data-ttu-id="b7209-110">Warum die neue Compilerleistung für Ihre App angewendet werden kann</span><span class="sxs-lookup"><span data-stu-id="b7209-110">Why the new compiler performance applies to your app</span></span>  

 <span data-ttu-id="b7209-111">Das .NET Compiler Platform-Team („Roslyn“) hat die C#- und Visual Basic-Compiler in verwalteten Code umgeschrieben, um neue APIs für das Modellieren und Analysieren von Code, das Erstellen von Tools und das Unterstützen einer wesentlich umfassenderen codeabhängigen Erfahrung in Visual Studio bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b7209-111">The .NET Compiler Platform ("Roslyn") team rewrote the C# and Visual Basic compilers in managed code to provide new APIs for modeling and analyzing code, building tools, and enabling much richer, code-aware experiences in Visual Studio.</span></span> <span data-ttu-id="b7209-112">Das Umschreiben der Compiler und das Erstellen von Visual Studio-Erfahrungen in den neuen Compilern hat nützliche Leistungseinblicke ergeben, die für jede große .NET Framework-App oder jede App anwendbar sind, die viele Daten verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b7209-112">Rewriting the compilers and building Visual Studio experiences on the new compilers revealed useful performance insights that are applicable to any large .NET Framework app or any app that processes a lot of data.</span></span> <span data-ttu-id="b7209-113">Sie müssen sich nicht mit Compilern auskennen, um die Einblicke und Beispiele aus dem C#-Compiler nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="b7209-113">You don't need to know about compilers to take advantage of the insights and examples from the C# compiler.</span></span>
  
 <span data-ttu-id="b7209-114">Visual Studio verwendet die Compiler-APIs, um all die IntelliSense-Funktionen zu erstellen, die bei Benutzern beliebt sind, zum Beispiel die farbliche Kennzeichnung von Bezeichnern und Schlüsselwörtern, Syntaxvervollständigungslisten, Wellenlinien für Fehler, Parametertipps, Codeprobleme und Codeaktionen.</span><span class="sxs-lookup"><span data-stu-id="b7209-114">Visual Studio uses the compiler APIs to build all the IntelliSense features that users love, such as colorization of identifiers and keywords, syntax completion lists, squiggles for errors, parameter tips, code issues, and code actions.</span></span> <span data-ttu-id="b7209-115">Visual Studio stellt diese Hilfe bereit, während Entwickler ihren Code eingeben und ändern, und Visual Studio muss reaktionsfähig bleiben, während der Compiler den von Entwicklern bearbeiteten Code kontinuierlich modelliert.</span><span class="sxs-lookup"><span data-stu-id="b7209-115">Visual Studio provides this help while developers are typing and changing their code, and Visual Studio must remain responsive while the compiler continually models the code developers edit.</span></span>
  
 <span data-ttu-id="b7209-116">Wenn Ihre Endbenutzer mit der App interagieren, erwarten sie, dass die App reaktionsfähig ist.</span><span class="sxs-lookup"><span data-stu-id="b7209-116">When your end users interact with your app, they expect it to be responsive.</span></span> <span data-ttu-id="b7209-117">Eingaben oder Befehlsverarbeitung sollten nie blockiert sein.</span><span class="sxs-lookup"><span data-stu-id="b7209-117">Typing or command handling should never be blocked.</span></span> <span data-ttu-id="b7209-118">Die Hilfe sollte schnell angezeigt oder geschlossen werden, wenn der Benutzer die Eingabe fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="b7209-118">Help should pop up quickly or give up if the user continues typing.</span></span> <span data-ttu-id="b7209-119">Ihre App sollte vermeiden, den UI-Thread mit langen Berechnungen zu blockieren, die Ihre App langsam machen.</span><span class="sxs-lookup"><span data-stu-id="b7209-119">Your app should avoid blocking the UI thread with long computations that make the app feel sluggish.</span></span>
  
 <span data-ttu-id="b7209-120">Weitere Informationen zu Roslyn-Compilern finden Sie [im .NET Compiler Platform SDK](../../csharp/roslyn-sdk/index.md).</span><span class="sxs-lookup"><span data-stu-id="b7209-120">For more information about Roslyn compilers, see [The .NET Compiler Platform SDK](../../csharp/roslyn-sdk/index.md).</span></span>
  
## <a name="just-the-facts"></a><span data-ttu-id="b7209-121">Reine Tatsachen</span><span class="sxs-lookup"><span data-stu-id="b7209-121">Just the Facts</span></span>  

 <span data-ttu-id="b7209-122">Berücksichtigen Sie die folgenden Tatsachen, wenn Sie die Leistung optimieren und reaktionsfähige .NET Framework-Apps erstellen.</span><span class="sxs-lookup"><span data-stu-id="b7209-122">Consider these facts when tuning performance and creating responsive .NET Framework apps.</span></span>
  
### <a name="fact-1-dont-prematurely-optimize"></a><span data-ttu-id="b7209-123">Tatsache 1: Vermeiden Sie eine vorzeitige Optimierung.</span><span class="sxs-lookup"><span data-stu-id="b7209-123">Fact 1: Don’t prematurely optimize</span></span>  

 <span data-ttu-id="b7209-124">Das Schreiben von Code, der komplexer als notwendig ist, zieht Kosten für Wartung, Debugging und Verfeinerung nach sich.</span><span class="sxs-lookup"><span data-stu-id="b7209-124">Writing code that is more complex than it needs to be incurs maintenance, debugging, and polishing costs.</span></span> <span data-ttu-id="b7209-125">Erfahrene Programmierer verstehen intuitiv, wie sie Codierungsprobleme lösen und einen effizienteren Code schreiben.</span><span class="sxs-lookup"><span data-stu-id="b7209-125">Experienced programmers have an intuitive grasp of how to solve coding problems and write more efficient code.</span></span> <span data-ttu-id="b7209-126">Dennoch optimieren Sie ihren Code manchmal vorzeitig.</span><span class="sxs-lookup"><span data-stu-id="b7209-126">However, they sometimes prematurely optimize their code.</span></span> <span data-ttu-id="b7209-127">Sie verwenden beispielsweise eine Hashtabelle, wenn ein einfaches Array ausreichen würde, oder sie verwenden ein kompliziertes Zwischenspeichern, das möglicherweise Speicherverluste verursacht statt einfach Werte neu zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="b7209-127">For example, they use a hash table when a simple array would suffice, or use complicated caching that may leak memory instead of simply recomputing values.</span></span> <span data-ttu-id="b7209-128">Selbst wenn Sie ein erfahrener Programmierer sind, sollten Sie Ihren Code auf Leistung testen und analysieren, wenn Sie Probleme finden.</span><span class="sxs-lookup"><span data-stu-id="b7209-128">Even if you’re an experience programmer, you should test for performance and analyze your code when you find issues.</span></span>
  
### <a name="fact-2-if-youre-not-measuring-youre-guessing"></a><span data-ttu-id="b7209-129">Tatsache 2: Wenn Sie nicht messen, raten Sie.</span><span class="sxs-lookup"><span data-stu-id="b7209-129">Fact 2: If you’re not measuring, you’re guessing</span></span>  

 <span data-ttu-id="b7209-130">Profile und Messungen lügen nicht.</span><span class="sxs-lookup"><span data-stu-id="b7209-130">Profiles and measurements don’t lie.</span></span> <span data-ttu-id="b7209-131">Profile zeigen Ihnen, ob die CPU vollständig geladen ist oder Sie von Datenträger-E/A blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="b7209-131">Profiles show you whether the CPU is fully loaded or whether you’re blocked on disk I/O.</span></span> <span data-ttu-id="b7209-132">Profile teilen Ihnen mit, welche Art und wie viel Speicher Sie zuweisen und ob Ihre CPU viel Zeit in der [Garbage Collection](../../standard/garbage-collection/index.md) (GC) verbringt.</span><span class="sxs-lookup"><span data-stu-id="b7209-132">Profiles tell you what kind and how much memory you’re allocating and whether your CPU is spending a lot of time in [garbage collection](../../standard/garbage-collection/index.md) (GC).</span></span>
  
 <span data-ttu-id="b7209-133">Sie sollten Leistungsziele für wichtige Kundenerfahrungen oder -szenarien in Ihrer App festlegen und Tests schreiben, um die Leistung zu messen.</span><span class="sxs-lookup"><span data-stu-id="b7209-133">You should set performance goals for key customer experiences or scenarios in your app and write tests to measure performance.</span></span> <span data-ttu-id="b7209-134">Untersuchen Sie fehlschlagende Tests, indem Sie die wissenschaftliche Methode anwenden: Verwenden Sie Profile, um Ihnen die Richtung zu weisen, stellen Sie Hypothesen auf, worin das Problem bestehen könnte, und testen Sie Ihre Hypothese mit einem Experiment oder einer Codeänderung.</span><span class="sxs-lookup"><span data-stu-id="b7209-134">Investigate failing tests by applying the scientific method: use profiles to guide you, hypothesize what the issue might be, and test your hypothesis with an experiment or code change.</span></span> <span data-ttu-id="b7209-135">Richten Sie Baselineleistungsmessungen über die Zeit mit regelmäßigen Tests ein, damit Sie Änderungen isolieren können, die Leistungsregressionen verursachen.</span><span class="sxs-lookup"><span data-stu-id="b7209-135">Establish baseline performance measurements over time with regular testing, so you can isolate changes that cause regressions in performance.</span></span> <span data-ttu-id="b7209-136">Wenn Sie die Leistungsarbeit auf eine rigorose Weise angehen, verschwenden Sie keine Zeit mit Codeaktualisierungen, die Sie nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="b7209-136">By approaching performance work in a rigorous way, you’ll avoid wasting time with code updates you don’t need.</span></span>
  
### <a name="fact-3-good-tools-make-all-the-difference"></a><span data-ttu-id="b7209-137">Tatsache 3: Gute Tools machen einen großen Unterschied.</span><span class="sxs-lookup"><span data-stu-id="b7209-137">Fact 3: Good tools make all the difference</span></span>  

 <span data-ttu-id="b7209-138">Mit guten Tools können Sie schnell einen Drilldown in die größten Leistungsprobleme (CPU, Speicher oder Datenträger) ausführen und den Code finden, der diese Engpässe verursacht.</span><span class="sxs-lookup"><span data-stu-id="b7209-138">Good tools let you drill quickly into the biggest performance issues (CPU, memory, or disk) and help you locate the code that causes those bottlenecks.</span></span> <span data-ttu-id="b7209-139">Microsoft umfasst eine Reihe von Leistungs Tools wie [Visual Studio Profiler](/visualstudio/profiling/beginners-guide-to-performance-profiling) und [perfview](https://www.microsoft.com/download/details.aspx?id=28567).</span><span class="sxs-lookup"><span data-stu-id="b7209-139">Microsoft ships a variety of performance tools such as [Visual Studio Profiler](/visualstudio/profiling/beginners-guide-to-performance-profiling) and [PerfView](https://www.microsoft.com/download/details.aspx?id=28567).</span></span>
  
 <span data-ttu-id="b7209-140">PerfView ist ein kostenloses und erstaunlich leistungsstarkes Tool, mit dem Sie sich auf tiefliegende Probleme wie Datenträger-E/A, GC-Ereignisse und Arbeitsspeicher konzentrieren können.</span><span class="sxs-lookup"><span data-stu-id="b7209-140">PerfView is a free and amazingly powerful tool that helps you focus on deep issues such as disk I/O, GC events, and memory.</span></span> <span data-ttu-id="b7209-141">Sie erfassen leistungsrelevante Ereignisse der [Ereignisablaufverfolgung für Windows](../wcf/samples/etw-tracing.md) (Event Tracing for Windows, ETW) und zeigen auf einfache Weise Informationen pro App, pro Prozess, pro Stapel und pro Thread an.</span><span class="sxs-lookup"><span data-stu-id="b7209-141">You can capture performance-related [Event Tracing for Windows](../wcf/samples/etw-tracing.md) (ETW) events and view easily per app, per process, per stack, and per thread information.</span></span> <span data-ttu-id="b7209-142">PerfView zeigt Ihnen, wie viel und welche Art von Speicher Ihre App zuweist und welche Funktionen oder Aufrufstapel zu welchem Anteil der Speicherbelegungen beitragen.</span><span class="sxs-lookup"><span data-stu-id="b7209-142">PerfView shows you how much and what kind of memory your app allocates, and which functions or call stacks contribute how much to the memory allocations.</span></span> <span data-ttu-id="b7209-143">Einzelheiten finden Sie in den umfassenden Hilfethemen, Demos und Videos, die mit dem Tool ausgeliefert werden (zum Beispiel die [PerfView-Tutorials](https://channel9.msdn.com/Series/PerfView-Tutorial) auf Channel 9).</span><span class="sxs-lookup"><span data-stu-id="b7209-143">For details, see the rich help topics, demos, and videos included with the tool (such as the [PerfView tutorials](https://channel9.msdn.com/Series/PerfView-Tutorial) on Channel 9).</span></span>
  
### <a name="fact-4-its-all-about-allocations"></a><span data-ttu-id="b7209-144">Tatsache 4: Es dreht sich alles um Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="b7209-144">Fact 4: It’s all about allocations</span></span>  

 <span data-ttu-id="b7209-145">Möglicherweise denken Sie, dass es beim Erstellen einer reaktionsfähigen .NET Framework-App vor allem um Algorithmen wie die Verwendung von QuickSort anstelle von BubbleSort geht, aber das ist nicht der Fall.</span><span class="sxs-lookup"><span data-stu-id="b7209-145">You might think that building a responsive .NET Framework app is all about algorithms, such as using quick sort instead of bubble sort, but that's not the case.</span></span> <span data-ttu-id="b7209-146">Der größte Faktor bei der Erstellung einer reaktionsfähigen App ist die Speicherbelegung, insbesondere wenn Ihre App sehr groß ist oder große Datenmengen verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b7209-146">The biggest factor in building a responsive app is allocating memory, especially when your app is very large or processes large amounts of data.</span></span>
  
 <span data-ttu-id="b7209-147">Nahezu die gesamte Arbeit beim Erstellen reaktionsfähiger IDE-Erfahrungen mit den neuen Compiler-APIs beinhaltete das Vermeiden von Speicherbelegungen und das Verwalten von Zwischenspeicherstrategien.</span><span class="sxs-lookup"><span data-stu-id="b7209-147">Almost all the work to build responsive IDE experiences with the new compiler APIs involved avoiding allocations and managing caching strategies.</span></span> <span data-ttu-id="b7209-148">PerfView-Ablaufverfolgungen zeigen, dass die Leistung der neuen C#- und Visual Basic-Compiler selten CPU-gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="b7209-148">PerfView traces show that the performance of the new C# and Visual Basic compilers is rarely CPU bound.</span></span> <span data-ttu-id="b7209-149">Die Compiler können E/A-gebunden sein, wenn Sie Hundertausende oder Millionen von Codezielen oder Metadaten lesen oder generierten Code ausgeben.</span><span class="sxs-lookup"><span data-stu-id="b7209-149">The compilers can be I/O bound when reading hundreds of thousands or millions of lines of code, reading metadata, or emitting generated code.</span></span> <span data-ttu-id="b7209-150">Die UI-Threadverzögerungen erfolgen nahezu alle wegen der Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b7209-150">The UI thread delays are nearly all due to garbage collection.</span></span> <span data-ttu-id="b7209-151">Die .NET Framework GC ist weitgehend für Leistung optimiert und führt einen großen Teil ihrer Arbeit parallel zur Ausführung von App-Code durch.</span><span class="sxs-lookup"><span data-stu-id="b7209-151">The .NET Framework GC is highly tuned for performance and does much of its work concurrently while app code executes.</span></span> <span data-ttu-id="b7209-152">Dennoch kann eine einzige Speicherbelegung eine teure [gen2](../../standard/garbage-collection/fundamentals.md)-Collection auslösen, die alle Threads anhält.</span><span class="sxs-lookup"><span data-stu-id="b7209-152">However, a single allocation can trigger an expensive [gen2](../../standard/garbage-collection/fundamentals.md) collection, stopping all threads.</span></span>
  
## <a name="common-allocations-and-examples"></a><span data-ttu-id="b7209-153">Typische Speicherbelegungen und Beispiele</span><span class="sxs-lookup"><span data-stu-id="b7209-153">Common allocations and examples</span></span>  

 <span data-ttu-id="b7209-154">Die Beispielausdrücke in diesem Abschnitt haben verborgene Speicherbelegungen, die klein erscheinen.</span><span class="sxs-lookup"><span data-stu-id="b7209-154">The example expressions in this section have hidden allocations that appear small.</span></span> <span data-ttu-id="b7209-155">Aber wenn eine große App die Ausdrücke oft genug ausführt, können Sie Speicherbelegungen mit Hunderten von Megabyte oder sogar Gigabyte verursachen.</span><span class="sxs-lookup"><span data-stu-id="b7209-155">However, if a large app executes the expressions enough times, they can causes hundreds of megabytes, even gigabytes, of allocations.</span></span> <span data-ttu-id="b7209-156">Beispielsweise wurden bei einminütigen Tests, in denen eine Eingabe des Entwicklers im Editor simuliert wurden, mehrere Gigabyte Speicher belegt und dazu geführt, dass sich das Leistungsteam auf Eingabeszenarien konzentrierte.</span><span class="sxs-lookup"><span data-stu-id="b7209-156">For example, one-minute tests that simulated a developer’s typing in the editor allocated gigabytes of memory and led the performance team to focus on typing scenarios.</span></span>
  
### <a name="boxing"></a><span data-ttu-id="b7209-157">Boxing</span><span class="sxs-lookup"><span data-stu-id="b7209-157">Boxing</span></span>  

 <span data-ttu-id="b7209-158">[Boxing](../../csharp/programming-guide/types/boxing-and-unboxing.md) findet statt, wenn Werttypen, die normalerweise im Stapel oder in Datenstrukturen vorkommen, in ein Objekt eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="b7209-158">[Boxing](../../csharp/programming-guide/types/boxing-and-unboxing.md) occurs when value types that normally live on the stack or in data structures are wrapped in an object.</span></span> <span data-ttu-id="b7209-159">Das heißt, Sie ordnen ein Objekt zu, das die Daten hält, und geben dann einen Zeiger zum Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="b7209-159">That is, you allocate an object to hold the data, and then return a pointer to the object.</span></span> <span data-ttu-id="b7209-160">.NET Framework führt das Boxing von Werten manchmal aufgrund der Signatur einer Methode oder des Typs eines Speicherstandorts durch.</span><span class="sxs-lookup"><span data-stu-id="b7209-160">The .NET Framework sometimes boxes values due to the signature of a method or the type of a storage location.</span></span> <span data-ttu-id="b7209-161">Das Einschließen eines Werttyps in ein Objekt führt zu einer Speicherbelegung.</span><span class="sxs-lookup"><span data-stu-id="b7209-161">Wrapping a value type in an object causes memory allocation.</span></span> <span data-ttu-id="b7209-162">Viele Boxingvorgänge können zu Speicherbelegungen mit mehrere Megabyte oder Gigabyte für Ihre App beitragen, was bedeutet, dass Ihre App mehr GCs verursacht.</span><span class="sxs-lookup"><span data-stu-id="b7209-162">Many boxing operations can contribute megabytes or gigabytes of allocations to your app, which means that your app will cause more GCs.</span></span> <span data-ttu-id="b7209-163">.NET Framework und die Sprachcompiler vermeiden das Boxing, wenn möglich, aber manchmal kommt es dazu, wenn Sie es am wenigsten erwarten.</span><span class="sxs-lookup"><span data-stu-id="b7209-163">The .NET Framework and the language compilers avoid boxing when possible, but sometimes it happens when you least expect it.</span></span>
  
 <span data-ttu-id="b7209-164">Um Boxing in PerfView zu sehen, öffnen Sie eine Ablaufverfolgung, und sehen Sie sich GC-Heapbelegungsstapel unter dem Prozessnamen Ihrer App an (denken Sie daran, dass PerfView Berichte zu allen Prozessen erstellt).</span><span class="sxs-lookup"><span data-stu-id="b7209-164">To see boxing in PerfView, open a trace and look at GC Heap Alloc Stacks under your app’s process name (remember, PerfView reports on all processes).</span></span> <span data-ttu-id="b7209-165">Wenn Sie Typen wie <xref:System.Int32?displayProperty=nameWithType> und <xref:System.Char?displayProperty=nameWithType> unter Belegungen sehen, wird ein Boxing von Werttypen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="b7209-165">If you see types like <xref:System.Int32?displayProperty=nameWithType> and <xref:System.Char?displayProperty=nameWithType> under allocations, you are boxing value types.</span></span> <span data-ttu-id="b7209-166">Wenn Sie einen dieser Typen auswählen, werden die Stapel und Funktionen angezeigt, in denen sie verschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="b7209-166">Choosing one of these types will show the stacks and functions in which they are boxed.</span></span>
  
 <span data-ttu-id="b7209-167">**Beispiel 1: Zeichenfolgenmethoden und Werttypargumente**</span><span class="sxs-lookup"><span data-stu-id="b7209-167">**Example 1: string methods and value type arguments**</span></span>  
  
 <span data-ttu-id="b7209-168">In diesem Beispielcode wird ein potenziell unnötiges und übermäßiges Boxing dargestellt:</span><span class="sxs-lookup"><span data-stu-id="b7209-168">This sample code illustrates potentially unnecessary and excessive boxing:</span></span>  
  
```csharp  
public class Logger  
{  
    public static void WriteLine(string s) { /*...*/ }  
}  
  
public class BoxingExample  
{  
    public void Log(int id, int size)  
    {  
        var s = string.Format("{0}:{1}", id, size);  
        Logger.WriteLine(s);  
    }  
}  
```  
  
 <span data-ttu-id="b7209-169">Dieser Code stellt Protokollierungsfunktionen bereit, was bedeutet, dass eine App die `Log`-Funktion häufig, möglicherweise mehrere Millionen mal aufruft.</span><span class="sxs-lookup"><span data-stu-id="b7209-169">This code provides logging functionality, so an app may call the `Log` function frequently, maybe millions of times.</span></span> <span data-ttu-id="b7209-170">Das Problem ist, dass der Aufruf an `string.Format` in die <xref:System.String.Format%28System.String%2CSystem.Object%2CSystem.Object%29>-Überladung aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="b7209-170">The problem is that the call to `string.Format` resolves to the <xref:System.String.Format%28System.String%2CSystem.Object%2CSystem.Object%29> overload.</span></span>
  
 <span data-ttu-id="b7209-171">Für diese Überladung muss .NET die `int`-Werte in Objekten verschachteln, um sie an diesen Methodenaufruf zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="b7209-171">This overload requires the .NET Framework to box the `int` values into objects to pass them to this method call.</span></span> <span data-ttu-id="b7209-172">Eine Teilkorrektur besteht darin, `id.ToString()` und `size.ToString()` aufzurufen und alle Zeichenfolgen (die Objekte sind) an den `string.Format`-Aufruf zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="b7209-172">A partial fix is to call `id.ToString()` and `size.ToString()` and pass all strings (which are objects) to the `string.Format` call.</span></span> <span data-ttu-id="b7209-173">Das Aufrufen von `ToString()` ordnet eine Zeichenfolge zu, aber diese Zuordnung findet in `string.Format` sowieso statt.</span><span class="sxs-lookup"><span data-stu-id="b7209-173">Calling `ToString()` does allocate a string, but that allocation will happen anyway inside `string.Format`.</span></span>
  
 <span data-ttu-id="b7209-174">Sie können überlegen, dass dieser grundlegende Aufruf an `string.Format` nur eine Zeichenfolgenverkettung ist, deshalb können Sie stattdessen den folgenden Code schreiben:</span><span class="sxs-lookup"><span data-stu-id="b7209-174">You might consider that this basic call to `string.Format` is just string concatenation, so you might write this code instead:</span></span>  
  
```csharp  
var s = id.ToString() + ':' + size.ToString();  
```  
  
 <span data-ttu-id="b7209-175">Diese Codezeile führt jedoch eine Boxingbelegung ein, da sie zu <xref:System.String.Concat%28System.Object%2CSystem.Object%2CSystem.Object%29> kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="b7209-175">However, that line of code introduces a boxing allocation because it compiles to <xref:System.String.Concat%28System.Object%2CSystem.Object%2CSystem.Object%29>.</span></span> <span data-ttu-id="b7209-176">.NET Framework muss das Zeichenliteral verschachteln, um `Concat` aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="b7209-176">The .NET Framework must box the character literal to invoke `Concat`</span></span>  
  
 <span data-ttu-id="b7209-177">**Korrektur für Beispiel 1**</span><span class="sxs-lookup"><span data-stu-id="b7209-177">**Fix for example 1**</span></span>  
  
 <span data-ttu-id="b7209-178">Die vollständige Korrektur ist einfach.</span><span class="sxs-lookup"><span data-stu-id="b7209-178">The complete fix is simple.</span></span> <span data-ttu-id="b7209-179">Ersetzen Sie einfach das Zeichenliteral mit einem Zeichenfolgenliteral, das kein Boxing hervorruft, da Zeichenfolgen bereits Objekte sind:</span><span class="sxs-lookup"><span data-stu-id="b7209-179">Just replace the character literal with a string literal, which incurs no boxing because strings are already objects:</span></span>  
  
```csharp  
var s = id.ToString() + ":" + size.ToString();  
```  
  
 <span data-ttu-id="b7209-180">**Beispiel 2: Enum-Boxing**</span><span class="sxs-lookup"><span data-stu-id="b7209-180">**Example 2: enum boxing**</span></span>  
  
 <span data-ttu-id="b7209-181">Dieses Beispiel war aufgrund der häufigen Verwendung von Enumerationstypen, insbesondere bei Wörterbuchsuchvorgängen, für eine enorme Menge an Belegung in den neuen C#- und Visual Basic-Compilern verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="b7209-181">This example was responsible for a huge amount of allocation in the new C# and Visual Basic compilers due to frequent use of enumeration types, especially in dictionary lookup operations.</span></span>
  
```csharp  
public enum Color  
{  
    Red, Green, Blue  
}  
  
public class BoxingExample  
{  
    private string name;  
    private Color color;  
    public override int GetHashCode()  
    {  
        return name.GetHashCode() ^ color.GetHashCode();  
    }  
}  
```  
  
 <span data-ttu-id="b7209-182">Das Problem ist sehr subtil.</span><span class="sxs-lookup"><span data-stu-id="b7209-182">This problem is very subtle.</span></span> <span data-ttu-id="b7209-183">PerfView würde dies als <xref:System.Enum.GetHashCode>-Boxing melden, weil die Methode die zugrunde liegende Darstellung des Enumerationstyps aus Implementierungsgründen verschachtelt.</span><span class="sxs-lookup"><span data-stu-id="b7209-183">PerfView would report this as <xref:System.Enum.GetHashCode> boxing because the method boxes the underlying representation of the enumeration type, for implementation reasons.</span></span> <span data-ttu-id="b7209-184">Wenn Sie in PerfView genau hinsehen, sehen Sie möglicherweise zwei Boxingzuordnungen für jeden Aufruf an <xref:System.Enum.GetHashCode>.</span><span class="sxs-lookup"><span data-stu-id="b7209-184">If you look closely in PerfView, you may see two boxing allocations for each call to <xref:System.Enum.GetHashCode>.</span></span> <span data-ttu-id="b7209-185">Der Compiler fügt eine ein, .NET Framework die andere.</span><span class="sxs-lookup"><span data-stu-id="b7209-185">The compiler inserts one, and the .NET Framework inserts the other.</span></span>
  
 <span data-ttu-id="b7209-186">**Korrektur für Beispiel 2**</span><span class="sxs-lookup"><span data-stu-id="b7209-186">**Fix for example 2**</span></span>  
  
 <span data-ttu-id="b7209-187">Sie können beide Zuordnungen leicht vermeiden, indem Sie eine Umwandlung zur zugrunde liegenden Darstellung vornehmen, bevor Sie <xref:System.Enum.GetHashCode> aufrufen:</span><span class="sxs-lookup"><span data-stu-id="b7209-187">You can easily avoid both allocations by casting to the underlying representation before calling <xref:System.Enum.GetHashCode>:</span></span>  
  
```csharp  
((int)color).GetHashCode()  
```  
  
 <span data-ttu-id="b7209-188">Eine andere übliche Quelle für das Boxing bei Enumerationstypen ist die <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="b7209-188">Another common source of boxing on enumeration types is the <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="b7209-189">Das an <xref:System.Enum.HasFlag%28System.Enum%29> übergebene Argument muss geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="b7209-189">The argument passed to <xref:System.Enum.HasFlag%28System.Enum%29> has to be boxed.</span></span> <span data-ttu-id="b7209-190">In den meisten Fällen ist es einfacher und zuordnungsfrei, Aufrufe an <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType> durch einen bitweisen Test zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="b7209-190">In most cases, replacing calls to <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType> with a bitwise test is simpler and allocation-free.</span></span>
  
 <span data-ttu-id="b7209-191">Behalten Sie die erste Leistungstatsache im Hinterkopf (keine vorzeitige Optimierung), und fangen Sie nicht an, Ihren gesamten Code auf diese Weise umzuschreiben.</span><span class="sxs-lookup"><span data-stu-id="b7209-191">Keep the first performance fact in mind (that is, don’t prematurely optimize) and don’t start rewriting all your code in this way.</span></span> <span data-ttu-id="b7209-192">Ihnen sollten diese Boxingkosten bewusst sein, aber Sie sollten Ihren Code nur ändern, nachdem Sie ein Profil für Ihre App erstellt und die Hotspots gefunden haben.</span><span class="sxs-lookup"><span data-stu-id="b7209-192">Be aware of these boxing costs, but change your code only after profiling your app and finding the hot spots.</span></span>
  
### <a name="strings"></a><span data-ttu-id="b7209-193">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="b7209-193">Strings</span></span>  

 <span data-ttu-id="b7209-194">Zeichenfolgenmanipulationen zählen zu den größten Verursachern von Zuordnungen und zeigen sich in PerfView oft in den ersten fünf Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="b7209-194">String manipulations are some of the biggest culprits for allocations, and they often show up in PerfView in the top five allocations.</span></span> <span data-ttu-id="b7209-195">Programme verwenden Zeichenfolgen für die Serialisierung, JSON und REST-APIs.</span><span class="sxs-lookup"><span data-stu-id="b7209-195">Programs use strings for serialization, JSON, and REST APIs.</span></span> <span data-ttu-id="b7209-196">Sie können Zeichenfolgen als programmgesteuerte Konstanten für die Interoperation mit Systemen verwenden, wenn Sie keine Enumerationstypen benutzen können.</span><span class="sxs-lookup"><span data-stu-id="b7209-196">You can use strings as programmatic constants for interoperating with systems when you can’t use enumeration types.</span></span> <span data-ttu-id="b7209-197">Wenn Ihre Profilerstellung zeigt, dass sich Zeichenfolgen stark auf die Leistungs auswirken, suchen Sie nach Aufrufen an <xref:System.String>-Methoden wie <xref:System.String.Format%2A>, <xref:System.String.Concat%2A>, <xref:System.String.Split%2A>, <xref:System.String.Join%2A>, <xref:System.String.Substring%2A> und so weiter.</span><span class="sxs-lookup"><span data-stu-id="b7209-197">When your profiling shows that strings are highly affecting performance, look for calls to <xref:System.String> methods such as <xref:System.String.Format%2A>, <xref:System.String.Concat%2A>, <xref:System.String.Split%2A>, <xref:System.String.Join%2A>, <xref:System.String.Substring%2A>, and so on.</span></span> <span data-ttu-id="b7209-198">Die Verwendung von <xref:System.Text.StringBuilder> zum Vermeiden der Kosten der Erstellung einer Zeichenfolge aus vielen Teilen hilft, aber selbst das Zuordnen des <xref:System.Text.StringBuilder>-Objekts kann zu einem Engpass werden, den Sie verwalten müssen.</span><span class="sxs-lookup"><span data-stu-id="b7209-198">Using <xref:System.Text.StringBuilder> to avoid the cost of creating one string from many pieces helps, but even allocating the <xref:System.Text.StringBuilder> object might become a bottleneck that you need to manage.</span></span>
  
 <span data-ttu-id="b7209-199">**Beispiel 3: Zeichenfolgenvorgänge**</span><span class="sxs-lookup"><span data-stu-id="b7209-199">**Example 3: string operations**</span></span>  
  
 <span data-ttu-id="b7209-200">Der C#-Compiler hatte den folgenden Code, der den Text eines formatierten XML-Dokumentationskommentars schreibt:</span><span class="sxs-lookup"><span data-stu-id="b7209-200">The C# compiler had this code that writes the text of a formatted XML doc comment:</span></span>  
  
```csharp  
public void WriteFormattedDocComment(string text)  
{  
    string[] lines = text.Split(new[] { "\r\n", "\r", "\n" },  
                                StringSplitOptions.None);  
    int numLines = lines.Length;  
    bool skipSpace = true;  
    if (lines[0].TrimStart().StartsWith("///"))  
    {  
        for (int i = 0; i < numLines; i++)  
        {  
            string trimmed = lines[i].TrimStart();  
            if (trimmed.Length < 4 || !char.IsWhiteSpace(trimmed[3]))  
            {  
                skipSpace = false;  
                break;  
            }  
        }  
        int substringStart = skipSpace ? 4 : 3;  
        for (int i = 0; i < numLines; i++)  
            WriteLine(lines[i].TrimStart().Substring(substringStart));  
    }  
    else { /* ... */ }  
```  
  
 <span data-ttu-id="b7209-201">Sie können sehen, dass dieser Code eine Menge Zeichenfolgenmanipulation durchführt.</span><span class="sxs-lookup"><span data-stu-id="b7209-201">You can see that this code does a lot of string manipulation.</span></span> <span data-ttu-id="b7209-202">Der Code verwendet Bibliotheksmethoden, um Zeilen in separate Zeichenfolgen zu trennen, Leerzeichen zu entfernen, zu überprüfen, ob das Argument `text` ein XML-Dokumentationskommentar ist, und untergeordnete Zeichenfolgen zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="b7209-202">The code uses library methods to split lines into separate strings, to trim white space, to check whether the argument `text` is an XML documentation comment, and to extract substrings from lines.</span></span>
  
 <span data-ttu-id="b7209-203">In der erste Zeile in `WriteFormattedDocComment` ordnet der Aufruf `text.Split` bei jedem Aufruf ein neues Array mit drei Elementen als Argument zu.</span><span class="sxs-lookup"><span data-stu-id="b7209-203">On the first line inside `WriteFormattedDocComment`, the `text.Split` call allocates a new three-element array as the argument every time it’s called.</span></span> <span data-ttu-id="b7209-204">Der Compiler muss Code ausgeben, um dieses Array jedes Mal zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="b7209-204">The compiler has to emit code to allocate this array each time.</span></span> <span data-ttu-id="b7209-205">Der Grund hierfür ist, dass der Compiler nicht weiß, ob <xref:System.String.Split%2A> das Array irgendwo speichert, wo es möglicherweise von anderem Code modifiziert wird, was sich auf spätere Aufrufe an `WriteFormattedDocComment` auswirken würde.</span><span class="sxs-lookup"><span data-stu-id="b7209-205">That’s because the compiler doesn’t know if <xref:System.String.Split%2A> stores the array somewhere where the array might be modified by other code, which would affect later calls to `WriteFormattedDocComment`.</span></span> <span data-ttu-id="b7209-206">Der Anruf an <xref:System.String.Split%2A> ordnet außerdem eine Zeichenfolge für jede Zeile in `text` zu und belegt anderen Speicher, um den Vorgang durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="b7209-206">The call to <xref:System.String.Split%2A> also allocates a string for every line in `text` and allocates other memory to perform the operation.</span></span>
  
 <span data-ttu-id="b7209-207">`WriteFormattedDocComment` hat drei Aufrufe an die <xref:System.String.TrimStart%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="b7209-207">`WriteFormattedDocComment` has three calls to the <xref:System.String.TrimStart%2A> method.</span></span> <span data-ttu-id="b7209-208">Zwei befinden sich in inneren Schleifen, die Arbeit und Zuordnungen duplizieren.</span><span class="sxs-lookup"><span data-stu-id="b7209-208">Two are in inner loops that duplicate work and allocations.</span></span> <span data-ttu-id="b7209-209">Erschwerend kommt noch hinzu, dass beim Aufrufen der <xref:System.String.TrimStart%2A>-Methode ohne Argumente zusätzlich zum Zeichenfolgenergebnis ein leeres Array (für den Parameter `params`) zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="b7209-209">To make matters worse, calling the <xref:System.String.TrimStart%2A> method with no arguments allocates an empty array (for the `params` parameter) in addition to the string result.</span></span>
  
 <span data-ttu-id="b7209-210">Und schließlich gibt es einen Aufruf an die <xref:System.String.Substring%2A>-Methode, der für gewöhnlich eine neue Zeichenfolge zuordnet.</span><span class="sxs-lookup"><span data-stu-id="b7209-210">Lastly, there is a call to the <xref:System.String.Substring%2A> method, which usually allocates a new string.</span></span>
  
 <span data-ttu-id="b7209-211">**Korrektur für Beispiel 3**</span><span class="sxs-lookup"><span data-stu-id="b7209-211">**Fix for example 3**</span></span>  
  
 <span data-ttu-id="b7209-212">Im Gegensatz zu den vorherigen Beispiele können diese Zuordnungen nicht durch kleine Korrekturen behoben werden.</span><span class="sxs-lookup"><span data-stu-id="b7209-212">Unlike the earlier examples, small edits cannot fix these allocations.</span></span> <span data-ttu-id="b7209-213">Sie müssen zurückgehen, sich das Problem ansehen und es anders angehen.</span><span class="sxs-lookup"><span data-stu-id="b7209-213">You need to step back, look at the problem, and approach it differently.</span></span> <span data-ttu-id="b7209-214">Sie werden beispielsweise bemerken, dass das Argument für `WriteFormattedDocComment()` eine Zeichenfolge ist, die alle Informationen enthält, die die Methode benötigt, sodass der Code mehr Indizierung anstelle der Zuordnung vieler Teilzeichenfolgen durchführen könnte.</span><span class="sxs-lookup"><span data-stu-id="b7209-214">For example, you'll notice that the argument to `WriteFormattedDocComment()` is a string that has all the information that the method needs, so the code could do more indexing instead of allocating many partial strings.</span></span>
  
 <span data-ttu-id="b7209-215">Das Leistungsteam für den Compiler hat all diese Zuordnungen mit einem Code wie dem folgenden gelöst:</span><span class="sxs-lookup"><span data-stu-id="b7209-215">The compiler’s performance team tackled all these allocations with code like this:</span></span>  
  
```csharp  
private int IndexOfFirstNonWhiteSpaceChar(string text, int start) {  
    while (start < text.Length && char.IsWhiteSpace(text[start])) start++;  
    return start;  
}  
  
private bool TrimmedStringStartsWith(string text, int start, string prefix) {  
    start = IndexOfFirstNonWhiteSpaceChar(text, start);  
    int len = text.Length - start;  
    if (len < prefix.Length) return false;  
    for (int i = 0; i < len; i++)  
    {  
        if (prefix[i] != text[start + i]) return false;  
    }  
    return true;  
}  
  
// etc...
```  
  
 <span data-ttu-id="b7209-216">Die erste Version von `WriteFormattedDocComment()` hat ein Array, mehrere untergeordnete Zeichenfolgen und eine abgeschnittene Zeichenfolge zusammen mit einem leeren `params`-Array zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="b7209-216">The first version of `WriteFormattedDocComment()` allocated an array, several substrings, and a trimmed substring along with an empty `params` array.</span></span> <span data-ttu-id="b7209-217">Es wurde auch auf "///" geprüft.</span><span class="sxs-lookup"><span data-stu-id="b7209-217">It also checked for "///".</span></span> <span data-ttu-id="b7209-218">Der überarbeitete Code verwendet nur die Indizierung und ordnet nichts zu.</span><span class="sxs-lookup"><span data-stu-id="b7209-218">The revised code uses only indexing and allocates nothing.</span></span> <span data-ttu-id="b7209-219">Es findet das erste Zeichen, das kein Leerzeichen ist, und überprüft dann Zeichen nach Zeichen, um festzustellen, ob die Zeichenfolge mit "///" beginnt.</span><span class="sxs-lookup"><span data-stu-id="b7209-219">It finds the first character that is not white space, and then checks character by character to see if the string starts with "///".</span></span> <span data-ttu-id="b7209-220">Der neue Code verwendet `IndexOfFirstNonWhiteSpaceChar` anstelle von <xref:System.String.TrimStart%2A> , um den ersten Index (nach einem angegebenen Start Index) zurückzugeben, bei dem ein nicht-Leerzeichen auftritt.</span><span class="sxs-lookup"><span data-stu-id="b7209-220">The new code uses `IndexOfFirstNonWhiteSpaceChar` instead of <xref:System.String.TrimStart%2A> to return the first index (after a specified start index) where a non-white-space character occurs.</span></span> <span data-ttu-id="b7209-221">Die Korrektur ist nicht vollständig, aber Sie können sehen, wie Sie ähnliche Korrekturen für eine vollständige Lösung anwenden können.</span><span class="sxs-lookup"><span data-stu-id="b7209-221">The fix is not complete, but you can see how to apply similar fixes for a complete solution.</span></span> <span data-ttu-id="b7209-222">Durch Anwendung dieses Ansatzes im gesamten Code können Sie alle Zuordnungen in `WriteFormattedDocComment()` entfernen.</span><span class="sxs-lookup"><span data-stu-id="b7209-222">By applying this approach throughout the code, you can remove all allocations in `WriteFormattedDocComment()`.</span></span>
  
 <span data-ttu-id="b7209-223">**Beispiel 4: StringBuilder**</span><span class="sxs-lookup"><span data-stu-id="b7209-223">**Example 4: StringBuilder**</span></span>  
  
 <span data-ttu-id="b7209-224">In diesem Beispiel wird ein <xref:System.Text.StringBuilder>-Objekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="b7209-224">This example uses a <xref:System.Text.StringBuilder> object.</span></span> <span data-ttu-id="b7209-225">Die folgende Funktion generiert einen vollständigen Typnamen für generische Typen:</span><span class="sxs-lookup"><span data-stu-id="b7209-225">The following function generates a full type name for generic types:</span></span>  
  
```csharp  
public class Example  
{  
    // Constructs a name like "SomeType<T1, T2, T3>"  
    public string GenerateFullTypeName(string name, int arity)  
    {  
        StringBuilder sb = new StringBuilder();  
  
        sb.Append(name);  
        if (arity != 0)  
        {  
            sb.Append("<");  
            for (int i = 1; i < arity; i++)  
            {  
                sb.Append("T"); sb.Append(i.ToString()); sb.Append(", ");  
            }  
            sb.Append("T"); sb.Append(i.ToString()); sb.Append(">");  
        }  
  
        return sb.ToString();  
    }  
}  
```  
  
 <span data-ttu-id="b7209-226">Der Schwerpunkt liegt auf der Zeile, die eine neue <xref:System.Text.StringBuilder>-Instanz erstellt.</span><span class="sxs-lookup"><span data-stu-id="b7209-226">The focus is on the line that creates a new <xref:System.Text.StringBuilder> instance.</span></span> <span data-ttu-id="b7209-227">Der Code verursacht eine Zuordnung für `sb.ToString()` und interne Zuordnungen in der <xref:System.Text.StringBuilder>-Implementierung, aber können diese Zuordnungen nicht steuern, wenn Sie das Zeichenfolgenergebnis wollen.</span><span class="sxs-lookup"><span data-stu-id="b7209-227">The code causes an allocation for `sb.ToString()` and internal allocations within the <xref:System.Text.StringBuilder> implementation, but you cannot control those allocations if you want the string result.</span></span>
  
 <span data-ttu-id="b7209-228">**Korrektur für Beispiel 4**</span><span class="sxs-lookup"><span data-stu-id="b7209-228">**Fix for example 4**</span></span>  
  
 <span data-ttu-id="b7209-229">Speichern Sie das Objekt zwischen, um die `StringBuilder`-Objektzuordnung zu korrigieren.</span><span class="sxs-lookup"><span data-stu-id="b7209-229">To fix the `StringBuilder` object allocation, cache the  object.</span></span> <span data-ttu-id="b7209-230">Jedes Zwischenspeichern einer einzigen Instanz, die möglicherweise entfernt wird, kann die Leistung deutlich verbessern.</span><span class="sxs-lookup"><span data-stu-id="b7209-230">Even caching a single instance that might get thrown away can improve performance significantly.</span></span> <span data-ttu-id="b7209-231">Im Folgenden sehen Sie die neue Implementierung der Funktion, wobei der Code mit Ausnahme der neuen ersten und letzten Zeile ausgelassen wurde:</span><span class="sxs-lookup"><span data-stu-id="b7209-231">This is the function’s new implementation, omitting all the code except for the new first and last lines:</span></span>  
  
```csharp  
// Constructs a name like "MyType<T1, T2, T3>"  
public string GenerateFullTypeName(string name, int arity)  
{  
    StringBuilder sb = AcquireBuilder();  
    /* Use sb as before */  
    return GetStringAndReleaseBuilder(sb);  
}  
```  
  
 <span data-ttu-id="b7209-232">Die wichtigen Teile sind die neuen Funktionen `AcquireBuilder()` und `GetStringAndReleaseBuilder()`:</span><span class="sxs-lookup"><span data-stu-id="b7209-232">The key parts are the new `AcquireBuilder()` and `GetStringAndReleaseBuilder()` functions:</span></span>  
  
```csharp  
[ThreadStatic]  
private static StringBuilder cachedStringBuilder;  
  
private static StringBuilder AcquireBuilder()  
{  
    StringBuilder result = cachedStringBuilder;  
    if (result == null)  
    {  
        return new StringBuilder();  
    }  
    result.Clear();  
    cachedStringBuilder = null;  
    return result;  
}  
  
private static string GetStringAndReleaseBuilder(StringBuilder sb)  
{  
    string result = sb.ToString();  
    cachedStringBuilder = sb;  
    return result;  
}  
```  
  
 <span data-ttu-id="b7209-233">Da die neuen Compiler Threading verwenden, wird in diesen Implementierungen ein threadstatisches Feld (Attribut <xref:System.ThreadStaticAttribute>) verwendet, um <xref:System.Text.StringBuilder> zwischenzuspeichern, und Sie können die `ThreadStatic`-Deklaration wahrscheinlich übergehen.</span><span class="sxs-lookup"><span data-stu-id="b7209-233">Because the new compilers use threading, these implementations use a thread-static field (<xref:System.ThreadStaticAttribute> attribute) to cache the <xref:System.Text.StringBuilder>, and you likely can forgo the `ThreadStatic` declaration.</span></span> <span data-ttu-id="b7209-234">Das threadstatische Feld enthält einen eindeutigen Wert für jeden Thread, der diesen Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="b7209-234">The thread-static field holds a unique value for each thread that executes this code.</span></span>
  
 <span data-ttu-id="b7209-235">`AcquireBuilder()` gibt die zwischengespeicherte <xref:System.Text.StringBuilder>-Instanz zurück, wenn eine vorhanden ist, nachdem sie gelöscht und das Feld oder der Cache auf Null festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="b7209-235">`AcquireBuilder()` returns the cached <xref:System.Text.StringBuilder> instance if there is one, after clearing it and setting the field or cache to null.</span></span> <span data-ttu-id="b7209-236">Andernfalls erstellt `AcquireBuilder()` eine neue Instanz und gibt sie zurück. Die Festlegung des Felds oder Caches auf Null wird dabei beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b7209-236">Otherwise, `AcquireBuilder()` creates a new instance and returns it, leaving the field or cache set to null.</span></span>
  
 <span data-ttu-id="b7209-237">Wenn Sie mit <xref:System.Text.StringBuilder> fertig sind, rufen Sie `GetStringAndReleaseBuilder()` auf, um das Zeichenfolgenergebnis abzurufen, speichern die <xref:System.Text.StringBuilder>-Instanz im Feld oder Cache und geben dann das Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="b7209-237">When you’re done with <xref:System.Text.StringBuilder> , you call `GetStringAndReleaseBuilder()` to get the string result, save the <xref:System.Text.StringBuilder> instance in the field or cache, and then return the result.</span></span> <span data-ttu-id="b7209-238">Für die Ausführung ist es möglich, diesen Code erneut einzugeben und mehrere <xref:System.Text.StringBuilder>-Objekte zu erstellen (obwohl dies selten geschieht).</span><span class="sxs-lookup"><span data-stu-id="b7209-238">It is possible for execution to re-enter this code and to create multiple <xref:System.Text.StringBuilder> objects (although that rarely happens).</span></span> <span data-ttu-id="b7209-239">Der Code speichert nur die zuletzt freigegebene <xref:System.Text.StringBuilder>-Instanz zur späteren Verwendung.</span><span class="sxs-lookup"><span data-stu-id="b7209-239">The code saves only the last released <xref:System.Text.StringBuilder> instance for later use.</span></span> <span data-ttu-id="b7209-240">Diese einfache Zwischenspeicherstrategie reduziert Zuordnungen in den neuen Compilern deutlich.</span><span class="sxs-lookup"><span data-stu-id="b7209-240">This simple caching strategy significantly reduced allocations in the new compilers.</span></span> <span data-ttu-id="b7209-241">Teile von .NET Framework und MSBuild („MSBuild“) verwenden eine ähnliche Technik, um die Leistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="b7209-241">Parts of the .NET Framework and MSBuild ("MSBuild") use a similar technique to improve performance.</span></span>
  
 <span data-ttu-id="b7209-242">Diese einfache Zwischenspeicherstrategie entspricht einem guten Cachedesign, da sie über eine Größenbeschränkung verfügt.</span><span class="sxs-lookup"><span data-stu-id="b7209-242">This simple caching strategy adheres to good cache design because it has a size cap.</span></span> <span data-ttu-id="b7209-243">Jetzt ist jedoch mehr Code als im Original vorhanden, was höhere Wartungskosten bedeutet.</span><span class="sxs-lookup"><span data-stu-id="b7209-243">However, there is more code now than in the original, which means more maintenance costs.</span></span> <span data-ttu-id="b7209-244">Sie sollten die Zwischenspeicherstrategie nur übernehmen, wenn Sie ein Leistungsproblem gefunden haben und PerfView gezeigt hat, dass <xref:System.Text.StringBuilder>-Zuordnungen einen signifikanten Beitrag dazu leisten.</span><span class="sxs-lookup"><span data-stu-id="b7209-244">You should adopt the caching strategy only if you’ve found a performance problem, and PerfView has shown that <xref:System.Text.StringBuilder> allocations are a significant contributor.</span></span>
  
### <a name="linq-and-lambdas"></a><span data-ttu-id="b7209-245">LINQ und Lambdas</span><span class="sxs-lookup"><span data-stu-id="b7209-245">LINQ and lambdas</span></span>  

<span data-ttu-id="b7209-246">Language-Integrated Query (LINQ), zusammen mit Lambda-Ausdrücken, ist ein Beispiel für ein Produktivitäts Feature.</span><span class="sxs-lookup"><span data-stu-id="b7209-246">Language-Integrated Query (LINQ), in conjunction with lambda expressions, is an example of a productivity feature.</span></span> <span data-ttu-id="b7209-247">Allerdings kann sich seine Verwendung im Laufe der Zeit erheblich auf die Leistung auswirken, und Sie müssen möglicherweise den Code neu schreiben.</span><span class="sxs-lookup"><span data-stu-id="b7209-247">However, its use may have a significant impact on performance over time, and you might find you need to rewrite your code.</span></span>
  
 <span data-ttu-id="b7209-248">**Beispiel 5: Lambdas, List \<T> und IEnumerable\<T>**</span><span class="sxs-lookup"><span data-stu-id="b7209-248">**Example 5: Lambdas, List\<T>, and IEnumerable\<T>**</span></span>  
  
 <span data-ttu-id="b7209-249">Dieses Beispiel verwendet [LINQ und Funktionsformatcode](/archive/blogs/charlie/anders-hejlsberg-on-linq-and-functional-programming), um ein Symbol im Modell des Compilers anhand einer Namenszeichenfolge zu finden:</span><span class="sxs-lookup"><span data-stu-id="b7209-249">This example uses [LINQ and functional style code](/archive/blogs/charlie/anders-hejlsberg-on-linq-and-functional-programming) to find a symbol in the compiler’s model, given a name string:</span></span>  
  
```csharp  
class Symbol {  
    public string Name { get; private set; }  
    /*...*/  
}  
  
class Compiler {  
    private List<Symbol> symbols;  
    public Symbol FindMatchingSymbol(string name)  
    {  
        return symbols.FirstOrDefault(s => s.Name == name);  
    }  
}  
```  
  
 <span data-ttu-id="b7209-250">Der neue Compiler und die darauf aufgebauten IDE-Erfahrungen rufen `FindMatchingSymbol()` sehr häufig auf, und es gibt mehrere verborgene Zuordnungen ein der einzigen Codezeile dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="b7209-250">The new compiler and the IDE experiences built on it call `FindMatchingSymbol()` very frequently, and there are several hidden allocations in this function’s single line of code.</span></span> <span data-ttu-id="b7209-251">Um diese Zuordnungen zu untersuchen, teilen Sie die einzelne Codezeile der Funktion zunächst in zwei Zeilen auf:</span><span class="sxs-lookup"><span data-stu-id="b7209-251">To examine those allocations, first split the function’s single line of code into two lines:</span></span>  
  
```csharp  
Func<Symbol, bool> predicate = s => s.Name == name;  
     return symbols.FirstOrDefault(predicate);  
```  
  
 <span data-ttu-id="b7209-252">In der ersten Zeile schließt der [Lambda-Ausdruck](../../csharp/language-reference/operators/lambda-expressions.md) `s => s.Name == name` [über](/archive/blogs/ericlippert/what-are-closures) die lokale Variable `name`.</span><span class="sxs-lookup"><span data-stu-id="b7209-252">In the first line, the [lambda expression](../../csharp/language-reference/operators/lambda-expressions.md) `s => s.Name == name` [closes over](/archive/blogs/ericlippert/what-are-closures) the local variable `name`.</span></span> <span data-ttu-id="b7209-253">Das bedeutet, dass zusätzlich zum Zuordnen eines Objekts für den[Delegaten](../../csharp/language-reference/builtin-types/reference-types.md#the-delegate-type), den `predicate` speichert, der Code eine statische Klasse zuordnet, um die Umgebung zu speichern, die den Wert von `name` erfasst.</span><span class="sxs-lookup"><span data-stu-id="b7209-253">This means that in addition to allocating an object for the [delegate](../../csharp/language-reference/builtin-types/reference-types.md#the-delegate-type) that `predicate` holds, the code allocates a static class to hold the environment that captures the value of `name`.</span></span> <span data-ttu-id="b7209-254">Der Compiler generiert Code wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="b7209-254">The compiler generates code like the following:</span></span>  
  
```csharp  
// Compiler-generated class to hold environment state for lambda  
private class Lambda1Environment  
{  
    public string capturedName;  
    public bool Evaluate(Symbol s)  
    {  
        return s.Name == this.capturedName;  
    }  
}  
  
// Expanded Func<Symbol, bool> predicate = s => s.Name == name;  
Lambda1Environment l = new Lambda1Environment() { capturedName = name };  
var predicate = new Func<Symbol, bool>(l.Evaluate);  
```  
  
 <span data-ttu-id="b7209-255">Die zwei `new`-Zuordnungen (eine für die Umgebungsklasse und eine für den Delegaten) sind jetzt explizit.</span><span class="sxs-lookup"><span data-stu-id="b7209-255">The two `new` allocations (one for the environment class and one for the delegate) are explicit now.</span></span>
  
 <span data-ttu-id="b7209-256">Sehen Sie sich jetzt den Aufruf an `FirstOrDefault` an.</span><span class="sxs-lookup"><span data-stu-id="b7209-256">Now look at the call to `FirstOrDefault`.</span></span> <span data-ttu-id="b7209-257">Diese Erweiterungsmethode für den <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>-Typ ruft ebenfalls eine Zuordnung hervor.</span><span class="sxs-lookup"><span data-stu-id="b7209-257">This extension method on the <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> type incurs an allocation too.</span></span> <span data-ttu-id="b7209-258">Da `FirstOrDefault` ein <xref:System.Collections.Generic.IEnumerable%601>-Objekt als erstes Argument annimmt, können Sie den Aufruf in den folgenden Code erweitern (für die Darstellung etwas vereinfacht):</span><span class="sxs-lookup"><span data-stu-id="b7209-258">Because `FirstOrDefault` takes an <xref:System.Collections.Generic.IEnumerable%601> object as its first argument, you can expand the call to the following code (simplified a bit for discussion):</span></span>  
  
```csharp  
// Expanded return symbols.FirstOrDefault(predicate) ...
     IEnumerable<Symbol> enumerable = symbols;  
     IEnumerator<Symbol> enumerator = enumerable.GetEnumerator();  
     while(enumerator.MoveNext())  
     {  
         if (predicate(enumerator.Current))  
             return enumerator.Current;  
     }  
     return default(Symbol);  
```  
  
 <span data-ttu-id="b7209-259">Die Variable `symbols` hat den Typ <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="b7209-259">The `symbols` variable has type <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="b7209-260">Der <xref:System.Collections.Generic.List%601>-Auflistungstyp implementiert <xref:System.Collections.Generic.IEnumerable%601> und definiert auf clevere Weise einen Enumerator (<xref:System.Collections.Generic.IEnumerator%601>-Schnittstelle), den <xref:System.Collections.Generic.List%601> mit einem `struct` implementiert.</span><span class="sxs-lookup"><span data-stu-id="b7209-260">The <xref:System.Collections.Generic.List%601> collection type implements <xref:System.Collections.Generic.IEnumerable%601> and cleverly defines an enumerator (<xref:System.Collections.Generic.IEnumerator%601> interface) that <xref:System.Collections.Generic.List%601> implements with a `struct`.</span></span> <span data-ttu-id="b7209-261">Die Verwendung einer Struktur anstelle einer Klasse bedeutet, dass Sie für gewöhnlich Heapzuordnungen vermeiden, was sich wiederum auf die Garbage Collection-Leistung auswirken kann.</span><span class="sxs-lookup"><span data-stu-id="b7209-261">Using a structure instead of a class means that you usually avoid any heap allocations, which, in turn, can affect garbage collection performance.</span></span> <span data-ttu-id="b7209-262">Enumeratoren werden normalerweise mit der `foreach`-Schleife der Sprache verwendet, die die Emulatorstruktur verwendet, wie sie auf den Aufrufstapel zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b7209-262">Enumerators are typically used with the language’s `foreach` loop, which uses the enumerator structure as it is returned on the call stack.</span></span> <span data-ttu-id="b7209-263">Das Erhöhen des Aufruflistenzeigers, um Platz für ein Objekt zu machen, wirkt sich nicht wie eine Heapzuordnung auf die GC aus.</span><span class="sxs-lookup"><span data-stu-id="b7209-263">Incrementing the call stack pointer to make room for an object does not affect GC the way a heap allocation does.</span></span>
  
 <span data-ttu-id="b7209-264">Bei einem erweiterten `FirstOrDefault`-Aufruf muss der Code `GetEnumerator()` auf einem <xref:System.Collections.Generic.IEnumerable%601> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b7209-264">In the case of the expanded `FirstOrDefault` call, the code needs to call `GetEnumerator()` on an <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="b7209-265">Beim Zuordnen von `symbols` zur `enumerable`-Variable des Typs `IEnumerable<Symbol>` geht die Information verloren, dass das tatsächliche Objekt ein <xref:System.Collections.Generic.List%601> ist.</span><span class="sxs-lookup"><span data-stu-id="b7209-265">Assigning `symbols` to the `enumerable` variable of type `IEnumerable<Symbol>` loses the information that the actual object is a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="b7209-266">Das bedeutet, dass beim Abrufen des Enumerators durch den Code mit `enumerable.GetEnumerator()` .NET Framework die zurückgegebene Struktur verschachteln muss, um sie der Variable `enumerator` zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="b7209-266">This means that when the code fetches the enumerator with `enumerable.GetEnumerator()`, the .NET Framework has to box the returned structure to assign it to the `enumerator` variable.</span></span>
  
 <span data-ttu-id="b7209-267">**Korrektur für Beispiel 5**</span><span class="sxs-lookup"><span data-stu-id="b7209-267">**Fix for example 5**</span></span>  
  
 <span data-ttu-id="b7209-268">Die Korrektur besteht darin, `FindMatchingSymbol` wie folgt umzuschreiben und dabei die einzelne Codezeile durch sechs Codezeilen zu ersetzen, die immer noch präzise, einfach zu lesen und zu verstehen und leicht zu warten sind:</span><span class="sxs-lookup"><span data-stu-id="b7209-268">The fix is to rewrite `FindMatchingSymbol` as follows, replacing its single line of code with six lines of code that are still concise, easy to read and understand, and easy to maintain:</span></span>  
  
```csharp  
public Symbol FindMatchingSymbol(string name)  
    {  
        foreach (Symbol s in symbols)  
        {  
            if (s.Name == name)  
                return s;  
        }  
        return null;  
    }  
```  
  
 <span data-ttu-id="b7209-269">Dieser Code verwendet keine LINQ-Erweiterungsmethoden, Lambdas oder Enumeratoren und verursacht keine Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="b7209-269">This code doesn’t use LINQ extension methods, lambdas, or enumerators, and it incurs no allocations.</span></span> <span data-ttu-id="b7209-270">Es gibt keine Zuordnungen, weil der Compiler sehen kann, dass die `symbols`-Auflistung eine <xref:System.Collections.Generic.List%601> ist und den resultierenden Enumerator (eine Struktur) an eine lokale Variable des richtigen Typs binden kann, um ein Boxing zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="b7209-270">There are no allocations because the compiler can see that the `symbols` collection is a <xref:System.Collections.Generic.List%601> and can bind the resulting enumerator (a structure) to a local variable with the right type to avoid boxing.</span></span> <span data-ttu-id="b7209-271">Die ursprüngliche Version dieser Funktion war ein hervorragendes Beispiel für die Ausdrucksstärke von C# und die Produktivität von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b7209-271">The original version of this function was a great example of the expressive power of C# and the productivity of the .NET Framework.</span></span> <span data-ttu-id="b7209-272">Diese neue und effizientere Version behält diese Qualitäten bei, ohne komplexen Code hinzuzufügen, der gewartet werden muss.</span><span class="sxs-lookup"><span data-stu-id="b7209-272">This new and more efficient version preserves those qualities without adding any complex code to maintain.</span></span>
  
### <a name="async-method-caching"></a><span data-ttu-id="b7209-273">Zwischenspeichern der Async-Methode</span><span class="sxs-lookup"><span data-stu-id="b7209-273">Async method caching</span></span>  

<span data-ttu-id="b7209-274">Das nächste Beispiel zeigt ein typisches Problem, wenn Sie versuchen, zwischengespeicherte Ergebnisse in einer [Async](../../csharp/programming-guide/concepts/async/index.md)-Methode zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7209-274">The next example shows a common problem when you try to use cached results in an [async](../../csharp/programming-guide/concepts/async/index.md) method.</span></span>
  
 <span data-ttu-id="b7209-275">**Beispiel 6: Zwischenspeichern in Async-Methoden**</span><span class="sxs-lookup"><span data-stu-id="b7209-275">**Example 6: caching in async methods**</span></span>  
  
 <span data-ttu-id="b7209-276">Die Visual Studio IDE-Funktionen, die auf den neuen C#- und Visual Basic-Compilern aufgebaut sind, rufen häufig Syntaxstrukturen auf, und die Compiler verwenden dabei Async, damit Visual Studio reaktionsfähig bleibt.</span><span class="sxs-lookup"><span data-stu-id="b7209-276">The Visual Studio IDE features built on the new C# and Visual Basic compilers frequently fetch syntax trees, and the compilers use async when doing so to keep Visual Studio responsive.</span></span> <span data-ttu-id="b7209-277">Hier ist die erste Version des Codes, den Sie möglicherweise schreiben, um eine Syntaxstruktur abzurufen:</span><span class="sxs-lookup"><span data-stu-id="b7209-277">Here’s the first version of the code you might write to get a syntax tree:</span></span>  
  
```csharp  
class SyntaxTree { /*...*/ }  
  
class Parser { /*...*/  
    public SyntaxTree Syntax { get; }  
    public Task ParseSourceCode() { /*...*/ }  
}  
  
class Compilation { /*...*/  
    public async Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        var parser = new Parser(); // allocation  
        await parser.ParseSourceCode(); // expensive  
        return parser.Syntax;  
    }  
}  
```  
  
 <span data-ttu-id="b7209-278">Sie sehen, dass durch das Aufrufen von `GetSyntaxTreeAsync()` ein `Parser` initiiert, der Code analysiert und dann ein <xref:System.Threading.Tasks.Task>-Objekt, `Task<SyntaxTree>`, zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b7209-278">You can see that calling `GetSyntaxTreeAsync()` instantiates a `Parser`, parses the code, and then returns a <xref:System.Threading.Tasks.Task> object, `Task<SyntaxTree>`.</span></span> <span data-ttu-id="b7209-279">Der ressourcenintensive Teil ist das Zuordnen der `Parser`-Instanz und das Analysieren des Codes.</span><span class="sxs-lookup"><span data-stu-id="b7209-279">The expensive part is allocating the `Parser` instance and parsing the code.</span></span> <span data-ttu-id="b7209-280">Die Funktion gibt einen <xref:System.Threading.Tasks.Task> zurück, sodass Aufrufer auf die Analysearbeit warten und den UI-Thread freigeben können, damit er auf Benutzereingaben reagiert.</span><span class="sxs-lookup"><span data-stu-id="b7209-280">The function returns a <xref:System.Threading.Tasks.Task> so that callers can await the parsing work and free the UI thread to be responsive to user input.</span></span>
  
 <span data-ttu-id="b7209-281">Möglicherweise versuchen mehrere Visual Studio-Funktionen, dieselbe Syntaxstruktur abzurufen, deshalb können Sie den folgenden Code schreiben, um die Analyseergebnisse zwischenzuspeichern und so Zeit und Zuordnungen zu sparen.</span><span class="sxs-lookup"><span data-stu-id="b7209-281">Several Visual Studio features might try to get the same syntax tree, so you might write the following code to cache the parsing result to save time and allocations.</span></span> <span data-ttu-id="b7209-282">Dieser Code ruft jedoch eine Zuordnung hervor:</span><span class="sxs-lookup"><span data-stu-id="b7209-282">However, this code incurs an allocation:</span></span>  
  
```csharp  
class Compilation { /*...*/  
  
    private SyntaxTree cachedResult;  
  
    public async Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        if (this.cachedResult == null)  
        {  
            var parser = new Parser(); // allocation  
            await parser.ParseSourceCode(); // expensive  
            this.cachedResult = parser.Syntax;  
        }  
        return this.cachedResult;  
    }  
}  
```  
  
 <span data-ttu-id="b7209-283">Sie sehen, dass der neue Code mit Zwischenspeichern ein `SyntaxTree`-Feld mit dem Namen `cachedResult` hat.</span><span class="sxs-lookup"><span data-stu-id="b7209-283">You see that the new code with caching has a `SyntaxTree` field named `cachedResult`.</span></span> <span data-ttu-id="b7209-284">Wenn dieses Feld Null ist, übernimmt `GetSyntaxTreeAsync()` die Arbeit und speichert das Ergebnis im Cache.</span><span class="sxs-lookup"><span data-stu-id="b7209-284">When this field is null, `GetSyntaxTreeAsync()` does the work and saves the result in the cache.</span></span> <span data-ttu-id="b7209-285">`GetSyntaxTreeAsync()` gibt das `SyntaxTree`-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="b7209-285">`GetSyntaxTreeAsync()` returns the `SyntaxTree` object.</span></span> <span data-ttu-id="b7209-286">Wenn Sie eine `async`-Funktion des Typs `Task<SyntaxTree>` haben und einen Wert des Typs `SyntaxTree` zurückgeben, besteht das Problem darin, dass der Compiler Code ausgibt, um eine Aufgabe zuzuordnen, die das Ergebnis speichert (durch Verwendung von `Task<SyntaxTree>.FromResult()`).</span><span class="sxs-lookup"><span data-stu-id="b7209-286">The problem is that when you have an `async` function of type `Task<SyntaxTree>`, and you return a value of type `SyntaxTree`, the compiler emits code to allocate a Task to hold the result (by using `Task<SyntaxTree>.FromResult()`).</span></span> <span data-ttu-id="b7209-287">Die Aufgabe wird als abgeschlossen gekennzeichnet, und das Ergebnis ist sofort verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b7209-287">The Task is marked as completed, and the result is immediately available.</span></span> <span data-ttu-id="b7209-288">Im Code für die neuen Compiler kamen bereits abgeschlossene <xref:System.Threading.Tasks.Task>-Objekte so oft vor, dass eine Korrektur dieser Zuordnungen die Reaktionsfähigkeit merklich verbessert hat.</span><span class="sxs-lookup"><span data-stu-id="b7209-288">In the code for the new compilers, <xref:System.Threading.Tasks.Task> objects that were already completed occurred so often that fixing these allocations improved responsiveness noticeably.</span></span>
  
 <span data-ttu-id="b7209-289">**Korrektur für Beispiel 6**</span><span class="sxs-lookup"><span data-stu-id="b7209-289">**Fix for example 6**</span></span>  
  
 <span data-ttu-id="b7209-290">Zum Entfernen der abgeschlossenen <xref:System.Threading.Tasks.Task> Zuordnung können Sie das Aufgaben Objekt mit dem abgeschlossenen Ergebnis Zwischenspeichern:</span><span class="sxs-lookup"><span data-stu-id="b7209-290">To remove the completed <xref:System.Threading.Tasks.Task> allocation, you can cache the Task object with the completed result:</span></span>  
  
```csharp  
class Compilation { /*...*/  
  
    private Task<SyntaxTree> cachedResult;  
  
    public Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        return this.cachedResult ??
               (this.cachedResult = GetSyntaxTreeUncachedAsync());  
    }  
  
    private async Task<SyntaxTree> GetSyntaxTreeUncachedAsync()  
    {  
        var parser = new Parser(); // allocation  
        await parser.ParseSourceCode(); // expensive  
        return parser.Syntax;  
    }  
}  
```  
  
 <span data-ttu-id="b7209-291">Dieser Code ändert den Typ von `cachedResult` in `Task<SyntaxTree>` und wendet eine `async`-Hilfsfunktion an, die den Originalcode von `GetSyntaxTreeAsync()` speichert.</span><span class="sxs-lookup"><span data-stu-id="b7209-291">This code changes the type of `cachedResult` to `Task<SyntaxTree>` and employs an `async` helper function that holds the original code from `GetSyntaxTreeAsync()`.</span></span> <span data-ttu-id="b7209-292">`GetSyntaxTreeAsync()` verwendet jetzt den [NULL-Sammeloperator](../../csharp/language-reference/operators/null-coalescing-operator.md), um `cachedResult` zurückzugeben, wenn es nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="b7209-292">`GetSyntaxTreeAsync()` now uses the [null coalescing operator](../../csharp/language-reference/operators/null-coalescing-operator.md) to return `cachedResult` if it isn't null.</span></span> <span data-ttu-id="b7209-293">Wenn `cachedResult` Null ist, ruft `GetSyntaxTreeAsync()``GetSyntaxTreeUncachedAsync()` auf und speichert das Ergebnis zwischen.</span><span class="sxs-lookup"><span data-stu-id="b7209-293">If `cachedResult` is null, then `GetSyntaxTreeAsync()` calls `GetSyntaxTreeUncachedAsync()` and caches the result.</span></span> <span data-ttu-id="b7209-294">Beachten Sie, dass `GetSyntaxTreeAsync()` nicht auf den Aufruf an `GetSyntaxTreeUncachedAsync()` wartet, wie es der Code normalerweise tun würde.</span><span class="sxs-lookup"><span data-stu-id="b7209-294">Notice that `GetSyntaxTreeAsync()` doesn’t await the call to `GetSyntaxTreeUncachedAsync()` as the code would normally.</span></span> <span data-ttu-id="b7209-295">Wenn await nicht verwendetet wird, bedeutet das, dass, wenn `GetSyntaxTreeUncachedAsync()` sein <xref:System.Threading.Tasks.Task>-Objekt zurückgibt, `GetSyntaxTreeAsync()` sofort <xref:System.Threading.Tasks.Task> zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b7209-295">Not using await means that when `GetSyntaxTreeUncachedAsync()` returns its <xref:System.Threading.Tasks.Task> object, `GetSyntaxTreeAsync()` immediately returns the <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="b7209-296">Jetzt ist das zwischengespeicherte Objekt ein <xref:System.Threading.Tasks.Task>, sodass keine Zuordnungen vorhanden sind, die das zwischengespeicherte Ergebnis zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="b7209-296">Now, the cached result is a <xref:System.Threading.Tasks.Task>, so there are no allocations to return the cached result.</span></span>
  
### <a name="additional-considerations"></a><span data-ttu-id="b7209-297">Weitere Überlegungen</span><span class="sxs-lookup"><span data-stu-id="b7209-297">Additional considerations</span></span>  

 <span data-ttu-id="b7209-298">Hier sind einige weitere Punkt zu potenziellen Problemen in großen Apps oder Apps, die viele Daten verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b7209-298">Here are a few more points about potential problems in large apps or apps that process a lot of data.</span></span>
  
 <span data-ttu-id="b7209-299">**Wörterbücher**</span><span class="sxs-lookup"><span data-stu-id="b7209-299">**Dictionaries**</span></span>  
  
 <span data-ttu-id="b7209-300">Wörterbücher sind in vielen Programmen allgegenwärtig, denn sie sind sehr praktisch und an sich effizient.</span><span class="sxs-lookup"><span data-stu-id="b7209-300">Dictionaries are used ubiquitously in many programs, and though dictionaries are very convenient and inherently efficient.</span></span> <span data-ttu-id="b7209-301">Aber oft werden sie nicht ordnungsgemäß verwendet.</span><span class="sxs-lookup"><span data-stu-id="b7209-301">However, they’re often used inappropriately.</span></span> <span data-ttu-id="b7209-302">In Visual Studio und den Compilern zeigen Analysen, dass viele der Wörterbücher ein einziges Element enthielten oder leer waren.</span><span class="sxs-lookup"><span data-stu-id="b7209-302">In Visual Studio and the new compilers, analysis shows that many of the dictionaries contained a single element or were empty.</span></span> <span data-ttu-id="b7209-303">Ein leeres <xref:System.Collections.Generic.Dictionary%602> hat zehn Felder und belegt 48 Byte auf dem Heap in einem x86-Computer.</span><span class="sxs-lookup"><span data-stu-id="b7209-303">An empty <xref:System.Collections.Generic.Dictionary%602> has ten fields and occupies 48 bytes on the heap on an x86 machine.</span></span> <span data-ttu-id="b7209-304">Wörterbücher sind großartig, wenn Sie eine Zuordnung oder assoziative Datenstruktur mit konstanter Zeitsuche benötigen.</span><span class="sxs-lookup"><span data-stu-id="b7209-304">Dictionaries are great when you need a mapping or associative data structure with constant-time lookup.</span></span> <span data-ttu-id="b7209-305">Wenn Sie jedoch nur einige wenige Elemente haben, verschwenden Sie viel Speicherplatz, wenn Sie ein Wörterbuch verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7209-305">However, when you have only a few elements, you waste a lot of space by using a dictionary.</span></span> <span data-ttu-id="b7209-306">Stattdessen könnten Sie beispielsweise ebenso schnell iterativ ein `List<KeyValuePair\<K,V>>` durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="b7209-306">Instead, for example, you could iteratively look through a `List<KeyValuePair\<K,V>>`, just as fast.</span></span> <span data-ttu-id="b7209-307">Wenn Sie ein Wörterbuch nur verwenden, um es mit Daten zu laden und dann daraus zu lesen (ein sehr übliches Muster), ist die Verwendung eines sortierten Arrays mit einer N(log(N))-Suche möglicherweise je nach Anzahl der verwendeten Elemente nahezu ebenso schnell.</span><span class="sxs-lookup"><span data-stu-id="b7209-307">If you use a dictionary only to load it with data and then read from it (a very common pattern), using a sorted array with an N(log(N)) lookup might be nearly as fast, depending on the number of elements you're using.</span></span>
  
 <span data-ttu-id="b7209-308">**Klassen im Vergleich zu Strukturen**</span><span class="sxs-lookup"><span data-stu-id="b7209-308">**Classes vs. structures**</span></span>  
  
 <span data-ttu-id="b7209-309">Auf eine gewisse Weise bieten Klassen und Strukturen einen klassischen Platz-/Zeitkompromiss für die Optimierung Ihrer Apps.</span><span class="sxs-lookup"><span data-stu-id="b7209-309">In a way, classes and structures provide a classic space/time tradeoff for tuning your apps.</span></span> <span data-ttu-id="b7209-310">Klassen verursachen 12 Byte Mehraufwand auf einem x86-Computer, selbst wenn sie keine Felder haben, allerdings ist das Übergeben nicht ressourcenintensiv, da nur ein Zeiger erforderlich ist, um auf eine Klasseninstanz zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="b7209-310">Classes incur 12 bytes of overhead on an x86 machine even if they have no fields, but they are inexpensive to pass around because it only takes a pointer to refer to a class instance.</span></span> <span data-ttu-id="b7209-311">Strukturen verursachen keine Heapzuordnungen, wenn sie nicht verschachtelt sind, aber wenn Sie große Strukturen als Funktionsargumente oder Rückgabewerte übergeben, ist CPU-Zeit erforderlich, um alle Datenmitglieder der Strukturen atomisch zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="b7209-311">Structures incur no heap allocations if they aren’t boxed, but when you pass large structures as function arguments or return values, it takes CPU time to atomically copy all the data members of the structures.</span></span> <span data-ttu-id="b7209-312">Achten Sie auf wiederholte Aufrufe an Eigenschaften, die Strukturen zurückgeben, und speichern Sie den Wert der Eigenschaft in einer lokalen Variable zwischen, um ein übermäßiges Kopieren von Daten zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="b7209-312">Watch out for repeated calls to properties that return structures, and cache the property’s value in a local variable to avoid excessive data copying.</span></span>
  
 <span data-ttu-id="b7209-313">**Caches**</span><span class="sxs-lookup"><span data-stu-id="b7209-313">**Caches**</span></span>  
  
 <span data-ttu-id="b7209-314">Ein gängiger Leistungstrick besteht darin, Ergebnisse zwischenzuspeichern.</span><span class="sxs-lookup"><span data-stu-id="b7209-314">A common performance trick is to cache results.</span></span> <span data-ttu-id="b7209-315">Aber ein Cache ohne Größenbeschränkung oder Entsorgungsrichtlinie kann zu einem Speicherverlust führen.</span><span class="sxs-lookup"><span data-stu-id="b7209-315">However, a cache without a size cap or disposal policy can be a memory leak.</span></span> <span data-ttu-id="b7209-316">Wenn große Datenmengen verarbeitet werden und Sie viel Arbeitsspeicher in Caches speichern, kann die Garbage Collection die Vorteile Ihrer zwischengespeicherten Suchen aufheben.</span><span class="sxs-lookup"><span data-stu-id="b7209-316">When processing large amounts of data, if you hold on to a lot of memory in caches, you can cause garbage collection to override the benefits of your cached lookups.</span></span>
  
 <span data-ttu-id="b7209-317">In diesem Artikel haben wir dargestellt, dass Ihnen Leistungsengpasssymptome bewusst sein sollten, die sich auf die Reaktionsfähigkeit Ihrer App auswirken können, insbesondere bei großen Systemen oder Systemen, die große Datenmengen verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b7209-317">In this article, we discussed how you should be aware of performance bottleneck symptoms that can affect your app's responsiveness, especially for large systems or systems that process a large amount of data.</span></span> <span data-ttu-id="b7209-318">Zu den typischen Übeltätern gehören Boxing, Zeichenfolgenmanipulationen, LINQ und Lambda, das Zwischenspeichern in Async-Methoden, das Zwischenspeichern ohne Größenbeschränkung oder Entsorgungsrichtlinie, die nicht ordnungsgemäße Verwendung von Wörterbüchern und das Übergeben von Strukturen.</span><span class="sxs-lookup"><span data-stu-id="b7209-318">Common culprits include boxing, string manipulations, LINQ and lambda, caching in async methods, caching without a size limit or disposal policy, inappropriate use of dictionaries, and passing around structures.</span></span> <span data-ttu-id="b7209-319">Behalten Sie die vier Fakten für die Optimierung von Apps im Hinterkopf:</span><span class="sxs-lookup"><span data-stu-id="b7209-319">Keep in mind the four facts for tuning your apps:</span></span>  
  
- <span data-ttu-id="b7209-320">Keine vorzeitige Optimierung: Seien Sie produktiv, und optimieren Sie Ihre App, wenn Sie Probleme entdecken.</span><span class="sxs-lookup"><span data-stu-id="b7209-320">Don’t prematurely optimize – be productive and tune your app when you spot problems.</span></span>
  
- <span data-ttu-id="b7209-321">Profile lügen nicht: Sie raten, wenn Sie nicht messen.</span><span class="sxs-lookup"><span data-stu-id="b7209-321">Profiles don’t lie – you’re guessing if you’re not measuring.</span></span>
  
- <span data-ttu-id="b7209-322">Gute Tools machen einen großen Unterschied: Laden Sie PerfView herunter, und probieren Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="b7209-322">Good tools make all the difference – download PerfView and try it out.</span></span>
  
- <span data-ttu-id="b7209-323">Es dreht sich alles um Zuordnungen: Hier hat das Compilerplattformteam die meiste Zeit mit der Optimierung der Leistung der neuen Compiler verbracht.</span><span class="sxs-lookup"><span data-stu-id="b7209-323">It's all about allocations – that is where the compiler platform team spent most of their time improving the performance of the new compilers.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b7209-324">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7209-324">See also</span></span>

- [<span data-ttu-id="b7209-325">Video mit einer Darstellung dieses Themas</span><span class="sxs-lookup"><span data-stu-id="b7209-325">Video of presentation of this topic</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2013/DEV-B333)
- [<span data-ttu-id="b7209-326">Einführung in die Leistungsprofil Erstellung</span><span class="sxs-lookup"><span data-stu-id="b7209-326">Beginners Guide to Performance Profiling</span></span>](/visualstudio/profiling/beginners-guide-to-performance-profiling)
- [<span data-ttu-id="b7209-327">Leistung</span><span class="sxs-lookup"><span data-stu-id="b7209-327">Performance</span></span>](index.md)
- <span data-ttu-id="b7209-328">[.NET-Leistungstipps](/previous-versions/dotnet/articles/ms973839(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="b7209-328">[.NET Performance Tips](/previous-versions/dotnet/articles/ms973839(v=msdn.10))</span></span>
- [<span data-ttu-id="b7209-329">Channel 9 PerfView-Tutorials</span><span class="sxs-lookup"><span data-stu-id="b7209-329">Channel 9 PerfView tutorials</span></span>](https://channel9.msdn.com/Series/PerfView-Tutorial)
- [<span data-ttu-id="b7209-330">.NET Compiler Platform-SDK</span><span class="sxs-lookup"><span data-stu-id="b7209-330">The .NET Compiler Platform SDK</span></span>](../../csharp/roslyn-sdk/index.md)
- [<span data-ttu-id="b7209-331">DotNet/Roslyn-Repository auf GitHub</span><span class="sxs-lookup"><span data-stu-id="b7209-331">dotnet/roslyn repo on GitHub</span></span>](https://github.com/dotnet/roslyn)
