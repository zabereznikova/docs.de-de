---
title: Using-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: 6ec0e228b3898f66f27e322b5db2dd7f3bf3d7d6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352758"
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="76348-102">Using-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="76348-102">Using Statement (Visual Basic)</span></span>

<span data-ttu-id="76348-103">Deklariert den Anfang eines `Using` Blocks und ruft optional die Systemressourcen ab, die der Block steuert.</span><span class="sxs-lookup"><span data-stu-id="76348-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>

## <a name="syntax"></a><span data-ttu-id="76348-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="76348-104">Syntax</span></span>

```vb
Using { resourcelist | resourceexpression }
    [ statements ]
End Using
```

## <a name="parts"></a><span data-ttu-id="76348-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="76348-105">Parts</span></span>

|<span data-ttu-id="76348-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="76348-106">Term</span></span>|<span data-ttu-id="76348-107">Definition</span><span class="sxs-lookup"><span data-stu-id="76348-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="76348-108">Erforderlich, wenn Sie keine `resourceexpression`bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="76348-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="76348-109">Eine Liste mit einer oder mehreren Systemressourcen, die von dieser `Using` blockiert werden, durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="76348-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="76348-110">Erforderlich, wenn Sie keine `resourcelist`bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="76348-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="76348-111">Verweis Variable oder-Ausdruck, die auf eine System Ressource verweist, die von diesem `Using` Block gesteuert werden soll.</span><span class="sxs-lookup"><span data-stu-id="76348-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="76348-112">Optional.</span><span class="sxs-lookup"><span data-stu-id="76348-112">Optional.</span></span> <span data-ttu-id="76348-113">Ein Block von-Anweisungen, die der `Using`-Block ausführt.</span><span class="sxs-lookup"><span data-stu-id="76348-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="76348-114">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="76348-114">Required.</span></span> <span data-ttu-id="76348-115">Beendet die Definition des `Using` Blocks und gibt alle von ihm kontrollierten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="76348-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  

 <span data-ttu-id="76348-116">Jede Ressource im `resourcelist` Teil hat die folgende Syntax und die folgenden Teile:</span><span class="sxs-lookup"><span data-stu-id="76348-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>

 `resourcename As New resourcetype [ ( [ arglist ] ) ]`

 <span data-ttu-id="76348-117">\- oder -</span><span class="sxs-lookup"><span data-stu-id="76348-117">-or-</span></span>

 `resourcename As resourcetype = resourceexpression`

## <a name="resourcelist-parts"></a><span data-ttu-id="76348-118">resourceList-Teile</span><span class="sxs-lookup"><span data-stu-id="76348-118">resourcelist Parts</span></span>

|<span data-ttu-id="76348-119">Begriff</span><span class="sxs-lookup"><span data-stu-id="76348-119">Term</span></span>|<span data-ttu-id="76348-120">Definition</span><span class="sxs-lookup"><span data-stu-id="76348-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="76348-121">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="76348-121">Required.</span></span> <span data-ttu-id="76348-122">Verweis Variable, die auf eine System Ressource verweist, die von der `Using` blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="76348-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="76348-123">Erforderlich, wenn die `Using`-Anweisung die Ressource abruft.</span><span class="sxs-lookup"><span data-stu-id="76348-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="76348-124">Wenn Sie die Ressource bereits abgerufen haben, verwenden Sie die zweite Syntax Alternative.</span><span class="sxs-lookup"><span data-stu-id="76348-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="76348-125">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="76348-125">Required.</span></span> <span data-ttu-id="76348-126">Die Klasse der Ressource.</span><span class="sxs-lookup"><span data-stu-id="76348-126">The class of the resource.</span></span> <span data-ttu-id="76348-127">Die-Klasse muss die <xref:System.IDisposable>-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="76348-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="76348-128">Optional.</span><span class="sxs-lookup"><span data-stu-id="76348-128">Optional.</span></span> <span data-ttu-id="76348-129">Liste von Argumenten, die Sie an den Konstruktor übergeben, um eine Instanz von `resourcetype`zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="76348-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="76348-130">Siehe [Parameter Liste](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="76348-130">See [Parameter List](parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="76348-131">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="76348-131">Required.</span></span> <span data-ttu-id="76348-132">Eine Variable oder ein Ausdruck, der auf eine System Ressource verweist, die die Anforderungen von `resourcetype`erfüllt.</span><span class="sxs-lookup"><span data-stu-id="76348-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="76348-133">Wenn Sie die zweite Syntax Alternative verwenden, müssen Sie die Ressource abrufen, bevor Sie die Steuerung an die `Using`-Anweisung übergeben.</span><span class="sxs-lookup"><span data-stu-id="76348-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76348-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="76348-134">Remarks</span></span>

 <span data-ttu-id="76348-135">Manchmal erfordert Ihr Code eine nicht verwaltete Ressource, z. b. ein Datei Handle, einen COM-Wrapper oder eine SQL-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="76348-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="76348-136">Ein `Using` Block gewährleistet, dass mindestens eine solche Ressource freigegeben wird, wenn der Code damit fertig ist.</span><span class="sxs-lookup"><span data-stu-id="76348-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="76348-137">Dies macht Sie für anderen Code verfügbar.</span><span class="sxs-lookup"><span data-stu-id="76348-137">This makes them available for other code to use.</span></span>

 <span data-ttu-id="76348-138">Verwaltete Ressourcen werden vom .NET Framework Garbage Collector (GC) verworfen, ohne dass zusätzliche Codierungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="76348-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="76348-139">Sie benötigen keinen `Using`-Block für verwaltete Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="76348-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="76348-140">Sie können jedoch weiterhin einen `Using`-Block verwenden, um die Freigabe einer verwalteten Ressource zu erzwingen, anstatt auf die Garbage Collector zu warten.</span><span class="sxs-lookup"><span data-stu-id="76348-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>

 <span data-ttu-id="76348-141">Ein `Using`-Block besteht aus drei Teilen: Erwerb, Verwendung und Entsorgung.</span><span class="sxs-lookup"><span data-stu-id="76348-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>

- <span data-ttu-id="76348-142">Der *Erwerb* bedeutet, dass eine Variable erstellt und initialisiert wird, um auf die System Ressource zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="76348-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="76348-143">Mit der `Using`-Anweisung können Sie eine oder mehrere Ressourcen abrufen, oder Sie können genau eine Ressource abrufen, bevor Sie den Block eingeben und für die `Using`-Anweisung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="76348-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="76348-144">Wenn Sie `resourceexpression`bereitstellen, müssen Sie die Ressource abrufen, bevor Sie die Steuerung an die `Using`-Anweisung übergeben.</span><span class="sxs-lookup"><span data-stu-id="76348-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>

- <span data-ttu-id="76348-145">*Verwendung* bedeutet, dass auf die Ressourcen zugegriffen und Aktionen mit Ihnen durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="76348-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="76348-146">Die Anweisungen zwischen `Using` und `End Using` repräsentieren die Verwendung der Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="76348-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>

- <span data-ttu-id="76348-147">Die *Beseitigung* bedeutet, dass die <xref:System.IDisposable.Dispose%2A>-Methode für das-Objekt in `resourcename`aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="76348-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="76348-148">Dies ermöglicht es dem-Objekt, seine Ressourcen ordnungsgemäß zu beenden.</span><span class="sxs-lookup"><span data-stu-id="76348-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="76348-149">Die `End Using`-Anweisung gibt die Ressourcen unter dem Steuerelement des `Using` Blocks frei.</span><span class="sxs-lookup"><span data-stu-id="76348-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>

## <a name="behavior"></a><span data-ttu-id="76348-150">Verhalten</span><span class="sxs-lookup"><span data-stu-id="76348-150">Behavior</span></span>

 <span data-ttu-id="76348-151">Ein `Using`-Block verhält sich wie ein `Try`...`Finally` Konstruktion, in der der `Try` Block die Ressourcen verwendet und der `Finally` Block diese freigibt.</span><span class="sxs-lookup"><span data-stu-id="76348-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="76348-152">Aus diesem Grund wird durch den `Using` Block die Beseitigung der Ressourcen garantiert, unabhängig davon, wie Sie den Block beenden.</span><span class="sxs-lookup"><span data-stu-id="76348-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="76348-153">Dies gilt auch im Fall einer nicht behandelten Ausnahme, mit Ausnahme eines <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="76348-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>

 <span data-ttu-id="76348-154">Der Gültigkeitsbereich jeder Ressourcenvariablen, die durch die `Using`-Anweisung abgerufen wird, ist auf den `Using`-Block beschränkt.</span><span class="sxs-lookup"><span data-stu-id="76348-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>

 <span data-ttu-id="76348-155">Wenn Sie in der `Using`-Anweisung mehr als eine System Ressource angeben, ist der Effekt identisch mit der geschachtelten `Using` Blöcke innerhalb einer anderen.</span><span class="sxs-lookup"><span data-stu-id="76348-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>

 <span data-ttu-id="76348-156">Wenn `resourcename` `Nothing`ist, wird kein <xref:System.IDisposable.Dispose%2A> aufgerufen, und es wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="76348-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>

## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="76348-157">Strukturierte Ausnahmebehandlung innerhalb eines using-Blocks</span><span class="sxs-lookup"><span data-stu-id="76348-157">Structured Exception Handling Within a Using Block</span></span>

 <span data-ttu-id="76348-158">Wenn Sie eine Ausnahme behandeln müssen, die möglicherweise im `Using`-Block auftritt, können Sie eine komplette `Try`...`Finally`-Konstruktion hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="76348-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="76348-159">Wenn Sie den Fall behandeln müssen, in dem die `Using`-Anweisung beim Abrufen einer Ressource nicht erfolgreich ist, können Sie überprüfen, ob `resourcename` `Nothing`ist.</span><span class="sxs-lookup"><span data-stu-id="76348-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>

## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="76348-160">Strukturierte Ausnahmebehandlung anstelle eines using-Blocks</span><span class="sxs-lookup"><span data-stu-id="76348-160">Structured Exception Handling Instead of a Using Block</span></span>

 <span data-ttu-id="76348-161">Wenn Sie eine präzisere Kontrolle über den Erwerb der Ressourcen benötigen oder zusätzlichen Code im `Finally`-Block benötigen, können Sie den `Using`-Block als `Try`...`Finally` Konstruktion umschreiben.</span><span class="sxs-lookup"><span data-stu-id="76348-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="76348-162">Im folgenden Beispiel werden Skeleton `Try` und `Using` Konstruktionen veranschaulicht, die im Erwerb und der Entsorgung von `resource`äquivalent sind.</span><span class="sxs-lookup"><span data-stu-id="76348-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>

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
> <span data-ttu-id="76348-163">Der Code innerhalb des `Using` Blocks sollte das Objekt in `resourcename` nicht einer anderen Variablen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="76348-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="76348-164">Wenn Sie den `Using`-Block beenden, wird die Ressource verworfen, und die andere Variable kann nicht auf die Ressource zugreifen, auf die Sie verweist.</span><span class="sxs-lookup"><span data-stu-id="76348-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>

## <a name="example"></a><span data-ttu-id="76348-165">Beispiel</span><span class="sxs-lookup"><span data-stu-id="76348-165">Example</span></span>

 <span data-ttu-id="76348-166">Im folgenden Beispiel wird eine Datei mit dem Namen Log. txt erstellt, und es werden zwei Textzeilen in die Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="76348-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="76348-167">Das Beispiel liest auch dieselbe Datei und zeigt die Textzeilen an:</span><span class="sxs-lookup"><span data-stu-id="76348-167">The example also reads that same file and displays the lines of text:</span></span>

 <span data-ttu-id="76348-168">Da die Klassen <xref:System.IO.TextWriter> und <xref:System.IO.TextReader> die <xref:System.IDisposable>-Schnittstelle implementieren, kann der Code `Using`-Anweisungen verwenden, um sicherzustellen, dass die Datei nach den Schreib-und Lesevorgängen ordnungsgemäß geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="76348-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>

 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]

## <a name="see-also"></a><span data-ttu-id="76348-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="76348-169">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="76348-170">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="76348-170">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="76348-171">Gewusst wie: Freigeben einer Systemressource</span><span class="sxs-lookup"><span data-stu-id="76348-171">How to: Dispose of a System Resource</span></span>](../../programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
