---
title: Parameterentwurf
ms.date: 10/22/2008
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
ms.openlocfilehash: 707ae48be3f45d82ed3819f943dc5ba3743172f3
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828802"
---
# <a name="parameter-design"></a><span data-ttu-id="ebbfa-102">Parameterentwurf</span><span class="sxs-lookup"><span data-stu-id="ebbfa-102">Parameter Design</span></span>

<span data-ttu-id="ebbfa-103">Dieser Abschnitt enthält allgemeine Richtlinien zum Parameter Entwurf, einschließlich Abschnitten mit Richtlinien zum Überprüfen von Argumenten.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-103">This section provides broad guidelines on parameter design, including sections with guidelines for checking arguments.</span></span> <span data-ttu-id="ebbfa-104">Außerdem sollten Sie die in [Benennungs Parametern](naming-parameters.md)beschriebenen Richtlinien beachten.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-104">In addition, you should refer to the guidelines described in [Naming Parameters](naming-parameters.md).</span></span>

 <span data-ttu-id="ebbfa-105">in ✔️ wird der am wenigsten abgeleitete Parametertyp verwendet, der die für den Member erforderliche Funktionalität bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-105">✔️ DO use the least derived parameter type that provides the functionality required by the member.</span></span>

 <span data-ttu-id="ebbfa-106">Angenommen, Sie möchten eine Methode entwerfen, die eine Auflistung auflistet und jedes Element in der Konsole ausgibt.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-106">For example, suppose you want to design a method that enumerates a collection and prints each item to the console.</span></span> <span data-ttu-id="ebbfa-107">Eine solche Methode sollte z <xref:System.Collections.IEnumerable> . b. den-Parameter, nicht <xref:System.Collections.ArrayList> oder verwenden <xref:System.Collections.IList> .</span><span class="sxs-lookup"><span data-stu-id="ebbfa-107">Such a method should take <xref:System.Collections.IEnumerable> as the parameter, not <xref:System.Collections.ArrayList> or <xref:System.Collections.IList>, for example.</span></span>

 <span data-ttu-id="ebbfa-108">❌ Verwenden Sie keine reservierten Parameter.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-108">❌ DO NOT use reserved parameters.</span></span>

 <span data-ttu-id="ebbfa-109">Wenn in einer zukünftigen Version mehr Eingaben für einen Member erforderlich sind, kann eine neue Überladung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-109">If more input to a member is needed in some future version, a new overload can be added.</span></span>

 <span data-ttu-id="ebbfa-110">❌ Sie verfügen nicht über öffentlich verfügbar gemachte Methoden, die Zeiger, Zeiger Arrays oder mehrdimensionale Arrays als Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-110">❌ DO NOT have publicly exposed methods that take pointers, arrays of pointers, or multidimensional arrays as parameters.</span></span>

 <span data-ttu-id="ebbfa-111">Zeiger und mehrdimensionale Arrays sind relativ schwierig zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-111">Pointers and multidimensional arrays are relatively difficult to use properly.</span></span> <span data-ttu-id="ebbfa-112">In fast allen Fällen können APIs umgestaltet werden, um zu vermeiden, dass diese Typen als Parameter übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-112">In almost all cases, APIs can be redesigned to avoid taking these types as parameters.</span></span>

 <span data-ttu-id="ebbfa-113">✔️ alle `out` Parameter nach allen nach-Wert-und- `ref` Parametern platzieren (ausgenommen Parameter Arrays), selbst wenn dies zu einer Inkonsistenz bei der Parameter Anordnung zwischen über Ladungen führt (siehe Element [Überladung](member-overloading.md)).</span><span class="sxs-lookup"><span data-stu-id="ebbfa-113">✔️ DO place all `out` parameters following all of the by-value and `ref` parameters (excluding parameter arrays), even if it results in an inconsistency in parameter ordering between overloads (see [Member Overloading](member-overloading.md)).</span></span>

 <span data-ttu-id="ebbfa-114">Die `out` Parameter können als zusätzliche Rückgabewerte angesehen werden. durch Gruppierung werden die Methoden Signaturen leichter zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-114">The `out` parameters can be seen as extra return values, and grouping them together makes the method signature easier to understand.</span></span>

 <span data-ttu-id="ebbfa-115">beim Überschreiben von Membern oder Implementieren von Schnittstellenmembern sind ✔️ konsistent.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-115">✔️ DO be consistent in naming parameters when overriding members or implementing interface members.</span></span>

 <span data-ttu-id="ebbfa-116">Dadurch wird die Beziehung zwischen den Methoden besser kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-116">This better communicates the relationship between the methods.</span></span>

### <a name="choosing-between-enum-and-boolean-parameters"></a><span data-ttu-id="ebbfa-117">Auswählen zwischen Aufzählungs-und booleschen Parametern</span><span class="sxs-lookup"><span data-stu-id="ebbfa-117">Choosing Between Enum and Boolean Parameters</span></span>  
 <span data-ttu-id="ebbfa-118">✔️ verwenden Enumerationswerte, wenn ein Member andernfalls mindestens zwei boolesche Parameter aufweisen würde.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-118">✔️ DO use enums if a member would otherwise have two or more Boolean parameters.</span></span>

 <span data-ttu-id="ebbfa-119">❌ Verwenden Sie keine booleschen Werte, es sei denn, Sie sind sicher, dass nie mehr als zwei Werte benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-119">❌ DO NOT use Booleans unless you are absolutely sure there will never be a need for more than two values.</span></span>

 <span data-ttu-id="ebbfa-120">Enumerationen geben Ihnen einen gewissen Raum für eine zukünftige Addition von Werten. Sie sollten jedoch alle Implikationen beachten, die sich aus dem Hinzufügen von Werten zu Enumerationen machen, die im [Enumerationsentwurf](enum.md)beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-120">Enums give you some room for future addition of values, but you should be aware of all the implications of adding values to enums, which are described in [Enum Design](enum.md).</span></span>

 <span data-ttu-id="ebbfa-121">✔️ sollten Sie die Verwendung von booleschen Werten für Konstruktorparameter in Erwägung gezogen, die tatsächlich zwei Zustands Werte sind und einfach zum Initialisieren von booleschen Eigenschaften verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-121">✔️ CONSIDER using Booleans for constructor parameters that are truly two-state values and are simply used to initialize Boolean properties.</span></span>

### <a name="validating-arguments"></a><span data-ttu-id="ebbfa-122">Validieren von Argumenten</span><span class="sxs-lookup"><span data-stu-id="ebbfa-122">Validating Arguments</span></span>
 <span data-ttu-id="ebbfa-123">✔️ Überprüfen Sie Argumente, die an öffentliche, geschützte oder explizit implementierte Member übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-123">✔️ DO validate arguments passed to public, protected, or explicitly implemented members.</span></span> <span data-ttu-id="ebbfa-124">Throw <xref:System.ArgumentException?displayProperty=nameWithType> oder eine der zugehörigen Unterklassen, wenn die Validierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-124">Throw <xref:System.ArgumentException?displayProperty=nameWithType>, or one of its subclasses, if the validation fails.</span></span>

 <span data-ttu-id="ebbfa-125">Beachten Sie, dass die tatsächliche Validierung nicht unbedingt im öffentlichen oder geschützten Member selbst erfolgen muss.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-125">Note that the actual validation does not necessarily have to happen in the public or protected member itself.</span></span> <span data-ttu-id="ebbfa-126">Dies kann in einer privaten oder internen Routine auf einer niedrigeren Ebene vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-126">It could happen at a lower level in some private or internal routine.</span></span> <span data-ttu-id="ebbfa-127">Der Hauptgrund dafür ist, dass die gesamte Oberfläche, die den Endbenutzern zur Verfügung gestellt wird, die Argumente prüft.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-127">The main point is that the entire surface area that is exposed to the end users checks the arguments.</span></span>

 <span data-ttu-id="ebbfa-128">✔️ lösen Sie aus, <xref:System.ArgumentNullException> Wenn ein NULL-Argument übergeben wird und der Member keine NULL-Argumente unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-128">✔️ DO throw <xref:System.ArgumentNullException> if a null argument is passed and the member does not support null arguments.</span></span>

 <span data-ttu-id="ebbfa-129">✔️ Überprüfen Sie die Aufzählungs Parameter.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-129">✔️ DO validate enum parameters.</span></span>

 <span data-ttu-id="ebbfa-130">Gehen Sie nicht davon aus, dass sich die Aufzählungs Argumente in dem von der-Aufzählung definierten Bereich befinden.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-130">Do not assume enum arguments will be in the range defined by the enum.</span></span> <span data-ttu-id="ebbfa-131">Die CLR ermöglicht das Umwandeln eines beliebigen ganzzahligen Werts in einen Enumerationswert, auch wenn der Wert nicht in der Enumeration definiert ist.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-131">The CLR allows casting any integer value into an enum value even if the value is not defined in the enum.</span></span>

 <span data-ttu-id="ebbfa-132">❌ Verwenden Sie nicht für Aufzählungs <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> Bereichs Überprüfungen.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-132">❌ DO NOT use <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> for enum range checks.</span></span>

 <span data-ttu-id="ebbfa-133">✔️ Beachten Sie, dass änderbare Argumente möglicherweise geändert wurden, nachdem Sie überprüft wurden.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-133">✔️ DO be aware that mutable arguments might have changed after they were validated.</span></span>

 <span data-ttu-id="ebbfa-134">Wenn der Member Sicherheits sensibel ist, wird empfohlen, eine Kopie zu erstellen und dann das Argument zu validieren und zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-134">If the member is security sensitive, you are encouraged to make a copy and then validate and process the argument.</span></span>

### <a name="parameter-passing"></a><span data-ttu-id="ebbfa-135">Parameterübergabe</span><span class="sxs-lookup"><span data-stu-id="ebbfa-135">Parameter Passing</span></span>
 <span data-ttu-id="ebbfa-136">Aus der Perspektive eines Framework-Designers besteht aus drei Hauptgruppen von Parametern: nach Wert Parametern, `ref` Parametern und `out` Parametern.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-136">From the perspective of a framework designer, there are three main groups of parameters: by-value parameters, `ref` parameters, and `out` parameters.</span></span>

 <span data-ttu-id="ebbfa-137">Wenn ein Argument durch einen by-value-Parameter übergeben wird, empfängt der Member eine Kopie des tatsächlich übergebenen Arguments.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-137">When an argument is passed through a by-value parameter, the member receives a copy of the actual argument passed in.</span></span> <span data-ttu-id="ebbfa-138">Wenn das Argument ein Werttyp ist, wird eine Kopie des Arguments auf dem Stapel abgelegt.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-138">If the argument is a value type, a copy of the argument is put on the stack.</span></span> <span data-ttu-id="ebbfa-139">Wenn das Argument ein Referenztyp ist, wird eine Kopie des Verweises auf dem Stapel abgelegt.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-139">If the argument is a reference type, a copy of the reference is put on the stack.</span></span> <span data-ttu-id="ebbfa-140">Bei den beliebtesten CLR-Sprachen, wie z. b. c#, VB.net und C++, wird standardmäßig die Übergabe von Parametern nach Wert angegeben.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-140">Most popular CLR languages, such as C#, VB.NET, and C++, default to passing parameters by value.</span></span>

 <span data-ttu-id="ebbfa-141">Wenn ein Argument durch einen Parameter übergeben wird `ref` , erhält der Member einen Verweis auf das tatsächlich übergebene Argument.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-141">When an argument is passed through a `ref` parameter, the member receives a reference to the actual argument passed in.</span></span> <span data-ttu-id="ebbfa-142">Wenn das Argument ein Werttyp ist, wird ein Verweis auf das Argument auf dem Stapel abgelegt.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-142">If the argument is a value type, a reference to the argument is put on the stack.</span></span> <span data-ttu-id="ebbfa-143">Wenn es sich bei dem Argument um einen Verweistyp handelt, wird ein Verweis auf den Verweis auf den Stapel eingefügt.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-143">If the argument is a reference type, a reference to the reference is put on the stack.</span></span> <span data-ttu-id="ebbfa-144">`Ref` Parameter können verwendet werden, um zuzulassen, dass der Member vom Aufrufer übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-144">`Ref` parameters can be used to allow the member to modify arguments passed by the caller.</span></span>

 <span data-ttu-id="ebbfa-145">`Out` Parameter ähneln `ref` Parametern mit einigen kleinen unterschieden.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-145">`Out` parameters are similar to `ref` parameters, with some small differences.</span></span> <span data-ttu-id="ebbfa-146">Der-Parameter wird anfänglich als nicht zugewiesen betrachtet und kann nicht im Element Text gelesen werden, bevor ihm ein Wert zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-146">The parameter is initially considered unassigned and cannot be read in the member body before it is assigned some value.</span></span> <span data-ttu-id="ebbfa-147">Außerdem muss dem-Parameter ein Wert zugewiesen werden, bevor der Member zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-147">Also, the parameter has to be assigned some value before the member returns.</span></span>

 <span data-ttu-id="ebbfa-148">❌ Verwenden Sie keine- `out` oder- `ref` Parameter.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-148">❌ AVOID using `out` or `ref` parameters.</span></span>

 <span data-ttu-id="ebbfa-149">Die `out` Verwendung `ref` von-oder-Parametern erfordert die Verwendung von Zeigern, die Unterschiede zwischen Werttypen und Verweis Typen sowie die Behandlung von Methoden mit mehreren Rückgabe Werten</span><span class="sxs-lookup"><span data-stu-id="ebbfa-149">Using `out` or `ref` parameters requires experience with pointers, understanding how value types and reference types differ, and handling methods with multiple return values.</span></span> <span data-ttu-id="ebbfa-150">Außerdem wird der Unterschied zwischen `out` -und- `ref` Parametern nicht häufig verstanden.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-150">Also, the difference between `out` and `ref` parameters is not widely understood.</span></span> <span data-ttu-id="ebbfa-151">Frameworkarchitekten, die für eine allgemeine Zielgruppe entwerfen, sollten nicht erwarten, dass Benutzer mit- `out` oder- `ref` Parametern arbeiten</span><span class="sxs-lookup"><span data-stu-id="ebbfa-151">Framework architects designing for a general audience should not expect users to master working with `out` or `ref` parameters.</span></span>

 <span data-ttu-id="ebbfa-152">❌ Übergeben Sie Verweis Typen nicht als Verweis.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-152">❌ DO NOT pass reference types by reference.</span></span>

 <span data-ttu-id="ebbfa-153">Es gibt einige begrenzte Ausnahmen für die Regel, z. b. eine Methode, die zum Austauschen von Verweisen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-153">There are some limited exceptions to the rule, such as a method that can be used to swap references.</span></span>

### <a name="members-with-variable-number-of-parameters"></a><span data-ttu-id="ebbfa-154">Elemente mit variabler Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="ebbfa-154">Members with Variable Number of Parameters</span></span>
 <span data-ttu-id="ebbfa-155">Member, die eine Variable Anzahl von Argumenten annehmen können, werden durch Angabe eines Array Parameters ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-155">Members that can take a variable number of arguments are expressed by providing an array parameter.</span></span> <span data-ttu-id="ebbfa-156">Beispielsweise <xref:System.String> stellt die folgende Methode bereit:</span><span class="sxs-lookup"><span data-stu-id="ebbfa-156">For example, <xref:System.String> provides the following method:</span></span>

```csharp
public class String {
    public static string Format(string format, object[] parameters);
}
```

 <span data-ttu-id="ebbfa-157">Ein Benutzer kann dann die- <xref:System.String.Format%2A?displayProperty=nameWithType> Methode wie folgt aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="ebbfa-157">A user can then call the <xref:System.String.Format%2A?displayProperty=nameWithType> method, as follows:</span></span>

 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`

 <span data-ttu-id="ebbfa-158">Wenn Sie das c#-params-Schlüsselwort zu einem Array-Parameter hinzufügen, wird der Parameter in einen sogenannten params-Array Parameter geändert und eine Verknüpfung zur Erstellung eines temporären Arrays bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-158">Adding the C# params keyword to an array parameter changes the parameter to a so-called params array parameter and provides a shortcut to creating a temporary array.</span></span>

```csharp
public class String {
    public static string Format(string format, params object[] parameters);
}
```

 <span data-ttu-id="ebbfa-159">Dadurch kann der Benutzer die Methode aufzurufen, indem er die Array Elemente direkt in der Argumentliste übergibt.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-159">Doing this allows the user to call the method by passing the array elements directly in the argument list.</span></span>

 `String.Format("File {0} not found in {1}",filename,directory);`

 <span data-ttu-id="ebbfa-160">Beachten Sie, dass das parameterschlüsselwort nur dem letzten Parameter in der Parameterliste hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-160">Note that the params keyword can be added only to the last parameter in the parameter list.</span></span>

 <span data-ttu-id="ebbfa-161">✔️ Sie ggf. das params-Schlüsselwort zu Array Parametern hinzufügen, wenn Sie erwarten, dass die Endbenutzer Arrays mit einer kleinen Anzahl von Elementen übergeben.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-161">✔️ CONSIDER adding the params keyword to array parameters if you expect the end users to pass arrays with a small number of elements.</span></span> <span data-ttu-id="ebbfa-162">Wenn davon ausgegangen wird, dass viele Elemente in gängigen Szenarien übergeben werden, werden diese Elemente wahrscheinlich nicht von den Benutzern Inline übergeben, sodass das params-Schlüsselwort nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-162">If it's expected that lots of elements will be passed in common scenarios, users will probably not pass these elements inline anyway, and so the params keyword is not necessary.</span></span>

 <span data-ttu-id="ebbfa-163">❌ Vermeiden Sie die Verwendung von params-Arrays, wenn der Aufrufer fast immer die Eingabe in einem Array haben würde.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-163">❌ AVOID using params arrays if the caller would almost always have the input already in an array.</span></span>

 <span data-ttu-id="ebbfa-164">Beispielsweise werden Elemente mit Bytearray-Parametern fast nie aufgerufen, indem einzelne Bytes übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-164">For example, members with byte array parameters would almost never be called by passing individual bytes.</span></span> <span data-ttu-id="ebbfa-165">Aus diesem Grund verwenden Bytearray-Parameter im .NET Framework nicht das params-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-165">For this reason, byte array parameters in the .NET Framework do not use the params keyword.</span></span>

 <span data-ttu-id="ebbfa-166">❌ Verwenden Sie keine params-Arrays, wenn das Array durch den Member geändert wird, der den Parameter "params Array" annimmt.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-166">❌ DO NOT use params arrays if the array is modified by the member taking the params array parameter.</span></span>

 <span data-ttu-id="ebbfa-167">Aufgrund der Tatsache, dass viele Compiler die Argumente für den Member in ein temporäres Array an der aufrufssite umwandeln, kann das Array ein temporäres Objekt sein. Daher gehen alle Änderungen am Array verloren.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-167">Because of the fact that many compilers turn the arguments to the member into a temporary array at the call site, the array might be a temporary object, and therefore any modifications to the array will be lost.</span></span>

 <span data-ttu-id="ebbfa-168">✔️ in Erwägung gezogen, das Schlüsselwort "para" in einer einfachen Überladung zu verwenden, auch wenn es von einer komplexeren Überladung nicht verwendet werden konnte.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-168">✔️ CONSIDER using the params keyword in a simple overload, even if a more complex overload could not use it.</span></span>

 <span data-ttu-id="ebbfa-169">Fragen Sie sich, ob Benutzer den Wert des params-Arrays in einer Überladung haben würden, auch wenn Sie nicht in allen über Ladungen vorhanden wäre.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-169">Ask yourself if users would value having the params array in one overload even if it wasn't in all overloads.</span></span>

 <span data-ttu-id="ebbfa-170">✔️ versuchen, Parameter zu sortieren, um die Verwendung des Schlüssel Worts "Parameter" zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-170">✔️ DO try to order parameters to make it possible to use the params keyword.</span></span>

 <span data-ttu-id="ebbfa-171">✔️ sollten Sie besondere über Ladungen und Codepfade für Aufrufe mit einer kleinen Anzahl von Argumenten in äußerst Leistungs relevanten APIs bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-171">✔️ CONSIDER providing special overloads and code paths for calls with a small number of arguments in extremely performance-sensitive APIs.</span></span>

 <span data-ttu-id="ebbfa-172">Dadurch ist es möglich, keine Array Objekte zu erstellen, wenn die API mit einer kleinen Anzahl von Argumenten aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-172">This makes it possible to avoid creating array objects when the API is called with a small number of arguments.</span></span> <span data-ttu-id="ebbfa-173">Bilden Sie die Namen der Parameter, indem Sie eine Singular Form des Array-Parameters und ein numerisches Suffix hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-173">Form the names of the parameters by taking a singular form of the array parameter and adding a numeric suffix.</span></span>

 <span data-ttu-id="ebbfa-174">Dies sollten Sie nur tun, wenn Sie den gesamten Codepfad als Sonderfall verwenden, nicht nur ein Array erstellen und die allgemeinere Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-174">You should only do this if you are going to special-case the entire code path, not just create an array and call the more general method.</span></span>

 <span data-ttu-id="ebbfa-175">✔️ Beachten Sie, dass NULL als params-Array Argument übermittelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-175">✔️ DO be aware that null could be passed as a params array argument.</span></span>

 <span data-ttu-id="ebbfa-176">Vor der Verarbeitung sollten Sie überprüfen, ob das Array nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-176">You should validate that the array is not null before processing.</span></span>

 <span data-ttu-id="ebbfa-177">❌ Verwenden Sie die- `varargs` Methoden, die auch als Ellipsen bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-177">❌ DO NOT use the `varargs` methods, otherwise known as the ellipsis.</span></span>

 <span data-ttu-id="ebbfa-178">Einige CLR-Sprachen, wie z. b. C++, unterstützen eine alternative Konvention zum Übergeben von Variablen Parameterlisten mit dem Namen `varargs` Methoden.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-178">Some CLR languages, such as C++, support an alternative convention for passing variable parameter lists called `varargs` methods.</span></span> <span data-ttu-id="ebbfa-179">Die Konvention sollte nicht in Frameworks verwendet werden, da Sie nicht CLS-kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-179">The convention should not be used in frameworks, because it is not CLS compliant.</span></span>

### <a name="pointer-parameters"></a><span data-ttu-id="ebbfa-180">Zeigerparameter</span><span class="sxs-lookup"><span data-stu-id="ebbfa-180">Pointer Parameters</span></span>
 <span data-ttu-id="ebbfa-181">Im Allgemeinen sollten Zeiger nicht in der öffentlichen Oberfläche eines gut entworfenen verwalteten Code-Frameworks angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-181">In general, pointers should not appear in the public surface area of a well-designed managed code framework.</span></span> <span data-ttu-id="ebbfa-182">In den meisten Fällen sollten Zeiger gekapselt werden.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-182">Most of the time, pointers should be encapsulated.</span></span> <span data-ttu-id="ebbfa-183">In einigen Fällen sind Zeiger aber aus Interoperabilitäts Gründen erforderlich, und die Verwendung von Zeigern in solchen Fällen ist angemessen.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-183">However, in some cases pointers are required for interoperability reasons, and using pointers in such cases is appropriate.</span></span>

 <span data-ttu-id="ebbfa-184">✔️ eine Alternative für alle Member bereitstellen, die ein Zeigerargument verwenden, da Zeiger nicht CLS-kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-184">✔️ DO provide an alternative for any member that takes a pointer argument, because pointers are not CLS-compliant.</span></span>

 <span data-ttu-id="ebbfa-185">❌ Vermeiden Sie eine teure Argument Überprüfung von Zeiger Argumenten.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-185">❌ AVOID doing expensive argument checking of pointer arguments.</span></span>

 <span data-ttu-id="ebbfa-186">beim Entwerfen von Membern mit Zeigern folgen ✔️ allgemeinen Zeiger bezogenen Konventionen.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-186">✔️ DO follow common pointer-related conventions when designing members with pointers.</span></span>

 <span data-ttu-id="ebbfa-187">Beispielsweise ist es nicht erforderlich, den Start Index zu übergeben, da einfache Zeigerarithmetik verwendet werden kann, um das gleiche Ergebnis zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-187">For example, there is no need to pass the start index, because simple pointer arithmetic can be used to accomplish the same result.</span></span>

 <span data-ttu-id="ebbfa-188">*Teile &copy; 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="ebbfa-188">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="ebbfa-189">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="ebbfa-189">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="ebbfa-190">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebbfa-190">See also</span></span>

- [<span data-ttu-id="ebbfa-191">Entwurfs Richtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="ebbfa-191">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="ebbfa-192">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="ebbfa-192">Framework Design Guidelines</span></span>](index.md)
