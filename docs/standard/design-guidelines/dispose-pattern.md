---
title: Dispose-Muster
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Dispose method
- class library design guidelines [.NET Framework], Dispose method
- class library design guidelines [.NET Framework], Finalize method
- customizing Dispose method name
- Finalize method
ms.assetid: 31a6c13b-d6a2-492b-9a9f-e5238c983bcb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7bb9420d6439cff36c5cfa997152773503fbd9a
ms.sourcegitcommit: ed7b4b9b77d35e94a35a2634e8c874f46603fb2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36948549"
---
# <a name="dispose-pattern"></a><span data-ttu-id="409af-102">Dispose-Muster</span><span class="sxs-lookup"><span data-stu-id="409af-102">Dispose Pattern</span></span>
<span data-ttu-id="409af-103">Alle Programme abrufen eine oder mehrere Systemressourcen, z. B. Arbeitsspeicher, Systemhandles oder Datenbankverbindungen, im Rahmen ihrer Ausführung.</span><span class="sxs-lookup"><span data-stu-id="409af-103">All programs acquire one or more system resources, such as memory, system handles, or database connections, during the course of their execution.</span></span> <span data-ttu-id="409af-104">Entwickler müssen solche Systemressourcen mit Vorsicht werden, da sie freigegeben werden müssen, nachdem sie eingerichtet und verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="409af-104">Developers have to be careful when using such system resources, because they must be released after they have been acquired and used.</span></span>  
  
 <span data-ttu-id="409af-105">Die CLR bietet Unterstützung für die automatische Speicherverwaltung.</span><span class="sxs-lookup"><span data-stu-id="409af-105">The CLR provides support for automatic memory management.</span></span> <span data-ttu-id="409af-106">Verwalteter Speicher (mit dem c#-Operator zugeordnete Arbeitsspeicher `new`) muss nicht explizit freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="409af-106">Managed memory (memory allocated using the C# operator `new`) does not need to be explicitly released.</span></span> <span data-ttu-id="409af-107">Es wird automatisch vom Garbage Collector (GC) freigegeben.</span><span class="sxs-lookup"><span data-stu-id="409af-107">It is released automatically by the garbage collector (GC).</span></span> <span data-ttu-id="409af-108">Dies müssen Entwickler von der Aufgabe aufwändig und schwer Freigeben von Arbeitsspeicher und wurde einer der Hauptgründe, warum die unvergleichlich hohe Produktivität von .NET Framework gewährt wurden.</span><span class="sxs-lookup"><span data-stu-id="409af-108">This frees developers from the tedious and difficult task of releasing memory and has been one of the main reasons for the unprecedented productivity afforded by the .NET Framework.</span></span>  
  
 <span data-ttu-id="409af-109">Leider ist verwalteter Speicher nur eine verschiedener Arten von Systemressourcen.</span><span class="sxs-lookup"><span data-stu-id="409af-109">Unfortunately, managed memory is just one of many types of system resources.</span></span> <span data-ttu-id="409af-110">Ressourcen mit Ausnahme des verwalteten Speichers noch explizit freigegeben werden müssen und nicht verwalteten Ressourcen genannt werden.</span><span class="sxs-lookup"><span data-stu-id="409af-110">Resources other than managed memory still need to be released explicitly and are referred to as unmanaged resources.</span></span> <span data-ttu-id="409af-111">Der globale Katalogserver wurde ausdrücklich nicht entwickelt solche nicht verwalteten Ressourcen verwalten was bedeutet, dass die Verantwortung für die Verwaltung von nicht verwalteten Ressourcen in die Hände der Entwickler liegt.</span><span class="sxs-lookup"><span data-stu-id="409af-111">The GC was specifically not designed to manage such unmanaged resources, which means that the responsibility for managing unmanaged resources lies in the hands of the developers.</span></span>  
  
 <span data-ttu-id="409af-112">Die CLR bietet Hilfe in nicht verwaltete Ressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="409af-112">The CLR provides some help in releasing unmanaged resources.</span></span> <span data-ttu-id="409af-113"><xref:System.Object?displayProperty=nameWithType> deklariert eine virtuelle Methode <xref:System.Object.Finalize%2A> (auch als "Finalizer" bezeichnet), wird vom GC aufgerufen, bevor der Speicher des Objekts vom GC freigegeben wird und überschrieben werden, kann um nicht verwaltete Ressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="409af-113"><xref:System.Object?displayProperty=nameWithType> declares a virtual method <xref:System.Object.Finalize%2A> (also called the finalizer) that is called by the GC before the object’s memory is reclaimed by the GC and can be overridden to release unmanaged resources.</span></span> <span data-ttu-id="409af-114">Typen, die den Finalizer außer Kraft setzen, werden als finalisierbaren Typen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="409af-114">Types that override the finalizer are referred to as finalizable types.</span></span>  
  
 <span data-ttu-id="409af-115">Obwohl Finalizer in einigen Szenarien Cleanup wirksam sind, haben sie zwei erhebliche Nachteile:</span><span class="sxs-lookup"><span data-stu-id="409af-115">Although finalizers are effective in some cleanup scenarios, they have two significant drawbacks:</span></span>  
  
-   <span data-ttu-id="409af-116">Der Finalizer wird aufgerufen, wenn der globale Katalogserver erkennt, dass ein Objekt für die Auflistung geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="409af-116">The finalizer is called when the GC detects that an object is eligible for collection.</span></span> <span data-ttu-id="409af-117">Dies erfolgt bei einigen unbestimmten Zeitraum nach die Ressource nicht mehr benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="409af-117">This happens at some undetermined period of time after the resource is not needed anymore.</span></span> <span data-ttu-id="409af-118">Die Verzögerung zwischen den bei der Entwickler kann möchten oder Version der Ressource und die Uhrzeit, wann die Ressource tatsächlich von den Finalizer freigegeben wird, möglicherweise nicht akzeptabel in Programmen, die viele knappe Ressourcen (Ressourcen, die leicht erschöpft sein können) erwerben oder in Fällen, in denen Ressourcen kostspielige verwendet (z. B. große nicht verwalteten Speicherpuffer) beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="409af-118">The delay between when the developer could or would like to release the resource and the time when the resource is actually released by the finalizer might be unacceptable in programs that acquire many scarce resources (resources that can be easily exhausted) or in cases in which resources are costly to keep in use (e.g., large unmanaged memory buffers).</span></span>  
  
-   <span data-ttu-id="409af-119">Wenn die CLR einen Finalizer aufrufen muss, muss er Auflistung von Arbeitsspeicher für das Objekt verschieben, bis das nächste gerundet wird, der Garbagecollection (die Finalizer zwischen Auflistungen ausgeführt).</span><span class="sxs-lookup"><span data-stu-id="409af-119">When the CLR needs to call a finalizer, it must postpone collection of the object’s memory until the next round of garbage collection (the finalizers run between collections).</span></span> <span data-ttu-id="409af-120">Dies bedeutet, dass der Speicher des Objekts (und alle Objekte, denen er verweist) wird nicht für einen längeren Zeitraum freigegeben.</span><span class="sxs-lookup"><span data-stu-id="409af-120">This means that the object’s memory (and all objects it refers to) will not be released for a longer period of time.</span></span>  
  
 <span data-ttu-id="409af-121">Aus diesem Grund der vertrauenden Seite ausschließlich auf Finalizer möglicherweise nicht geeignet, in vielen Szenarien, wenn es darauf ankommt, nicht verwaltete Ressourcen freizugeben so schnell wie möglich, beim Umgang mit knappe Ressourcen oder in äußerst leistungsfähigen Szenarien, in denen der hinzugefügten GC-Mehraufwand der Abschluss ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="409af-121">Therefore, relying exclusively on finalizers might not be appropriate in many scenarios when it is important to reclaim unmanaged resources as quickly as possible, when dealing with scarce resources, or in highly performant scenarios in which the added GC overhead of finalization is unacceptable.</span></span>  
  
 <span data-ttu-id="409af-122">Das Framework bietet die <xref:System.IDisposable?displayProperty=nameWithType> -Schnittstelle, die implementiert werden soll, um dem Entwickler stellen eine manuelle Möglichkeit, die nicht verwaltete Ressourcen freizugeben, sobald sie nicht benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="409af-122">The Framework provides the <xref:System.IDisposable?displayProperty=nameWithType> interface that should be implemented to provide the developer a manual way to release unmanaged resources as soon as they are not needed.</span></span> <span data-ttu-id="409af-123">Sie bietet außerdem die <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> -Methode, die dem globalen Katalogserver, die erkennen kann ein Objekt wurde manuell verworfen und müssen nicht mehr freigegeben werden in diesem Fall kann der Speicher des Objekts früher freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="409af-123">It also provides the <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> method that can tell the GC that an object was manually disposed of and does not need to be finalized anymore, in which case the object’s memory can be reclaimed earlier.</span></span> <span data-ttu-id="409af-124">Typen implementiert, die `IDisposable` Schnittstelle als Verwerfbare Typen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="409af-124">Types that implement the `IDisposable` interface are referred to as disposable types.</span></span>  
  
 <span data-ttu-id="409af-125">Um die Verwendung und Implementierung der Finalizer zu standardisieren richtet sich an das Dispose-Muster und die `IDisposable` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="409af-125">The Dispose Pattern is intended to standardize the usage and implementation of finalizers and the `IDisposable` interface.</span></span>  
  
 <span data-ttu-id="409af-126">Die wichtigsten Motivation für das Muster besteht darin Reduzierung der Komplexität der Implementierung von der <xref:System.Object.Finalize%2A> und <xref:System.IDisposable.Dispose%2A> Methoden.</span><span class="sxs-lookup"><span data-stu-id="409af-126">The main motivation for the pattern is to reduce the complexity of the implementation of the <xref:System.Object.Finalize%2A> and the <xref:System.IDisposable.Dispose%2A> methods.</span></span> <span data-ttu-id="409af-127">Die Komplexität ist die Tatsache, dass die Methoden einige, aber nicht alle Codepfade nutzen (die Unterschiede werden später in diesem Kapitel beschrieben).</span><span class="sxs-lookup"><span data-stu-id="409af-127">The complexity stems from the fact that the methods share some but not all code paths (the differences are described later in the chapter).</span></span> <span data-ttu-id="409af-128">Darüber hinaus stehen aus Verlaufsgründen für die Benutzeroberflächenelemente des Musters im Zusammenhang mit der Entwicklung der sprachunterstützung für deterministische ressourcenverwaltung.</span><span class="sxs-lookup"><span data-stu-id="409af-128">In addition, there are historical reasons for some elements of the pattern related to the evolution of language support for deterministic resource management.</span></span>  
  
 <span data-ttu-id="409af-129">**Führen Sie ✓** das grundlegende Dispose-Muster für Typen, die Instanzen von Verwerfbare Typen implementieren.</span><span class="sxs-lookup"><span data-stu-id="409af-129">**✓ DO** implement the Basic Dispose Pattern on types containing instances of disposable types.</span></span> <span data-ttu-id="409af-130">Finden Sie unter der [grundlegende Dispose-Muster](#basic_pattern) Abschnitt, um Details für das grundlegende Muster.</span><span class="sxs-lookup"><span data-stu-id="409af-130">See the [Basic Dispose Pattern](#basic_pattern) section for details on the basic pattern.</span></span>  
  
 <span data-ttu-id="409af-131">Wenn ein Typ für die Lebensdauer des anderen verwerfbare Objekte verantwortlich ist, benötigen Entwicklern eine Möglichkeit, diese zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="409af-131">If a type is responsible for the lifetime of other disposable objects, developers need a way to dispose of them, too.</span></span> <span data-ttu-id="409af-132">Mithilfe des Containers `Dispose` Methode ist eine komfortable Methode, um dies zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="409af-132">Using the container’s `Dispose` method is a convenient way to make this possible.</span></span>  
  
 <span data-ttu-id="409af-133">**Führen Sie ✓** grundlegende Dispose-Muster implementiert wird und einen Finalizer bereitstellen, auf Ressourcen, die explizit freigegeben werden müssen und die keine Finalizer.</span><span class="sxs-lookup"><span data-stu-id="409af-133">**✓ DO** implement the Basic Dispose Pattern and provide a finalizer on types holding resources that need to be freed explicitly and that do not have finalizers.</span></span>  
  
 <span data-ttu-id="409af-134">Beispielsweise sollte das Muster für Typen, die Speichern von nicht verwalteten Arbeitsspeicher implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="409af-134">For example, the pattern should be implemented on types storing unmanaged memory buffers.</span></span> <span data-ttu-id="409af-135">Die [finalisierbaren Typen](#finalizable_types) Abschnitt wird erläutert, Richtlinien, die im Zusammenhang mit der Finalizer zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="409af-135">The [Finalizable Types](#finalizable_types) section discusses guidelines related to implementing finalizers.</span></span>  
  
 <span data-ttu-id="409af-136">**· ERWÄGEN SIE** die Implementierung des grundlegenden Dispose-Musters bei Klassen, die selbst keine verwalteten Ressourcen oder verwerfbaren Objekte enthalten, aber Untertypen umfassen können, die dies tun.</span><span class="sxs-lookup"><span data-stu-id="409af-136">**✓ CONSIDER** implementing the Basic Dispose Pattern on classes that themselves don’t hold unmanaged resources or disposable objects but are likely to have subtypes that do.</span></span>  
  
 <span data-ttu-id="409af-137">Ein hervorragendes Beispiel dafür ist die <xref:System.IO.Stream?displayProperty=nameWithType> -Klasse.</span><span class="sxs-lookup"><span data-stu-id="409af-137">A great example of this is the <xref:System.IO.Stream?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="409af-138">Während es sich hierbei um eine abstrakte Basisklasse handelt, die keinerlei Ressourcen enthält, tun dies die meisten ihrer Unterklassen. Aus diesem Grund implementiert sie das Dispose-Muster.</span><span class="sxs-lookup"><span data-stu-id="409af-138">Although it is an abstract base class that doesn’t hold any resources, most of its subclasses do and because of this, it implements this pattern.</span></span>  
  
<a name="basic_pattern"></a>   
## <a name="basic-dispose-pattern"></a><span data-ttu-id="409af-139">Grundlegende Dispose-Muster</span><span class="sxs-lookup"><span data-stu-id="409af-139">Basic Dispose Pattern</span></span>  
 <span data-ttu-id="409af-140">Die grundlegende Implementierung des Musters beinhaltet die Implementierung der `System.IDisposable` Schnittstelle und meldet die `Dispose(bool)` -Methode, die alle Ressourcen der Bereinigungslogik, gemeinsam genutzt werden die `Dispose` -Methode und der optionalen Finalizer.</span><span class="sxs-lookup"><span data-stu-id="409af-140">The basic implementation of the pattern involves implementing the `System.IDisposable` interface and declaring the `Dispose(bool)` method that implements all resource cleanup logic to be shared between the `Dispose` method and the optional finalizer.</span></span>  
  
 <span data-ttu-id="409af-141">Das folgende Beispiel zeigt eine einfache Implementierung der das grundlegende Muster:</span><span class="sxs-lookup"><span data-stu-id="409af-141">The following example shows a simple implementation of the basic pattern:</span></span>  
  
```csharp
public class DisposableResourceHolder : IDisposable {  
  
    private SafeHandle resource; // handle to a resource  
  
    public DisposableResourceHolder() {  
        this.resource = ... // allocates the resource  
    }  
  
    public void Dispose() {  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
  
    protected virtual void Dispose(bool disposing) {  
        if (disposing) {  
            if (resource!= null) resource.Dispose();  
        }  
    }  
}  
```  
  
 <span data-ttu-id="409af-142">Den booleschen Parameter `disposing` gibt an, ob die Methode aufgerufen wurde, aus der `IDisposable.Dispose` Implementierung oder von der Finalizer.</span><span class="sxs-lookup"><span data-stu-id="409af-142">The Boolean parameter `disposing` indicates whether the method was invoked from the `IDisposable.Dispose` implementation or from the finalizer.</span></span> <span data-ttu-id="409af-143">Die `Dispose(bool)` Implementierung sollte überprüfen Sie den Parameter vor dem Zugriff auf andere Verweisobjekte (z. B. das Ressourcenfeld im vorhergehenden Beispiel).</span><span class="sxs-lookup"><span data-stu-id="409af-143">The `Dispose(bool)` implementation should check the parameter before accessing other reference objects (e.g., the resource field in the preceding sample).</span></span> <span data-ttu-id="409af-144">Solche Objekte nur zugegriffen werden soll, wenn die Methode aufgerufen wird, aus der `IDisposable.Dispose` Implementierung (bei der `disposing` Parameter gleich "true").</span><span class="sxs-lookup"><span data-stu-id="409af-144">Such objects should only be accessed when the method is called from the `IDisposable.Dispose` implementation (when the `disposing` parameter is equal to true).</span></span> <span data-ttu-id="409af-145">Wenn die Methode, von der Finalizer aufgerufen wird (`disposing` lautet "false"), andere Objekte nicht zugegriffen werden soll.</span><span class="sxs-lookup"><span data-stu-id="409af-145">If the method is invoked from the finalizer (`disposing` is false), other objects should not be accessed.</span></span> <span data-ttu-id="409af-146">Der Grund ist, dass Objekte in einem unvorhersehbaren Reihenfolge abgeschlossen werden und daher diese oder eine ihrer Abhängigkeiten möglicherweise bereits abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="409af-146">The reason is that objects are finalized in an unpredictable order and so they, or any of their dependencies, might already have been finalized.</span></span>  
  
 <span data-ttu-id="409af-147">In diesem Abschnitt gilt auch, Klassen, mit der eine Basis, die nicht bereits das Dispose-Muster implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="409af-147">Also, this section applies to classes with a base that does not already implement the Dispose Pattern.</span></span> <span data-ttu-id="409af-148">Wenn Sie von einer Klasse, die bereits das Steuerelementmuster implementiert erben, überschreiben Sie einfach die `Dispose(bool)` Methode, um zusätzliche Ressourcen Bereinigungslogik bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="409af-148">If you are inheriting from a class that already implements the pattern, simply override the `Dispose(bool)` method to provide additional resource cleanup logic.</span></span>  
  
 <span data-ttu-id="409af-149">**Führen Sie ✓** deklarieren eine `protected virtual void Dispose(bool disposing)` Methode, um die gesamte Logik zu zentralisieren, die sich auf die Freigabe nicht verwalteter Ressourcen beziehen.</span><span class="sxs-lookup"><span data-stu-id="409af-149">**✓ DO** declare a `protected virtual void Dispose(bool disposing)` method to centralize all logic related to releasing unmanaged resources.</span></span>  
  
 <span data-ttu-id="409af-150">Bei dieser Methode sollten alle ressourcenbereinigung auftreten.</span><span class="sxs-lookup"><span data-stu-id="409af-150">All resource cleanup should occur in this method.</span></span> <span data-ttu-id="409af-151">Die Methode wird von beiden die Finalizer aufgerufen und die `IDisposable.Dispose` Methode.</span><span class="sxs-lookup"><span data-stu-id="409af-151">The method is called from both the finalizer and the `IDisposable.Dispose` method.</span></span> <span data-ttu-id="409af-152">Der Parameter werden "false", wenn in einer Finalize-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="409af-152">The parameter will be false if being invoked from inside a finalizer.</span></span> <span data-ttu-id="409af-153">Es sollte verwendet werden, um sicherzustellen, dass jedem Code ausgeführt wird, während des Abschlusses nicht andere finalisierbare Objekte zugreift.</span><span class="sxs-lookup"><span data-stu-id="409af-153">It should be used to ensure any code running during finalization is not accessing other finalizable objects.</span></span> <span data-ttu-id="409af-154">Informationen zum Implementieren der Finalizer werden im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="409af-154">Details of implementing finalizers are described in the next section.</span></span>  
  
```csharp
protected virtual void Dispose(bool disposing) {  
    if (disposing) {  
        if (resource!= null) resource.Dispose();  
    }  
}  
```  
  
 <span data-ttu-id="409af-155">**Führen Sie ✓** implementieren die `IDisposable` Schnittstelle durch den Aufruf einfach `Dispose(true)` gefolgt von `GC.SuppressFinalize(this)`.</span><span class="sxs-lookup"><span data-stu-id="409af-155">**✓ DO** implement the `IDisposable` interface by simply calling `Dispose(true)` followed by `GC.SuppressFinalize(this)`.</span></span>  
  
 <span data-ttu-id="409af-156">Der Aufruf von `SuppressFinalize` sollte nur erfolgen, wenn `Dispose(true)` erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="409af-156">The call to `SuppressFinalize` should only occur if `Dispose(true)` executes successfully.</span></span>  
  
```csharp
public void Dispose(){  
    Dispose(true);  
    GC.SuppressFinalize(this);  
}  
```  
  
 <span data-ttu-id="409af-157">**X nicht** stellen die parameterlose `Dispose` virtuelle Methode.</span><span class="sxs-lookup"><span data-stu-id="409af-157">**X DO NOT** make the parameterless `Dispose` method virtual.</span></span>  
  
 <span data-ttu-id="409af-158">Die `Dispose(bool)` Methode ist dasjenige, das von Unterklassen überschrieben werden sollte.</span><span class="sxs-lookup"><span data-stu-id="409af-158">The `Dispose(bool)` method is the one that should be overridden by subclasses.</span></span>  
  
```csharp
// bad design  
public class DisposableResourceHolder : IDisposable {  
    public virtual void Dispose() { ... }  
    protected virtual void Dispose(bool disposing) { ... }  
}  
  
// good design  
public class DisposableResourceHolder : IDisposable {  
    public void Dispose() { ... }  
    protected virtual void Dispose(bool disposing) { ... }  
}  
```  
  
 <span data-ttu-id="409af-159">**X nicht** alle Überladungen der deklarieren die `Dispose` andere Methode als `Dispose()` und `Dispose(bool)`.</span><span class="sxs-lookup"><span data-stu-id="409af-159">**X DO NOT** declare any overloads of the `Dispose` method other than `Dispose()` and `Dispose(bool)`.</span></span>  
  
 <span data-ttu-id="409af-160">`Dispose` Berücksichtigen Sie ein reserviertes Wort zu helfen, dieses Muster Sicherungssystems und schließt Verwechslungen zwischen Implementierer, Benutzer und -Compiler.</span><span class="sxs-lookup"><span data-stu-id="409af-160">`Dispose` should be considered a reserved word to help codify this pattern and prevent confusion among implementers, users, and compilers.</span></span> <span data-ttu-id="409af-161">Für einige Sprachen empfiehlt sich, dieses Muster für bestimmte Typen automatisch zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="409af-161">Some languages might choose to automatically implement this pattern on certain types.</span></span>  
  
 <span data-ttu-id="409af-162">**Führen Sie ✓** ermöglichen die `Dispose(bool)` Methode, die mehr als einmal aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="409af-162">**✓ DO** allow the `Dispose(bool)` method to be called more than once.</span></span> <span data-ttu-id="409af-163">Die Methode empfiehlt sich, nach dem ersten Aufruf nichts zu tun.</span><span class="sxs-lookup"><span data-stu-id="409af-163">The method might choose to do nothing after the first call.</span></span>  
  
```csharp
public class DisposableResourceHolder : IDisposable {  
  
    bool disposed = false;  
  
    protected virtual void Dispose(bool disposing) {  
        if (disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 <span data-ttu-id="409af-164">**X vermeiden** Auslösen einer Ausnahme heraus `Dispose(bool)` außer in kritischen Situationen, in denen der enthaltende Prozess wurde beschädigt (Speicherverlusten, inkonsistent Freigabezustand usw..).</span><span class="sxs-lookup"><span data-stu-id="409af-164">**X AVOID** throwing an exception from within `Dispose(bool)` except under critical situations where the containing process has been corrupted (leaks, inconsistent shared state, etc.).</span></span>  
  
 <span data-ttu-id="409af-165">Benutzer erwarten, dass ein Aufruf von `Dispose` wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="409af-165">Users expect that a call to `Dispose` will not raise an exception.</span></span>  
  
 <span data-ttu-id="409af-166">Wenn `Dispose` konnte eine Ausnahme ausgelöst werden, weitere finally-Block Bereinigungslogik wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="409af-166">If `Dispose` could raise an exception, further finally-block cleanup logic will not execute.</span></span> <span data-ttu-id="409af-167">Um dieses Problem umgehen, muss der Benutzer zum Umschließen von jedem Aufruf von `Dispose` (innerhalb der finally-block!) in einem Try-Block, der in sehr komplexen Bereinigung Handler führt.</span><span class="sxs-lookup"><span data-stu-id="409af-167">To work around this, the user would need to wrap every call to `Dispose` (within the finally block!) in a try block, which leads to very complex cleanup handlers.</span></span> <span data-ttu-id="409af-168">Wenn die Ausführung einer `Dispose(bool disposing)` Methode nie löst eine Ausnahme aus, wenn der disposing "false" ist.</span><span class="sxs-lookup"><span data-stu-id="409af-168">If executing a `Dispose(bool disposing)` method, never throw an exception if disposing is false.</span></span> <span data-ttu-id="409af-169">Auf diese Weise wird der Prozess beendet, wenn in einem Finalizer-Kontext ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="409af-169">Doing so will terminate the process if executing inside a finalizer context.</span></span>  
  
 <span data-ttu-id="409af-170">**✓ FÜHREN** Auslösen einer <xref:System.ObjectDisposedException> über ein Element, das verwendet werden kann, nachdem das Objekt verworfen wurde.</span><span class="sxs-lookup"><span data-stu-id="409af-170">**✓ DO** throw an <xref:System.ObjectDisposedException> from any member that cannot be used after the object has been disposed of.</span></span>  
  
```csharp
public class DisposableResourceHolder : IDisposable {  
    bool disposed = false;  
    SafeHandle resource; // handle to a resource  
  
    public void DoSomething() {  
        if (disposed) throw new ObjectDisposedException(...);  
        // now call some native methods using the resource   
        ...  
    }  
    protected virtual void Dispose(bool disposing) {  
        if (disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 <span data-ttu-id="409af-171">**✓ GGF.** als Methode `Close()`, zusätzlich zu den `Dispose()`, wenn schließen standard Terminologie im Bereich ist.</span><span class="sxs-lookup"><span data-stu-id="409af-171">**✓ CONSIDER** providing method `Close()`, in addition to the `Dispose()`, if close is standard terminology in the area.</span></span>  
  
 <span data-ttu-id="409af-172">Dabei ist es wichtig, dass Sie stellen der `Close` Implementierung identisch mit `Dispose` und implementieren Sie die `IDisposable.Dispose` Methode explizit.</span><span class="sxs-lookup"><span data-stu-id="409af-172">When doing so, it is important that you make the `Close` implementation identical to `Dispose` and consider implementing the `IDisposable.Dispose` method explicitly.</span></span>  
  
```csharp
public class Stream : IDisposable {  
    IDisposable.Dispose() {  
        Close();  
    }  
    public void Close() {  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
<a name="finalizable_types"></a>   
## <a name="finalizable-types"></a><span data-ttu-id="409af-173">Finalisierbaren Typen</span><span class="sxs-lookup"><span data-stu-id="409af-173">Finalizable Types</span></span>  
 <span data-ttu-id="409af-174">Finalisierbare Typen sind Typen, die das grundlegende Dispose-Muster zu erweitern, indem Sie den Finalizer überschreiben und das Bereitstellen von Codepfad in seiner Finalisierung verfolgt die `Dispose(bool)` Methode.</span><span class="sxs-lookup"><span data-stu-id="409af-174">Finalizable types are types that extend the Basic Dispose Pattern by overriding the finalizer and providing finalization code path in the `Dispose(bool)` method.</span></span>  
  
 <span data-ttu-id="409af-175">Finalizer sind bekanntermaßen schwierig zu ordnungsgemäß implementieren, in erster Linie verwendet werden, da Sie während ihrer Ausführung bestimmter (normalerweise gültigen) Annahmen über den Zustand des Systems vornehmen können.</span><span class="sxs-lookup"><span data-stu-id="409af-175">Finalizers are notoriously difficult to implement correctly, primarily because you cannot make certain (normally valid) assumptions about the state of the system during their execution.</span></span> <span data-ttu-id="409af-176">Die folgenden Richtlinien sollten eine sorgfältige berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="409af-176">The following guidelines should be taken into careful consideration.</span></span>  
  
 <span data-ttu-id="409af-177">Beachten Sie, dass einige der Richtlinien angewendet werden nicht nur auf die `Finalize` -Methode, jedoch keinen Code von einem Finalizer aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="409af-177">Note that some of the guidelines apply not just to the `Finalize` method, but to any code called from a finalizer.</span></span> <span data-ttu-id="409af-178">Bei der grundlegende Dispose-Muster zuvor definiert, bedeutet das Logik, die in ausgeführt wird `Dispose(bool disposing)` bei der `disposing` Parameter ist "false".</span><span class="sxs-lookup"><span data-stu-id="409af-178">In the case of the Basic Dispose Pattern previously defined, this means logic that executes inside `Dispose(bool disposing)` when the `disposing` parameter is false.</span></span>  
  
 <span data-ttu-id="409af-179">Wenn die Basisklasse bereits finalisierbaren und die grundlegende Dispose-Muster implementiert, sollten Sie nicht überschreiben `Finalize` erneut aus.</span><span class="sxs-lookup"><span data-stu-id="409af-179">If the base class already is finalizable and implements the Basic Dispose Pattern, you should not override `Finalize` again.</span></span> <span data-ttu-id="409af-180">Sie sollten stattdessen nur überschreiben die `Dispose(bool)` Methode, um zusätzliche Ressourcen Bereinigungslogik bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="409af-180">You should instead just override the `Dispose(bool)` method to provide additional resource cleanup logic.</span></span>  
  
 <span data-ttu-id="409af-181">Der folgende Code zeigt ein Beispiel eines finalisierbaren Typs:</span><span class="sxs-lookup"><span data-stu-id="409af-181">The following code shows an example of a finalizable type:</span></span>  
  
```csharp
public class ComplexResourceHolder : IDisposable {  
  
    private IntPtr buffer; // unmanaged memory buffer  
    private SafeHandle resource; // disposable handle to a resource  
  
    public ComplexResourceHolder() {  
        this.buffer = ... // allocates memory  
        this.resource = ... // allocates the resource  
    }  
  
    protected virtual void Dispose(bool disposing) {  
            ReleaseBuffer(buffer); // release unmanaged memory  
        if (disposing) { // release other disposable objects  
            if (resource!= null) resource.Dispose();  
        }  
    }  
  
    ~ComplexResourceHolder() {
        Dispose(false);  
    }  
  
    public void Dispose() {
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
 <span data-ttu-id="409af-182">**X vermeiden** Typen finalisierbaren vornehmen.</span><span class="sxs-lookup"><span data-stu-id="409af-182">**X AVOID** making types finalizable.</span></span>  
  
 <span data-ttu-id="409af-183">Bedenken Sie sorgfältig die jeder Fall, in dem Sie vorstellen, dass ein Finalizer erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="409af-183">Carefully consider any case in which you think a finalizer is needed.</span></span> <span data-ttu-id="409af-184">Es gibt ein echten Kosten Instanzen mit Finalizer aus Sicht der Komplexität einer Leistung und den Code.</span><span class="sxs-lookup"><span data-stu-id="409af-184">There is a real cost associated with instances with finalizers, from both a performance and code complexity standpoint.</span></span> <span data-ttu-id="409af-185">Es vorziehen, z. B. mit der Ressource Wrapper <xref:System.Runtime.InteropServices.SafeHandle> um nicht verwaltete Ressourcen möglichst zu kapseln, in diesem Fall ein Finalizer wird nicht erforderlich, da der Wrapper für einen eigenen ressourcenbereinigung zuständig ist.</span><span class="sxs-lookup"><span data-stu-id="409af-185">Prefer using resource wrappers such as <xref:System.Runtime.InteropServices.SafeHandle> to encapsulate unmanaged resources where possible, in which case a finalizer becomes unnecessary because the wrapper is responsible for its own resource cleanup.</span></span>  
  
 <span data-ttu-id="409af-186">**X nicht** Werttypen finalisierbaren vornehmen.</span><span class="sxs-lookup"><span data-stu-id="409af-186">**X DO NOT** make value types finalizable.</span></span>  
  
 <span data-ttu-id="409af-187">Nur Verweistypen abrufen tatsächlich von der CLR freigegeben und daher wird jeder Versuch, platzieren Sie einen Finalizer für einen Werttyp wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="409af-187">Only reference types actually get finalized by the CLR, and thus any attempt to place a finalizer on a value type will be ignored.</span></span> <span data-ttu-id="409af-188">Die C#- und C++-Compiler erzwingen diese Regel.</span><span class="sxs-lookup"><span data-stu-id="409af-188">The C# and C++ compilers enforce this rule.</span></span>  
  
 <span data-ttu-id="409af-189">**Führen Sie ✓** stellen einen Typ finalisierbaren, wenn der Typ verantwortlich ist für eine nicht verwaltete Ressource, die über keinen eigenen Finalizer freigeben.</span><span class="sxs-lookup"><span data-stu-id="409af-189">**✓ DO** make a type finalizable if the type is responsible for releasing an unmanaged resource that does not have its own finalizer.</span></span>  
  
 <span data-ttu-id="409af-190">Wenn Sie den Finalizer zu implementieren, rufen Sie einfach `Dispose(false)` und fügen Sie alle Ressourcen Bereinigungslogik innerhalb der `Dispose(bool disposing)` Methode.</span><span class="sxs-lookup"><span data-stu-id="409af-190">When implementing the finalizer, simply call `Dispose(false)` and place all resource cleanup logic inside the `Dispose(bool disposing)` method.</span></span>  
  
```csharp
public class ComplexResourceHolder : IDisposable {  
  
    ~ComplexResourceHolder() {
        Dispose(false);  
    }  
  
    protected virtual void Dispose(bool disposing) {
        ...  
    }  
}  
```  
  
 <span data-ttu-id="409af-191">**Führen Sie ✓** das grundlegende Dispose-Muster für jede finalisierbaren Typ zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="409af-191">**✓ DO** implement the Basic Dispose Pattern on every finalizable type.</span></span>  
  
 <span data-ttu-id="409af-192">Dadurch kann Benutzer des Typs eine deterministische Bereinigung von gleichen Ressourcen explizit führen Sie für die der Finalizer verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="409af-192">This gives users of the type a means to explicitly perform deterministic cleanup of those same resources for which the finalizer is responsible.</span></span>  
  
 <span data-ttu-id="409af-193">**X nicht** finalisierbare Objekte in der Finalizer-Codepfad zugegriffen werden, da ist es bedeutendes Risiko, dass sie bereits finalisiert sein werden.</span><span class="sxs-lookup"><span data-stu-id="409af-193">**X DO NOT** access any finalizable objects in the finalizer code path, because there is significant risk that they will have already been finalized.</span></span>  
  
 <span data-ttu-id="409af-194">Angenommen, ein abzuschließendes Objekt ein, die einen Verweis auf eine andere abzuschließendes Objekt B enthält zuverlässig können keine B in die Finalize-Methode oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="409af-194">For example, a finalizable object A that has a reference to another finalizable object B cannot reliably use B in A’s finalizer, or vice versa.</span></span> <span data-ttu-id="409af-195">Finalizer werden in zufälliger Reihenfolge (nicht genügend eine schwache Sortierung Garantie für Handleressourcen) aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="409af-195">Finalizers are called in a random order (short of a weak ordering guarantee for critical finalization).</span></span>  
  
 <span data-ttu-id="409af-196">Bedenken Sie außerdem, dass in statischen Variablen gespeicherten Objekte an bestimmten Punkten während der Anwendung Domäne entladen oder beim Beenden des Prozesses erfasst abrufen.</span><span class="sxs-lookup"><span data-stu-id="409af-196">Also, be aware that objects stored in static variables will get collected at certain points during an application domain unload or while exiting the process.</span></span> <span data-ttu-id="409af-197">Zugreifen auf eine statische Variable, die bezieht sich auf ein abzuschließendes Objekt (oder Aufrufs einer statischen Methode, die in statischen Variablen gespeicherten Werte verwenden kann) möglicherweise nicht sichere If <xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType> "Wahr" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="409af-197">Accessing a static variable that refers to a finalizable object (or calling a static method that might use values stored in static variables) might not be safe if <xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType> returns true.</span></span>  
  
 <span data-ttu-id="409af-198">**Führen Sie ✓** stellen Ihre `Finalize` geschützte Methode.</span><span class="sxs-lookup"><span data-stu-id="409af-198">**✓ DO** make your `Finalize` method protected.</span></span>  
  
 <span data-ttu-id="409af-199">C#, C++ und VB.NET Entwickler benötigen keine hierzu kümmern, da der Compiler helfen, um diese Richtlinie zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="409af-199">C#, C++, and VB.NET developers do not need to worry about this, because the compilers help to enforce this guideline.</span></span>  
  
 <span data-ttu-id="409af-200">**X nicht** können Ausnahmen Escapezeichen aus der Finalizer-Logik, mit Ausnahme von System kritische Fehler.</span><span class="sxs-lookup"><span data-stu-id="409af-200">**X DO NOT** let exceptions escape from the finalizer logic, except for system-critical failures.</span></span>  
  
 <span data-ttu-id="409af-201">Wenn von einem Finalizer eine Ausnahme ausgelöst wird, wird die CLR heruntergefahren, nach den gesamten Prozess (ab .NET Framework, Version 2.0), verhindern, dass andere Finalizer ausführen und die Ressourcen aus, die kontrolliert freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="409af-201">If an exception is thrown from a finalizer, the CLR will shut down the entire process (as of .NET Framework version 2.0), preventing other finalizers from executing and resources from being released in a controlled manner.</span></span>  
  
 <span data-ttu-id="409af-202">**✓ GGF.** erstellen und verwenden ein abzuschließendes Objekt inaktiv kritische (ein Typ mit einer Typhierarchie, die enthält <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>) für Situationen, in der ein Finalizer absolut werden auch bei der erzwungenen Anwendung Domäne entladen und Threads ausgeführt muss, Bricht ab.</span><span class="sxs-lookup"><span data-stu-id="409af-202">**✓ CONSIDER** creating and using a critical finalizable object (a type with a type hierarchy that contains <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>) for situations in which a finalizer absolutely must execute even in the face of forced application domain unloads and thread aborts.</span></span>  
  
 <span data-ttu-id="409af-203">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="409af-203">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="409af-204">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="409af-204">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="409af-205">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="409af-205">See Also</span></span>  
 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>  
 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="409af-206">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="409af-206">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="409af-207">Allgemeine Entwurfsmuster</span><span class="sxs-lookup"><span data-stu-id="409af-207">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 [<span data-ttu-id="409af-208">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="409af-208">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
