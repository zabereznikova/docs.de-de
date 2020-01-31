---
title: Parameterentwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
ms.openlocfilehash: 78eb07503810e75d14bcd73740fe429e2f73475e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743677"
---
# <a name="parameter-design"></a><span data-ttu-id="8bc59-102">Parameter Entwurf</span><span class="sxs-lookup"><span data-stu-id="8bc59-102">Parameter design</span></span>

<span data-ttu-id="8bc59-103">Dieser Abschnitt enthält allgemeine Richtlinien zum Parameter Entwurf, einschließlich Abschnitten mit Richtlinien zum Überprüfen von Argumenten.</span><span class="sxs-lookup"><span data-stu-id="8bc59-103">This section provides broad guidelines on parameter design, including sections with guidelines for checking arguments.</span></span> <span data-ttu-id="8bc59-104">Außerdem sollten Sie die in [Benennungs Parametern](../../../docs/standard/design-guidelines/naming-parameters.md)beschriebenen Richtlinien beachten.</span><span class="sxs-lookup"><span data-stu-id="8bc59-104">In addition, you should refer to the guidelines described in [Naming Parameters](../../../docs/standard/design-guidelines/naming-parameters.md).</span></span>

 <span data-ttu-id="8bc59-105">in ✔️ wird der am wenigsten abgeleitete Parametertyp verwendet, der die für den Member erforderliche Funktionalität bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8bc59-105">✔️ DO use the least derived parameter type that provides the functionality required by the member.</span></span>

 <span data-ttu-id="8bc59-106">Angenommen, Sie möchten eine Methode entwerfen, die eine Auflistung auflistet und jedes Element in der Konsole ausgibt.</span><span class="sxs-lookup"><span data-stu-id="8bc59-106">For example, suppose you want to design a method that enumerates a collection and prints each item to the console.</span></span> <span data-ttu-id="8bc59-107">Eine solche Methode sollte z. b. <xref:System.Collections.IEnumerable> als Parameter, nicht jedoch <xref:System.Collections.ArrayList> oder <xref:System.Collections.IList>annehmen.</span><span class="sxs-lookup"><span data-stu-id="8bc59-107">Such a method should take <xref:System.Collections.IEnumerable> as the parameter, not <xref:System.Collections.ArrayList> or <xref:System.Collections.IList>, for example.</span></span>

 <span data-ttu-id="8bc59-108">❌ keine reservierten Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="8bc59-108">❌ DO NOT use reserved parameters.</span></span>

 <span data-ttu-id="8bc59-109">Wenn in einer zukünftigen Version mehr Eingaben für einen Member erforderlich sind, kann eine neue Überladung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8bc59-109">If more input to a member is needed in some future version, a new overload can be added.</span></span>

 <span data-ttu-id="8bc59-110">❌ verfügen über keine öffentlich verfügbar gemachten Methoden, die Zeiger, Zeiger Arrays oder mehrdimensionale Arrays als Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="8bc59-110">❌ DO NOT have publicly exposed methods that take pointers, arrays of pointers, or multidimensional arrays as parameters.</span></span>

 <span data-ttu-id="8bc59-111">Zeiger und mehrdimensionale Arrays sind relativ schwierig zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8bc59-111">Pointers and multidimensional arrays are relatively difficult to use properly.</span></span> <span data-ttu-id="8bc59-112">In fast allen Fällen können APIs umgestaltet werden, um zu vermeiden, dass diese Typen als Parameter übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="8bc59-112">In almost all cases, APIs can be redesigned to avoid taking these types as parameters.</span></span>

 <span data-ttu-id="8bc59-113">✔️ Alle `out` Parameter nach allen nach Wert-und `ref`-Parametern platzieren (ausgenommen Parameter Arrays), selbst wenn dies zu einer Inkonsistenz bei der Parameter Anordnung zwischen über Ladungen führt (siehe Element [Überladung](../../../docs/standard/design-guidelines/member-overloading.md)).</span><span class="sxs-lookup"><span data-stu-id="8bc59-113">✔️ DO place all `out` parameters following all of the by-value and `ref` parameters (excluding parameter arrays), even if it results in an inconsistency in parameter ordering between overloads (see [Member Overloading](../../../docs/standard/design-guidelines/member-overloading.md)).</span></span>

 <span data-ttu-id="8bc59-114">Die `out` Parameter können als zusätzliche Rückgabewerte angesehen werden, und durch Gruppierung werden die Methoden Signaturen leichter zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="8bc59-114">The `out` parameters can be seen as extra return values, and grouping them together makes the method signature easier to understand.</span></span>

 <span data-ttu-id="8bc59-115">beim Überschreiben von Membern oder Implementieren von Schnittstellenmembern sind ✔️ konsistent.</span><span class="sxs-lookup"><span data-stu-id="8bc59-115">✔️ DO be consistent in naming parameters when overriding members or implementing interface members.</span></span>

 <span data-ttu-id="8bc59-116">Dadurch wird die Beziehung zwischen den Methoden besser kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="8bc59-116">This better communicates the relationship between the methods.</span></span>

### <a name="choose-between-enum-and-boolean-parameters"></a><span data-ttu-id="8bc59-117">Auswahl zwischen Aufzählungs-und booleschen Parametern</span><span class="sxs-lookup"><span data-stu-id="8bc59-117">Choose between enum and boolean parameters</span></span>
 <span data-ttu-id="8bc59-118">✔️ verwenden Enumerationswerte, wenn ein Member andernfalls mindestens zwei boolesche Parameter aufweisen würde.</span><span class="sxs-lookup"><span data-stu-id="8bc59-118">✔️ DO use enums if a member would otherwise have two or more Boolean parameters.</span></span>

 <span data-ttu-id="8bc59-119">❌ verwenden keine booleschen Werte, es sei denn, Sie sind sicher, dass nie mehr als zwei Werte benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="8bc59-119">❌ DO NOT use Booleans unless you are absolutely sure there will never be a need for more than two values.</span></span>

 <span data-ttu-id="8bc59-120">Enumerationen geben Ihnen einen gewissen Raum für eine zukünftige Addition von Werten. Sie sollten jedoch alle Implikationen beachten, die sich aus dem Hinzufügen von Werten zu Enumerationen machen, die im [Enumerationsentwurf](../../../docs/standard/design-guidelines/enum.md)beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="8bc59-120">Enums give you some room for future addition of values, but you should be aware of all the implications of adding values to enums, which are described in [Enum Design](../../../docs/standard/design-guidelines/enum.md).</span></span>

 <span data-ttu-id="8bc59-121">✔️ sollten Sie die Verwendung von booleschen Werten für Konstruktorparameter in Erwägung gezogen, die tatsächlich zwei Zustands Werte sind und einfach zum Initialisieren von booleschen Eigenschaften verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8bc59-121">✔️ CONSIDER using Booleans for constructor parameters that are truly two-state values and are simply used to initialize Boolean properties.</span></span>

### <a name="validate-arguments"></a><span data-ttu-id="8bc59-122">Validieren von Argumenten</span><span class="sxs-lookup"><span data-stu-id="8bc59-122">Validate arguments</span></span>
 <span data-ttu-id="8bc59-123">✔️ Überprüfen Sie Argumente, die an öffentliche, geschützte oder explizit implementierte Member übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="8bc59-123">✔️ DO validate arguments passed to public, protected, or explicitly implemented members.</span></span> <span data-ttu-id="8bc59-124">Lösen Sie <xref:System.ArgumentException?displayProperty=nameWithType>oder eine der zugehörigen Unterklassen aus, wenn die Validierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="8bc59-124">Throw <xref:System.ArgumentException?displayProperty=nameWithType>, or one of its subclasses, if the validation fails.</span></span>

 <span data-ttu-id="8bc59-125">Beachten Sie, dass die tatsächliche Validierung nicht unbedingt im öffentlichen oder geschützten Member selbst erfolgen muss.</span><span class="sxs-lookup"><span data-stu-id="8bc59-125">Note that the actual validation does not necessarily have to happen in the public or protected member itself.</span></span> <span data-ttu-id="8bc59-126">Dies kann in einer privaten oder internen Routine auf einer niedrigeren Ebene vorkommen.</span><span class="sxs-lookup"><span data-stu-id="8bc59-126">It could happen at a lower level in some private or internal routine.</span></span> <span data-ttu-id="8bc59-127">Der Hauptgrund dafür ist, dass die gesamte Oberfläche, die den Endbenutzern zur Verfügung gestellt wird, die Argumente prüft.</span><span class="sxs-lookup"><span data-stu-id="8bc59-127">The main point is that the entire surface area that is exposed to the end users checks the arguments.</span></span>

 <span data-ttu-id="8bc59-128">✔️ lösen <xref:System.ArgumentNullException> aus, wenn ein NULL-Argument übergeben wird und der Member keine NULL-Argumente unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8bc59-128">✔️ DO throw <xref:System.ArgumentNullException> if a null argument is passed and the member does not support null arguments.</span></span>

 <span data-ttu-id="8bc59-129">✔️ Überprüfen Sie die Aufzählungs Parameter.</span><span class="sxs-lookup"><span data-stu-id="8bc59-129">✔️ DO validate enum parameters.</span></span>

 <span data-ttu-id="8bc59-130">Gehen Sie nicht davon aus, dass sich die Aufzählungs Argumente in dem von der-Aufzählung definierten Bereich befinden.</span><span class="sxs-lookup"><span data-stu-id="8bc59-130">Do not assume enum arguments will be in the range defined by the enum.</span></span> <span data-ttu-id="8bc59-131">Die CLR ermöglicht das Umwandeln eines beliebigen ganzzahligen Werts in einen Enumerationswert, auch wenn der Wert nicht in der Enumeration definiert ist.</span><span class="sxs-lookup"><span data-stu-id="8bc59-131">The CLR allows casting any integer value into an enum value even if the value is not defined in the enum.</span></span>

 <span data-ttu-id="8bc59-132">❌ keine <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> für Überprüfungen des Aufzählungs Bereichs verwenden.</span><span class="sxs-lookup"><span data-stu-id="8bc59-132">❌ DO NOT use <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> for enum range checks.</span></span>

 <span data-ttu-id="8bc59-133">✔️ Beachten Sie, dass änderbare Argumente möglicherweise geändert wurden, nachdem Sie überprüft wurden.</span><span class="sxs-lookup"><span data-stu-id="8bc59-133">✔️ DO be aware that mutable arguments might have changed after they were validated.</span></span>

 <span data-ttu-id="8bc59-134">Wenn der Member Sicherheits sensibel ist, wird empfohlen, eine Kopie zu erstellen und dann das Argument zu validieren und zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="8bc59-134">If the member is security sensitive, you are encouraged to make a copy and then validate and process the argument.</span></span>

### <a name="pass-parameters"></a><span data-ttu-id="8bc59-135">Übergeben von Parametern</span><span class="sxs-lookup"><span data-stu-id="8bc59-135">Pass parameters</span></span>
 <span data-ttu-id="8bc59-136">Aus Sicht eines Framework-Designers gibt es drei Hauptgruppen von Parametern: nach Wert Parameter, `ref` Parameter und `out` Parameter.</span><span class="sxs-lookup"><span data-stu-id="8bc59-136">From the perspective of a framework designer, there are three main groups of parameters: by-value parameters, `ref` parameters, and `out` parameters.</span></span>

 <span data-ttu-id="8bc59-137">Wenn ein Argument durch einen by-value-Parameter übergeben wird, empfängt der Member eine Kopie des tatsächlich übergebenen Arguments.</span><span class="sxs-lookup"><span data-stu-id="8bc59-137">When an argument is passed through a by-value parameter, the member receives a copy of the actual argument passed in.</span></span> <span data-ttu-id="8bc59-138">Wenn das Argument ein Werttyp ist, wird eine Kopie des Arguments auf dem Stapel abgelegt.</span><span class="sxs-lookup"><span data-stu-id="8bc59-138">If the argument is a value type, a copy of the argument is put on the stack.</span></span> <span data-ttu-id="8bc59-139">Wenn das Argument ein Referenztyp ist, wird eine Kopie des Verweises auf dem Stapel abgelegt.</span><span class="sxs-lookup"><span data-stu-id="8bc59-139">If the argument is a reference type, a copy of the reference is put on the stack.</span></span> <span data-ttu-id="8bc59-140">Die beliebtesten CLR-Sprachen, wie C#z. b. C++, Visual Basic und, werden standardmäßig zum Übergeben von Parametern nach Wert übergeben.</span><span class="sxs-lookup"><span data-stu-id="8bc59-140">Most popular CLR languages, such as C#, Visual Basic, and C++, default to passing parameters by value.</span></span>

 <span data-ttu-id="8bc59-141">Wenn ein Argument über einen `ref`-Parameter übergeben wird, empfängt der Member einen Verweis auf das tatsächlich übergebene Argument.</span><span class="sxs-lookup"><span data-stu-id="8bc59-141">When an argument is passed through a `ref` parameter, the member receives a reference to the actual argument passed in.</span></span> <span data-ttu-id="8bc59-142">Wenn das Argument ein Werttyp ist, wird ein Verweis auf das Argument auf dem Stapel abgelegt.</span><span class="sxs-lookup"><span data-stu-id="8bc59-142">If the argument is a value type, a reference to the argument is put on the stack.</span></span> <span data-ttu-id="8bc59-143">Wenn es sich bei dem Argument um einen Verweistyp handelt, wird ein Verweis auf den Verweis auf den Stapel eingefügt.</span><span class="sxs-lookup"><span data-stu-id="8bc59-143">If the argument is a reference type, a reference to the reference is put on the stack.</span></span> <span data-ttu-id="8bc59-144">`Ref` Parameter können verwendet werden, um zuzulassen, dass der Member vom Aufrufer übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="8bc59-144">`Ref` parameters can be used to allow the member to modify arguments passed by the caller.</span></span>

 <span data-ttu-id="8bc59-145">`Out` Parameter ähneln `ref` Parametern, mit einigen kleinen unterschieden.</span><span class="sxs-lookup"><span data-stu-id="8bc59-145">`Out` parameters are similar to `ref` parameters, with some small differences.</span></span> <span data-ttu-id="8bc59-146">Der-Parameter wird anfänglich als nicht zugewiesen betrachtet und kann nicht im Element Text gelesen werden, bevor ihm ein Wert zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="8bc59-146">The parameter is initially considered unassigned and cannot be read in the member body before it is assigned some value.</span></span> <span data-ttu-id="8bc59-147">Außerdem muss dem-Parameter ein Wert zugewiesen werden, bevor der Member zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8bc59-147">Also, the parameter has to be assigned some value before the member returns.</span></span>

 <span data-ttu-id="8bc59-148">❌ die Verwendung von `out` oder `ref` Parametern vermeiden.</span><span class="sxs-lookup"><span data-stu-id="8bc59-148">❌ AVOID using `out` or `ref` parameters.</span></span>

 <span data-ttu-id="8bc59-149">Die Verwendung von `out`-oder `ref`-Parametern erfordert die Verwendung von Zeigern, das Verständnis der Unterschiede zwischen Werttypen und Verweis Typen sowie die Behandlung von Methoden mit mehreren</span><span class="sxs-lookup"><span data-stu-id="8bc59-149">Using `out` or `ref` parameters requires experience with pointers, understanding how value types and reference types differ, and handling methods with multiple return values.</span></span> <span data-ttu-id="8bc59-150">Außerdem wird der Unterschied zwischen `out`-und `ref`-Parametern nicht weitgehend verstanden.</span><span class="sxs-lookup"><span data-stu-id="8bc59-150">Also, the difference between `out` and `ref` parameters is not widely understood.</span></span> <span data-ttu-id="8bc59-151">Frameworkarchitekten, die für eine allgemeine Zielgruppe entwerfen, sollten nicht erwarten, dass Benutzer mit `out`-oder `ref`-Parametern arbeiten.</span><span class="sxs-lookup"><span data-stu-id="8bc59-151">Framework architects designing for a general audience should not expect users to master working with `out` or `ref` parameters.</span></span>

 <span data-ttu-id="8bc59-152">❌ die Verweis Typen nicht als Verweis übergeben.</span><span class="sxs-lookup"><span data-stu-id="8bc59-152">❌ DO NOT pass reference types by reference.</span></span>

 <span data-ttu-id="8bc59-153">Es gibt einige begrenzte Ausnahmen für die Regel, z. b. eine Methode, die zum Austauschen von Verweisen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="8bc59-153">There are some limited exceptions to the rule, such as a method that can be used to swap references.</span></span>

### <a name="members-with-variable-number-of-parameters"></a><span data-ttu-id="8bc59-154">Elemente mit variabler Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="8bc59-154">Members with variable number of parameters</span></span>
 <span data-ttu-id="8bc59-155">Member, die eine Variable Anzahl von Argumenten annehmen können, werden durch Angabe eines Array Parameters ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="8bc59-155">Members that can take a variable number of arguments are expressed by providing an array parameter.</span></span> <span data-ttu-id="8bc59-156"><xref:System.String> stellt z. b. die folgende Methode bereit:</span><span class="sxs-lookup"><span data-stu-id="8bc59-156">For example, <xref:System.String> provides the following method:</span></span>

```csharp
public class String {
    public static string Format(string format, object[] parameters);
}
```

 <span data-ttu-id="8bc59-157">Ein Benutzer kann dann die <xref:System.String.Format%2A?displayProperty=nameWithType>-Methode wie folgt aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="8bc59-157">A user can then call the <xref:System.String.Format%2A?displayProperty=nameWithType> method, as follows:</span></span>

 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`

 <span data-ttu-id="8bc59-158">Durch das C# Hinzufügen des params-Schlüssel Worts zu einem Array Parameter wird der Parameter in einen sogenannten params-Array Parameter geändert und eine Verknüpfung zur Erstellung eines temporären Arrays bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="8bc59-158">Adding the C# params keyword to an array parameter changes the parameter to a so-called params array parameter and provides a shortcut to creating a temporary array.</span></span>

```csharp
public class String {
    public static string Format(string format, params object[] parameters);
}
```

 <span data-ttu-id="8bc59-159">Dadurch kann der Benutzer die Methode aufzurufen, indem er die Array Elemente direkt in der Argumentliste übergibt.</span><span class="sxs-lookup"><span data-stu-id="8bc59-159">Doing this allows the user to call the method by passing the array elements directly in the argument list.</span></span>

 `String.Format("File {0} not found in {1}",filename,directory);`

 <span data-ttu-id="8bc59-160">Beachten Sie, dass das parameterschlüsselwort nur dem letzten Parameter in der Parameterliste hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8bc59-160">Note that the params keyword can be added only to the last parameter in the parameter list.</span></span>

 <span data-ttu-id="8bc59-161">✔️ Sie ggf. das params-Schlüsselwort zu Array Parametern hinzufügen, wenn Sie erwarten, dass die Endbenutzer Arrays mit einer kleinen Anzahl von Elementen übergeben.</span><span class="sxs-lookup"><span data-stu-id="8bc59-161">✔️ CONSIDER adding the params keyword to array parameters if you expect the end users to pass arrays with a small number of elements.</span></span> <span data-ttu-id="8bc59-162">Wenn davon ausgegangen wird, dass viele Elemente in gängigen Szenarien übergeben werden, werden diese Elemente wahrscheinlich nicht von den Benutzern Inline übergeben, sodass das params-Schlüsselwort nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8bc59-162">If it’s expected that lots of elements will be passed in common scenarios, users will probably not pass these elements inline anyway, and so the params keyword is not necessary.</span></span>

 <span data-ttu-id="8bc59-163">❌ die Verwendung von params-Arrays vermeiden, wenn der Aufrufer fast immer die Eingabe in einem Array haben würde.</span><span class="sxs-lookup"><span data-stu-id="8bc59-163">❌ AVOID using params arrays if the caller would almost always have the input already in an array.</span></span>

 <span data-ttu-id="8bc59-164">Beispielsweise werden Elemente mit Bytearray-Parametern fast nie aufgerufen, indem einzelne Bytes übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="8bc59-164">For example, members with byte array parameters would almost never be called by passing individual bytes.</span></span> <span data-ttu-id="8bc59-165">Aus diesem Grund verwenden Bytearray-Parameter im .NET Framework nicht das params-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="8bc59-165">For this reason, byte array parameters in the .NET Framework do not use the params keyword.</span></span>

 <span data-ttu-id="8bc59-166">❌ keine params-Arrays verwenden, wenn das Array vom Member geändert wird, der den Parameter "params Array" annimmt.</span><span class="sxs-lookup"><span data-stu-id="8bc59-166">❌ DO NOT use params arrays if the array is modified by the member taking the params array parameter.</span></span>

 <span data-ttu-id="8bc59-167">Aufgrund der Tatsache, dass viele Compiler die Argumente für den Member in ein temporäres Array an der aufrufssite umwandeln, kann das Array ein temporäres Objekt sein. Daher gehen alle Änderungen am Array verloren.</span><span class="sxs-lookup"><span data-stu-id="8bc59-167">Because of the fact that many compilers turn the arguments to the member into a temporary array at the call site, the array might be a temporary object, and therefore any modifications to the array will be lost.</span></span>

 <span data-ttu-id="8bc59-168">✔️ in Erwägung gezogen, das Schlüsselwort "para" in einer einfachen Überladung zu verwenden, auch wenn es von einer komplexeren Überladung nicht verwendet werden konnte.</span><span class="sxs-lookup"><span data-stu-id="8bc59-168">✔️ CONSIDER using the params keyword in a simple overload, even if a more complex overload could not use it.</span></span>

 <span data-ttu-id="8bc59-169">Fragen Sie sich, ob Benutzer den Wert des params-Arrays in einer Überladung haben würden, auch wenn Sie nicht in allen über Ladungen vorhanden wäre.</span><span class="sxs-lookup"><span data-stu-id="8bc59-169">Ask yourself if users would value having the params array in one overload even if it wasn’t in all overloads.</span></span>

 <span data-ttu-id="8bc59-170">✔️ versuchen, Parameter zu sortieren, um die Verwendung des Schlüssel Worts "Parameter" zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="8bc59-170">✔️ DO try to order parameters to make it possible to use the params keyword.</span></span>

 <span data-ttu-id="8bc59-171">✔️ sollten Sie besondere über Ladungen und Codepfade für Aufrufe mit einer kleinen Anzahl von Argumenten in äußerst Leistungs relevanten APIs bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8bc59-171">✔️ CONSIDER providing special overloads and code paths for calls with a small number of arguments in extremely performance-sensitive APIs.</span></span>

 <span data-ttu-id="8bc59-172">Dadurch ist es möglich, keine Array Objekte zu erstellen, wenn die API mit einer kleinen Anzahl von Argumenten aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8bc59-172">This makes it possible to avoid creating array objects when the API is called with a small number of arguments.</span></span> <span data-ttu-id="8bc59-173">Bilden Sie die Namen der Parameter, indem Sie eine Singular Form des Array-Parameters und ein numerisches Suffix hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8bc59-173">Form the names of the parameters by taking a singular form of the array parameter and adding a numeric suffix.</span></span>

 <span data-ttu-id="8bc59-174">Dies sollten Sie nur tun, wenn Sie den gesamten Codepfad als Sonderfall verwenden, nicht nur ein Array erstellen und die allgemeinere Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8bc59-174">You should only do this if you are going to special-case the entire code path, not just create an array and call the more general method.</span></span>

 <span data-ttu-id="8bc59-175">✔️ Beachten Sie, dass NULL als params-Array Argument übermittelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8bc59-175">✔️ DO be aware that null could be passed as a params array argument.</span></span>

 <span data-ttu-id="8bc59-176">Vor der Verarbeitung sollten Sie überprüfen, ob das Array nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="8bc59-176">You should validate that the array is not null before processing.</span></span>

 <span data-ttu-id="8bc59-177">❌ nicht die `varargs` Methoden verwenden, die auch als Ellipsen bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="8bc59-177">❌ DO NOT use the `varargs` methods, otherwise known as the ellipsis.</span></span>

 <span data-ttu-id="8bc59-178">Einige CLR-Sprachen, wie C++z. b., unterstützen eine alternative Konvention zum Übergeben von Variablen Parameterlisten, die als `varargs` Methoden bezeichnet</span><span class="sxs-lookup"><span data-stu-id="8bc59-178">Some CLR languages, such as C++, support an alternative convention for passing variable parameter lists called `varargs` methods.</span></span> <span data-ttu-id="8bc59-179">Die Konvention sollte nicht in Frameworks verwendet werden, da Sie nicht CLS-kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="8bc59-179">The convention should not be used in frameworks, because it is not CLS compliant.</span></span>

### <a name="pointer-parameters"></a><span data-ttu-id="8bc59-180">Zeiger Parameter</span><span class="sxs-lookup"><span data-stu-id="8bc59-180">Pointer parameters</span></span>
 <span data-ttu-id="8bc59-181">Im Allgemeinen sollten Zeiger nicht in der öffentlichen Oberfläche eines gut entworfenen verwalteten Code-Frameworks angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8bc59-181">In general, pointers should not appear in the public surface area of a well-designed managed code framework.</span></span> <span data-ttu-id="8bc59-182">In den meisten Fällen sollten Zeiger gekapselt werden.</span><span class="sxs-lookup"><span data-stu-id="8bc59-182">Most of the time, pointers should be encapsulated.</span></span> <span data-ttu-id="8bc59-183">In einigen Fällen sind Zeiger aber aus Interoperabilitäts Gründen erforderlich, und die Verwendung von Zeigern in solchen Fällen ist angemessen.</span><span class="sxs-lookup"><span data-stu-id="8bc59-183">However, in some cases pointers are required for interoperability reasons, and using pointers in such cases is appropriate.</span></span>

 <span data-ttu-id="8bc59-184">✔️ eine Alternative für alle Member bereitstellen, die ein Zeigerargument verwenden, da Zeiger nicht CLS-kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="8bc59-184">✔️ DO provide an alternative for any member that takes a pointer argument, because pointers are not CLS-compliant.</span></span>

 <span data-ttu-id="8bc59-185">❌ eine teure Argument Überprüfung von Zeiger Argumenten vermeiden.</span><span class="sxs-lookup"><span data-stu-id="8bc59-185">❌ AVOID doing expensive argument checking of pointer arguments.</span></span>

 <span data-ttu-id="8bc59-186">beim Entwerfen von Membern mit Zeigern folgen ✔️ allgemeinen Zeiger bezogenen Konventionen.</span><span class="sxs-lookup"><span data-stu-id="8bc59-186">✔️ DO follow common pointer-related conventions when designing members with pointers.</span></span>

 <span data-ttu-id="8bc59-187">Beispielsweise ist es nicht erforderlich, den Start Index zu übergeben, da einfache Zeigerarithmetik verwendet werden kann, um das gleiche Ergebnis zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="8bc59-187">For example, there is no need to pass the start index, because simple pointer arithmetic can be used to accomplish the same result.</span></span>

 <span data-ttu-id="8bc59-188">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="8bc59-188">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="8bc59-189">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="8bc59-189">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="8bc59-190">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bc59-190">See also</span></span>

- [<span data-ttu-id="8bc59-191">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="8bc59-191">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="8bc59-192">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="8bc59-192">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
