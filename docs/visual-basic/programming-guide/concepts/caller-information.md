---
title: Aufruferinformationen
ms.date: 07/20/2015
ms.assetid: 15d556eb-4d0c-4497-98a3-7f60abb7d6a1
ms.openlocfilehash: 7c87b540a68f4d0219918fed66de6c1b635104a9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349476"
---
# <a name="caller-information-visual-basic"></a><span data-ttu-id="670d4-102">Aufruferinformationen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="670d4-102">Caller Information (Visual Basic)</span></span>
<span data-ttu-id="670d4-103">Mithilfe der Aufrufer-Informationsattribute können Sie Informationen zum Aufrufer einer Methode abrufen.</span><span class="sxs-lookup"><span data-stu-id="670d4-103">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="670d4-104">Sie können den Dateipfad des Quellcodes, die Zeilennummer im Quellcode und den Membernamen des Aufrufers abrufen.</span><span class="sxs-lookup"><span data-stu-id="670d4-104">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="670d4-105">Diese Informationen sind zum Verfolgen, Debuggen und Erstellen von Diagnosetools sehr nützlich.</span><span class="sxs-lookup"><span data-stu-id="670d4-105">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>  
  
 <span data-ttu-id="670d4-106">Um diese Informationen zu erhalten, verwenden Sie die Attribute, die auf optionale Parameter angewendet werden, von denen jeder einen Standardwert besitzt.</span><span class="sxs-lookup"><span data-stu-id="670d4-106">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="670d4-107">In der folgenden Tabelle sind die Aufrufer-Informationsattribute angegeben, die im <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>-Namespace definiert sind:</span><span class="sxs-lookup"><span data-stu-id="670d4-107">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>  
  
|<span data-ttu-id="670d4-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="670d4-108">Attribute</span></span>|<span data-ttu-id="670d4-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="670d4-109">Description</span></span>|<span data-ttu-id="670d4-110">Typ</span><span class="sxs-lookup"><span data-stu-id="670d4-110">Type</span></span>|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="670d4-111">Vollständiger Pfad der Quelldatei, die den Aufrufer enthält.</span><span class="sxs-lookup"><span data-stu-id="670d4-111">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="670d4-112">Dies ist der Dateipfad zum Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="670d4-112">This is the file path at compile time.</span></span>|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="670d4-113">Zeilennummer in der Quelldatei, in der die Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="670d4-113">Line number in the source file at which the method is called.</span></span>|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="670d4-114">Der Methoden- oder Eigenschaftenname des Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="670d4-114">Method or property name of the caller.</span></span> <span data-ttu-id="670d4-115">Weitere Informationen hierzu finden Sie unter [Membernamen](#MEMBERNAMES) weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="670d4-115">See [Member Names](#MEMBERNAMES) later in this topic.</span></span>|`String`|  
  
## <a name="example"></a><span data-ttu-id="670d4-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="670d4-116">Example</span></span>  
 <span data-ttu-id="670d4-117">Im folgenden Beispiel wird die Verwendung der Aufrufer-Informationsattribute veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="670d4-117">The following example shows how to use Caller Info attributes.</span></span> <span data-ttu-id="670d4-118">Bei jedem Aufruf der `TraceMessage`-Methode werden die Aufruferinformationen als Argumente für optionale Parameter ersetzt.</span><span class="sxs-lookup"><span data-stu-id="670d4-118">On each call to the `TraceMessage` method, the caller information is substituted as arguments to the optional parameters.</span></span>  
  
```vb  
Private Sub DoProcessing()  
    TraceMessage("Something happened.")  
End Sub  
  
Public Sub TraceMessage(message As String,  
        <System.Runtime.CompilerServices.CallerMemberName> Optional memberName As String = Nothing,  
        <System.Runtime.CompilerServices.CallerFilePath> Optional sourcefilePath As String = Nothing,  
        <System.Runtime.CompilerServices.CallerLineNumber()> Optional sourceLineNumber As Integer = 0)  
  
    System.Diagnostics.Trace.WriteLine("message: " & message)  
    System.Diagnostics.Trace.WriteLine("member name: " & memberName)  
    System.Diagnostics.Trace.WriteLine("source file path: " & sourcefilePath)  
    System.Diagnostics.Trace.WriteLine("source line number: " & sourceLineNumber)  
End Sub  
  
' Sample output:  
'   message: Something happened.  
'   member name: DoProcessing  
'   source file path: C:\Users\username\Documents\Visual Studio 2012\Projects\CallerInfoVB\CallerInfoVB\Form1.vb  
'   source line number: 15  
```  
  
## <a name="remarks"></a><span data-ttu-id="670d4-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="670d4-119">Remarks</span></span>  
 <span data-ttu-id="670d4-120">Sie müssen einen expliziten Standardwert für jeden optionalen Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="670d4-120">You must specify an explicit default value for each optional parameter.</span></span> <span data-ttu-id="670d4-121">Sie können Aufrufer-Informationsattribute nicht auf Parameter anwenden, die nicht als optional festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="670d4-121">You can't apply Caller Info attributes to parameters that aren't specified as optional.</span></span>  
  
 <span data-ttu-id="670d4-122">Durch die Aufrufer-Informationsattribute wird ein Parameter nicht optional.</span><span class="sxs-lookup"><span data-stu-id="670d4-122">The Caller Info attributes don't make a parameter optional.</span></span> <span data-ttu-id="670d4-123">Stattdessen beeinflussen sie den Standardwert, der beim Auslassen des Arguments übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="670d4-123">Instead, they affect the default value that's passed in when the argument is omitted.</span></span>  
  
 <span data-ttu-id="670d4-124">Aufrufer-Informationswerte werden zur Kompilierzeit als Literale in Intermediate Language (IL) ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="670d4-124">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="670d4-125">Im Gegensatz zu den Ergebnissen der <xref:System.Exception.StackTrace%2A>-Eigenschaft für Ausnahmen werden die Ergebnisse nicht durch Verbergen beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="670d4-125">Unlike the results of the <xref:System.Exception.StackTrace%2A> property for exceptions, the results aren't affected by obfuscation.</span></span>  
  
 <span data-ttu-id="670d4-126">Sie können die optionalen Argumente explizit angeben, um die Aufruferinformationen zu steuern oder auszublenden.</span><span class="sxs-lookup"><span data-stu-id="670d4-126">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>  
  
### <a name="MEMBERNAMES"></a> <span data-ttu-id="670d4-127">Membernamen</span><span class="sxs-lookup"><span data-stu-id="670d4-127">Member Names</span></span>  
 <span data-ttu-id="670d4-128">Sie können das `CallerMemberName`-Attribut verwenden, um den Membernamen nicht als `String`-Argument für die aufgerufene Methode angeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="670d4-128">You can use the `CallerMemberName` attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="670d4-129">Auf diese Weise umgehen Sie das Problem, dass durch die **Umgestaltung mit Umbenennung** die `String`-Werte nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="670d4-129">By using this technique, you avoid the problem that **Rename Refactoring** doesn't change the `String` values.</span></span> <span data-ttu-id="670d4-130">Dieser Vorteil ist für die folgenden Aufgaben besonders hilfreich:</span><span class="sxs-lookup"><span data-stu-id="670d4-130">This benefit is especially useful for the following tasks:</span></span>  
  
- <span data-ttu-id="670d4-131">Verwenden der Ablaufverfolgung und der Diagnoseprogramme</span><span class="sxs-lookup"><span data-stu-id="670d4-131">Using tracing and diagnostic routines.</span></span>  
  
- <span data-ttu-id="670d4-132">Implementieren der <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle beim Binden von Daten</span><span class="sxs-lookup"><span data-stu-id="670d4-132">Implementing the <xref:System.ComponentModel.INotifyPropertyChanged> interface when binding data.</span></span> <span data-ttu-id="670d4-133">Diese Schnittstelle ermöglicht es der Eigenschaft eines Objekts, ein gebundenes Steuerelement über die Änderung der Eigenschaft zu benachrichtigen, damit das Steuerelement die aktualisierten Informationen anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="670d4-133">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="670d4-134">Ohne das `CallerMemberName`-Attribut müssen Sie den Eigenschaftennamen als Literal angeben.</span><span class="sxs-lookup"><span data-stu-id="670d4-134">Without the `CallerMemberName` attribute, you must specify the property name as a literal.</span></span>  
  
 <span data-ttu-id="670d4-135">Im folgenden Diagramm sind die Membernamen aufgeführt, die beim Verwenden des `CallerMemberName`-Attributs zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="670d4-135">The following chart shows the member names that are returned when you use the `CallerMemberName` attribute.</span></span>  
  
|<span data-ttu-id="670d4-136">Aufrufe erfolgen in</span><span class="sxs-lookup"><span data-stu-id="670d4-136">Calls occurs within</span></span>|<span data-ttu-id="670d4-137">Ergebnis des Membernamens</span><span class="sxs-lookup"><span data-stu-id="670d4-137">Member name result</span></span>|  
|-------------------------|------------------------|  
|<span data-ttu-id="670d4-138">Methode, Eigenschaft oder Ereignis</span><span class="sxs-lookup"><span data-stu-id="670d4-138">Method, property, or event</span></span>|<span data-ttu-id="670d4-139">Der Name der Methode, der Eigenschaft oder des Ereignisses, aus dem bzw. aus der der Aufruf stammt.</span><span class="sxs-lookup"><span data-stu-id="670d4-139">The name of the method, property, or event from which the call originated.</span></span>|  
|<span data-ttu-id="670d4-140">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="670d4-140">Constructor</span></span>|<span data-ttu-id="670d4-141">Die Zeichenfolge ".ctor"</span><span class="sxs-lookup"><span data-stu-id="670d4-141">The string ".ctor"</span></span>|  
|<span data-ttu-id="670d4-142">Statischer Konstruktor</span><span class="sxs-lookup"><span data-stu-id="670d4-142">Static constructor</span></span>|<span data-ttu-id="670d4-143">Die Zeichenfolge ".cctor"</span><span class="sxs-lookup"><span data-stu-id="670d4-143">The string ".cctor"</span></span>|  
|<span data-ttu-id="670d4-144">Destructor</span><span class="sxs-lookup"><span data-stu-id="670d4-144">Destructor</span></span>|<span data-ttu-id="670d4-145">Die Zeichenfolge "Finalize"</span><span class="sxs-lookup"><span data-stu-id="670d4-145">The string "Finalize"</span></span>|  
|<span data-ttu-id="670d4-146">Benutzerdefinierte Operatoren oder Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="670d4-146">User-defined operators or conversions</span></span>|<span data-ttu-id="670d4-147">Der generierte Name für den Member, beispielsweise "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="670d4-147">The generated name for the member, for example, "op_Addition".</span></span>|  
|<span data-ttu-id="670d4-148">Attributkonstruktor</span><span class="sxs-lookup"><span data-stu-id="670d4-148">Attribute constructor</span></span>|<span data-ttu-id="670d4-149">Der Name des Members, auf den das Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="670d4-149">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="670d4-150">Wenn das Attribut ein beliebiges Element in einem Member ist (z. B. ein Parameter, ein Rückgabewert oder ein generischer Typparameter), wird als Ergebnis der Name des Members ausgegeben, der diesem Element zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="670d4-150">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|  
|<span data-ttu-id="670d4-151">Kein enthaltender Member (z. B. auf Assemblyebene oder Attribute, die auf Typen angewendet werden)</span><span class="sxs-lookup"><span data-stu-id="670d4-151">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="670d4-152">Der Standardwert des optionalen Parameters.</span><span class="sxs-lookup"><span data-stu-id="670d4-152">The default value of the optional parameter.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="670d4-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="670d4-153">See also</span></span>

- [<span data-ttu-id="670d4-154">Attribute (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="670d4-154">Attributes (Visual Basic)</span></span>](../../../visual-basic/language-reference/attributes.md)
- <span data-ttu-id="670d4-155">[Common Attributes (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md) (Gemeinsame Attribute (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="670d4-155">[Common Attributes (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md)</span></span>
- [<span data-ttu-id="670d4-156">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="670d4-156">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="670d4-157">Programming Concepts (Visual Basic) (Programmierkonzepte (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="670d4-157">Programming Concepts (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/index.md)
