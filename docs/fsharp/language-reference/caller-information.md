---
title: Aufruferinformationen
description: Beschreibt, wie aufruferinfo-Argument Attribute verwendet werden, um Aufruferinformationen von einer Methode abzurufen.
ms.date: 11/04/2019
ms.openlocfilehash: d995b37149277b7c7d1b6217ee484d3c90a7f8b3
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976795"
---
# <a name="caller-information"></a><span data-ttu-id="eae74-103">Aufruferinformationen</span><span class="sxs-lookup"><span data-stu-id="eae74-103">Caller information</span></span>

<span data-ttu-id="eae74-104">Mithilfe der Aufrufer-Informationsattribute können Sie Informationen zum Aufrufer einer Methode abrufen.</span><span class="sxs-lookup"><span data-stu-id="eae74-104">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="eae74-105">Sie können den Dateipfad des Quellcodes, die Zeilennummer im Quellcode und den Membernamen des Aufrufers abrufen.</span><span class="sxs-lookup"><span data-stu-id="eae74-105">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="eae74-106">Diese Informationen sind zum Verfolgen, Debuggen und Erstellen von Diagnosetools sehr nützlich.</span><span class="sxs-lookup"><span data-stu-id="eae74-106">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>

<span data-ttu-id="eae74-107">Um diese Informationen zu erhalten, verwenden Sie die Attribute, die auf optionale Parameter angewendet werden, von denen jeder einen Standardwert besitzt.</span><span class="sxs-lookup"><span data-stu-id="eae74-107">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="eae74-108">In der folgenden Tabelle sind die Aufrufer-Informations Attribute aufgelistet, die im [System. Runtime. CompilerServices](/dotnet/api/system.runtime.compilerservices) -Namespace definiert sind:</span><span class="sxs-lookup"><span data-stu-id="eae74-108">The following table lists the Caller Info attributes that are defined in the [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) namespace:</span></span>

|<span data-ttu-id="eae74-109">Attribut</span><span class="sxs-lookup"><span data-stu-id="eae74-109">Attribute</span></span>|<span data-ttu-id="eae74-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eae74-110">Description</span></span>|<span data-ttu-id="eae74-111">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="eae74-111">Type</span></span>|
|---------|-----------|----|
|[<span data-ttu-id="eae74-112">Callerfilepath</span><span class="sxs-lookup"><span data-stu-id="eae74-112">CallerFilePath</span></span>](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|<span data-ttu-id="eae74-113">Vollständiger Pfad der Quelldatei, die den Aufrufer enthält.</span><span class="sxs-lookup"><span data-stu-id="eae74-113">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="eae74-114">Dies ist der Dateipfad zum Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="eae74-114">This is the file path at compile time.</span></span>|`String`
|[<span data-ttu-id="eae74-115">Callerlinenumber</span><span class="sxs-lookup"><span data-stu-id="eae74-115">CallerLineNumber</span></span>](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|<span data-ttu-id="eae74-116">Zeilennummer in der Quelldatei, in der die Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="eae74-116">Line number in the source file at which the method is called.</span></span>|`Integer`|
|[<span data-ttu-id="eae74-117">CallerMemberName</span><span class="sxs-lookup"><span data-stu-id="eae74-117">CallerMemberName</span></span>](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|<span data-ttu-id="eae74-118">Der Methoden- oder Eigenschaftenname des Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="eae74-118">Method or property name of the caller.</span></span> <span data-ttu-id="eae74-119">Weitere Informationen finden Sie im Abschnitt Elementnamen weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="eae74-119">See the Member Names section later in this topic.</span></span>|`String`|

## <a name="example"></a><span data-ttu-id="eae74-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eae74-120">Example</span></span>

<span data-ttu-id="eae74-121">Im folgenden Beispiel wird gezeigt, wie Sie diese Attribute zum Verfolgen eines Aufrufers verwenden können.</span><span class="sxs-lookup"><span data-stu-id="eae74-121">The following example shows how you might use these attributes to trace a caller.</span></span>

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices
open System.Runtime.InteropServices

type Tracer() =
    member _.DoTrace(message: string,
                      [<CallerMemberName; Optional; DefaultParameterValue("")>] memberName: string,
                      [<CallerFilePath; Optional; DefaultParameterValue("")>] path: string,
                      [<CallerLineNumber; Optional; DefaultParameterValue(0)>] line: int) =
        Trace.WriteLine(sprintf "Message: %s" message)
        Trace.WriteLine(sprintf "Member name: %s" memberName)
        Trace.WriteLine(sprintf "Source file path: %s" path)
        Trace.WriteLine(sprintf "Source line number: %d" line)
```

## <a name="remarks"></a><span data-ttu-id="eae74-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eae74-122">Remarks</span></span>

<span data-ttu-id="eae74-123">Aufrufer-Informations Attribute können nur auf optionale Parameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="eae74-123">Caller Info attributes can only be applied to optional parameters.</span></span> <span data-ttu-id="eae74-124">Die Attribute für Aufruferinformationen bewirken, dass der Compiler den richtigen Wert für jeden optionalen Parameter schreibt, der mit einem aufruferinformationsattribut versehen ist</span><span class="sxs-lookup"><span data-stu-id="eae74-124">The Caller Info attributes cause the compiler to write the proper value for each optional parameter decorated with a Caller Info attribute.</span></span>

<span data-ttu-id="eae74-125">Aufrufer-Informationswerte werden zur Kompilierzeit als Literale in Intermediate Language (IL) ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="eae74-125">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="eae74-126">Im Gegensatz zu den Ergebnissen der [StackTrace](/dotnet/api/system.diagnostics.stacktrace) -Eigenschaft für Ausnahmen sind die Ergebnisse nicht von der Verschleierung betroffen.</span><span class="sxs-lookup"><span data-stu-id="eae74-126">Unlike the results of the [StackTrace](/dotnet/api/system.diagnostics.stacktrace) property for exceptions, the results aren't affected by obfuscation.</span></span>

<span data-ttu-id="eae74-127">Sie können die optionalen Argumente explizit angeben, um die Aufruferinformationen zu steuern oder auszublenden.</span><span class="sxs-lookup"><span data-stu-id="eae74-127">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

## <a name="member-names"></a><span data-ttu-id="eae74-128">Membernamen</span><span class="sxs-lookup"><span data-stu-id="eae74-128">Member names</span></span>

<span data-ttu-id="eae74-129">Sie können das [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) -Attribut verwenden, um zu vermeiden, dass der Elementname als `String` Argument der aufgerufenen Methode angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="eae74-129">You can use the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="eae74-130">Wenn Sie dieses Verfahren verwenden, vermeiden Sie das Problem, dass die `String` Werte durch das Umbenennen von Refactoring nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="eae74-130">By using this technique, you avoid the problem that Rename Refactoring doesn't change the `String` values.</span></span> <span data-ttu-id="eae74-131">Dieser Vorteil ist für die folgenden Aufgaben besonders hilfreich:</span><span class="sxs-lookup"><span data-stu-id="eae74-131">This benefit is especially useful for the following tasks:</span></span>

- <span data-ttu-id="eae74-132">Verwenden der Ablaufverfolgung und der Diagnoseprogramme</span><span class="sxs-lookup"><span data-stu-id="eae74-132">Using tracing and diagnostic routines.</span></span>
- <span data-ttu-id="eae74-133">Implementieren der [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) -Schnittstelle beim Binden von Daten.</span><span class="sxs-lookup"><span data-stu-id="eae74-133">Implementing the [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interface when binding data.</span></span> <span data-ttu-id="eae74-134">Diese Schnittstelle ermöglicht es der Eigenschaft eines Objekts, ein gebundenes Steuerelement über die Änderung der Eigenschaft zu benachrichtigen, damit das Steuerelement die aktualisierten Informationen anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="eae74-134">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="eae74-135">Ohne das [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) -Attribut müssen Sie den Eigenschaftsnamen als Literalwert angeben.</span><span class="sxs-lookup"><span data-stu-id="eae74-135">Without the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="eae74-136">Das folgende Diagramm zeigt die Elementnamen, die zurückgegeben werden, wenn Sie das callermembership Name-Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="eae74-136">The following chart shows the member names that are returned when you use the CallerMemberName attribute.</span></span>

|<span data-ttu-id="eae74-137">Aufrufe erfolgen in</span><span class="sxs-lookup"><span data-stu-id="eae74-137">Calls occurs within</span></span>|<span data-ttu-id="eae74-138">Ergebnis des Membernamens</span><span class="sxs-lookup"><span data-stu-id="eae74-138">Member name result</span></span>|
|-------------------|------------------|
|<span data-ttu-id="eae74-139">Methode, Eigenschaft oder Ereignis</span><span class="sxs-lookup"><span data-stu-id="eae74-139">Method, property, or event</span></span>|<span data-ttu-id="eae74-140">Der Name der Methode, der Eigenschaft oder des Ereignisses, aus dem bzw. aus der der Aufruf stammt.</span><span class="sxs-lookup"><span data-stu-id="eae74-140">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="eae74-141">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="eae74-141">Constructor</span></span>|<span data-ttu-id="eae74-142">Die Zeichenfolge ".ctor"</span><span class="sxs-lookup"><span data-stu-id="eae74-142">The string ".ctor"</span></span>|
|<span data-ttu-id="eae74-143">Statischer Konstruktor</span><span class="sxs-lookup"><span data-stu-id="eae74-143">Static constructor</span></span>|<span data-ttu-id="eae74-144">Die Zeichenfolge ".cctor"</span><span class="sxs-lookup"><span data-stu-id="eae74-144">The string ".cctor"</span></span>|
|<span data-ttu-id="eae74-145">Destruktor</span><span class="sxs-lookup"><span data-stu-id="eae74-145">Destructor</span></span>|<span data-ttu-id="eae74-146">Die Zeichenfolge "Finalize"</span><span class="sxs-lookup"><span data-stu-id="eae74-146">The string "Finalize"</span></span>|
|<span data-ttu-id="eae74-147">Benutzerdefinierte Operatoren oder Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="eae74-147">User-defined operators or conversions</span></span>|<span data-ttu-id="eae74-148">Der generierte Name für den Member, beispielsweise "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="eae74-148">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="eae74-149">Attributkonstruktor</span><span class="sxs-lookup"><span data-stu-id="eae74-149">Attribute constructor</span></span>|<span data-ttu-id="eae74-150">Der Name des Members, auf den das Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="eae74-150">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="eae74-151">Wenn das Attribut ein beliebiges Element in einem Member ist (z. B. ein Parameter, ein Rückgabewert oder ein generischer Typparameter), wird als Ergebnis der Name des Members ausgegeben, der diesem Element zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="eae74-151">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="eae74-152">Kein enthaltender Member (z. B. auf Assemblyebene oder Attribute, die auf Typen angewendet werden)</span><span class="sxs-lookup"><span data-stu-id="eae74-152">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="eae74-153">Der Standardwert des optionalen Parameters.</span><span class="sxs-lookup"><span data-stu-id="eae74-153">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="eae74-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eae74-154">See also</span></span>

- [<span data-ttu-id="eae74-155">Attribute</span><span class="sxs-lookup"><span data-stu-id="eae74-155">Attributes</span></span>](attributes.md)
- [<span data-ttu-id="eae74-156">Benannte Argumente</span><span class="sxs-lookup"><span data-stu-id="eae74-156">Named arguments</span></span>](parameters-and-arguments.md#named-arguments)
- [<span data-ttu-id="eae74-157">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="eae74-157">Optional parameters</span></span>](parameters-and-arguments.md#optional-parameters)
