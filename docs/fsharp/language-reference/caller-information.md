---
title: Aufruferinformationen (f#)
description: Beschreibt die Attribute "Callerinfo"-Argument zu verwenden, um von einer Methode memberaufruferinformationen zu erhalten.
ms.date: 04/25/2017
ms.openlocfilehash: 0f2f4b16804d9156d234cc29d1f72ebe80a5b556
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "44353446"
---
# <a name="caller-information"></a><span data-ttu-id="90429-103">Aufruferinformationen</span><span class="sxs-lookup"><span data-stu-id="90429-103">Caller information</span></span>

<span data-ttu-id="90429-104">Mithilfe der Aufrufer-Informationsattribute können Sie Informationen zum Aufrufer einer Methode abrufen.</span><span class="sxs-lookup"><span data-stu-id="90429-104">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="90429-105">Sie können den Dateipfad des Quellcodes, die Zeilennummer im Quellcode und den Membernamen des Aufrufers abrufen.</span><span class="sxs-lookup"><span data-stu-id="90429-105">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="90429-106">Diese Informationen sind zum Verfolgen, Debuggen und Erstellen von Diagnosetools sehr nützlich.</span><span class="sxs-lookup"><span data-stu-id="90429-106">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>

<span data-ttu-id="90429-107">Um diese Informationen zu erhalten, verwenden Sie die Attribute, die auf optionale Parameter angewendet werden, von denen jeder einen Standardwert besitzt.</span><span class="sxs-lookup"><span data-stu-id="90429-107">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="90429-108">Die folgende Tabelle enthält die Aufrufer-Informationsattribute, die definiert sind die ["System.Runtime.CompilerServices"](/dotnet/api/system.runtime.compilerservices) Namespace:</span><span class="sxs-lookup"><span data-stu-id="90429-108">The following table lists the Caller Info attributes that are defined in the [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) namespace:</span></span>

|<span data-ttu-id="90429-109">Attribut</span><span class="sxs-lookup"><span data-stu-id="90429-109">Attribute</span></span>|<span data-ttu-id="90429-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90429-110">Description</span></span>|<span data-ttu-id="90429-111">Typ</span><span class="sxs-lookup"><span data-stu-id="90429-111">Type</span></span>|
|---------|-----------|----|
|[<span data-ttu-id="90429-112">CallerFilePath</span><span class="sxs-lookup"><span data-stu-id="90429-112">CallerFilePath</span></span>](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|<span data-ttu-id="90429-113">Vollständiger Pfad der Quelldatei, die den Aufrufer enthält.</span><span class="sxs-lookup"><span data-stu-id="90429-113">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="90429-114">Dies ist der Dateipfad zum Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="90429-114">This is the file path at compile time.</span></span>|`String`
|[<span data-ttu-id="90429-115">CallerLineNumber</span><span class="sxs-lookup"><span data-stu-id="90429-115">CallerLineNumber</span></span>](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|<span data-ttu-id="90429-116">Zeilennummer in der Quelldatei, in der die Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="90429-116">Line number in the source file at which the method is called.</span></span>|`Integer`|
|[<span data-ttu-id="90429-117">"Callermembername"</span><span class="sxs-lookup"><span data-stu-id="90429-117">CallerMemberName</span></span>](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|<span data-ttu-id="90429-118">Der Methoden- oder Eigenschaftenname des Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="90429-118">Method or property name of the caller.</span></span> <span data-ttu-id="90429-119">Finden Sie im Abschnitt "Elementnamen" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="90429-119">See the Member Names section later in this topic.</span></span>|`String`|

## <a name="example"></a><span data-ttu-id="90429-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90429-120">Example</span></span>

<span data-ttu-id="90429-121">Das folgende Beispiel zeigt, wie Sie diese Attribute verwenden können, um einen Aufrufer zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="90429-121">The following example shows how you might use these attributes to trace a caller.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="90429-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90429-122">Remarks</span></span>

<span data-ttu-id="90429-123">Attribute "callerinfo" können nur auf optionale Parameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="90429-123">Caller Info attributes can only be applied to optional parameters.</span></span> <span data-ttu-id="90429-124">Sie müssen einen expliziten Wert für jeden optionalen Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="90429-124">You must supply an explicit value for each optional parameter.</span></span> <span data-ttu-id="90429-125">Der Aufrufer-Informationsattribute dazu führen, dass den Compiler den richtigen Wert für jeden optionalen Parameter, die mit einem Aufrufer-Informationsattribute-Attribut versehen zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="90429-125">The Caller Info attributes cause the compiler to write the proper value for each optional parameter decorated with a Caller Info attribute.</span></span>

<span data-ttu-id="90429-126">Aufrufer-Informationswerte werden zur Kompilierzeit als Literale in Intermediate Language (IL) ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="90429-126">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="90429-127">Im Gegensatz zu die Ergebnisse der [StackTrace](/dotnet/api/system.diagnostics.stacktrace) -Eigenschaft für Ausnahmen, die Ergebnisse nicht durch verbergen beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="90429-127">Unlike the results of the [StackTrace](/dotnet/api/system.diagnostics.stacktrace) property for exceptions, the results aren't affected by obfuscation.</span></span>

<span data-ttu-id="90429-128">Sie können die optionalen Argumente explizit angeben, um die Aufruferinformationen zu steuern oder auszublenden.</span><span class="sxs-lookup"><span data-stu-id="90429-128">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

## <a name="member-names"></a><span data-ttu-id="90429-129">Elementnamen</span><span class="sxs-lookup"><span data-stu-id="90429-129">Member names</span></span>

<span data-ttu-id="90429-130">Können Sie die [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) Attribut, um zu vermeiden, den Namen des Members als Angabe einer `String` Argument an die aufgerufene Methode.</span><span class="sxs-lookup"><span data-stu-id="90429-130">You can use the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="90429-131">Mit diesem Verfahren, umgehen Sie das Problem, die Umgestaltung mit Umbenennung ändern nicht die `String` Werte.</span><span class="sxs-lookup"><span data-stu-id="90429-131">By using this technique, you avoid the problem that Rename Refactoring doesn't change the `String` values.</span></span> <span data-ttu-id="90429-132">Dieser Vorteil ist für die folgenden Aufgaben besonders hilfreich:</span><span class="sxs-lookup"><span data-stu-id="90429-132">This benefit is especially useful for the following tasks:</span></span>

* <span data-ttu-id="90429-133">Verwenden der Ablaufverfolgung und der Diagnoseprogramme</span><span class="sxs-lookup"><span data-stu-id="90429-133">Using tracing and diagnostic routines.</span></span>
* <span data-ttu-id="90429-134">Implementieren der ["INotifyPropertyChanged"](/dotnet/api/system.componentmodel.inotifypropertychanged) -Schnittstelle beim Binden von Daten.</span><span class="sxs-lookup"><span data-stu-id="90429-134">Implementing the [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interface when binding data.</span></span> <span data-ttu-id="90429-135">Diese Schnittstelle ermöglicht es der Eigenschaft eines Objekts, ein gebundenes Steuerelement über die Änderung der Eigenschaft zu benachrichtigen, damit das Steuerelement die aktualisierten Informationen anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="90429-135">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="90429-136">Ohne die [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) -Attribut, müssen Sie den Eigenschaftennamen als Literal angeben.</span><span class="sxs-lookup"><span data-stu-id="90429-136">Without the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="90429-137">Im folgende Diagramm sind die Membernamen aufgeführt, die zurückgegeben werden, wenn Sie das CallerMemberName-Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="90429-137">The following chart shows the member names that are returned when you use the CallerMemberName attribute.</span></span>

|<span data-ttu-id="90429-138">Aufrufe erfolgen in</span><span class="sxs-lookup"><span data-stu-id="90429-138">Calls occurs within</span></span>|<span data-ttu-id="90429-139">Ergebnis des Membernamens</span><span class="sxs-lookup"><span data-stu-id="90429-139">Member name result</span></span>|
|-------------------|------------------|
|<span data-ttu-id="90429-140">Methode, Eigenschaft oder Ereignis</span><span class="sxs-lookup"><span data-stu-id="90429-140">Method, property, or event</span></span>|<span data-ttu-id="90429-141">Der Name der Methode, der Eigenschaft oder des Ereignisses, aus dem bzw. aus der der Aufruf stammt.</span><span class="sxs-lookup"><span data-stu-id="90429-141">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="90429-142">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="90429-142">Constructor</span></span>|<span data-ttu-id="90429-143">Die Zeichenfolge ".ctor"</span><span class="sxs-lookup"><span data-stu-id="90429-143">The string ".ctor"</span></span>|
|<span data-ttu-id="90429-144">Statischer Konstruktor</span><span class="sxs-lookup"><span data-stu-id="90429-144">Static constructor</span></span>|<span data-ttu-id="90429-145">Die Zeichenfolge ".cctor"</span><span class="sxs-lookup"><span data-stu-id="90429-145">The string ".cctor"</span></span>|
|<span data-ttu-id="90429-146">Destruktor</span><span class="sxs-lookup"><span data-stu-id="90429-146">Destructor</span></span>|<span data-ttu-id="90429-147">Die Zeichenfolge "Finalize"</span><span class="sxs-lookup"><span data-stu-id="90429-147">The string "Finalize"</span></span>|
|<span data-ttu-id="90429-148">Benutzerdefinierte Operatoren oder Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="90429-148">User-defined operators or conversions</span></span>|<span data-ttu-id="90429-149">Der generierte Name für den Member, beispielsweise "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="90429-149">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="90429-150">Attributkonstruktor</span><span class="sxs-lookup"><span data-stu-id="90429-150">Attribute constructor</span></span>|<span data-ttu-id="90429-151">Der Name des Members, auf den das Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="90429-151">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="90429-152">Wenn das Attribut ein beliebiges Element in einem Member ist (z. B. ein Parameter, ein Rückgabewert oder ein generischer Typparameter), wird als Ergebnis der Name des Members ausgegeben, der diesem Element zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="90429-152">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="90429-153">Kein enthaltender Member (z. B. auf Assemblyebene oder Attribute, die auf Typen angewendet werden)</span><span class="sxs-lookup"><span data-stu-id="90429-153">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="90429-154">Der Standardwert des optionalen Parameters.</span><span class="sxs-lookup"><span data-stu-id="90429-154">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="90429-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90429-155">See also</span></span>

- [<span data-ttu-id="90429-156">Attribute</span><span class="sxs-lookup"><span data-stu-id="90429-156">Attributes</span></span>](attributes.md)  
- [<span data-ttu-id="90429-157">Benannte Argumente</span><span class="sxs-lookup"><span data-stu-id="90429-157">Named arguments</span></span>](parameters-and-arguments.md#named-arguments)  
- [<span data-ttu-id="90429-158">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="90429-158">Optional parameters</span></span>](parameters-and-arguments.md#optional-parameters)  
