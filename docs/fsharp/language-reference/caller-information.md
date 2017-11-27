---
title: Aufruferinformationen (f#)
description: Beschreibt, wie, Aufrufer-Informationsattribute Argument Aufruferinformationen von einer Methode abzurufen.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 04/25/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a3dcc335-433b-4672-ac2d-ae6b11b816f3
ms.openlocfilehash: 533d2f0429ddb31e6d1dd7efca2f0760069a2945
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="caller-information"></a><span data-ttu-id="a8fdb-104">Aufruferinformationen</span><span class="sxs-lookup"><span data-stu-id="a8fdb-104">Caller information</span></span>

<span data-ttu-id="a8fdb-105">Mithilfe der Aufrufer-Informationsattribute können Sie Informationen zum Aufrufer einer Methode abrufen.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-105">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="a8fdb-106">Sie können den Dateipfad des Quellcodes, die Zeilennummer im Quellcode und den Membernamen des Aufrufers abrufen.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-106">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="a8fdb-107">Diese Informationen sind zum Verfolgen, Debuggen und Erstellen von Diagnosetools sehr nützlich.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-107">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>

<span data-ttu-id="a8fdb-108">Um diese Informationen zu erhalten, verwenden Sie die Attribute, die auf optionale Parameter angewendet werden, von denen jeder einen Standardwert besitzt.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-108">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="a8fdb-109">Die folgende Tabelle enthält die Aufrufer-Informationsattribute angegeben, die in definiert werden die [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) Namespace:</span><span class="sxs-lookup"><span data-stu-id="a8fdb-109">The following table lists the Caller Info attributes that are defined in the [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) namespace:</span></span>

|<span data-ttu-id="a8fdb-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="a8fdb-110">Attribute</span></span>|<span data-ttu-id="a8fdb-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8fdb-111">Description</span></span>|<span data-ttu-id="a8fdb-112">Typ</span><span class="sxs-lookup"><span data-stu-id="a8fdb-112">Type</span></span>|
|---------|-----------|----|
|[<span data-ttu-id="a8fdb-113">CallerFilePath</span><span class="sxs-lookup"><span data-stu-id="a8fdb-113">CallerFilePath</span></span>](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|<span data-ttu-id="a8fdb-114">Vollständiger Pfad der Quelldatei, die den Aufrufer enthält.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-114">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="a8fdb-115">Dies ist der Dateipfad zum Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-115">This is the file path at compile time.</span></span>|`String`
|[<span data-ttu-id="a8fdb-116">CallerLineNumber</span><span class="sxs-lookup"><span data-stu-id="a8fdb-116">CallerLineNumber</span></span>](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|<span data-ttu-id="a8fdb-117">Zeilennummer in der Quelldatei, in der die Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-117">Line number in the source file at which the method is called.</span></span>|`Integer`|
|[<span data-ttu-id="a8fdb-118">CallerMemberName</span><span class="sxs-lookup"><span data-stu-id="a8fdb-118">CallerMemberName</span></span>](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|<span data-ttu-id="a8fdb-119">Der Methoden- oder Eigenschaftenname des Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-119">Method or property name of the caller.</span></span> <span data-ttu-id="a8fdb-120">Finden Sie im Abschnitt "Elementnamen" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-120">See the Member Names section later in this topic.</span></span>|`String`|

## <a name="example"></a><span data-ttu-id="a8fdb-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a8fdb-121">Example</span></span>

<span data-ttu-id="a8fdb-122">Das folgende Beispiel zeigt, wie Sie diese Attribute verwenden können, um einen Aufrufer zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-122">The following example shows how you might use these attributes to trace a caller.</span></span>

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices

type Tracer() =
    member __.DoTrace(msg: string,
                      [<CallerMemberName>] ?memberName: string,
                      [<CallerFilePath>] ?path: string
                      [<CallerLineNumber>] ?line: int) =
        Trace.WriteLine(sprintf "Message: %s" message)
        match (memberName, path, line) with
        | Some m, Some p, Some l ->
            Trace.WriteLine(sprintf "Member name: %s" m)
            Trace.WriteLine(sprintf "Source file path: %s" p)
            Trace.WriteLine(sprintf "Source line number: %d" l)
        | _,_,_ -> ()
```

## <a name="remarks"></a><span data-ttu-id="a8fdb-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a8fdb-123">Remarks</span></span>

<span data-ttu-id="a8fdb-124">Aufrufer-Informationsattribute können nur auf optionale Parameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-124">Caller Info attributes can only be applied to optional parameters.</span></span> <span data-ttu-id="a8fdb-125">Sie müssen einen expliziten Wert für jeden optionalen Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-125">You must supply an explicit value for each optional parameter.</span></span> <span data-ttu-id="a8fdb-126">Der Aufrufer-Informationsattribute dazu führen, dass den Compiler den korrekten Wert für jeden optionalen Parameter mit einem Aufrufer-Informationsattribute-Attribut ergänzt schreiben.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-126">The Caller Info attributes cause the compiler to write the proper value for each optional parameter decorated with a Caller Info attribute.</span></span>

<span data-ttu-id="a8fdb-127">Aufrufer-Informationswerte werden zur Kompilierzeit als Literale in Intermediate Language (IL) ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-127">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="a8fdb-128">Im Gegensatz zu den Ergebnissen von der [StackTrace](/dotnet/api/system.diagnostics.stacktrace) -Eigenschaft für Ausnahmen werden die Ergebnisse nicht durch verbergen beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-128">Unlike the results of the [StackTrace](/dotnet/api/system.diagnostics.stacktrace) property for exceptions, the results aren't affected by obfuscation.</span></span>

<span data-ttu-id="a8fdb-129">Sie können die optionalen Argumente explizit angeben, um die Aufruferinformationen zu steuern oder auszublenden.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-129">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

## <a name="member-names"></a><span data-ttu-id="a8fdb-130">Elementnamen</span><span class="sxs-lookup"><span data-stu-id="a8fdb-130">Member names</span></span>

<span data-ttu-id="a8fdb-131">Sie können die [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) Attribut, um den Membernamen nicht als angeben zu müssen eine `String` Argument an die aufgerufene Methode.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-131">You can use the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="a8fdb-132">Mit dieser Technik, umgehen Sie das Problem, die Umgestaltung mit Umbenennung ändern nicht den `String` Werte.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-132">By using this technique, you avoid the problem that Rename Refactoring doesn't change the `String` values.</span></span> <span data-ttu-id="a8fdb-133">Dieser Vorteil ist für die folgenden Aufgaben besonders hilfreich:</span><span class="sxs-lookup"><span data-stu-id="a8fdb-133">This benefit is especially useful for the following tasks:</span></span>

* <span data-ttu-id="a8fdb-134">Verwenden der Ablaufverfolgung und der Diagnoseprogramme</span><span class="sxs-lookup"><span data-stu-id="a8fdb-134">Using tracing and diagnostic routines.</span></span>
* <span data-ttu-id="a8fdb-135">Implementieren der [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) -Schnittstelle beim Binden von Daten.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-135">Implementing the [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interface when binding data.</span></span> <span data-ttu-id="a8fdb-136">Diese Schnittstelle ermöglicht es der Eigenschaft eines Objekts, ein gebundenes Steuerelement über die Änderung der Eigenschaft zu benachrichtigen, damit das Steuerelement die aktualisierten Informationen anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-136">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="a8fdb-137">Ohne die [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) -Attribut, müssen Sie den Eigenschaftennamen als Literal angeben.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-137">Without the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="a8fdb-138">Im folgende Diagramm sind die Membernamen aufgeführt, die zurückgegeben werden, wenn Sie das CallerMemberName-Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-138">The following chart shows the member names that are returned when you use the CallerMemberName attribute.</span></span>

|<span data-ttu-id="a8fdb-139">Aufrufe erfolgen in</span><span class="sxs-lookup"><span data-stu-id="a8fdb-139">Calls occurs within</span></span>|<span data-ttu-id="a8fdb-140">Ergebnis des Membernamens</span><span class="sxs-lookup"><span data-stu-id="a8fdb-140">Member name result</span></span>|
|-------------------|------------------|
|<span data-ttu-id="a8fdb-141">Methode, Eigenschaft oder Ereignis</span><span class="sxs-lookup"><span data-stu-id="a8fdb-141">Method, property, or event</span></span>|<span data-ttu-id="a8fdb-142">Der Name der Methode, der Eigenschaft oder des Ereignisses, aus dem bzw. aus der der Aufruf stammt.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-142">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="a8fdb-143">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="a8fdb-143">Constructor</span></span>|<span data-ttu-id="a8fdb-144">Die Zeichenfolge ".ctor"</span><span class="sxs-lookup"><span data-stu-id="a8fdb-144">The string ".ctor"</span></span>|
|<span data-ttu-id="a8fdb-145">Statischer Konstruktor</span><span class="sxs-lookup"><span data-stu-id="a8fdb-145">Static constructor</span></span>|<span data-ttu-id="a8fdb-146">Die Zeichenfolge ".cctor"</span><span class="sxs-lookup"><span data-stu-id="a8fdb-146">The string ".cctor"</span></span>|
|<span data-ttu-id="a8fdb-147">Destruktor</span><span class="sxs-lookup"><span data-stu-id="a8fdb-147">Destructor</span></span>|<span data-ttu-id="a8fdb-148">Die Zeichenfolge "Finalize"</span><span class="sxs-lookup"><span data-stu-id="a8fdb-148">The string "Finalize"</span></span>|
|<span data-ttu-id="a8fdb-149">Benutzerdefinierte Operatoren oder Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="a8fdb-149">User-defined operators or conversions</span></span>|<span data-ttu-id="a8fdb-150">Der generierte Name für den Member, beispielsweise "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="a8fdb-150">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="a8fdb-151">Attributkonstruktor</span><span class="sxs-lookup"><span data-stu-id="a8fdb-151">Attribute constructor</span></span>|<span data-ttu-id="a8fdb-152">Der Name des Members, auf den das Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-152">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="a8fdb-153">Wenn das Attribut ein beliebiges Element in einem Member ist (z. B. ein Parameter, ein Rückgabewert oder ein generischer Typparameter), wird als Ergebnis der Name des Members ausgegeben, der diesem Element zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-153">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="a8fdb-154">Kein enthaltender Member (z. B. auf Assemblyebene oder Attribute, die auf Typen angewendet werden)</span><span class="sxs-lookup"><span data-stu-id="a8fdb-154">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="a8fdb-155">Der Standardwert des optionalen Parameters.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-155">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="a8fdb-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8fdb-156">See also</span></span>
 [<span data-ttu-id="a8fdb-157">Attribute</span><span class="sxs-lookup"><span data-stu-id="a8fdb-157">Attributes</span></span>](attributes.md)  
 [<span data-ttu-id="a8fdb-158">Benannte Argumente</span><span class="sxs-lookup"><span data-stu-id="a8fdb-158">Named arguments</span></span>](parameters-and-arguments.md#named-arguments)  
 [<span data-ttu-id="a8fdb-159">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="a8fdb-159">Optional parameters</span></span>](parameters-and-arguments.md#optional-parameters)  
