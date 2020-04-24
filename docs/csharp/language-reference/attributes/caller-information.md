---
title: 'Reservierte C#-Attribute: Verfolgen von Aufruferinformationen'
ms.date: 04/09/2020
description: Diese Attribute weisen den Compiler an, Informationen zum Code zu generieren, der einen Member aufruft. Sie verwenden CallerFilePath, CallerLineNumber und CallerMemberName, um detaillierte Ablaufverfolgungsinformationen bereitzustellen.
ms.openlocfilehash: ee061d4cae35bdcc0b89007e360e94fee8c5f87c
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389823"
---
# <a name="reserved-attributes-determine-caller-information"></a><span data-ttu-id="ffb39-104">Reservierte Attribute: Bestimmen von Aufruferinformationen</span><span class="sxs-lookup"><span data-stu-id="ffb39-104">Reserved attributes: Determine caller information</span></span>

<span data-ttu-id="ffb39-105">Mithilfe der Informationsattribute können Sie Informationen zum Aufrufer einer Methode abrufen.</span><span class="sxs-lookup"><span data-stu-id="ffb39-105">Using info attributes, you obtain information about the caller to a method.</span></span> <span data-ttu-id="ffb39-106">Sie können den Dateipfad des Quellcodes, die Zeilennummer im Quellcode und den Membernamen des Aufrufers abrufen.</span><span class="sxs-lookup"><span data-stu-id="ffb39-106">You obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="ffb39-107">Um diese Memberaufruferinformationen zu erhalten, verwenden Sie die Attribute, die auf optionale Parameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="ffb39-107">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="ffb39-108">Jeder optionale Parameter gibt einen Standardwert an.</span><span class="sxs-lookup"><span data-stu-id="ffb39-108">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="ffb39-109">In der folgenden Tabelle sind die Aufrufer-Informationsattribute angegeben, die im <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>-Namespace definiert sind:</span><span class="sxs-lookup"><span data-stu-id="ffb39-109">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>

|<span data-ttu-id="ffb39-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="ffb39-110">Attribute</span></span>|<span data-ttu-id="ffb39-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ffb39-111">Description</span></span>|<span data-ttu-id="ffb39-112">Typ</span><span class="sxs-lookup"><span data-stu-id="ffb39-112">Type</span></span>|
|---|---|---|
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="ffb39-113">Vollständiger Pfad der Quelldatei, die den Aufrufer enthält.</span><span class="sxs-lookup"><span data-stu-id="ffb39-113">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="ffb39-114">Der vollständige Pfad zum Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="ffb39-114">The full path is the path at compile time.</span></span>|`String`|
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="ffb39-115">Zeilennummer in der Quelldatei, in der die Methode aufgerufen wird</span><span class="sxs-lookup"><span data-stu-id="ffb39-115">Line number in the source file from which the method is called.</span></span>|`Integer`|
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="ffb39-116">Der Methoden- oder Eigenschaftenname des Aufrufers</span><span class="sxs-lookup"><span data-stu-id="ffb39-116">Method name or property name of the caller.</span></span>|`String`|

<span data-ttu-id="ffb39-117">Diese Informationen sind für Ablaufverfolgung, Debuggen und zum Erstellen von Diagnosetools sehr nützlich.</span><span class="sxs-lookup"><span data-stu-id="ffb39-117">This information helps you write tracing, debugging, and create diagnostic tools.</span></span> <span data-ttu-id="ffb39-118">Im folgenden Beispiel wird die Verwendung der Aufruferinformationsattribute für Aufrufer veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ffb39-118">The following example shows how to use caller info attributes.</span></span> <span data-ttu-id="ffb39-119">Bei jedem Aufruf der `TraceMessage`-Methode werden die Aufruferinformationen als Argumente für optionale Parameter ersetzt.</span><span class="sxs-lookup"><span data-stu-id="ffb39-119">On each call to the `TraceMessage` method, the caller information is substituted as arguments to the optional parameters.</span></span>

```csharp
public void DoProcessing()
{
    TraceMessage("Something happened.");
}

public void TraceMessage(string message,
        [CallerMemberName] string memberName = "",
        [CallerFilePath] string sourceFilePath = "",
        [CallerLineNumber] int sourceLineNumber = 0)
{
    Trace.WriteLine("message: " + message);
    Trace.WriteLine("member name: " + memberName);
    Trace.WriteLine("source file path: " + sourceFilePath);
    Trace.WriteLine("source line number: " + sourceLineNumber);
}

// Sample Output:
//  message: Something happened.
//  member name: DoProcessing
//  source file path: c:\Visual Studio Projects\CallerInfoCS\CallerInfoCS\Form1.cs
//  source line number: 31
```

<span data-ttu-id="ffb39-120">Sie geben einen expliziten Standardwert für jeden optionalen Parameter an.</span><span class="sxs-lookup"><span data-stu-id="ffb39-120">You specify an explicit default value for each optional parameter.</span></span> <span data-ttu-id="ffb39-121">Sie können Aufruferinformationsattribute nicht auf Parameter anwenden, die nicht als optional festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="ffb39-121">You can't apply caller info attributes to parameters that aren't specified as optional.</span></span> <span data-ttu-id="ffb39-122">Durch die Aufruferinformationsattribute wird ein Parameter nicht optional.</span><span class="sxs-lookup"><span data-stu-id="ffb39-122">The caller info attributes don't make a parameter optional.</span></span> <span data-ttu-id="ffb39-123">Stattdessen beeinflussen sie den Standardwert, der beim Auslassen des Arguments übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="ffb39-123">Instead, they affect the default value that's passed in when the argument is omitted.</span></span> <span data-ttu-id="ffb39-124">Aufruferinformationswerte werden zur Kompilierzeit als Literale in Intermediate Language (IL) ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="ffb39-124">Caller info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="ffb39-125">Im Gegensatz zu den Ergebnissen der <xref:System.Exception.StackTrace%2A>-Eigenschaft für Ausnahmen werden die Ergebnisse nicht durch Verbergen beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="ffb39-125">Unlike the results of the <xref:System.Exception.StackTrace%2A> property for exceptions, the results aren't affected by obfuscation.</span></span> <span data-ttu-id="ffb39-126">Sie können die optionalen Argumente explizit angeben, um die Aufruferinformationen zu steuern oder auszublenden.</span><span class="sxs-lookup"><span data-stu-id="ffb39-126">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

### <a name="member-names"></a><span data-ttu-id="ffb39-127">Membernamen</span><span class="sxs-lookup"><span data-stu-id="ffb39-127">Member names</span></span>

<span data-ttu-id="ffb39-128">Sie können das `CallerMemberName`-Attribut verwenden, um den Membernamen nicht als `String`-Argument für die aufgerufene Methode angeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="ffb39-128">You can use the `CallerMemberName` attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="ffb39-129">Auf diese Weise umgehen Sie das Problem, dass durch die **Umgestaltung mit Umbenennung** die `String`-Werte nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ffb39-129">By using this technique, you avoid the problem that **Rename Refactoring** doesn't change the `String` values.</span></span> <span data-ttu-id="ffb39-130">Dieser Vorteil ist für die folgenden Aufgaben besonders hilfreich:</span><span class="sxs-lookup"><span data-stu-id="ffb39-130">This benefit is especially useful for the following tasks:</span></span>

- <span data-ttu-id="ffb39-131">Verwenden der Ablaufverfolgung und der Diagnoseprogramme</span><span class="sxs-lookup"><span data-stu-id="ffb39-131">Using tracing and diagnostic routines.</span></span>
- <span data-ttu-id="ffb39-132">Implementieren der <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle beim Binden von Daten</span><span class="sxs-lookup"><span data-stu-id="ffb39-132">Implementing the <xref:System.ComponentModel.INotifyPropertyChanged> interface when binding data.</span></span> <span data-ttu-id="ffb39-133">Diese Schnittstelle ermöglicht es der Eigenschaft eines Objekts, ein gebundenes Steuerelement über die Änderung der Eigenschaft zu benachrichtigen, damit das Steuerelement die aktualisierten Informationen anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="ffb39-133">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="ffb39-134">Ohne das `CallerMemberName`-Attribut müssen Sie den Eigenschaftennamen als Literal angeben.</span><span class="sxs-lookup"><span data-stu-id="ffb39-134">Without the `CallerMemberName` attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="ffb39-135">Im folgenden Diagramm sind die Membernamen aufgeführt, die beim Verwenden des `CallerMemberName`-Attributs zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ffb39-135">The following chart shows the member names that are returned when you use the `CallerMemberName` attribute.</span></span>

|<span data-ttu-id="ffb39-136">Aufrufe erfolgen in:</span><span class="sxs-lookup"><span data-stu-id="ffb39-136">Calls occur within</span></span>|<span data-ttu-id="ffb39-137">Membernamenergebnis</span><span class="sxs-lookup"><span data-stu-id="ffb39-137">Member name result</span></span>|
|-|-|
|<span data-ttu-id="ffb39-138">Methode, Eigenschaft oder Ereignis</span><span class="sxs-lookup"><span data-stu-id="ffb39-138">Method, property, or event</span></span>|<span data-ttu-id="ffb39-139">Der Name der Methode, der Eigenschaft oder des Ereignisses, aus dem bzw. aus der der Aufruf stammt.</span><span class="sxs-lookup"><span data-stu-id="ffb39-139">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="ffb39-140">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="ffb39-140">Constructor</span></span>|<span data-ttu-id="ffb39-141">Die Zeichenfolge „.ctor“</span><span class="sxs-lookup"><span data-stu-id="ffb39-141">The string ".ctor"</span></span>|
|<span data-ttu-id="ffb39-142">Statischer Konstruktor</span><span class="sxs-lookup"><span data-stu-id="ffb39-142">Static constructor</span></span>|<span data-ttu-id="ffb39-143">Die Zeichenfolge „.cctor“</span><span class="sxs-lookup"><span data-stu-id="ffb39-143">The string ".cctor"</span></span>|
|<span data-ttu-id="ffb39-144">Destruktor</span><span class="sxs-lookup"><span data-stu-id="ffb39-144">Destructor</span></span>|<span data-ttu-id="ffb39-145">Die Zeichenfolge „Finalize“</span><span class="sxs-lookup"><span data-stu-id="ffb39-145">The string "Finalize"</span></span>|
|<span data-ttu-id="ffb39-146">Benutzerdefinierte Operatoren oder Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="ffb39-146">User-defined operators or conversions</span></span>|<span data-ttu-id="ffb39-147">Der generierte Name für den Member, beispielsweise „op_Addition“.</span><span class="sxs-lookup"><span data-stu-id="ffb39-147">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="ffb39-148">Attributkonstruktor</span><span class="sxs-lookup"><span data-stu-id="ffb39-148">Attribute constructor</span></span>|<span data-ttu-id="ffb39-149">Der Name der Methode oder Eigenschaft, auf die das Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ffb39-149">The name of the method or property to which the attribute is applied.</span></span> <span data-ttu-id="ffb39-150">Wenn das Attribut ein beliebiges Element in einem Member ist (z. B. ein Parameter, ein Rückgabewert oder ein generischer Typparameter), wird als Ergebnis der Name des Members ausgegeben, der diesem Element zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="ffb39-150">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="ffb39-151">Kein enthaltender Member (z. B. auf Assemblyebene oder Attribute, die auf Typen angewendet werden)</span><span class="sxs-lookup"><span data-stu-id="ffb39-151">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="ffb39-152">Der Standardwert des optionalen Parameters.</span><span class="sxs-lookup"><span data-stu-id="ffb39-152">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="ffb39-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ffb39-153">See also</span></span>

- [<span data-ttu-id="ffb39-154">Benannte und optionale Argumente</span><span class="sxs-lookup"><span data-stu-id="ffb39-154">Named and Optional Arguments</span></span>](../../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="ffb39-155">Attribute</span><span class="sxs-lookup"><span data-stu-id="ffb39-155">Attributes</span></span>](../../../standard/attributes/index.md)
