---
title: Aufruferinformationen
description: Beschreibt, wie aufruferinfo-Argument Attribute verwendet werden, um Aufruferinformationen von einer Methode abzurufen.
ms.date: 11/04/2019
ms.openlocfilehash: 700cde26fbe4e6c48155f88bfc63af59af86cfe2
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739775"
---
# <a name="caller-information"></a><span data-ttu-id="4168b-103">Aufruferinformationen</span><span class="sxs-lookup"><span data-stu-id="4168b-103">Caller information</span></span>

<span data-ttu-id="4168b-104">Mithilfe der Aufrufer-Informationsattribute können Sie Informationen zum Aufrufer einer Methode abrufen.</span><span class="sxs-lookup"><span data-stu-id="4168b-104">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="4168b-105">Sie können den Dateipfad des Quellcodes, die Zeilennummer im Quellcode und den Membernamen des Aufrufers abrufen.</span><span class="sxs-lookup"><span data-stu-id="4168b-105">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="4168b-106">Diese Informationen sind zum Verfolgen, Debuggen und Erstellen von Diagnosetools sehr nützlich.</span><span class="sxs-lookup"><span data-stu-id="4168b-106">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>

<span data-ttu-id="4168b-107">Um diese Informationen zu erhalten, verwenden Sie die Attribute, die auf optionale Parameter angewendet werden, von denen jeder einen Standardwert besitzt.</span><span class="sxs-lookup"><span data-stu-id="4168b-107">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="4168b-108">In der folgenden Tabelle sind die Aufrufer-Informations Attribute aufgelistet, die im [System. Runtime. CompilerServices](/dotnet/api/system.runtime.compilerservices) -Namespace definiert sind:</span><span class="sxs-lookup"><span data-stu-id="4168b-108">The following table lists the Caller Info attributes that are defined in the [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) namespace:</span></span>

|<span data-ttu-id="4168b-109">attribute</span><span class="sxs-lookup"><span data-stu-id="4168b-109">Attribute</span></span>|<span data-ttu-id="4168b-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4168b-110">Description</span></span>|<span data-ttu-id="4168b-111">type</span><span class="sxs-lookup"><span data-stu-id="4168b-111">Type</span></span>|
|---------|-----------|----|
|[<span data-ttu-id="4168b-112">Callerfilepath</span><span class="sxs-lookup"><span data-stu-id="4168b-112">CallerFilePath</span></span>](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|<span data-ttu-id="4168b-113">Vollständiger Pfad der Quelldatei, die den Aufrufer enthält.</span><span class="sxs-lookup"><span data-stu-id="4168b-113">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="4168b-114">Dies ist der Dateipfad zum Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="4168b-114">This is the file path at compile time.</span></span>|`String`
|[<span data-ttu-id="4168b-115">Callerlinenumber</span><span class="sxs-lookup"><span data-stu-id="4168b-115">CallerLineNumber</span></span>](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|<span data-ttu-id="4168b-116">Zeilennummer in der Quelldatei, in der die Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4168b-116">Line number in the source file at which the method is called.</span></span>|`Integer`|
|[<span data-ttu-id="4168b-117">CallerMemberName</span><span class="sxs-lookup"><span data-stu-id="4168b-117">CallerMemberName</span></span>](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|<span data-ttu-id="4168b-118">Der Methoden- oder Eigenschaftenname des Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="4168b-118">Method or property name of the caller.</span></span> <span data-ttu-id="4168b-119">Weitere Informationen finden Sie im Abschnitt Elementnamen weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="4168b-119">See the Member Names section later in this topic.</span></span>|`String`|

## <a name="example"></a><span data-ttu-id="4168b-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4168b-120">Example</span></span>

<span data-ttu-id="4168b-121">Im folgenden Beispiel wird gezeigt, wie Sie diese Attribute zum Verfolgen eines Aufrufers verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4168b-121">The following example shows how you might use these attributes to trace a caller.</span></span>

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices
open System.Runtime.InteropServices

type Tracer() =
    member _.DoTrace(message: string,
                      [<CallerMemberName; Optional; DefaultParameterValue("")>] memberName: string,
                      [<CallerFilePath; Optional; DefaultParameterValue("")>] path: string,
                      [<CallerLineNumber; Optional; DefaultParameterValue(0)>] line: int) =
        Trace.WriteLine(sprintf $"Message: {message}")
        Trace.WriteLine(sprintf $"Member name: {memberName}")
        Trace.WriteLine(sprintf $"Source file path: {path}")
        Trace.WriteLine(sprintf $"Source line number: {line}")
```

## <a name="remarks"></a><span data-ttu-id="4168b-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4168b-122">Remarks</span></span>

<span data-ttu-id="4168b-123">Aufrufer-Informations Attribute können nur auf optionale Parameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="4168b-123">Caller Info attributes can only be applied to optional parameters.</span></span> <span data-ttu-id="4168b-124">Die Attribute für Aufruferinformationen bewirken, dass der Compiler den richtigen Wert für jeden optionalen Parameter schreibt, der mit einem aufruferinformationsattribut versehen ist</span><span class="sxs-lookup"><span data-stu-id="4168b-124">The Caller Info attributes cause the compiler to write the proper value for each optional parameter decorated with a Caller Info attribute.</span></span>

<span data-ttu-id="4168b-125">Aufrufer-Informationswerte werden zur Kompilierzeit als Literale in Intermediate Language (IL) ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="4168b-125">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="4168b-126">Im Gegensatz zu den Ergebnissen der [StackTrace](/dotnet/api/system.diagnostics.stacktrace) -Eigenschaft für Ausnahmen sind die Ergebnisse nicht von der Verschleierung betroffen.</span><span class="sxs-lookup"><span data-stu-id="4168b-126">Unlike the results of the [StackTrace](/dotnet/api/system.diagnostics.stacktrace) property for exceptions, the results aren't affected by obfuscation.</span></span>

<span data-ttu-id="4168b-127">Sie können die optionalen Argumente explizit angeben, um die Aufruferinformationen zu steuern oder auszublenden.</span><span class="sxs-lookup"><span data-stu-id="4168b-127">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

## <a name="member-names"></a><span data-ttu-id="4168b-128">Membernamen</span><span class="sxs-lookup"><span data-stu-id="4168b-128">Member names</span></span>

<span data-ttu-id="4168b-129">Sie können das- [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) Attribut verwenden, um zu vermeiden, dass der Elementname als `String` Argument für die aufgerufene Methode angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4168b-129">You can use the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="4168b-130">Auf diese Weise umgehen Sie das Problem, dass durch die Umgestaltung mit Umbenennung die `String`-Werte nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4168b-130">By using this technique, you avoid the problem that Rename Refactoring doesn't change the `String` values.</span></span> <span data-ttu-id="4168b-131">Dieser Vorteil ist für die folgenden Aufgaben besonders hilfreich:</span><span class="sxs-lookup"><span data-stu-id="4168b-131">This benefit is especially useful for the following tasks:</span></span>

- <span data-ttu-id="4168b-132">Verwenden der Ablaufverfolgung und der Diagnoseprogramme</span><span class="sxs-lookup"><span data-stu-id="4168b-132">Using tracing and diagnostic routines.</span></span>
- <span data-ttu-id="4168b-133">Implementieren der [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) -Schnittstelle beim Binden von Daten.</span><span class="sxs-lookup"><span data-stu-id="4168b-133">Implementing the [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interface when binding data.</span></span> <span data-ttu-id="4168b-134">Diese Schnittstelle ermöglicht es der Eigenschaft eines Objekts, ein gebundenes Steuerelement über die Änderung der Eigenschaft zu benachrichtigen, damit das Steuerelement die aktualisierten Informationen anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="4168b-134">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="4168b-135">Ohne das- [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) Attribut müssen Sie den Eigenschaftsnamen als Literalwert angeben.</span><span class="sxs-lookup"><span data-stu-id="4168b-135">Without the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="4168b-136">Das folgende Diagramm zeigt die Elementnamen, die zurückgegeben werden, wenn Sie das callermembership Name-Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="4168b-136">The following chart shows the member names that are returned when you use the CallerMemberName attribute.</span></span>

|<span data-ttu-id="4168b-137">Aufrufe erfolgen in</span><span class="sxs-lookup"><span data-stu-id="4168b-137">Calls occurs within</span></span>|<span data-ttu-id="4168b-138">Membernamenergebnis</span><span class="sxs-lookup"><span data-stu-id="4168b-138">Member name result</span></span>|
|-------------------|------------------|
|<span data-ttu-id="4168b-139">Methode, Eigenschaft oder Ereignis</span><span class="sxs-lookup"><span data-stu-id="4168b-139">Method, property, or event</span></span>|<span data-ttu-id="4168b-140">Der Name der Methode, der Eigenschaft oder des Ereignisses, aus dem bzw. aus der der Aufruf stammt.</span><span class="sxs-lookup"><span data-stu-id="4168b-140">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="4168b-141">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="4168b-141">Constructor</span></span>|<span data-ttu-id="4168b-142">Die Zeichenfolge „.ctor“</span><span class="sxs-lookup"><span data-stu-id="4168b-142">The string ".ctor"</span></span>|
|<span data-ttu-id="4168b-143">Statischer Konstruktor</span><span class="sxs-lookup"><span data-stu-id="4168b-143">Static constructor</span></span>|<span data-ttu-id="4168b-144">Die Zeichenfolge „.cctor“</span><span class="sxs-lookup"><span data-stu-id="4168b-144">The string ".cctor"</span></span>|
|<span data-ttu-id="4168b-145">Destruktor</span><span class="sxs-lookup"><span data-stu-id="4168b-145">Destructor</span></span>|<span data-ttu-id="4168b-146">Die Zeichenfolge „Finalize“</span><span class="sxs-lookup"><span data-stu-id="4168b-146">The string "Finalize"</span></span>|
|<span data-ttu-id="4168b-147">Benutzerdefinierte Operatoren oder Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="4168b-147">User-defined operators or conversions</span></span>|<span data-ttu-id="4168b-148">Der generierte Name für den Member, beispielsweise „op_Addition“.</span><span class="sxs-lookup"><span data-stu-id="4168b-148">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="4168b-149">Attributkonstruktor</span><span class="sxs-lookup"><span data-stu-id="4168b-149">Attribute constructor</span></span>|<span data-ttu-id="4168b-150">Der Name des Members, auf den das Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="4168b-150">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="4168b-151">Wenn das Attribut ein beliebiges Element in einem Member ist (z. B. ein Parameter, ein Rückgabewert oder ein generischer Typparameter), wird als Ergebnis der Name des Members ausgegeben, der diesem Element zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="4168b-151">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="4168b-152">Kein enthaltender Member (z. B. auf Assemblyebene oder Attribute, die auf Typen angewendet werden)</span><span class="sxs-lookup"><span data-stu-id="4168b-152">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="4168b-153">Der Standardwert des optionalen Parameters.</span><span class="sxs-lookup"><span data-stu-id="4168b-153">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="4168b-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4168b-154">See also</span></span>

- [<span data-ttu-id="4168b-155">Attribute</span><span class="sxs-lookup"><span data-stu-id="4168b-155">Attributes</span></span>](attributes.md)
- [<span data-ttu-id="4168b-156">Benannte Argumente</span><span class="sxs-lookup"><span data-stu-id="4168b-156">Named arguments</span></span>](parameters-and-arguments.md#named-arguments)
- [<span data-ttu-id="4168b-157">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="4168b-157">Optional parameters</span></span>](parameters-and-arguments.md#optional-parameters)
