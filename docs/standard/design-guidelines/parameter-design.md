---
title: Parameterentwurf
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea5311de8cef266af23b259d943568bfa95eaf72
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45964815"
---
# <a name="parameter-design"></a><span data-ttu-id="5f1c9-102">Parameterentwurf</span><span class="sxs-lookup"><span data-stu-id="5f1c9-102">Parameter Design</span></span>
<span data-ttu-id="5f1c9-103">Dieser Abschnitt enthält allgemeine Richtlinien zum parameterentwurf, einschließlich der Abschnitte mit Richtlinien für die Überprüfung der Argumente.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-103">This section provides broad guidelines on parameter design, including sections with guidelines for checking arguments.</span></span> <span data-ttu-id="5f1c9-104">Darüber hinaus, lesen Sie die Hinweise in [Naming Parameters](../../../docs/standard/design-guidelines/naming-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="5f1c9-104">In addition, you should refer to the guidelines described in [Naming Parameters](../../../docs/standard/design-guidelines/naming-parameters.md).</span></span>  
  
 <span data-ttu-id="5f1c9-105">**✓ DO** verwenden, der am wenigsten abgeleiteten Parametertyp, die die Funktionen für das Element bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-105">**✓ DO** use the least derived parameter type that provides the functionality required by the member.</span></span>  
  
 <span data-ttu-id="5f1c9-106">Nehmen wir beispielsweise an, dass eine Methode zu entwerfen, die Listet eine Auflistung, und jedes Element in der Konsole ausgegeben, werden soll.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-106">For example, suppose you want to design a method that enumerates a collection and prints each item to the console.</span></span> <span data-ttu-id="5f1c9-107">Eine solche Methode dauert <xref:System.Collections.IEnumerable> als Parameter nicht <xref:System.Collections.ArrayList> oder <xref:System.Collections.IList>, z. B.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-107">Such a method should take <xref:System.Collections.IEnumerable> as the parameter, not <xref:System.Collections.ArrayList> or <xref:System.Collections.IList>, for example.</span></span>  
  
 <span data-ttu-id="5f1c9-108">**X DO NOT** reservierte Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-108">**X DO NOT** use reserved parameters.</span></span>  
  
 <span data-ttu-id="5f1c9-109">Wenn mehr Eingabe, um ein Element in einer künftigen Version erforderlich ist, kann eine neue Überladung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-109">If more input to a member is needed in some future version, a new overload can be added.</span></span>  
  
 <span data-ttu-id="5f1c9-110">**X DO NOT** haben öffentlich verfügbar gemachten Methoden, die Zeiger, Arrays von Zeigern oder mehrdimensionale Arrays als Parameter akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-110">**X DO NOT** have publicly exposed methods that take pointers, arrays of pointers, or multidimensional arrays as parameters.</span></span>  
  
 <span data-ttu-id="5f1c9-111">Zeiger und mehrdimensionale Arrays sind relativ schwierig, ordnungsgemäß zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-111">Pointers and multidimensional arrays are relatively difficult to use properly.</span></span> <span data-ttu-id="5f1c9-112">In fast allen Fällen können APIs überarbeitet werden, um zu vermeiden, nehmen diese Typen als Parameter.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-112">In almost all cases, APIs can be redesigned to avoid taking these types as parameters.</span></span>  
  
 <span data-ttu-id="5f1c9-113">**✓ DO** platzieren Sie alle `out` Parameter, die alle per-Wert und `ref` Parameter (ausgenommen Parameterarrays), auch wenn dies zu einer Inkonsistenz der Sortierung zwischen Überladungen Parameter führt (finden Sie unter [Member Überladen von](../../../docs/standard/design-guidelines/member-overloading.md)).</span><span class="sxs-lookup"><span data-stu-id="5f1c9-113">**✓ DO** place all `out` parameters following all of the by-value and `ref` parameters (excluding parameter arrays), even if it results in an inconsistency in parameter ordering between overloads (see [Member Overloading](../../../docs/standard/design-guidelines/member-overloading.md)).</span></span>  
  
 <span data-ttu-id="5f1c9-114">Die `out` Parameter können als zusätzliche Werte angezeigt werden, und gruppieren sie die Signatur der Methode ist einfacher zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-114">The `out` parameters can be seen as extra return values, and grouping them together makes the method signature easier to understand.</span></span>  
  
 <span data-ttu-id="5f1c9-115">**✓ DO** benennen Parameter aus, wenn Sie Member überschreiben oder Implementieren von Schnittstellenmembern konsistent sein.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-115">**✓ DO** be consistent in naming parameters when overriding members or implementing interface members.</span></span>  
  
 <span data-ttu-id="5f1c9-116">Dies besser wird die Beziehung zwischen den Methoden kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-116">This better communicates the relationship between the methods.</span></span>  
  
### <a name="choosing-between-enum-and-boolean-parameters"></a><span data-ttu-id="5f1c9-117">Auswählen zwischen für Enumerationen und booleschen Parametern</span><span class="sxs-lookup"><span data-stu-id="5f1c9-117">Choosing Between Enum and Boolean Parameters</span></span>  
 <span data-ttu-id="5f1c9-118">**✓ DO** Enumerationen verwenden, wenn ein Element mindestens zwei boolesche Parameter hätten.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-118">**✓ DO** use enums if a member would otherwise have two or more Boolean parameters.</span></span>  
  
 <span data-ttu-id="5f1c9-119">**X DO NOT** boolesche Werte verwenden, es sei denn, Sie absolut sicher, dass es werden nie mehr als zwei Werte erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-119">**X DO NOT** use Booleans unless you are absolutely sure there will never be a need for more than two values.</span></span>  
  
 <span data-ttu-id="5f1c9-120">Enumerationen bieten Ihnen etwas Platz für zukünftige Hinzufügen von Werten, aber Sie sollten über alle Auswirkungen auf die Enumerationen, die in beschriebenen Werte hinzufügen [Enum-Entwurf](../../../docs/standard/design-guidelines/enum.md).</span><span class="sxs-lookup"><span data-stu-id="5f1c9-120">Enums give you some room for future addition of values, but you should be aware of all the implications of adding values to enums, which are described in [Enum Design](../../../docs/standard/design-guidelines/enum.md).</span></span>  
  
 <span data-ttu-id="5f1c9-121">**✓ CONSIDER** mit boolesche Werte für Konstruktorparameter, die tatsächlich zwei-Status-Werte sind und zur Initialisierung von boolescher Eigenschaften, die einfach verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-121">**✓ CONSIDER** using Booleans for constructor parameters that are truly two-state values and are simply used to initialize Boolean properties.</span></span>  
  
### <a name="validating-arguments"></a><span data-ttu-id="5f1c9-122">Überprüfen von Argumenten</span><span class="sxs-lookup"><span data-stu-id="5f1c9-122">Validating Arguments</span></span>  
 <span data-ttu-id="5f1c9-123">**✓ DO** weitergegebenen Argumenten um öffentlich, geschützt oder explizit implementierten Member zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-123">**✓ DO** validate arguments passed to public, protected, or explicitly implemented members.</span></span> <span data-ttu-id="5f1c9-124">Löst <xref:System.ArgumentException?displayProperty=nameWithType>, oder eine ihrer Unterklassen, wenn die Validierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-124">Throw <xref:System.ArgumentException?displayProperty=nameWithType>, or one of its subclasses, if the validation fails.</span></span>  
  
 <span data-ttu-id="5f1c9-125">Beachten Sie, dass die tatsächliche Validierung nicht unbedingt in der öffentlichen oder geschützten Member selbst nicht geschehen.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-125">Note that the actual validation does not necessarily have to happen in the public or protected member itself.</span></span> <span data-ttu-id="5f1c9-126">Dies kann auf einer niedrigeren Ebene in eine private oder interne Routine eintreten.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-126">It could happen at a lower level in some private or internal routine.</span></span> <span data-ttu-id="5f1c9-127">Der wichtigste Aspekt ist, überprüft die Argumente, die gesamte Oberfläche, die an die Endbenutzer verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-127">The main point is that the entire surface area that is exposed to the end users checks the arguments.</span></span>  
  
 <span data-ttu-id="5f1c9-128">**✓ DO** auslösen <xref:System.ArgumentNullException> Wenn ein null-Argument übergeben wird und das Element keine null-Argumente unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-128">**✓ DO** throw <xref:System.ArgumentNullException> if a null argument is passed and the member does not support null arguments.</span></span>  
  
 <span data-ttu-id="5f1c9-129">**✓ DO** Enum-Parameter überprüft.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-129">**✓ DO** validate enum parameters.</span></span>  
  
 <span data-ttu-id="5f1c9-130">Führen Sie Sie nicht davon gehen Sie aus, dass Enum-Argumente in den Bereich, der von der Enumeration definiert ist.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-130">Do not assume enum arguments will be in the range defined by the enum.</span></span> <span data-ttu-id="5f1c9-131">Die CLR ermöglicht, einen beliebigen ganzzahligen Wert in einen Enum-Wert umwandeln, selbst wenn der Wert nicht in die Enumeration definiert ist.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-131">The CLR allows casting any integer value into an enum value even if the value is not defined in the enum.</span></span>  
  
 <span data-ttu-id="5f1c9-132">**X DO NOT** verwenden <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> für Enum Bereich überprüft.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-132">**X DO NOT** use <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> for enum range checks.</span></span>  
  
 <span data-ttu-id="5f1c9-133">**✓ DO** Beachten Sie, dass änderbare Argumente möglicherweise geändert wurden, nachdem sie überprüft wurden.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-133">**✓ DO** be aware that mutable arguments might have changed after they were validated.</span></span>  
  
 <span data-ttu-id="5f1c9-134">Wenn der Member sicherheitsrelevant ist, werden Sie aufgefordert, erstellen Sie eine Kopie, und klicken Sie dann überprüfen und verarbeiten das Argument.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-134">If the member is security sensitive, you are encouraged to make a copy and then validate and process the argument.</span></span>  
  
### <a name="parameter-passing"></a><span data-ttu-id="5f1c9-135">Parameterübergabe</span><span class="sxs-lookup"><span data-stu-id="5f1c9-135">Parameter Passing</span></span>  
 <span data-ttu-id="5f1c9-136">Aus der Perspektive einer Framework-Designer, es gibt drei Hauptgruppen von Parametern: per-Wert-Parametern `ref` Parameter und `out` Parameter.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-136">From the perspective of a framework designer, there are three main groups of parameters: by-value parameters, `ref` parameters, and `out` parameters.</span></span>  
  
 <span data-ttu-id="5f1c9-137">Wenn ein Argument über einen Parameter nach Wert übergeben wird, erhält das Element eine Kopie des tatsächlichen Arguments übergeben.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-137">When an argument is passed through a by-value parameter, the member receives a copy of the actual argument passed in.</span></span> <span data-ttu-id="5f1c9-138">Wenn das Argument ein Werttyp ist, wird eine Kopie des Arguments auf dem Stapel abgelegt.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-138">If the argument is a value type, a copy of the argument is put on the stack.</span></span> <span data-ttu-id="5f1c9-139">Wenn das Argument ein Verweistyp ist, wird eine Kopie des Verweises auf dem Stapel abgelegt.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-139">If the argument is a reference type, a copy of the reference is put on the stack.</span></span> <span data-ttu-id="5f1c9-140">Am häufigsten verwendete CLR-Sprachen wie c#, VB.NET und C++-Standard zum Übergeben von Parametern als Wert.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-140">Most popular CLR languages, such as C#, VB.NET, and C++, default to passing parameters by value.</span></span>  
  
 <span data-ttu-id="5f1c9-141">Wenn ein Argument übergeben wird, über eine `ref` Parameter, der Mitglied erhält einen Verweis auf das tatsächliche Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-141">When an argument is passed through a `ref` parameter, the member receives a reference to the actual argument passed in.</span></span> <span data-ttu-id="5f1c9-142">Wenn das Argument ein Werttyp ist, wird ein Verweis auf das Argument auf dem Stapel abgelegt.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-142">If the argument is a value type, a reference to the argument is put on the stack.</span></span> <span data-ttu-id="5f1c9-143">Wenn das Argument ein Verweistyp ist, wird ein Verweis auf den Verweis auf dem Stapel abgelegt.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-143">If the argument is a reference type, a reference to the reference is put on the stack.</span></span> <span data-ttu-id="5f1c9-144">`Ref` Parameter können verwendet werden, um das Element zu ändern, vom Aufrufer übergegebene Argumente machen.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-144">`Ref` parameters can be used to allow the member to modify arguments passed by the caller.</span></span>  
  
 <span data-ttu-id="5f1c9-145">`Out` Parameter sind ähnlich, `ref` Parameter, mit einigen kleinen unterschieden.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-145">`Out` parameters are similar to `ref` parameters, with some small differences.</span></span> <span data-ttu-id="5f1c9-146">Der Parameter wird anfänglich betrachtet, nicht zugewiesen und kann nicht in den Text des Elements gelesen werden, bevor ihr einen Wert zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-146">The parameter is initially considered unassigned and cannot be read in the member body before it is assigned some value.</span></span> <span data-ttu-id="5f1c9-147">Darüber hinaus muss der Parameter einen Wert zugewiesen werden, bevor das Element zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-147">Also, the parameter has to be assigned some value before the member returns.</span></span>  
  
 <span data-ttu-id="5f1c9-148">**X AVOID** mit `out` oder `ref` Parameter.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-148">**X AVOID** using `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="5f1c9-149">Mithilfe von `out` oder `ref` Parameter erfordert Erfahrung mit Zeigern, Kenntnisse der Unterschiede zwischen Werttypen und Verweistypen und Umgang mit Methoden mit mehreren Rückgabewerten.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-149">Using `out` or `ref` parameters requires experience with pointers, understanding how value types and reference types differ, and handling methods with multiple return values.</span></span> <span data-ttu-id="5f1c9-150">Außerdem ist der Unterschied zwischen `out` und `ref` Parameter kann häufig nicht interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-150">Also, the difference between `out` and `ref` parameters is not widely understood.</span></span> <span data-ttu-id="5f1c9-151">Framework-Architekten Entwerfen für eine Breite Zielgruppe sollten nicht erwarten, dass der Benutzer das master arbeiten mit `out` oder `ref` Parameter.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-151">Framework architects designing for a general audience should not expect users to master working with `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="5f1c9-152">**X DO NOT** Verweistypen als Verweis übergeben.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-152">**X DO NOT** pass reference types by reference.</span></span>  
  
 <span data-ttu-id="5f1c9-153">Es gibt einige wenige Ausnahmen für die Regel, wie z. B. eine Methode, die zum Austauschen von Verweisen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-153">There are some limited exceptions to the rule, such as a method that can be used to swap references.</span></span>  
  
### <a name="members-with-variable-number-of-parameters"></a><span data-ttu-id="5f1c9-154">Elemente mit einer Variablen Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="5f1c9-154">Members with Variable Number of Parameters</span></span>  
 <span data-ttu-id="5f1c9-155">Elemente, die eine Variable Anzahl von Argumenten akzeptieren können, werden durch die Bereitstellung eines Arrayparameter ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-155">Members that can take a variable number of arguments are expressed by providing an array parameter.</span></span> <span data-ttu-id="5f1c9-156">Z. B. <xref:System.String> bietet die folgende Methode:</span><span class="sxs-lookup"><span data-stu-id="5f1c9-156">For example, <xref:System.String> provides the following method:</span></span>  
  
```  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 <span data-ttu-id="5f1c9-157">Ein Benutzer kann dann Aufrufen der <xref:System.String.Format%2A?displayProperty=nameWithType> -Methode wie folgt:</span><span class="sxs-lookup"><span data-stu-id="5f1c9-157">A user can then call the <xref:System.String.Format%2A?displayProperty=nameWithType> method, as follows:</span></span>  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 <span data-ttu-id="5f1c9-158">Durch Hinzufügen des C#-Params-Schlüsselworts auf einen Arrayparameter ändert der Parameter auf einen Arrayparameter so genannte Params und verfügt über eine Tastenkombination für das ein temporäres Array erstellen.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-158">Adding the C# params keyword to an array parameter changes the parameter to a so-called params array parameter and provides a shortcut to creating a temporary array.</span></span>  
  
```  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 <span data-ttu-id="5f1c9-159">Auf diese Weise kann der Benutzer zum Aufrufen der Methode durch die Elemente des Arrays in der Argumentliste direkt übergeben.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-159">Doing this allows the user to call the method by passing the array elements directly in the argument list.</span></span>  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 <span data-ttu-id="5f1c9-160">Beachten Sie, dass das Params-Schlüsselwort nur der letzte Parameter in der Liste hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-160">Note that the params keyword can be added only to the last parameter in the parameter list.</span></span>  
  
 <span data-ttu-id="5f1c9-161">**✓ CONSIDER** Arrayparameter des Params-Schlüsselworts hinzugefügt, wenn Sie davon ausgehen, die Endbenutzer zum Übergeben von Arrays mit einer kleinen Anzahl von Elementen dass.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-161">**✓ CONSIDER** adding the params keyword to array parameters if you expect the end users to pass arrays with a small number of elements.</span></span> <span data-ttu-id="5f1c9-162">Erwartet werden, dass viele der Elemente in gängigen Szenarien übergeben werden, Benutzer übergibt diese Elemente Inline wahrscheinlich nicht ohnehin, und das Params-Schlüsselwort ist daher nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-162">If it’s expected that lots of elements will be passed in common scenarios, users will probably not pass these elements inline anyway, and so the params keyword is not necessary.</span></span>  
  
 <span data-ttu-id="5f1c9-163">**X AVOID** Params-Arrays verwenden, wenn ein Aufrufer fast immer die Eingabe bereits in einem Array würde.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-163">**X AVOID** using params arrays if the caller would almost always have the input already in an array.</span></span>  
  
 <span data-ttu-id="5f1c9-164">Mitglieder mit Arrayparametern Byte würde z. B. durch Übergeben der einzelnen Bytes fast nie aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-164">For example, members with byte array parameters would almost never be called by passing individual bytes.</span></span> <span data-ttu-id="5f1c9-165">Aus diesem Grund verwenden Byte-Array-Parameter in .NET Framework nicht das Params-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-165">For this reason, byte array parameters in the .NET Framework do not use the params keyword.</span></span>  
  
 <span data-ttu-id="5f1c9-166">**X DO NOT** Params-Arrays verwenden, wenn das Array vom dauert des Params-Array Parameters-Element geändert wird.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-166">**X DO NOT** use params arrays if the array is modified by the member taking the params array parameter.</span></span>  
  
 <span data-ttu-id="5f1c9-167">Aufgrund der Tatsache, dass viele Compiler die Argumente für das Element in ein temporäres Array an der Aufrufsite umwandeln das Array kann kein temporäres Objekt sein, und somit keine Änderungen an das Array verloren.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-167">Because of the fact that many compilers turn the arguments to the member into a temporary array at the call site, the array might be a temporary object, and therefore any modifications to the array will be lost.</span></span>  
  
 <span data-ttu-id="5f1c9-168">**✓ CONSIDER** des Params-Schlüsselworts in einer einfachen Überladung verwenden, auch wenn eine komplexere Überladung, konnte ihn nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-168">**✓ CONSIDER** using the params keyword in a simple overload, even if a more complex overload could not use it.</span></span>  
  
 <span data-ttu-id="5f1c9-169">Fragen Sie sich, wenn Benutzer in einer Überladung der Parameterarray müssen, auch wenn es in alle Überladungen war nicht Wert würde.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-169">Ask yourself if users would value having the params array in one overload even if it wasn’t in all overloads.</span></span>  
  
 <span data-ttu-id="5f1c9-170">**✓ DO** versuchen, Order-Parameter, und es Ihnen ermöglicht mithilfe des Params-Schlüsselworts.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-170">**✓ DO** try to order parameters to make it possible to use the params keyword.</span></span>  
  
 <span data-ttu-id="5f1c9-171">**✓ CONSIDER** spezielle Überladungen und Codepfade für Aufrufe mit einer kleinen Anzahl von Argumenten in extrem leistungsabhängigen-APIs bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-171">**✓ CONSIDER** providing special overloads and code paths for calls with a small number of arguments in extremely performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="5f1c9-172">Dadurch kann vermieden werden Array von Objekten erstellen, wenn die API mit einer kleinen Anzahl von Argumenten aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-172">This makes it possible to avoid creating array objects when the API is called with a small number of arguments.</span></span> <span data-ttu-id="5f1c9-173">Bilden Sie die Namen der Parameter, indem ein einzelnes Format des Array-Parameters und ein numerisches Suffix hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-173">Form the names of the parameters by taking a singular form of the array parameter and adding a numeric suffix.</span></span>  
  
 <span data-ttu-id="5f1c9-174">Sie sollten dies nur tun, wenn Sie beabsichtigen, der Pfad für den gesamten besondere Schreibweisen, nicht nur ein Array erstellen, und rufen Sie die allgemeine Methode.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-174">You should only do this if you are going to special-case the entire code path, not just create an array and call the more general method.</span></span>  
  
 <span data-ttu-id="5f1c9-175">**✓ DO** Beachten Sie, dass Null kann als ein Params-Argument übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-175">**✓ DO** be aware that null could be passed as a params array argument.</span></span>  
  
 <span data-ttu-id="5f1c9-176">Sie sollten überprüfen, dass das Array nicht vor der Verarbeitung null ist.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-176">You should validate that the array is not null before processing.</span></span>  
  
 <span data-ttu-id="5f1c9-177">**X DO NOT** verwenden die `varargs` Methoden, sogenannten mit den Auslassungspunkten.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-177">**X DO NOT** use the `varargs` methods, otherwise known as the ellipsis.</span></span>  
  
 <span data-ttu-id="5f1c9-178">Einige CLR-Sprachen, z. B. C++, unterstützen eine alternative Konvention für die Übergabe von Variablen Parameterlisten namens `varargs` Methoden.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-178">Some CLR languages, such as C++, support an alternative convention for passing variable parameter lists called `varargs` methods.</span></span> <span data-ttu-id="5f1c9-179">Die Konvention sollte nicht in Frameworks verwendet werden, da es nicht CLS-kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-179">The convention should not be used in frameworks, because it is not CLS compliant.</span></span>  
  
### <a name="pointer-parameters"></a><span data-ttu-id="5f1c9-180">Zeigerparameter</span><span class="sxs-lookup"><span data-stu-id="5f1c9-180">Pointer Parameters</span></span>  
 <span data-ttu-id="5f1c9-181">Im Allgemeinen Zeiger nicht in die öffentliche Oberfläche eines Frameworks gut entworfene von verwaltetem Code angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-181">In general, pointers should not appear in the public surface area of a well-designed managed code framework.</span></span> <span data-ttu-id="5f1c9-182">In den meisten Fällen, sollte als Zeiger gekapselt werden.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-182">Most of the time, pointers should be encapsulated.</span></span> <span data-ttu-id="5f1c9-183">Jedoch in einigen Fällen Zeiger aus Gründen der Interoperabilität erforderlich sind, und Verwenden von Zeigern in solchen Fällen eignet.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-183">However, in some cases pointers are required for interoperability reasons, and using pointers in such cases is appropriate.</span></span>  
  
 <span data-ttu-id="5f1c9-184">**✓ DO** bieten eine Alternative für ein Element, das ein Zeigerargument akzeptiert, da Zeiger nicht CLS-kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-184">**✓ DO** provide an alternative for any member that takes a pointer argument, because pointers are not CLS-compliant.</span></span>  
  
 <span data-ttu-id="5f1c9-185">**X AVOID** auf diese Weise die aufwändige Prüfung von Zeigerargumente Argument.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-185">**X AVOID** doing expensive argument checking of pointer arguments.</span></span>  
  
 <span data-ttu-id="5f1c9-186">**✓ DO** Konventionen gemeinsamen Zeiger-bezogene beim Entwerfen der Member mit Zeigern.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-186">**✓ DO** follow common pointer-related conventions when designing members with pointers.</span></span>  
  
 <span data-ttu-id="5f1c9-187">Beispielsweise besteht keine Notwendigkeit, übergeben den Startindex, da einfache Zeigerarithmetik verwendet werden kann, um das gleiche Ergebnis zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-187">For example, there is no need to pass the start index, because simple pointer arithmetic can be used to accomplish the same result.</span></span>  
  
 <span data-ttu-id="5f1c9-188">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="5f1c9-188">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="5f1c9-189">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="5f1c9-189">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f1c9-190">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f1c9-190">See also</span></span>

- [<span data-ttu-id="5f1c9-191">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="5f1c9-191">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="5f1c9-192">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="5f1c9-192">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
