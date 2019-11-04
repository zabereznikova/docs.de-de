---
title: Auflösen von Assemblyladevorgängen
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], resolving loads
- application domains, loading assemblies
- resolving assembly loads
- assemblies [.NET Framework], loading
- application domains, resolving assembly loads
ms.assetid: 5099e549-f4fd-49fb-a290-549edd456c6a
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 6a49c070bd7d2e3819044c6bb653671a2fc8199f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73106996"
---
# <a name="resolve-assembly-loads"></a><span data-ttu-id="73120-102">Auflösen von Assemblyladevorgängen</span><span class="sxs-lookup"><span data-stu-id="73120-102">Resolve assembly loads</span></span>
<span data-ttu-id="73120-103">.NET stellt das Ereignis <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> für Anwendungen bereit, die mehr Kontrolle beim Laden von Assemblys benötigen.</span><span class="sxs-lookup"><span data-stu-id="73120-103">.NET provides the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event for applications that require greater control over assembly loading.</span></span> <span data-ttu-id="73120-104">Durch das Behandeln dieses Ereignisses kann Ihre Anwendung eine Assembly außerhalb der Prüfpfade in einen Kontext laden, vor dem Laden zwischen verschiedenen Assemblyversionen wählen, eine dynamische Assembly ausgeben und diese zurückgeben und so weiter.</span><span class="sxs-lookup"><span data-stu-id="73120-104">By handling this event, your application can load an assembly into the load context from outside the normal probing paths, select which of several assembly versions to load, emit a dynamic assembly and return it, and so on.</span></span> <span data-ttu-id="73120-105">In diesem Thema erhalten Sie eine Anleitung zum Behandeln des Ereignisses <xref:System.AppDomain.AssemblyResolve>.</span><span class="sxs-lookup"><span data-stu-id="73120-105">This topic provides guidance for handling the <xref:System.AppDomain.AssemblyResolve> event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="73120-106">Zum Auflösen vom Laden einer Assembly in einem reflektionsbezogenen Kontext können Sie stattdessen das Ereignis <xref:System.AppDomain.ReflectionOnlyAssemblyResolve?displayProperty=nameWithType> verwenden.</span><span class="sxs-lookup"><span data-stu-id="73120-106">For resolving assembly loads in the reflection-only context, use the <xref:System.AppDomain.ReflectionOnlyAssemblyResolve?displayProperty=nameWithType> event instead.</span></span>  
  
## <a name="how-the-assemblyresolve-event-works"></a><span data-ttu-id="73120-107">Auslösung des Ereignisses „AssemblyResolve“</span><span class="sxs-lookup"><span data-stu-id="73120-107">How the AssemblyResolve event works</span></span>  
 <span data-ttu-id="73120-108">Wenn Sie einen Handler für das Ereignis <xref:System.AppDomain.AssemblyResolve> registrieren, wird der Handler immer dann aufgerufen, wenn die Runtime eine Assembly nicht anhand deren Namen binden kann.</span><span class="sxs-lookup"><span data-stu-id="73120-108">When you register a handler for the <xref:System.AppDomain.AssemblyResolve> event, the handler is invoked whenever the runtime fails to bind to an assembly by name.</span></span> <span data-ttu-id="73120-109">Wenn Sie z.B. die folgende Methode aus Benutzercode aufrufen, kann das Ereignis <xref:System.AppDomain.AssemblyResolve> ausgelöst werden:</span><span class="sxs-lookup"><span data-stu-id="73120-109">For example, calling the following methods from user code can cause the <xref:System.AppDomain.AssemblyResolve> event to be raised:</span></span>  
  
- <span data-ttu-id="73120-110">Die Methodenüberladung <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> oder <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>, deren erstes Argument eine Zeichenfolge ist, die den Anzeigenamen der zu ladenden Assembly darstellt (d.h. die von der Eigenschaft <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> zurückgegebene Zeichenfolge).</span><span class="sxs-lookup"><span data-stu-id="73120-110">An <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> method overload or <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method overload whose first argument is a string that represents the display name of the assembly to load (that is, the string returned by the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property).</span></span>  
  
- <span data-ttu-id="73120-111">Die Methodenüberladung <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> oder <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>, deren erstes Argument ein <xref:System.Reflection.AssemblyName>-Objekt ist, das die zu ladende Assembly angibt.</span><span class="sxs-lookup"><span data-stu-id="73120-111">An <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> method overload or <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method overload whose first argument is an <xref:System.Reflection.AssemblyName> object that identifies the assembly to load.</span></span>  
  
- <span data-ttu-id="73120-112">Die Methodenüberladung <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="73120-112">An <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType> method overload.</span></span>  
  
- <span data-ttu-id="73120-113">Die Methodenüberladung <xref:System.AppDomain.CreateInstance%2A?displayProperty=nameWithType> oder <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType>, das ein Objekt in einer anderen Anwendungsdomäne instantiiert.</span><span class="sxs-lookup"><span data-stu-id="73120-113">An <xref:System.AppDomain.CreateInstance%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType> method overload that instantiates an object in another application domain.</span></span>  
  
### <a name="what-the-event-handler-does"></a><span data-ttu-id="73120-114">Welche Aktionen der Ereignishandler ausführt</span><span class="sxs-lookup"><span data-stu-id="73120-114">What the event handler does</span></span>  
 <span data-ttu-id="73120-115">Der Handler für das Ereignis <xref:System.AppDomain.AssemblyResolve> erhält den Anzeigenamen der zu ladenden Assembly in der Eigenschaft <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="73120-115">The handler for the <xref:System.AppDomain.AssemblyResolve> event receives the display name of the assembly to be loaded, in the <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="73120-116">Wenn der Handler den Assemblynamen nicht erkennt, gibt er `null` (C#), `Nothing` (Visual Basic) oder `nullptr` (Visual C++) zurück.</span><span class="sxs-lookup"><span data-stu-id="73120-116">If the handler does not recognize the assembly name, it returns `null` (C#), `Nothing` (Visual Basic), or `nullptr` (Visual C++).</span></span>  
  
 <span data-ttu-id="73120-117">Wenn der Handler den Assemblynamen erkennt, kann er eine Assembly laden und zurückgeben, die der Anforderung entspricht.</span><span class="sxs-lookup"><span data-stu-id="73120-117">If the handler recognizes the assembly name, it can load and return an assembly that satisfies the request.</span></span> <span data-ttu-id="73120-118">In der folgenden Liste werden einige Beispielszenarios beschrieben.</span><span class="sxs-lookup"><span data-stu-id="73120-118">The following list describes some sample scenarios.</span></span>  
  
- <span data-ttu-id="73120-119">Wenn der Handler den Speicherort einer Version der Assembly kennt, kann er die Assembly mit den Methoden <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> oder <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType> laden und bei Erfolg die geladene Assembly zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="73120-119">If the handler knows the location of a version of the assembly, it can load the assembly by using the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType> method, and can return the loaded assembly if successful.</span></span>  
  
- <span data-ttu-id="73120-120">Wenn der Handler auf die Datenbank von Assemblys zugreifen kann, die als Bytearrays gespeichert sind, kann er das Bytearray mit den Methodenüberladungen <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> laden, die Bytearrays akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="73120-120">If the handler has access to a database of assemblies stored as byte arrays, it can load a byte array by using one of the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method overloads that take a byte array.</span></span>  
  
- <span data-ttu-id="73120-121">Der Handler kann eine dynamische Assembly generieren und diese zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="73120-121">The handler can generate a dynamic assembly and return it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="73120-122">Der Handler muss die Assembly entweder in den load-from-Kontext, den load-Kontext oder ohne Kontext laden. Wenn der Handler die Assembly mit den Methoden <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> oder <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=nameWithType> in den reflektionsbezogenen Kontext lädt, schlägt der Ladeversuch, der das Ereignis <xref:System.AppDomain.AssemblyResolve> ausgelöst hat, fehl.</span><span class="sxs-lookup"><span data-stu-id="73120-122">The handler must load the assembly into the load-from context, into the load context, or without context.If the handler loads the assembly into the reflection-only context by using the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> or the <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=nameWithType> method, the load attempt that raised the <xref:System.AppDomain.AssemblyResolve> event fails.</span></span>  
  
 <span data-ttu-id="73120-123">Der Ereignishandler ist dafür verantwortlich, eine passende Assembly zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="73120-123">It is the responsibility of the event handler to return a suitable assembly.</span></span> <span data-ttu-id="73120-124">Der Handler kann den Anzeigename der angeforderten Assembly analysieren, indem er den Wert der <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType>-Eigenschaft an den <xref:System.Reflection.AssemblyName.%23ctor%28System.String%29>-Konstruktor übergibt.</span><span class="sxs-lookup"><span data-stu-id="73120-124">The handler can parse the display name of the requested assembly by passing the <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType> property value to the <xref:System.Reflection.AssemblyName.%23ctor%28System.String%29> constructor.</span></span> <span data-ttu-id="73120-125">Ab .NET Framework 4 kann der Handler die <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType>-Eigenschaft verwenden, um zu bestimmen, ob die aktuelle Anforderung eine Abhängigkeit von einer anderen Assembly darstellt.</span><span class="sxs-lookup"><span data-stu-id="73120-125">Beginning with the .NET Framework 4, the handler can use the <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> property to determine whether the current request is a dependency of another assembly.</span></span> <span data-ttu-id="73120-126">Diese Information kann dabei helfen, eine Assembly zu identifizieren die die Abhängigkeit erfüllt.</span><span class="sxs-lookup"><span data-stu-id="73120-126">This information can help identify an assembly that will satisfy the dependency.</span></span>  
  
 <span data-ttu-id="73120-127">Der Ereignishandler kann eine Version der Assembly zurückgeben, die sich von der angeforderten Version unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="73120-127">The event handler can return a different version of the assembly than the version that was requested.</span></span>  
  
 <span data-ttu-id="73120-128">In den meisten Fällen befindet sich die vom Handler zurückgegebene Assembly in einem load-Kontext, unabhängig vom Kontext, in der der Handler sie lädt.</span><span class="sxs-lookup"><span data-stu-id="73120-128">In most cases, the assembly that is returned by the handler appears in the load context, regardless of the context the handler loads it into.</span></span> <span data-ttu-id="73120-129">Wenn der Handler z.B. die <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>-Methode verwendet, um eine Assembly in einen load-from-Kontext zu laden, befindet sich die Assembly im load-Kontext, wenn der Handler sie zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="73120-129">For example, if the handler uses the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method to load an assembly into the load-from context, the assembly appears in the load context when the handler returns it.</span></span> <span data-ttu-id="73120-130">Im folgenden Kontext befindet sich die Assembly jedoch in keinem Kontext, wenn sie vom Handler zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="73120-130">However, in the following case the assembly appears without context when the handler returns it:</span></span>  
  
- <span data-ttu-id="73120-131">Der Handler lädt eine Assembly ohne Kontext.</span><span class="sxs-lookup"><span data-stu-id="73120-131">The handler loads an assembly without context.</span></span>  
  
- <span data-ttu-id="73120-132">Die <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType>-Eigenschaft ist nicht NULL.</span><span class="sxs-lookup"><span data-stu-id="73120-132">The <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> property is not null.</span></span>  
  
- <span data-ttu-id="73120-133">Die angeforderte Assembly, also die Assembly, die von der <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType>-Eigenschaft zurückgegeben wird, wurde ohne Kontext geladen.</span><span class="sxs-lookup"><span data-stu-id="73120-133">The requesting assembly (that is, the assembly that is returned by the <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> property) was loaded without context.</span></span>  
  
 <span data-ttu-id="73120-134">Weitere Informationen zu Kontexten finden Sie in der Methodenüberladung <xref:System.Reflection.Assembly.LoadFrom%28System.String%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="73120-134">For information about contexts, see the <xref:System.Reflection.Assembly.LoadFrom%28System.String%29?displayProperty=nameWithType> method overload.</span></span>  
  
 <span data-ttu-id="73120-135">Mehrere Versionen derselben Assembly können in die gleiche Anwendungsdomäne geladen werden.</span><span class="sxs-lookup"><span data-stu-id="73120-135">Multiple versions of the same assembly can be loaded into the same application domain.</span></span> <span data-ttu-id="73120-136">Diese Vorgehensweise wird jedoch nicht empfohlen, da sie zu Problemen bei der Typzuweisung führen kann.</span><span class="sxs-lookup"><span data-stu-id="73120-136">This practice is not recommended, because it can lead to type assignment problems.</span></span> <span data-ttu-id="73120-137">Weitere Informationen finden Sie unter [Best Practices für das Laden von Assemblys](../../framework/deployment/best-practices-for-assembly-loading.md).</span><span class="sxs-lookup"><span data-stu-id="73120-137">See [Best practices for assembly loading](../../framework/deployment/best-practices-for-assembly-loading.md).</span></span>  
  
### <a name="what-the-event-handler-should-not-do"></a><span data-ttu-id="73120-138">Welche Aktionen der Ereignishandler nicht ausführen sollte</span><span class="sxs-lookup"><span data-stu-id="73120-138">What the event handler should not do</span></span>  
<span data-ttu-id="73120-139">Die erste Regeln beim Behandeln des Ereignis <xref:System.AppDomain.AssemblyResolve> ist, dass Sie nie versuchen sollten, eine Assembly zurückzugeben, die Sie nicht erkennen.</span><span class="sxs-lookup"><span data-stu-id="73120-139">The primary rule for handling the <xref:System.AppDomain.AssemblyResolve> event is that you should not try to return an assembly you do not recognize.</span></span> <span data-ttu-id="73120-140">Wenn Sie den Handler schreiben, sollten Sie wissen, welche Assemblys das Ereignis auslösen können.</span><span class="sxs-lookup"><span data-stu-id="73120-140">When you write the handler, you should know which assemblies might cause the event to be raised.</span></span> <span data-ttu-id="73120-141">Ihr Handler sollte für andere Assemblys NULL zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="73120-141">Your handler should return null for other assemblies.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="73120-142">Ab .NET Framework 4 wird das Ereignis <xref:System.AppDomain.AssemblyResolve> für Satellitenassemblys ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="73120-142">Beginning with the .NET Framework 4, the <xref:System.AppDomain.AssemblyResolve> event is raised for satellite assemblies.</span></span> <span data-ttu-id="73120-143">Diese Änderung betrifft Ereignishandler, die für eine frühere Version von .NET Framework geschrieben wurden, wenn diese versuchen, alle Ladeanforderungen von Assemblys aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="73120-143">This change affects an event handler that was written for an earlier version of the .NET Framework, if the handler tries to resolve all assembly load requests.</span></span> <span data-ttu-id="73120-144">Ereignishandler, die nicht erkannte Assemblys ignorieren, sind von dieser Änderung nicht betroffen: Sie geben NULL zurück. Danach wird auf die üblichen Fallbackmechanismen zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="73120-144">Event handlers that ignore assemblies they do not recognize are not affected by this change: They return null, and normal fallback mechanisms are followed.</span></span>  

<span data-ttu-id="73120-145">Beim Laden einer Assembly darf der Ereignishandler nicht die Methodenüberladungen <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> oder <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> verwendet, die dazu führen können, dass das Ereignis <xref:System.AppDomain.AssemblyResolve> rekursiv ausgelöst wird, da dies zu einem Stapelüberlauf führen kann.</span><span class="sxs-lookup"><span data-stu-id="73120-145">When loading an assembly, the event handler must not use any of the <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method overloads that can cause the <xref:System.AppDomain.AssemblyResolve> event to be raised recursively, because this can lead to a stack overflow.</span></span> <span data-ttu-id="73120-146">(Weitere Informationen finden Sie in der weiter oben in diesem Thema angegebenen Liste.) Dies geschieht auch, wenn Sie eine Ausnahmebehandlung für die Ladeanforderung bereitstellen, da keine Ausnahme ausgelöst wird, bis alle Ereignishandler etwas zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="73120-146">(See the list provided earlier in this topic.) This happens even if you provide exception handling for the load request, because no exception is thrown until all event handlers have returned.</span></span> <span data-ttu-id="73120-147">Deshalb führt der folgende Code zu einem Stapelüberlauf, wenn `MyAssembly` nicht gefunden werden kann:</span><span class="sxs-lookup"><span data-stu-id="73120-147">Thus, the following code results in a stack overflow if `MyAssembly` is not found:</span></span>  

```cpp
using namespace System;
using namespace System::Reflection;

ref class Example
{
internal:
    static Assembly^ MyHandler(Object^ source, ResolveEventArgs^ e) 
    {
        Console::WriteLine("Resolving {0}", e->Name);
        return Assembly::Load(e->Name);
    }
};

void main()
{
    AppDomain^ ad = AppDomain::CreateDomain("Test");
    ad->AssemblyResolve += gcnew ResolveEventHandler(&Example::MyHandler);

    try
    {
        Object^ obj = ad->CreateInstanceAndUnwrap(
            "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
            "MyType");
    } 
    catch (Exception^ ex)
    {
        Console::WriteLine(ex->Message);
    }
}

/* This example produces output similar to the following:

Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
...
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null

Process is terminated due to StackOverflowException.
 */
```

```csharp
using System;
using System.Reflection;

class BadExample
{
    static void Main()
    {
        AppDomain ad = AppDomain.CreateDomain("Test");
        ad.AssemblyResolve += MyHandler;

        try
        {
            object obj = ad.CreateInstanceAndUnwrap(
                "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
                "MyType");
        } 
        catch (Exception ex)
        {
            Console.WriteLine(ex.Message);
        }
    }

    static Assembly MyHandler(object source, ResolveEventArgs e) 
    {
        Console.WriteLine("Resolving {0}", e.Name);
        return Assembly.Load(e.Name);
    }
} 

/* This example produces output similar to the following:

Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
...
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null

Process is terminated due to StackOverflowException.
 */
```

```vb
Imports System
Imports System.Reflection

Class BadExample

    Shared Sub Main()
    
        Dim ad As AppDomain = AppDomain.CreateDomain("Test")
        AddHandler ad.AssemblyResolve, AddressOf MyHandler

        Try
            Dim obj As object = ad.CreateInstanceAndUnwrap(
                "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
                "MyType")
        Catch ex As Exception
            Console.WriteLine(ex.Message)
        End Try
    End Sub

    Shared Function MyHandler(ByVal source As Object, _
                              ByVal e As ResolveEventArgs) As Assembly
        Console.WriteLine("Resolving {0}", e.Name)
        Return Assembly.Load(e.Name)
    End Function
End Class

' This example produces output similar to the following:
'
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'...
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'
'Process is terminated due to StackOverflowException.
```

## <a name="see-also"></a><span data-ttu-id="73120-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73120-148">See also</span></span>

- [<span data-ttu-id="73120-149">Best Practices für das Laden von Assemblys</span><span class="sxs-lookup"><span data-stu-id="73120-149">Best practices for assembly loading</span></span>](../../framework/deployment/best-practices-for-assembly-loading.md)
- [<span data-ttu-id="73120-150">Verwenden von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="73120-150">Use application domains</span></span>](../../framework/app-domains/use.md)
