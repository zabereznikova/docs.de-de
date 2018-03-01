---
title: Using-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ed9cc0d04c89eac1fe342a0924dd89bb1e258a11
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="e5f37-102">Using-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5f37-102">Using Statement (Visual Basic)</span></span>
<span data-ttu-id="e5f37-103">Deklariert den Beginn einer `Using` blockieren und ruft optional die Systemressourcen, die steuert, der Block ab.</span><span class="sxs-lookup"><span data-stu-id="e5f37-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5f37-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5f37-104">Syntax</span></span>  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a><span data-ttu-id="e5f37-105">Teile</span><span class="sxs-lookup"><span data-stu-id="e5f37-105">Parts</span></span>  
  
|<span data-ttu-id="e5f37-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="e5f37-106">Term</span></span>|<span data-ttu-id="e5f37-107">Definition</span><span class="sxs-lookup"><span data-stu-id="e5f37-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="e5f37-108">Erforderlich, wenn Sie keine angeben `resourceexpression`.</span><span class="sxs-lookup"><span data-stu-id="e5f37-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="e5f37-109">Liste der Systemressourcen für eine oder mehrere, die von diesem `Using` blockieren, Steuerelemente, die durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="e5f37-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="e5f37-110">Erforderlich, wenn Sie keine angeben `resourcelist`.</span><span class="sxs-lookup"><span data-stu-id="e5f37-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="e5f37-111">Verweisvariable oder einen Ausdruck verweist auf eine Systemressource, die von diesem gesteuert werden `Using` Block.</span><span class="sxs-lookup"><span data-stu-id="e5f37-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="e5f37-112">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e5f37-112">Optional.</span></span> <span data-ttu-id="e5f37-113">Block von Anweisungen, die die `Using` -Block ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e5f37-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="e5f37-114">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e5f37-114">Required.</span></span> <span data-ttu-id="e5f37-115">Beendet die Definition des der `Using` Block und verwirft alle Ressourcen an, die er steuert.</span><span class="sxs-lookup"><span data-stu-id="e5f37-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  
  
 <span data-ttu-id="e5f37-116">Jede Ressource in der `resourcelist` Teil hat die folgende Syntax und Bestandteile:</span><span class="sxs-lookup"><span data-stu-id="e5f37-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 <span data-ttu-id="e5f37-117">- oder - </span><span class="sxs-lookup"><span data-stu-id="e5f37-117">-or-</span></span>  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a><span data-ttu-id="e5f37-118">ResourceList-Teile</span><span class="sxs-lookup"><span data-stu-id="e5f37-118">resourcelist Parts</span></span>  
  
|<span data-ttu-id="e5f37-119">Begriff</span><span class="sxs-lookup"><span data-stu-id="e5f37-119">Term</span></span>|<span data-ttu-id="e5f37-120">Definition</span><span class="sxs-lookup"><span data-stu-id="e5f37-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="e5f37-121">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e5f37-121">Required.</span></span> <span data-ttu-id="e5f37-122">Verweisvariable, der auf eine Systemressource verweist, die die `Using` Steuerelemente zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="e5f37-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="e5f37-123">Erforderlich, wenn die `Using` -Anweisung ruft die Ressource ab.</span><span class="sxs-lookup"><span data-stu-id="e5f37-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="e5f37-124">Wenn Sie die Ressource bereits abgerufen haben, verwenden Sie die zweite Syntax Alternative.</span><span class="sxs-lookup"><span data-stu-id="e5f37-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="e5f37-125">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e5f37-125">Required.</span></span> <span data-ttu-id="e5f37-126">Die Klasse der Ressource.</span><span class="sxs-lookup"><span data-stu-id="e5f37-126">The class of the resource.</span></span> <span data-ttu-id="e5f37-127">Implementieren Sie die Klasse muss die <xref:System.IDisposable> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e5f37-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="e5f37-128">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e5f37-128">Optional.</span></span> <span data-ttu-id="e5f37-129">Liste von Argumenten an den Konstruktor zum Erstellen einer Instanz von übergeben `resourcetype`.</span><span class="sxs-lookup"><span data-stu-id="e5f37-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="e5f37-130">Finden Sie unter [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="e5f37-130">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="e5f37-131">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e5f37-131">Required.</span></span> <span data-ttu-id="e5f37-132">Variable oder ein Ausdruck verweist auf eine Systemressource, erfüllen die Anforderungen des `resourcetype`.</span><span class="sxs-lookup"><span data-stu-id="e5f37-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="e5f37-133">Wenn Sie in der zweiten Alternative Syntax verwenden, müssen Sie die Ressource abrufen, bevor Sie übergeben der Steuerung an die `Using` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e5f37-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5f37-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e5f37-134">Remarks</span></span>  
 <span data-ttu-id="e5f37-135">Mitunter muss Ihren Code eine nicht verwaltete Ressource, z. B. ein Dateihandle, ein COM-Wrapper oder eine SQL-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="e5f37-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="e5f37-136">Ein `Using` Block gewährleistet die Freigabe dieser Ressourcen aus, wenn mit diesen Code abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="e5f37-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="e5f37-137">Dadurch sind sie von anderem Code zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e5f37-137">This makes them available for other code to use.</span></span>  
  
 <span data-ttu-id="e5f37-138">Verwaltete Ressourcen werden der von der .NET Framework-Garbage Collector (GC) freigegeben, ohne zusätzliche Codierung ihrerseits.</span><span class="sxs-lookup"><span data-stu-id="e5f37-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="e5f37-139">Sie müssen keine `Using` Block für die verwalteten Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="e5f37-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="e5f37-140">Allerdings können Sie weiterhin verwenden eine `Using` Block, um die Freigabe einer verwalteten Ressource nicht erst, wenn für den Garbage Collector zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="e5f37-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="e5f37-141">Ein `Using` Block besteht aus drei Teilen: Abruf, Verwendung und Freigabe.</span><span class="sxs-lookup"><span data-stu-id="e5f37-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>  
  
-   <span data-ttu-id="e5f37-142">*Erhalt* bedeutet, dass eine Variable erstellen und initialisieren es auf der Systemressource verweist.</span><span class="sxs-lookup"><span data-stu-id="e5f37-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="e5f37-143">Die `Using` Anweisung kann eine oder mehrere Ressourcen erwerben oder können Sie genau eine Ressource vor dem Wechsel in des Blocks abzurufen und sie zum Bereitstellen der `Using` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e5f37-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="e5f37-144">Wenn Sie angeben `resourceexpression`, Sie müssen die Ressource abrufen, bevor Sie übergeben der Steuerung an die `Using` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e5f37-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>  
  
-   <span data-ttu-id="e5f37-145">*Verwendung* bedeutet, dass Zugriff auf die Ressourcen und Aktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="e5f37-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="e5f37-146">Die Anweisungen zwischen `Using` und `End Using` die Nutzung der Ressourcen darstellen.</span><span class="sxs-lookup"><span data-stu-id="e5f37-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>  
  
-   <span data-ttu-id="e5f37-147">*Beseitigung* aufrufen bedeutet, dass die <xref:System.IDisposable.Dispose%2A> Methode für das Objekt in `resourcename`.</span><span class="sxs-lookup"><span data-stu-id="e5f37-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="e5f37-148">Dadurch wird das Objekt seine Ressourcen sauber beendet.</span><span class="sxs-lookup"><span data-stu-id="e5f37-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="e5f37-149">Die `End Using` Anweisung verwirft die Ressourcen unter der `Using` des TextBlock-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e5f37-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="e5f37-150">Verhalten</span><span class="sxs-lookup"><span data-stu-id="e5f37-150">Behavior</span></span>  
 <span data-ttu-id="e5f37-151">Ein `Using` Block verhält sich wie ein `Try`... `Finally` Konstruktion, in dem die `Try` Block verwendet wird, die Ressourcen und die `Finally` Block freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e5f37-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="e5f37-152">Aus diesem Grund die `Using` Block wird sichergestellt, Freigabe von Ressourcen, unabhängig davon, wie Sie den Block zu beenden.</span><span class="sxs-lookup"><span data-stu-id="e5f37-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="e5f37-153">Dies gilt sogar im Fall einer nicht behandelten Ausnahme, mit Ausnahme von einer <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="e5f37-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>  
  
 <span data-ttu-id="e5f37-154">Rahmen jeder Ressourcenvariablen durch die `Using` Anweisung ist auf die `Using` Block.</span><span class="sxs-lookup"><span data-stu-id="e5f37-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>  
  
 <span data-ttu-id="e5f37-155">Bei Angabe von mehr als eine Systemressource, die in der `Using` -Anweisung, die Auswirkung ist identisch, als ob Sie geschachtelte `Using` ineinander blockiert.</span><span class="sxs-lookup"><span data-stu-id="e5f37-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>  
  
 <span data-ttu-id="e5f37-156">Wenn `resourcename` ist `Nothing`, ohne Aufruf <xref:System.IDisposable.Dispose%2A> erfolgt, und es wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e5f37-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>  
  
## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="e5f37-157">Innerhalb eines Blocks verwenden die strukturierte Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="e5f37-157">Structured Exception Handling Within a Using Block</span></span>  
 <span data-ttu-id="e5f37-158">Wenn Sie eine Ausnahme zu behandeln, die innerhalb von auftreten müssen die `Using` blockieren, können Sie eine vollständige hinzufügen `Try`... `Finally` -Konstruktion hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e5f37-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="e5f37-159">Wenn Sie die Groß-/Kleinschreibung behandeln müssen, in dem die `Using` Anweisung ist nicht beim Abrufen einer Ressourcenpools erfolgreich, Sie können testen, um festzustellen, wenn `resourcename` ist `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="e5f37-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="e5f37-160">Strukturierte Ausnahmebehandlung anstelle eines Blocks verwenden</span><span class="sxs-lookup"><span data-stu-id="e5f37-160">Structured Exception Handling Instead of a Using Block</span></span>  
 <span data-ttu-id="e5f37-161">Wenn Sie eine präzisere Steuerung der Übernahme der Ressourcen, benötigen Sie zusätzlichen Code in der `Finally` blockieren, können Sie Umschreiben der `Using` als blockiert eine `Try`... `Finally` Konstruktion.</span><span class="sxs-lookup"><span data-stu-id="e5f37-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="e5f37-162">Das folgende Beispiel zeigt Skeleton `Try` und `Using` Konstruktionen, die in den Erhalt und die Beseitigung von entsprechen `resource`.</span><span class="sxs-lookup"><span data-stu-id="e5f37-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>  
  
```vb  
Using resource As New resourceType   
    ' Insert code to work with resource.  
End Using  
  
' For the acquisition and disposal of resource, the following  
' Try construction is equivalent to the Using block.  
Dim resource As New resourceType  
Try   
    ' Insert code to work with resource.  
Finally   
    If resource IsNot Nothing Then  
        resource.Dispose()   
    End If  
End Try   
```  
  
> [!NOTE]
>  <span data-ttu-id="e5f37-163">Der Code innerhalb der `Using` Block sollten nicht das Objekt im zuweisen `resourcename` einer anderen Variablen.</span><span class="sxs-lookup"><span data-stu-id="e5f37-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="e5f37-164">Wenn Sie beenden die `Using` blockieren, die Ressource freigegeben wird, und die andere Variable kann nicht auf den er zeigt Ressource zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="e5f37-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5f37-165">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e5f37-165">Example</span></span>  
 <span data-ttu-id="e5f37-166">Das folgende Beispiel erstellt eine Datei mit dem Namen log.txt und zwei Textzeilen in die Datei schreibt.</span><span class="sxs-lookup"><span data-stu-id="e5f37-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="e5f37-167">Im Beispiel wird auch liest diese Datei und zeigt die Textzeilen.</span><span class="sxs-lookup"><span data-stu-id="e5f37-167">The example also reads that same file and displays the lines of text.</span></span>  
  
 <span data-ttu-id="e5f37-168">Da die <xref:System.IO.TextWriter> und <xref:System.IO.TextReader> Klassen implementieren die <xref:System.IDisposable> -Schnittstelle, die den Code verwenden kann `Using` Anweisungen, um sicherzustellen, dass die Datei ordnungsgemäß werden, nach dem Schreiben geschlossen und Lesevorgänge.</span><span class="sxs-lookup"><span data-stu-id="e5f37-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>  
  
 [!code-vb[VbVbalrStatements#50](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/using-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e5f37-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5f37-169">See Also</span></span>  
 <xref:System.IDisposable>  
 [<span data-ttu-id="e5f37-170">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e5f37-170">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="e5f37-171">Gewusst wie: Freigeben einer Systemressource</span><span class="sxs-lookup"><span data-stu-id="e5f37-171">How to: Dispose of a System Resource</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
