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
ms.openlocfilehash: e39b38fd72f9f3b9ce76aa6f7e96e44841daabb9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="parameter-design"></a><span data-ttu-id="55594-102">Parameterentwurf</span><span class="sxs-lookup"><span data-stu-id="55594-102">Parameter Design</span></span>
<span data-ttu-id="55594-103">Dieser Abschnitt enthält allgemeine Richtlinien für Parameter Entwurf, einschließlich Abschnitte mit Richtlinien für die Überprüfung der Argumente.</span><span class="sxs-lookup"><span data-stu-id="55594-103">This section provides broad guidelines on parameter design, including sections with guidelines for checking arguments.</span></span> <span data-ttu-id="55594-104">Sie sollten darüber hinaus finden Sie in der beschriebenen Richtlinien [Benennung von Parametern](../../../docs/standard/design-guidelines/naming-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="55594-104">In addition, you should refer to the guidelines described in [Naming Parameters](../../../docs/standard/design-guidelines/naming-parameters.md).</span></span>  
  
 <span data-ttu-id="55594-105">**Führen Sie ✓** verwenden, der am wenigsten abgeleiteten Parametertyp, die die Funktionen für das Element bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="55594-105">**✓ DO** use the least derived parameter type that provides the functionality required by the member.</span></span>  
  
 <span data-ttu-id="55594-106">Nehmen Sie beispielsweise an, dass eine Methode zu entwerfen, die listet und jedes Element in der Konsole ausgegeben, werden sollen.</span><span class="sxs-lookup"><span data-stu-id="55594-106">For example, suppose you want to design a method that enumerates a collection and prints each item to the console.</span></span> <span data-ttu-id="55594-107">Eine solche Methode ergreift <xref:System.Collections.IEnumerable> als Parameter nicht <xref:System.Collections.ArrayList> oder <xref:System.Collections.IList>, z. B.</span><span class="sxs-lookup"><span data-stu-id="55594-107">Such a method should take <xref:System.Collections.IEnumerable> as the parameter, not <xref:System.Collections.ArrayList> or <xref:System.Collections.IList>, for example.</span></span>  
  
 <span data-ttu-id="55594-108">**X nicht** reservierte Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="55594-108">**X DO NOT** use reserved parameters.</span></span>  
  
 <span data-ttu-id="55594-109">Wenn weitere Eingabe für ein Element in einer künftigen Version erforderlich ist, kann eine neue Überladung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="55594-109">If more input to a member is needed in some future version, a new overload can be added.</span></span>  
  
 <span data-ttu-id="55594-110">**X nicht** haben öffentlich verfügbar gemachten Methoden, die Zeiger, Arrays von Zeigern oder mehrdimensionale Arrays als Parameter akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="55594-110">**X DO NOT** have publicly exposed methods that take pointers, arrays of pointers, or multidimensional arrays as parameters.</span></span>  
  
 <span data-ttu-id="55594-111">Zeiger und mehrdimensionale Arrays sind relativ schwer, ordnungsgemäß zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="55594-111">Pointers and multidimensional arrays are relatively difficult to use properly.</span></span> <span data-ttu-id="55594-112">In fast allen Fällen können APIs neu gestaltet werden, um zu vermeiden, diese Typen als Parameter übernimmt.</span><span class="sxs-lookup"><span data-stu-id="55594-112">In almost all cases, APIs can be redesigned to avoid taking these types as parameters.</span></span>  
  
 <span data-ttu-id="55594-113">**✓ FÜHREN** platzieren Sie alle `out` Parameter, die alle per-Wert und `ref` Parameter (ausgenommen Parameterarrays), auch wenn dies zu einer Inkonsistenz der Sortierung zwischen Überladungen Parameter führt (finden Sie unter [Member Überladen von](../../../docs/standard/design-guidelines/member-overloading.md)).</span><span class="sxs-lookup"><span data-stu-id="55594-113">**✓ DO** place all `out` parameters following all of the by-value and `ref` parameters (excluding parameter arrays), even if it results in an inconsistency in parameter ordering between overloads (see [Member Overloading](../../../docs/standard/design-guidelines/member-overloading.md)).</span></span>  
  
 <span data-ttu-id="55594-114">Die `out` Parameter können als zusätzliche Werte angezeigt werden, und gruppieren sie macht die Signatur der Methode leichter zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="55594-114">The `out` parameters can be seen as extra return values, and grouping them together makes the method signature easier to understand.</span></span>  
  
 <span data-ttu-id="55594-115">**Führen Sie ✓** benennen Parameter aus, wenn Sie Member überschreiben oder Implementieren von Schnittstellenmembern konsistent sein.</span><span class="sxs-lookup"><span data-stu-id="55594-115">**✓ DO** be consistent in naming parameters when overriding members or implementing interface members.</span></span>  
  
 <span data-ttu-id="55594-116">Dies kommuniziert besser die Beziehung zwischen den Methoden.</span><span class="sxs-lookup"><span data-stu-id="55594-116">This better communicates the relationship between the methods.</span></span>  
  
### <a name="choosing-between-enum-and-boolean-parameters"></a><span data-ttu-id="55594-117">Auswählen zwischen Enum und booleschen Parametern</span><span class="sxs-lookup"><span data-stu-id="55594-117">Choosing Between Enum and Boolean Parameters</span></span>  
 <span data-ttu-id="55594-118">**Führen Sie ✓** Enumerationen verwenden, wenn ein Element mindestens zwei boolesche Parameter hätten.</span><span class="sxs-lookup"><span data-stu-id="55594-118">**✓ DO** use enums if a member would otherwise have two or more Boolean parameters.</span></span>  
  
 <span data-ttu-id="55594-119">**X nicht** boolesche Werte verwenden, es sei denn, Sie absolut sicher, dass es werden nie mehr als zwei Werte erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="55594-119">**X DO NOT** use Booleans unless you are absolutely sure there will never be a need for more than two values.</span></span>  
  
 <span data-ttu-id="55594-120">Enumerationen bieten Ihnen einige Platz für zukünftige Werte hinzufügen, aber Sie sollten alle verbundenen Auswirkungen auf den zum Hinzufügen von Werten für Enumerationen, die in beschrieben werden [Enum-Entwurf](../../../docs/standard/design-guidelines/enum.md).</span><span class="sxs-lookup"><span data-stu-id="55594-120">Enums give you some room for future addition of values, but you should be aware of all the implications of adding values to enums, which are described in [Enum Design](../../../docs/standard/design-guidelines/enum.md).</span></span>  
  
 <span data-ttu-id="55594-121">**✓ GGF.** mit boolesche Werte für Konstruktorparameter, die tatsächlich zwei-Status-Werte sind und zur Initialisierung von boolescher Eigenschaften, die einfach verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="55594-121">**✓ CONSIDER** using Booleans for constructor parameters that are truly two-state values and are simply used to initialize Boolean properties.</span></span>  
  
### <a name="validating-arguments"></a><span data-ttu-id="55594-122">Überprüfen von Argumenten</span><span class="sxs-lookup"><span data-stu-id="55594-122">Validating Arguments</span></span>  
 <span data-ttu-id="55594-123">**Führen Sie ✓** weitergegebenen Argumenten um öffentlich, geschützt oder explizit implementierten Member zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="55594-123">**✓ DO** validate arguments passed to public, protected, or explicitly implemented members.</span></span> <span data-ttu-id="55594-124">Löst <xref:System.ArgumentException?displayProperty=nameWithType>, oder eine ihrer Unterklassen, wenn die Validierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="55594-124">Throw <xref:System.ArgumentException?displayProperty=nameWithType>, or one of its subclasses, if the validation fails.</span></span>  
  
 <span data-ttu-id="55594-125">Beachten Sie, dass die tatsächliche Validierung nicht unbedingt in der öffentlichen oder geschützten Member selbst durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="55594-125">Note that the actual validation does not necessarily have to happen in the public or protected member itself.</span></span> <span data-ttu-id="55594-126">Dies kann auf einer niedrigeren Ebene in eine private oder interne Routine eintreten.</span><span class="sxs-lookup"><span data-stu-id="55594-126">It could happen at a lower level in some private or internal routine.</span></span> <span data-ttu-id="55594-127">Im Mittelpunkt ist, überprüft die Argumente, die gesamte Oberfläche, die den Endbenutzern zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="55594-127">The main point is that the entire surface area that is exposed to the end users checks the arguments.</span></span>  
  
 <span data-ttu-id="55594-128">**Führen Sie ✓** auslösen <xref:System.ArgumentNullException> Wenn ein null-Argument übergeben wird und das Element keine null-Argumente unterstützt.</span><span class="sxs-lookup"><span data-stu-id="55594-128">**✓ DO** throw <xref:System.ArgumentNullException> if a null argument is passed and the member does not support null arguments.</span></span>  
  
 <span data-ttu-id="55594-129">**Führen Sie ✓** Enum-Parameter überprüft.</span><span class="sxs-lookup"><span data-stu-id="55594-129">**✓ DO** validate enum parameters.</span></span>  
  
 <span data-ttu-id="55594-130">Führen Sie Sie nicht davon gehen Sie aus, dass die Enum-Argumente in den Bereich, der durch die Enumeration definiert werden.</span><span class="sxs-lookup"><span data-stu-id="55594-130">Do not assume enum arguments will be in the range defined by the enum.</span></span> <span data-ttu-id="55594-131">Die CLR ermöglicht es, einen ganzzahligen Wert in einen Enum-Wert umwandeln, selbst wenn der Wert nicht in der Enumeration definiert ist.</span><span class="sxs-lookup"><span data-stu-id="55594-131">The CLR allows casting any integer value into an enum value even if the value is not defined in the enum.</span></span>  
  
 <span data-ttu-id="55594-132">**X nicht** verwenden <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> für Enum Bereich überprüft.</span><span class="sxs-lookup"><span data-stu-id="55594-132">**X DO NOT** use <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> for enum range checks.</span></span>  
  
 <span data-ttu-id="55594-133">**Führen Sie ✓** Beachten Sie, dass änderbare Argumente möglicherweise geändert wurden, nachdem sie überprüft wurden.</span><span class="sxs-lookup"><span data-stu-id="55594-133">**✓ DO** be aware that mutable arguments might have changed after they were validated.</span></span>  
  
 <span data-ttu-id="55594-134">Wenn der Member sicherheitsrelevant ist, werden Sie aufgefordert, erstellen Sie eine Kopie, und klicken Sie dann zu überprüfen und verarbeiten das Argument.</span><span class="sxs-lookup"><span data-stu-id="55594-134">If the member is security sensitive, you are encouraged to make a copy and then validate and process the argument.</span></span>  
  
### <a name="parameter-passing"></a><span data-ttu-id="55594-135">Parameterübergabe</span><span class="sxs-lookup"><span data-stu-id="55594-135">Parameter Passing</span></span>  
 <span data-ttu-id="55594-136">Aus der Perspektive eines Designers Framework, es gibt drei Hauptgruppen von Parametern: per-Wert-Parametern, `ref` Parameter, und `out` Parameter.</span><span class="sxs-lookup"><span data-stu-id="55594-136">From the perspective of a framework designer, there are three main groups of parameters: by-value parameters, `ref` parameters, and `out` parameters.</span></span>  
  
 <span data-ttu-id="55594-137">Wenn ein Argument durch einen Parameter nach Wert übergeben wird, erhält das Element eine Kopie des tatsächlichen Arguments übergeben.</span><span class="sxs-lookup"><span data-stu-id="55594-137">When an argument is passed through a by-value parameter, the member receives a copy of the actual argument passed in.</span></span> <span data-ttu-id="55594-138">Wenn das Argument ein Werttyp ist, wird eine Kopie des Arguments auf dem Stapel abgelegt.</span><span class="sxs-lookup"><span data-stu-id="55594-138">If the argument is a value type, a copy of the argument is put on the stack.</span></span> <span data-ttu-id="55594-139">Wenn das Argument ein Verweistyp ist, wird eine Kopie des Verweises auf dem Stapel abgelegt.</span><span class="sxs-lookup"><span data-stu-id="55594-139">If the argument is a reference type, a copy of the reference is put on the stack.</span></span> <span data-ttu-id="55594-140">Am häufigsten verwendete CLR-Sprachen wie c#, VB.NET und C++-Standard zum Übergeben von Parametern durch einen Wert.</span><span class="sxs-lookup"><span data-stu-id="55594-140">Most popular CLR languages, such as C#, VB.NET, and C++, default to passing parameters by value.</span></span>  
  
 <span data-ttu-id="55594-141">Wenn ein Argument übergeben wird, über eine `ref` Parameter, das Element erhält einen Verweis auf das tatsächliche Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="55594-141">When an argument is passed through a `ref` parameter, the member receives a reference to the actual argument passed in.</span></span> <span data-ttu-id="55594-142">Wenn das Argument ein Werttyp ist, wird ein Verweis auf das Argument auf dem Stapel abgelegt.</span><span class="sxs-lookup"><span data-stu-id="55594-142">If the argument is a value type, a reference to the argument is put on the stack.</span></span> <span data-ttu-id="55594-143">Wenn das Argument ein Verweistyp ist, wird ein Verweis auf den Verweis auf dem Stapel abgelegt.</span><span class="sxs-lookup"><span data-stu-id="55594-143">If the argument is a reference type, a reference to the reference is put on the stack.</span></span> <span data-ttu-id="55594-144">`Ref` Parameter können verwendet werden, um das Element so ändern Sie die vom Aufrufer übergegebene Argumente zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="55594-144">`Ref` parameters can be used to allow the member to modify arguments passed by the caller.</span></span>  
  
 <span data-ttu-id="55594-145">`Out` Parameter sind ähnlich `ref` Parameter, mit einige geringfügige Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="55594-145">`Out` parameters are similar to `ref` parameters, with some small differences.</span></span> <span data-ttu-id="55594-146">Der Parameter ist anfänglich betrachtet werden, nicht zugewiesen und kann im Hauptteil Elements gelesen werden, bevor ihr einen Wert zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="55594-146">The parameter is initially considered unassigned and cannot be read in the member body before it is assigned some value.</span></span> <span data-ttu-id="55594-147">Außerdem muss der Parameter einen Wert zugewiesen werden, bevor das Element zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="55594-147">Also, the parameter has to be assigned some value before the member returns.</span></span>  
  
 <span data-ttu-id="55594-148">**X vermeiden** mit `out` oder `ref` Parameter.</span><span class="sxs-lookup"><span data-stu-id="55594-148">**X AVOID** using `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="55594-149">Mit `out` oder `ref` Parameter erfordert Erfahrung mit Zeigern, Kenntnisse der Unterschiede zwischen Wert- und Verweistypen und Arbeiten mit Methoden mit mehreren Rückgabewerten.</span><span class="sxs-lookup"><span data-stu-id="55594-149">Using `out` or `ref` parameters requires experience with pointers, understanding how value types and reference types differ, and handling methods with multiple return values.</span></span> <span data-ttu-id="55594-150">Außerdem ist der Unterschied zwischen `out` und `ref` Parameter wird nicht umfassend unterstützt.</span><span class="sxs-lookup"><span data-stu-id="55594-150">Also, the difference between `out` and `ref` parameters is not widely understood.</span></span> <span data-ttu-id="55594-151">Framework Architekten Entwerfen für eine Breite Zielgruppe sollten nicht erwarten, dass der Benutzer mit `out` oder `ref` Parameter.</span><span class="sxs-lookup"><span data-stu-id="55594-151">Framework architects designing for a general audience should not expect users to master working with `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="55594-152">**X nicht** Verweistypen als Verweis übergeben.</span><span class="sxs-lookup"><span data-stu-id="55594-152">**X DO NOT** pass reference types by reference.</span></span>  
  
 <span data-ttu-id="55594-153">Es gibt einige wenige Ausnahmen für die Regel ein, z. B. eine Methode, die zum Austauschen von Verweise verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="55594-153">There are some limited exceptions to the rule, such as a method that can be used to swap references.</span></span>  
  
### <a name="members-with-variable-number-of-parameters"></a><span data-ttu-id="55594-154">Elemente mit einer Variablen Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="55594-154">Members with Variable Number of Parameters</span></span>  
 <span data-ttu-id="55594-155">Elemente, die eine Variable Anzahl von Argumenten akzeptieren können, werden durch die Bereitstellung eines Arrayparameter ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="55594-155">Members that can take a variable number of arguments are expressed by providing an array parameter.</span></span> <span data-ttu-id="55594-156">Beispielsweise <xref:System.String> bietet die folgende Methode:</span><span class="sxs-lookup"><span data-stu-id="55594-156">For example, <xref:System.String> provides the following method:</span></span>  
  
```  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 <span data-ttu-id="55594-157">Ein Benutzer kann dann rufen Sie die <xref:System.String.Format%2A?displayProperty=nameWithType> -Methode wie folgt:</span><span class="sxs-lookup"><span data-stu-id="55594-157">A user can then call the <xref:System.String.Format%2A?displayProperty=nameWithType> method, as follows:</span></span>  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 <span data-ttu-id="55594-158">Hinzufügen des Params-Schlüsselworts in c# auf einen Arrayparameter ändert der Parameter auf einen so genannten Params-Arrayparameter und verfügt über eine Tastenkombination erstellen Sie ein temporäres Array.</span><span class="sxs-lookup"><span data-stu-id="55594-158">Adding the C# params keyword to an array parameter changes the parameter to a so-called params array parameter and provides a shortcut to creating a temporary array.</span></span>  
  
```  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 <span data-ttu-id="55594-159">Auf diese Weise können die Benutzer zum Aufrufen der Methode durch die Elemente des Arrays direkt in der Argumentliste übergeben.</span><span class="sxs-lookup"><span data-stu-id="55594-159">Doing this allows the user to call the method by passing the array elements directly in the argument list.</span></span>  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 <span data-ttu-id="55594-160">Beachten Sie, dass der Params-Schlüsselworts nur der letzte Parameter in der Parameterliste hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="55594-160">Note that the params keyword can be added only to the last parameter in the parameter list.</span></span>  
  
 <span data-ttu-id="55594-161">**✓ GGF.** Arrayparameter des Params-Schlüsselworts hinzugefügt, wenn Sie davon ausgehen, die Endbenutzer zum Übergeben von Arrays mit einer kleinen Anzahl von Elementen dass.</span><span class="sxs-lookup"><span data-stu-id="55594-161">**✓ CONSIDER** adding the params keyword to array parameters if you expect the end users to pass arrays with a small number of elements.</span></span> <span data-ttu-id="55594-162">Wenn davon ausgegangen wird, dass viele Elemente gemeinsam Szenarien übergeben werden, Benutzer übergibt diese Elemente Inline wahrscheinlich nicht trotzdem und des Params-Schlüsselworts ist daher nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="55594-162">If it’s expected that lots of elements will be passed in common scenarios, users will probably not pass these elements inline anyway, and so the params keyword is not necessary.</span></span>  
  
 <span data-ttu-id="55594-163">**X vermeiden** Params-Arrays verwenden, wenn ein Aufrufer fast immer die Eingabe bereits in einem Array würde.</span><span class="sxs-lookup"><span data-stu-id="55594-163">**X AVOID** using params arrays if the caller would almost always have the input already in an array.</span></span>  
  
 <span data-ttu-id="55594-164">Mitglieder mit Arrayparametern Byte würde z. B. durch Übergeben der einzelnen Bytes fast nie aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="55594-164">For example, members with byte array parameters would almost never be called by passing individual bytes.</span></span> <span data-ttu-id="55594-165">Aus diesem Grund verwenden Sie Byte Arrayparametern in .NET Framework nicht des Params-Schlüsselworts.</span><span class="sxs-lookup"><span data-stu-id="55594-165">For this reason, byte array parameters in the .NET Framework do not use the params keyword.</span></span>  
  
 <span data-ttu-id="55594-166">**X nicht** Params-Arrays verwenden, wenn das Array vom dauert des Params-Array Parameters-Element geändert wird.</span><span class="sxs-lookup"><span data-stu-id="55594-166">**X DO NOT** use params arrays if the array is modified by the member taking the params array parameter.</span></span>  
  
 <span data-ttu-id="55594-167">Aufgrund der Tatsache, dass viele Compiler die Argumente für das Element in ein temporäres Array an der Aufrufsite verwandeln, das Array kann kein temporäres Objekt sein, und daher keine Änderungen an das Array verloren.</span><span class="sxs-lookup"><span data-stu-id="55594-167">Because of the fact that many compilers turn the arguments to the member into a temporary array at the call site, the array might be a temporary object, and therefore any modifications to the array will be lost.</span></span>  
  
 <span data-ttu-id="55594-168">**✓ GGF.** des Params-Schlüsselworts in einer einfachen Überladung verwenden, auch wenn eine komplexere Überladung, konnte ihn nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="55594-168">**✓ CONSIDER** using the params keyword in a simple overload, even if a more complex overload could not use it.</span></span>  
  
 <span data-ttu-id="55594-169">Fragen Sie sich, wenn Benutzer das Parameterarray in einer Überladung müssen, auch wenn es in alle Überladungen wurden keine Wert würde.</span><span class="sxs-lookup"><span data-stu-id="55594-169">Ask yourself if users would value having the params array in one overload even if it wasn’t in all overloads.</span></span>  
  
 <span data-ttu-id="55594-170">**Führen Sie ✓** versuchen, Order-Parameter, und es Ihnen ermöglicht mithilfe des Params-Schlüsselworts.</span><span class="sxs-lookup"><span data-stu-id="55594-170">**✓ DO** try to order parameters to make it possible to use the params keyword.</span></span>  
  
 <span data-ttu-id="55594-171">**✓ GGF.** spezielle Überladungen und Codepfade für Aufrufe mit einer kleinen Anzahl von Argumenten in extrem leistungsabhängigen-APIs bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="55594-171">**✓ CONSIDER** providing special overloads and code paths for calls with a small number of arguments in extremely performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="55594-172">Dadurch möglich, vermeiden Sie das Array von Objekten erstellen, wenn die API mit einer kleinen Anzahl von Argumenten aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="55594-172">This makes it possible to avoid creating array objects when the API is called with a small number of arguments.</span></span> <span data-ttu-id="55594-173">Bilden Sie die Namen der Parameter ein Singularform des Arrayparameter und sowie ein numerisches Suffix hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="55594-173">Form the names of the parameters by taking a singular form of the array parameter and adding a numeric suffix.</span></span>  
  
 <span data-ttu-id="55594-174">Sie sollten dies nur tun, wenn Sie beabsichtigen, um Sonderfällen der gesamte Codepfad, erstellen Sie nicht nur ein Array und rufen Sie die allgemeine Methode.</span><span class="sxs-lookup"><span data-stu-id="55594-174">You should only do this if you are going to special-case the entire code path, not just create an array and call the more general method.</span></span>  
  
 <span data-ttu-id="55594-175">**Führen Sie ✓** Beachten Sie, dass Null kann als ein Params-Argument übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="55594-175">**✓ DO** be aware that null could be passed as a params array argument.</span></span>  
  
 <span data-ttu-id="55594-176">Sie sollten überprüfen, dass das Array nicht vor der Verarbeitung null ist.</span><span class="sxs-lookup"><span data-stu-id="55594-176">You should validate that the array is not null before processing.</span></span>  
  
 <span data-ttu-id="55594-177">**X nicht** verwenden die `varargs` Methoden, sogenannten mit den Auslassungspunkten.</span><span class="sxs-lookup"><span data-stu-id="55594-177">**X DO NOT** use the `varargs` methods, otherwise known as the ellipsis.</span></span>  
  
 <span data-ttu-id="55594-178">Einige CLR-Sprachen, z. B. C++, unterstützen eine alternative Konvention für die Übergabe von Variablen Parameterlisten aufgerufen `varargs` Methoden.</span><span class="sxs-lookup"><span data-stu-id="55594-178">Some CLR languages, such as C++, support an alternative convention for passing variable parameter lists called `varargs` methods.</span></span> <span data-ttu-id="55594-179">Die Konvention sollte nicht in Frameworks verwendet werden, da sie nicht CLS-kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="55594-179">The convention should not be used in frameworks, because it is not CLS compliant.</span></span>  
  
### <a name="pointer-parameters"></a><span data-ttu-id="55594-180">Zeigerparameter</span><span class="sxs-lookup"><span data-stu-id="55594-180">Pointer Parameters</span></span>  
 <span data-ttu-id="55594-181">Im Allgemeinen Zeiger nicht in den öffentlichen Oberflächenbereich ein Framework ausgereifte verwalteten Code angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="55594-181">In general, pointers should not appear in the public surface area of a well-designed managed code framework.</span></span> <span data-ttu-id="55594-182">In den meisten Fällen, sollte als Zeiger gekapselt werden.</span><span class="sxs-lookup"><span data-stu-id="55594-182">Most of the time, pointers should be encapsulated.</span></span> <span data-ttu-id="55594-183">Jedoch in einigen Fällen Zeiger aus Gründen der Interoperabilität erforderlich sind, und Verwendung von Zeigern in solchen Fällen ist geeignet.</span><span class="sxs-lookup"><span data-stu-id="55594-183">However, in some cases pointers are required for interoperability reasons, and using pointers in such cases is appropriate.</span></span>  
  
 <span data-ttu-id="55594-184">**Führen Sie ✓** bieten eine Alternative für ein Element, das ein Zeigerargument akzeptiert, da Zeiger nicht CLS-kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="55594-184">**✓ DO** provide an alternative for any member that takes a pointer argument, because pointers are not CLS-compliant.</span></span>  
  
 <span data-ttu-id="55594-185">**X vermeiden** auf diese Weise die aufwändige Prüfung von Zeigerargumente Argument.</span><span class="sxs-lookup"><span data-stu-id="55594-185">**X AVOID** doing expensive argument checking of pointer arguments.</span></span>  
  
 <span data-ttu-id="55594-186">**Führen Sie ✓** Konventionen gemeinsamen Zeiger-bezogene beim Entwerfen der Member mit Zeigern.</span><span class="sxs-lookup"><span data-stu-id="55594-186">**✓ DO** follow common pointer-related conventions when designing members with pointers.</span></span>  
  
 <span data-ttu-id="55594-187">Beispielsweise besteht keine Notwendigkeit, übergeben den Startindex, da einfache Zeigerarithmetik verwendet werden kann, um das gleiche Ergebnis zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="55594-187">For example, there is no need to pass the start index, because simple pointer arithmetic can be used to accomplish the same result.</span></span>  
  
 <span data-ttu-id="55594-188">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="55594-188">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="55594-189">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="55594-189">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55594-190">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55594-190">See Also</span></span>  
 [<span data-ttu-id="55594-191">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="55594-191">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="55594-192">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="55594-192">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
