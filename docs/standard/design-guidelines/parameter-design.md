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
author: KrzysztofCwalina
ms.openlocfilehash: 28b00f5911bb47536ec44b96f284e47b6c671149
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71353740"
---
# <a name="parameter-design"></a><span data-ttu-id="c7e20-102">Parameterentwurf</span><span class="sxs-lookup"><span data-stu-id="c7e20-102">Parameter Design</span></span>
<span data-ttu-id="c7e20-103">Dieser Abschnitt enthält allgemeine Richtlinien zum Parameter Entwurf, einschließlich Abschnitten mit Richtlinien zum Überprüfen von Argumenten.</span><span class="sxs-lookup"><span data-stu-id="c7e20-103">This section provides broad guidelines on parameter design, including sections with guidelines for checking arguments.</span></span> <span data-ttu-id="c7e20-104">Außerdem sollten Sie die in [Benennungs Parametern](../../../docs/standard/design-guidelines/naming-parameters.md)beschriebenen Richtlinien beachten.</span><span class="sxs-lookup"><span data-stu-id="c7e20-104">In addition, you should refer to the guidelines described in [Naming Parameters](../../../docs/standard/design-guidelines/naming-parameters.md).</span></span>  
  
 <span data-ttu-id="c7e20-105">**✓ DO** verwenden, der am wenigsten abgeleiteten Parametertyp, die die Funktionen für das Element bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c7e20-105">**✓ DO** use the least derived parameter type that provides the functionality required by the member.</span></span>  
  
 <span data-ttu-id="c7e20-106">Angenommen, Sie möchten eine Methode entwerfen, die eine Auflistung auflistet und jedes Element in der Konsole ausgibt.</span><span class="sxs-lookup"><span data-stu-id="c7e20-106">For example, suppose you want to design a method that enumerates a collection and prints each item to the console.</span></span> <span data-ttu-id="c7e20-107">Eine solche Methode sollte z. b. <xref:System.Collections.IEnumerable> als Parameter, nicht jedoch <xref:System.Collections.ArrayList> oder <xref:System.Collections.IList>annehmen.</span><span class="sxs-lookup"><span data-stu-id="c7e20-107">Such a method should take <xref:System.Collections.IEnumerable> as the parameter, not <xref:System.Collections.ArrayList> or <xref:System.Collections.IList>, for example.</span></span>  
  
 <span data-ttu-id="c7e20-108">**X DO NOT** reservierte Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7e20-108">**X DO NOT** use reserved parameters.</span></span>  
  
 <span data-ttu-id="c7e20-109">Wenn in einer zukünftigen Version mehr Eingaben für einen Member erforderlich sind, kann eine neue Überladung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c7e20-109">If more input to a member is needed in some future version, a new overload can be added.</span></span>  
  
 <span data-ttu-id="c7e20-110">**X DO NOT** haben öffentlich verfügbar gemachten Methoden, die Zeiger, Arrays von Zeigern oder mehrdimensionale Arrays als Parameter akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="c7e20-110">**X DO NOT** have publicly exposed methods that take pointers, arrays of pointers, or multidimensional arrays as parameters.</span></span>  
  
 <span data-ttu-id="c7e20-111">Zeiger und mehrdimensionale Arrays sind relativ schwierig zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7e20-111">Pointers and multidimensional arrays are relatively difficult to use properly.</span></span> <span data-ttu-id="c7e20-112">In fast allen Fällen können APIs umgestaltet werden, um zu vermeiden, dass diese Typen als Parameter übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="c7e20-112">In almost all cases, APIs can be redesigned to avoid taking these types as parameters.</span></span>  
  
 <span data-ttu-id="c7e20-113">**✓ DO** platzieren Sie alle `out` Parameter, die alle per-Wert und `ref` Parameter (ausgenommen Parameterarrays), auch wenn dies zu einer Inkonsistenz der Sortierung zwischen Überladungen Parameter führt (finden Sie unter [Member Überladen von](../../../docs/standard/design-guidelines/member-overloading.md)).</span><span class="sxs-lookup"><span data-stu-id="c7e20-113">**✓ DO** place all `out` parameters following all of the by-value and `ref` parameters (excluding parameter arrays), even if it results in an inconsistency in parameter ordering between overloads (see [Member Overloading](../../../docs/standard/design-guidelines/member-overloading.md)).</span></span>  
  
 <span data-ttu-id="c7e20-114">Die `out` Parameter können als zusätzliche Rückgabewerte angesehen werden, und durch Gruppierung werden die Methoden Signaturen leichter zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="c7e20-114">The `out` parameters can be seen as extra return values, and grouping them together makes the method signature easier to understand.</span></span>  
  
 <span data-ttu-id="c7e20-115">**✓ DO** benennen Parameter aus, wenn Sie Member überschreiben oder Implementieren von Schnittstellenmembern konsistent sein.</span><span class="sxs-lookup"><span data-stu-id="c7e20-115">**✓ DO** be consistent in naming parameters when overriding members or implementing interface members.</span></span>  
  
 <span data-ttu-id="c7e20-116">Dadurch wird die Beziehung zwischen den Methoden besser kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="c7e20-116">This better communicates the relationship between the methods.</span></span>  
  
### <a name="choosing-between-enum-and-boolean-parameters"></a><span data-ttu-id="c7e20-117">Auswählen zwischen Aufzählungs-und booleschen Parametern</span><span class="sxs-lookup"><span data-stu-id="c7e20-117">Choosing Between Enum and Boolean Parameters</span></span>  
 <span data-ttu-id="c7e20-118">**✓ DO** Enumerationen verwenden, wenn ein Element mindestens zwei boolesche Parameter hätten.</span><span class="sxs-lookup"><span data-stu-id="c7e20-118">**✓ DO** use enums if a member would otherwise have two or more Boolean parameters.</span></span>  
  
 <span data-ttu-id="c7e20-119">**X DO NOT** boolesche Werte verwenden, es sei denn, Sie absolut sicher, dass es werden nie mehr als zwei Werte erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c7e20-119">**X DO NOT** use Booleans unless you are absolutely sure there will never be a need for more than two values.</span></span>  
  
 <span data-ttu-id="c7e20-120">Enumerationen geben Ihnen einen gewissen Raum für eine zukünftige Addition von Werten. Sie sollten jedoch alle Implikationen beachten, die sich aus dem Hinzufügen von Werten zu Enumerationen machen, die im [Enumerationsentwurf](../../../docs/standard/design-guidelines/enum.md)beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="c7e20-120">Enums give you some room for future addition of values, but you should be aware of all the implications of adding values to enums, which are described in [Enum Design](../../../docs/standard/design-guidelines/enum.md).</span></span>  
  
 <span data-ttu-id="c7e20-121">**✓ CONSIDER** mit boolesche Werte für Konstruktorparameter, die tatsächlich zwei-Status-Werte sind und zur Initialisierung von boolescher Eigenschaften, die einfach verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c7e20-121">**✓ CONSIDER** using Booleans for constructor parameters that are truly two-state values and are simply used to initialize Boolean properties.</span></span>  
  
### <a name="validating-arguments"></a><span data-ttu-id="c7e20-122">Validieren von Argumenten</span><span class="sxs-lookup"><span data-stu-id="c7e20-122">Validating Arguments</span></span>  
 <span data-ttu-id="c7e20-123">**✓ DO** weitergegebenen Argumenten um öffentlich, geschützt oder explizit implementierten Member zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c7e20-123">**✓ DO** validate arguments passed to public, protected, or explicitly implemented members.</span></span> <span data-ttu-id="c7e20-124">Lösen Sie <xref:System.ArgumentException?displayProperty=nameWithType>oder eine der zugehörigen Unterklassen aus, wenn die Validierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="c7e20-124">Throw <xref:System.ArgumentException?displayProperty=nameWithType>, or one of its subclasses, if the validation fails.</span></span>  
  
 <span data-ttu-id="c7e20-125">Beachten Sie, dass die tatsächliche Validierung nicht unbedingt im öffentlichen oder geschützten Member selbst erfolgen muss.</span><span class="sxs-lookup"><span data-stu-id="c7e20-125">Note that the actual validation does not necessarily have to happen in the public or protected member itself.</span></span> <span data-ttu-id="c7e20-126">Dies kann in einer privaten oder internen Routine auf einer niedrigeren Ebene vorkommen.</span><span class="sxs-lookup"><span data-stu-id="c7e20-126">It could happen at a lower level in some private or internal routine.</span></span> <span data-ttu-id="c7e20-127">Der Hauptgrund dafür ist, dass die gesamte Oberfläche, die den Endbenutzern zur Verfügung gestellt wird, die Argumente prüft.</span><span class="sxs-lookup"><span data-stu-id="c7e20-127">The main point is that the entire surface area that is exposed to the end users checks the arguments.</span></span>  
  
 <span data-ttu-id="c7e20-128">**✓ DO** auslösen <xref:System.ArgumentNullException> Wenn ein null-Argument übergeben wird und das Element keine null-Argumente unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c7e20-128">**✓ DO** throw <xref:System.ArgumentNullException> if a null argument is passed and the member does not support null arguments.</span></span>  
  
 <span data-ttu-id="c7e20-129">**✓ DO** Enum-Parameter überprüft.</span><span class="sxs-lookup"><span data-stu-id="c7e20-129">**✓ DO** validate enum parameters.</span></span>  
  
 <span data-ttu-id="c7e20-130">Gehen Sie nicht davon aus, dass sich die Aufzählungs Argumente in dem von der-Aufzählung definierten Bereich befinden.</span><span class="sxs-lookup"><span data-stu-id="c7e20-130">Do not assume enum arguments will be in the range defined by the enum.</span></span> <span data-ttu-id="c7e20-131">Die CLR ermöglicht das Umwandeln eines beliebigen ganzzahligen Werts in einen Enumerationswert, auch wenn der Wert nicht in der Enumeration definiert ist.</span><span class="sxs-lookup"><span data-stu-id="c7e20-131">The CLR allows casting any integer value into an enum value even if the value is not defined in the enum.</span></span>  
  
 <span data-ttu-id="c7e20-132">**X DO NOT** verwenden <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> für Enum Bereich überprüft.</span><span class="sxs-lookup"><span data-stu-id="c7e20-132">**X DO NOT** use <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> for enum range checks.</span></span>  
  
 <span data-ttu-id="c7e20-133">**✓ DO** Beachten Sie, dass änderbare Argumente möglicherweise geändert wurden, nachdem sie überprüft wurden.</span><span class="sxs-lookup"><span data-stu-id="c7e20-133">**✓ DO** be aware that mutable arguments might have changed after they were validated.</span></span>  
  
 <span data-ttu-id="c7e20-134">Wenn der Member Sicherheits sensibel ist, wird empfohlen, eine Kopie zu erstellen und dann das Argument zu validieren und zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c7e20-134">If the member is security sensitive, you are encouraged to make a copy and then validate and process the argument.</span></span>  
  
### <a name="parameter-passing"></a><span data-ttu-id="c7e20-135">Parameterübergabe</span><span class="sxs-lookup"><span data-stu-id="c7e20-135">Parameter Passing</span></span>  
 <span data-ttu-id="c7e20-136">Aus Sicht eines Framework-Designers gibt es drei Hauptgruppen von Parametern: nach Wert Parameter, `ref` Parameter und `out` Parameter.</span><span class="sxs-lookup"><span data-stu-id="c7e20-136">From the perspective of a framework designer, there are three main groups of parameters: by-value parameters, `ref` parameters, and `out` parameters.</span></span>  
  
 <span data-ttu-id="c7e20-137">Wenn ein Argument durch einen by-value-Parameter übergeben wird, empfängt der Member eine Kopie des tatsächlich übergebenen Arguments.</span><span class="sxs-lookup"><span data-stu-id="c7e20-137">When an argument is passed through a by-value parameter, the member receives a copy of the actual argument passed in.</span></span> <span data-ttu-id="c7e20-138">Wenn das Argument ein Werttyp ist, wird eine Kopie des Arguments auf dem Stapel abgelegt.</span><span class="sxs-lookup"><span data-stu-id="c7e20-138">If the argument is a value type, a copy of the argument is put on the stack.</span></span> <span data-ttu-id="c7e20-139">Wenn das Argument ein Referenztyp ist, wird eine Kopie des Verweises auf dem Stapel abgelegt.</span><span class="sxs-lookup"><span data-stu-id="c7e20-139">If the argument is a reference type, a copy of the reference is put on the stack.</span></span> <span data-ttu-id="c7e20-140">Die gängigsten CLR-Sprachen, C#wie z. b C++., VB.net und, übergeben standardmäßig Parameter nach Wert.</span><span class="sxs-lookup"><span data-stu-id="c7e20-140">Most popular CLR languages, such as C#, VB.NET, and C++, default to passing parameters by value.</span></span>  
  
 <span data-ttu-id="c7e20-141">Wenn ein Argument über einen `ref`-Parameter übergeben wird, empfängt der Member einen Verweis auf das tatsächlich übergebene Argument.</span><span class="sxs-lookup"><span data-stu-id="c7e20-141">When an argument is passed through a `ref` parameter, the member receives a reference to the actual argument passed in.</span></span> <span data-ttu-id="c7e20-142">Wenn das Argument ein Werttyp ist, wird ein Verweis auf das Argument auf dem Stapel abgelegt.</span><span class="sxs-lookup"><span data-stu-id="c7e20-142">If the argument is a value type, a reference to the argument is put on the stack.</span></span> <span data-ttu-id="c7e20-143">Wenn es sich bei dem Argument um einen Verweistyp handelt, wird ein Verweis auf den Verweis auf den Stapel eingefügt.</span><span class="sxs-lookup"><span data-stu-id="c7e20-143">If the argument is a reference type, a reference to the reference is put on the stack.</span></span> <span data-ttu-id="c7e20-144">`Ref` Parameter können verwendet werden, um zuzulassen, dass der Member vom Aufrufer übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="c7e20-144">`Ref` parameters can be used to allow the member to modify arguments passed by the caller.</span></span>  
  
 <span data-ttu-id="c7e20-145">`Out` Parameter ähneln `ref` Parametern, mit einigen kleinen unterschieden.</span><span class="sxs-lookup"><span data-stu-id="c7e20-145">`Out` parameters are similar to `ref` parameters, with some small differences.</span></span> <span data-ttu-id="c7e20-146">Der-Parameter wird anfänglich als nicht zugewiesen betrachtet und kann nicht im Element Text gelesen werden, bevor ihm ein Wert zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c7e20-146">The parameter is initially considered unassigned and cannot be read in the member body before it is assigned some value.</span></span> <span data-ttu-id="c7e20-147">Außerdem muss dem-Parameter ein Wert zugewiesen werden, bevor der Member zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c7e20-147">Also, the parameter has to be assigned some value before the member returns.</span></span>  
  
 <span data-ttu-id="c7e20-148">**X AVOID** mit `out` oder `ref` Parameter.</span><span class="sxs-lookup"><span data-stu-id="c7e20-148">**X AVOID** using `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="c7e20-149">Die Verwendung von `out`-oder `ref`-Parametern erfordert die Verwendung von Zeigern, das Verständnis der Unterschiede zwischen Werttypen und Verweis Typen sowie die Behandlung von Methoden mit mehreren</span><span class="sxs-lookup"><span data-stu-id="c7e20-149">Using `out` or `ref` parameters requires experience with pointers, understanding how value types and reference types differ, and handling methods with multiple return values.</span></span> <span data-ttu-id="c7e20-150">Außerdem wird der Unterschied zwischen `out`-und `ref`-Parametern nicht weitgehend verstanden.</span><span class="sxs-lookup"><span data-stu-id="c7e20-150">Also, the difference between `out` and `ref` parameters is not widely understood.</span></span> <span data-ttu-id="c7e20-151">Frameworkarchitekten, die für eine allgemeine Zielgruppe entwerfen, sollten nicht erwarten, dass Benutzer mit `out`-oder `ref`-Parametern arbeiten.</span><span class="sxs-lookup"><span data-stu-id="c7e20-151">Framework architects designing for a general audience should not expect users to master working with `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="c7e20-152">**X DO NOT** Verweistypen als Verweis übergeben.</span><span class="sxs-lookup"><span data-stu-id="c7e20-152">**X DO NOT** pass reference types by reference.</span></span>  
  
 <span data-ttu-id="c7e20-153">Es gibt einige begrenzte Ausnahmen für die Regel, z. b. eine Methode, die zum Austauschen von Verweisen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c7e20-153">There are some limited exceptions to the rule, such as a method that can be used to swap references.</span></span>  
  
### <a name="members-with-variable-number-of-parameters"></a><span data-ttu-id="c7e20-154">Elemente mit variabler Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="c7e20-154">Members with Variable Number of Parameters</span></span>  
 <span data-ttu-id="c7e20-155">Member, die eine Variable Anzahl von Argumenten annehmen können, werden durch Angabe eines Array Parameters ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="c7e20-155">Members that can take a variable number of arguments are expressed by providing an array parameter.</span></span> <span data-ttu-id="c7e20-156"><xref:System.String> stellt z. b. die folgende Methode bereit:</span><span class="sxs-lookup"><span data-stu-id="c7e20-156">For example, <xref:System.String> provides the following method:</span></span>  
  
```csharp  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 <span data-ttu-id="c7e20-157">Ein Benutzer kann dann die <xref:System.String.Format%2A?displayProperty=nameWithType>-Methode wie folgt aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="c7e20-157">A user can then call the <xref:System.String.Format%2A?displayProperty=nameWithType> method, as follows:</span></span>  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 <span data-ttu-id="c7e20-158">Durch das C# Hinzufügen des params-Schlüssel Worts zu einem Array Parameter wird der Parameter in einen sogenannten params-Array Parameter geändert und eine Verknüpfung zur Erstellung eines temporären Arrays bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c7e20-158">Adding the C# params keyword to an array parameter changes the parameter to a so-called params array parameter and provides a shortcut to creating a temporary array.</span></span>  
  
```csharp  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 <span data-ttu-id="c7e20-159">Dadurch kann der Benutzer die Methode aufzurufen, indem er die Array Elemente direkt in der Argumentliste übergibt.</span><span class="sxs-lookup"><span data-stu-id="c7e20-159">Doing this allows the user to call the method by passing the array elements directly in the argument list.</span></span>  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 <span data-ttu-id="c7e20-160">Beachten Sie, dass das parameterschlüsselwort nur dem letzten Parameter in der Parameterliste hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c7e20-160">Note that the params keyword can be added only to the last parameter in the parameter list.</span></span>  
  
 <span data-ttu-id="c7e20-161">**✓ CONSIDER** Arrayparameter des Params-Schlüsselworts hinzugefügt, wenn Sie davon ausgehen, die Endbenutzer zum Übergeben von Arrays mit einer kleinen Anzahl von Elementen dass.</span><span class="sxs-lookup"><span data-stu-id="c7e20-161">**✓ CONSIDER** adding the params keyword to array parameters if you expect the end users to pass arrays with a small number of elements.</span></span> <span data-ttu-id="c7e20-162">Wenn davon ausgegangen wird, dass viele Elemente in gängigen Szenarien übergeben werden, werden diese Elemente wahrscheinlich nicht von den Benutzern Inline übergeben, sodass das params-Schlüsselwort nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c7e20-162">If it’s expected that lots of elements will be passed in common scenarios, users will probably not pass these elements inline anyway, and so the params keyword is not necessary.</span></span>  
  
 <span data-ttu-id="c7e20-163">**X AVOID** Params-Arrays verwenden, wenn ein Aufrufer fast immer die Eingabe bereits in einem Array würde.</span><span class="sxs-lookup"><span data-stu-id="c7e20-163">**X AVOID** using params arrays if the caller would almost always have the input already in an array.</span></span>  
  
 <span data-ttu-id="c7e20-164">Beispielsweise werden Elemente mit Bytearray-Parametern fast nie aufgerufen, indem einzelne Bytes übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="c7e20-164">For example, members with byte array parameters would almost never be called by passing individual bytes.</span></span> <span data-ttu-id="c7e20-165">Aus diesem Grund verwenden Bytearray-Parameter im .NET Framework nicht das params-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="c7e20-165">For this reason, byte array parameters in the .NET Framework do not use the params keyword.</span></span>  
  
 <span data-ttu-id="c7e20-166">**X DO NOT** Params-Arrays verwenden, wenn das Array vom dauert des Params-Array Parameters-Element geändert wird.</span><span class="sxs-lookup"><span data-stu-id="c7e20-166">**X DO NOT** use params arrays if the array is modified by the member taking the params array parameter.</span></span>  
  
 <span data-ttu-id="c7e20-167">Aufgrund der Tatsache, dass viele Compiler die Argumente für den Member in ein temporäres Array an der aufrufssite umwandeln, kann das Array ein temporäres Objekt sein. Daher gehen alle Änderungen am Array verloren.</span><span class="sxs-lookup"><span data-stu-id="c7e20-167">Because of the fact that many compilers turn the arguments to the member into a temporary array at the call site, the array might be a temporary object, and therefore any modifications to the array will be lost.</span></span>  
  
 <span data-ttu-id="c7e20-168">**✓ CONSIDER** des Params-Schlüsselworts in einer einfachen Überladung verwenden, auch wenn eine komplexere Überladung, konnte ihn nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7e20-168">**✓ CONSIDER** using the params keyword in a simple overload, even if a more complex overload could not use it.</span></span>  
  
 <span data-ttu-id="c7e20-169">Fragen Sie sich, ob Benutzer den Wert des params-Arrays in einer Überladung haben würden, auch wenn Sie nicht in allen über Ladungen vorhanden wäre.</span><span class="sxs-lookup"><span data-stu-id="c7e20-169">Ask yourself if users would value having the params array in one overload even if it wasn’t in all overloads.</span></span>  
  
 <span data-ttu-id="c7e20-170">**✓ DO** versuchen, Order-Parameter, und es Ihnen ermöglicht mithilfe des Params-Schlüsselworts.</span><span class="sxs-lookup"><span data-stu-id="c7e20-170">**✓ DO** try to order parameters to make it possible to use the params keyword.</span></span>  
  
 <span data-ttu-id="c7e20-171">**✓ CONSIDER** spezielle Überladungen und Codepfade für Aufrufe mit einer kleinen Anzahl von Argumenten in extrem leistungsabhängigen-APIs bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c7e20-171">**✓ CONSIDER** providing special overloads and code paths for calls with a small number of arguments in extremely performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="c7e20-172">Dadurch ist es möglich, keine Array Objekte zu erstellen, wenn die API mit einer kleinen Anzahl von Argumenten aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c7e20-172">This makes it possible to avoid creating array objects when the API is called with a small number of arguments.</span></span> <span data-ttu-id="c7e20-173">Bilden Sie die Namen der Parameter, indem Sie eine Singular Form des Array-Parameters und ein numerisches Suffix hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c7e20-173">Form the names of the parameters by taking a singular form of the array parameter and adding a numeric suffix.</span></span>  
  
 <span data-ttu-id="c7e20-174">Dies sollten Sie nur tun, wenn Sie den gesamten Codepfad als Sonderfall verwenden, nicht nur ein Array erstellen und die allgemeinere Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c7e20-174">You should only do this if you are going to special-case the entire code path, not just create an array and call the more general method.</span></span>  
  
 <span data-ttu-id="c7e20-175">**✓ DO** Beachten Sie, dass Null kann als ein Params-Argument übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="c7e20-175">**✓ DO** be aware that null could be passed as a params array argument.</span></span>  
  
 <span data-ttu-id="c7e20-176">Vor der Verarbeitung sollten Sie überprüfen, ob das Array nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="c7e20-176">You should validate that the array is not null before processing.</span></span>  
  
 <span data-ttu-id="c7e20-177">**X DO NOT** verwenden die `varargs` Methoden, sogenannten mit den Auslassungspunkten.</span><span class="sxs-lookup"><span data-stu-id="c7e20-177">**X DO NOT** use the `varargs` methods, otherwise known as the ellipsis.</span></span>  
  
 <span data-ttu-id="c7e20-178">Einige CLR-Sprachen, wie C++z. b., unterstützen eine alternative Konvention zum Übergeben von Variablen Parameterlisten, die als `varargs` Methoden bezeichnet</span><span class="sxs-lookup"><span data-stu-id="c7e20-178">Some CLR languages, such as C++, support an alternative convention for passing variable parameter lists called `varargs` methods.</span></span> <span data-ttu-id="c7e20-179">Die Konvention sollte nicht in Frameworks verwendet werden, da Sie nicht CLS-kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="c7e20-179">The convention should not be used in frameworks, because it is not CLS compliant.</span></span>  
  
### <a name="pointer-parameters"></a><span data-ttu-id="c7e20-180">Zeigerparameter</span><span class="sxs-lookup"><span data-stu-id="c7e20-180">Pointer Parameters</span></span>  
 <span data-ttu-id="c7e20-181">Im Allgemeinen sollten Zeiger nicht in der öffentlichen Oberfläche eines gut entworfenen verwalteten Code-Frameworks angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c7e20-181">In general, pointers should not appear in the public surface area of a well-designed managed code framework.</span></span> <span data-ttu-id="c7e20-182">In den meisten Fällen sollten Zeiger gekapselt werden.</span><span class="sxs-lookup"><span data-stu-id="c7e20-182">Most of the time, pointers should be encapsulated.</span></span> <span data-ttu-id="c7e20-183">In einigen Fällen sind Zeiger aber aus Interoperabilitäts Gründen erforderlich, und die Verwendung von Zeigern in solchen Fällen ist angemessen.</span><span class="sxs-lookup"><span data-stu-id="c7e20-183">However, in some cases pointers are required for interoperability reasons, and using pointers in such cases is appropriate.</span></span>  
  
 <span data-ttu-id="c7e20-184">**✓ DO** bieten eine Alternative für ein Element, das ein Zeigerargument akzeptiert, da Zeiger nicht CLS-kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="c7e20-184">**✓ DO** provide an alternative for any member that takes a pointer argument, because pointers are not CLS-compliant.</span></span>  
  
 <span data-ttu-id="c7e20-185">**X AVOID** auf diese Weise die aufwändige Prüfung von Zeigerargumente Argument.</span><span class="sxs-lookup"><span data-stu-id="c7e20-185">**X AVOID** doing expensive argument checking of pointer arguments.</span></span>  
  
 <span data-ttu-id="c7e20-186">**✓ DO** Konventionen gemeinsamen Zeiger-bezogene beim Entwerfen der Member mit Zeigern.</span><span class="sxs-lookup"><span data-stu-id="c7e20-186">**✓ DO** follow common pointer-related conventions when designing members with pointers.</span></span>  
  
 <span data-ttu-id="c7e20-187">Beispielsweise ist es nicht erforderlich, den Start Index zu übergeben, da einfache Zeigerarithmetik verwendet werden kann, um das gleiche Ergebnis zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="c7e20-187">For example, there is no need to pass the start index, because simple pointer arithmetic can be used to accomplish the same result.</span></span>  
  
 <span data-ttu-id="c7e20-188">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="c7e20-188">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c7e20-189">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="c7e20-189">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7e20-190">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7e20-190">See also</span></span>

- [<span data-ttu-id="c7e20-191">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="c7e20-191">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="c7e20-192">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="c7e20-192">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
