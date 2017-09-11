---
title: Aufruferinformationen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: 15d556eb-4d0c-4497-98a3-7f60abb7d6a1
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d9a028474a3bb7ae020f466d4dfe51608c43ab07
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="caller-information-visual-basic"></a><span data-ttu-id="d577f-102">Aufruferinformationen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d577f-102">Caller Information (Visual Basic)</span></span>
<span data-ttu-id="d577f-103">Mithilfe der Aufrufer-Informationsattribute können Sie Informationen zum Aufrufer einer Methode abrufen.</span><span class="sxs-lookup"><span data-stu-id="d577f-103">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="d577f-104">Sie können den Dateipfad des Quellcodes, die Zeilennummer im Quellcode und den Membernamen des Aufrufers abrufen.</span><span class="sxs-lookup"><span data-stu-id="d577f-104">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="d577f-105">Diese Informationen sind zum Verfolgen, Debuggen und Erstellen von Diagnosetools sehr nützlich.</span><span class="sxs-lookup"><span data-stu-id="d577f-105">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>  
  
 <span data-ttu-id="d577f-106">Um diese Informationen zu erhalten, verwenden Sie die Attribute, die auf optionale Parameter angewendet werden, von denen jeder einen Standardwert besitzt.</span><span class="sxs-lookup"><span data-stu-id="d577f-106">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="d577f-107">Die folgende Tabelle enthält die Aufrufer-Informationsattribute angegeben, die in definiert sind die <xref:System.Runtime.CompilerServices?displayProperty=fullName>Namespace:</xref:System.Runtime.CompilerServices?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d577f-107">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=fullName> namespace:</span></span>  
  
|<span data-ttu-id="d577f-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="d577f-108">Attribute</span></span>|<span data-ttu-id="d577f-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d577f-109">Description</span></span>|<span data-ttu-id="d577f-110">Typ</span><span class="sxs-lookup"><span data-stu-id="d577f-110">Type</span></span>|  
|---|---|---|  
|<span data-ttu-id="d577f-111"><xref:System.Runtime.CompilerServices.CallerFilePathAttribute></xref:System.Runtime.CompilerServices.CallerFilePathAttribute></span><span class="sxs-lookup"><span data-stu-id="d577f-111"><xref:System.Runtime.CompilerServices.CallerFilePathAttribute></span></span>|<span data-ttu-id="d577f-112">Vollständiger Pfad der Quelldatei, die den Aufrufer enthält.</span><span class="sxs-lookup"><span data-stu-id="d577f-112">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="d577f-113">Dies ist der Dateipfad zum Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="d577f-113">This is the file path at compile time.</span></span>|`String`|  
|<span data-ttu-id="d577f-114"><xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></span><span class="sxs-lookup"><span data-stu-id="d577f-114"><xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></span></span>|<span data-ttu-id="d577f-115">Zeilennummer in der Quelldatei, in der die Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d577f-115">Line number in the source file at which the method is called.</span></span>|`Integer`|  
|<span data-ttu-id="d577f-116"><xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></span><span class="sxs-lookup"><span data-stu-id="d577f-116"><xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></span></span>|<span data-ttu-id="d577f-117">Der Methoden- oder Eigenschaftenname des Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="d577f-117">Method or property name of the caller.</span></span> <span data-ttu-id="d577f-118">Finden Sie unter [Elementnamen](#MEMBERNAMES) weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="d577f-118">See [Member Names](#MEMBERNAMES) later in this topic.</span></span>|`String`|  
  
## <a name="example"></a><span data-ttu-id="d577f-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d577f-119">Example</span></span>  
 <span data-ttu-id="d577f-120">Im folgenden Beispiel wird die Verwendung der Aufrufer-Informationsattribute veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d577f-120">The following example shows how to use Caller Info attributes.</span></span> <span data-ttu-id="d577f-121">Bei jedem Aufruf der `TraceMessage`-Methode werden die Aufruferinformationen als Argumente für optionale Parameter ersetzt.</span><span class="sxs-lookup"><span data-stu-id="d577f-121">On each call to the `TraceMessage` method, the caller information is substituted as arguments to the optional parameters.</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="d577f-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d577f-122">Remarks</span></span>  
 <span data-ttu-id="d577f-123">Sie müssen einen expliziten Standardwert für jeden optionalen Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="d577f-123">You must specify an explicit default value for each optional parameter.</span></span> <span data-ttu-id="d577f-124">Sie können Aufrufer-Informationsattribute nicht auf Parameter anwenden, die nicht als optional festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="d577f-124">You can't apply Caller Info attributes to parameters that aren't specified as optional.</span></span>  
  
 <span data-ttu-id="d577f-125">Durch die Aufrufer-Informationsattribute wird ein Parameter nicht optional.</span><span class="sxs-lookup"><span data-stu-id="d577f-125">The Caller Info attributes don't make a parameter optional.</span></span> <span data-ttu-id="d577f-126">Stattdessen beeinflussen sie den Standardwert, der beim Auslassen des Arguments übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="d577f-126">Instead, they affect the default value that's passed in when the argument is omitted.</span></span>  
  
 <span data-ttu-id="d577f-127">Aufrufer-Informationswerte werden zur Kompilierzeit als Literale in Intermediate Language (IL) ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="d577f-127">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="d577f-128">Im Gegensatz zu den Ergebnissen der <xref:System.Exception.StackTrace%2A>-Eigenschaft für Ausnahmen, die Ergebnisse nicht durch verbergen beeinflusst.</xref:System.Exception.StackTrace%2A></span><span class="sxs-lookup"><span data-stu-id="d577f-128">Unlike the results of the <xref:System.Exception.StackTrace%2A> property for exceptions, the results aren't affected by obfuscation.</span></span>  
  
 <span data-ttu-id="d577f-129">Sie können die optionalen Argumente explizit angeben, um die Aufruferinformationen zu steuern oder auszublenden.</span><span class="sxs-lookup"><span data-stu-id="d577f-129">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>  
  
###  <span data-ttu-id="d577f-130"><a name="MEMBERNAMES"></a>Elementnamen</span><span class="sxs-lookup"><span data-stu-id="d577f-130"><a name="MEMBERNAMES"></a> Member Names</span></span>  
 <span data-ttu-id="d577f-131">Sie können das `CallerMemberName`-Attribut verwenden, um den Membernamen nicht als `String`-Argument für die aufgerufene Methode angeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="d577f-131">You can use the `CallerMemberName` attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="d577f-132">Mithilfe dieser Technik können Sie das Problem vermeiden, **Umgestaltung mit Umbenennung** ändert nicht die `String` Werte.</span><span class="sxs-lookup"><span data-stu-id="d577f-132">By using this technique, you avoid the problem that **Rename Refactoring** doesn't change the `String` values.</span></span> <span data-ttu-id="d577f-133">Dieser Vorteil ist für die folgenden Aufgaben besonders hilfreich:</span><span class="sxs-lookup"><span data-stu-id="d577f-133">This benefit is especially useful for the following tasks:</span></span>  
  
-   <span data-ttu-id="d577f-134">Verwenden der Ablaufverfolgung und der Diagnoseprogramme</span><span class="sxs-lookup"><span data-stu-id="d577f-134">Using tracing and diagnostic routines.</span></span>  
  
-   <span data-ttu-id="d577f-135">Implementieren der <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle beim Binden von Daten.</xref:System.ComponentModel.INotifyPropertyChanged></span><span class="sxs-lookup"><span data-stu-id="d577f-135">Implementing the <xref:System.ComponentModel.INotifyPropertyChanged> interface when binding data.</span></span> <span data-ttu-id="d577f-136">Diese Schnittstelle ermöglicht es der Eigenschaft eines Objekts, ein gebundenes Steuerelement über die Änderung der Eigenschaft zu benachrichtigen, damit das Steuerelement die aktualisierten Informationen anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="d577f-136">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="d577f-137">Ohne das `CallerMemberName`-Attribut müssen Sie den Eigenschaftennamen als Literal angeben.</span><span class="sxs-lookup"><span data-stu-id="d577f-137">Without the `CallerMemberName` attribute, you must specify the property name as a literal.</span></span>  
  
 <span data-ttu-id="d577f-138">Im folgenden Diagramm sind die Membernamen aufgeführt, die beim Verwenden des `CallerMemberName`-Attributs zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d577f-138">The following chart shows the member names that are returned when you use the `CallerMemberName` attribute.</span></span>  
  
|<span data-ttu-id="d577f-139">Aufrufe erfolgen in</span><span class="sxs-lookup"><span data-stu-id="d577f-139">Calls occurs within</span></span>|<span data-ttu-id="d577f-140">Ergebnis des Membernamens</span><span class="sxs-lookup"><span data-stu-id="d577f-140">Member name result</span></span>|  
|-------------------------|------------------------|  
|<span data-ttu-id="d577f-141">Methode, Eigenschaft oder Ereignis</span><span class="sxs-lookup"><span data-stu-id="d577f-141">Method, property, or event</span></span>|<span data-ttu-id="d577f-142">Der Name der Methode, der Eigenschaft oder des Ereignisses, aus dem bzw. aus der der Aufruf stammt.</span><span class="sxs-lookup"><span data-stu-id="d577f-142">The name of the method, property, or event from which the call originated.</span></span>|  
|<span data-ttu-id="d577f-143">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="d577f-143">Constructor</span></span>|<span data-ttu-id="d577f-144">Die Zeichenfolge ".ctor"</span><span class="sxs-lookup"><span data-stu-id="d577f-144">The string ".ctor"</span></span>|  
|<span data-ttu-id="d577f-145">Statischer Konstruktor</span><span class="sxs-lookup"><span data-stu-id="d577f-145">Static constructor</span></span>|<span data-ttu-id="d577f-146">Die Zeichenfolge ".cctor"</span><span class="sxs-lookup"><span data-stu-id="d577f-146">The string ".cctor"</span></span>|  
|<span data-ttu-id="d577f-147">Destruktor</span><span class="sxs-lookup"><span data-stu-id="d577f-147">Destructor</span></span>|<span data-ttu-id="d577f-148">Die Zeichenfolge "Finalize"</span><span class="sxs-lookup"><span data-stu-id="d577f-148">The string "Finalize"</span></span>|  
|<span data-ttu-id="d577f-149">Benutzerdefinierte Operatoren oder Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="d577f-149">User-defined operators or conversions</span></span>|<span data-ttu-id="d577f-150">Der generierte Name für den Member, beispielsweise "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="d577f-150">The generated name for the member, for example, "op_Addition".</span></span>|  
|<span data-ttu-id="d577f-151">Attributkonstruktor</span><span class="sxs-lookup"><span data-stu-id="d577f-151">Attribute constructor</span></span>|<span data-ttu-id="d577f-152">Der Name des Members, auf den das Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="d577f-152">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="d577f-153">Wenn das Attribut ein beliebiges Element in einem Member ist (z. B. ein Parameter, ein Rückgabewert oder ein generischer Typparameter), wird als Ergebnis der Name des Members ausgegeben, der diesem Element zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d577f-153">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|  
|<span data-ttu-id="d577f-154">Kein enthaltender Member (z. B. auf Assemblyebene oder Attribute, die auf Typen angewendet werden)</span><span class="sxs-lookup"><span data-stu-id="d577f-154">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="d577f-155">Der Standardwert des optionalen Parameters.</span><span class="sxs-lookup"><span data-stu-id="d577f-155">The default value of the optional parameter.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d577f-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d577f-156">See Also</span></span>  
 <span data-ttu-id="d577f-157">[Attribute (Visual Basic)](../../../visual-basic/language-reference/attributes.md) </span><span class="sxs-lookup"><span data-stu-id="d577f-157">[Attributes (Visual Basic)](../../../visual-basic/language-reference/attributes.md) </span></span>  
<span data-ttu-id="d577f-158"> [Allgemeine Attribute (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="d577f-158"> [Common Attributes (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md) </span></span>  
<span data-ttu-id="d577f-159"> [Optionale Parameter](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="d577f-159"> [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md) </span></span>  
<span data-ttu-id="d577f-160"> [Programmierkonzepte (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md)</span><span class="sxs-lookup"><span data-stu-id="d577f-160"> [Programming Concepts (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md)</span></span>
