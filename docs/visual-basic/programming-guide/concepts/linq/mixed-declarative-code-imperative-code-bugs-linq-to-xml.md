---
title: Fehler durch Vermischung von deklarativem und imperativem Code (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: f12b1ab4-bb92-4b92-a648-0525e45b3ce7
ms.openlocfilehash: e5526a64805b19ea293d3ef28636738923d03662
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84361072"
---
# <a name="mixed-declarative-codeimperative-code-bugs-linq-to-xml-visual-basic"></a><span data-ttu-id="ebb0c-102">Fehler bei gemischtem deklarativem Code/imperativem Code (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebb0c-102">Mixed Declarative Code/Imperative Code Bugs (LINQ to XML) (Visual Basic)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="ebb0c-103">enthält verschiedene Methoden, mit denen Sie eine XML-Struktur direkt ändern können.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-103">contains various methods that allow you to modify an XML tree directly.</span></span> <span data-ttu-id="ebb0c-104">Sie können Elemente hinzufügen, Elemente löschen, den Inhalt eines Elements ändern, Attribute hinzufügen usw.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-104">You can add elements, delete elements, change the contents of an element, add attributes, and so on.</span></span> <span data-ttu-id="ebb0c-105">Diese Programmierschnittstelle wird in Ändern von XML-Strukturen [(LINQ to XML) (Visual Basic)](modifying-xml-trees-linq-to-xml.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-105">This programming interface is described in [Modifying XML Trees (LINQ to XML) (Visual Basic)](modifying-xml-trees-linq-to-xml.md).</span></span> <span data-ttu-id="ebb0c-106">Wenn Sie eine Iteration durch eine der Achsen, z. B. <xref:System.Xml.Linq.XContainer.Elements%2A> durchlaufen, und Sie dabei die XML-Struktur ändern, kann es zu einer Reihe eigenartiger Fehler kommen.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-106">If you are iterating through one of the axes, such as <xref:System.Xml.Linq.XContainer.Elements%2A>, and you are modifying the XML tree as you iterate through the axis, you can end up with some strange bugs.</span></span>  
  
 <span data-ttu-id="ebb0c-107">Dieses Problem wird manchmal als "Halloween-Problem" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-107">This problem is sometimes known as "The Halloween Problem".</span></span>  
  
## <a name="definition-of-the-problem"></a><span data-ttu-id="ebb0c-108">Definition des Problems</span><span class="sxs-lookup"><span data-stu-id="ebb0c-108">Definition of the Problem</span></span>  
 <span data-ttu-id="ebb0c-109">Wenn Sie unter Verwendung von LINQ Code schreiben, der eine Auflistung durchläuft, schreiben Sie Code in einem deklarativen Stil.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-109">When you write some code using LINQ that iterates through a collection, you are writing code in a declarative style.</span></span> <span data-ttu-id="ebb0c-110">Dabei beschreiben Sie eher, *was* Sie möchten, statt zu beschreiben, *wie* Sie es möchten.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-110">It is more akin to describing *what* you want, rather that *how* you want to get it done.</span></span> <span data-ttu-id="ebb0c-111">Wenn Sie Code schreiben würden, der 1.) das erste Element abruft, 2.) das Element auf bestimmte Bedingungen testet, 3.) das Element modifiziert und 4.) das Element dann wieder in die Liste setzt, wäre dies imperativer Code.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-111">If you write code that 1) gets the first element, 2) tests it for some condition, 3) modifies it, and 4) puts it back into the list, then this would be imperative code.</span></span> <span data-ttu-id="ebb0c-112">Sie würden dem Computer damit sagen, *wie* er die von Ihnen gestellte Aufgabe ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-112">You are telling the computer *how* to do what you want done.</span></span>  
  
 <span data-ttu-id="ebb0c-113">Wenn nun diese Formen von Code in ein und derselben Operation miteinander vermischt werden, treten Probleme auf.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-113">Mixing these styles of code in the same operation is what leads to problems.</span></span> <span data-ttu-id="ebb0c-114">Nehmen wir einmal die folgende Situation:</span><span class="sxs-lookup"><span data-stu-id="ebb0c-114">Consider the following:</span></span>  
  
 <span data-ttu-id="ebb0c-115">Stellen Sie sich vor, Sie haben eine verknüpfte Liste mit drei Elementen darin (a, b und c):</span><span class="sxs-lookup"><span data-stu-id="ebb0c-115">Suppose you have a linked list with three items in it (a, b, and c):</span></span>  
  
 `a -> b -> c`  
  
 <span data-ttu-id="ebb0c-116">Stellen Sie sich nun vor, Sie möchten die verknüpfte Liste durchgehen und drei neue Elemente (a', b' und c') hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-116">Now, suppose that you want to move through the linked list, adding three new items (a', b', and c').</span></span> <span data-ttu-id="ebb0c-117">Die resultierende verknüpfte Liste soll dann wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="ebb0c-117">You want the resulting linked list to look like this:</span></span>  
  
 `a -> a' -> b -> b' -> c -> c'`  
  
 <span data-ttu-id="ebb0c-118">Sie schreiben also Code, der die Liste durchläuft, und der sofort anschließend für jedes Element ein neues Element hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-118">So you write code that iterates through the list, and for every item, adds a new item right after it.</span></span> <span data-ttu-id="ebb0c-119">Nun geschieht Folgendes: Ihr Code sieht zuerst das `a`-Element und fügt dahinter `a'` ein.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-119">What happens is that your code will first see the `a` element, and insert `a'` after it.</span></span> <span data-ttu-id="ebb0c-120">Der Code geht dann zum nächsten Knoten in der Liste, dieser Knoten ist aber jetzt `a'`.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-120">Now, your code will move to the next node in the list, which is now `a'`!</span></span> <span data-ttu-id="ebb0c-121">Das stört den Code nicht, und er fügt der Liste ein neues Element, also `a''`, hinzu.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-121">It happily adds a new item to the list, `a''`.</span></span>  
  
 <span data-ttu-id="ebb0c-122">Wie würden Sie dieses Problem im richtigen Leben lösen?</span><span class="sxs-lookup"><span data-stu-id="ebb0c-122">How would you solve this in the real world?</span></span> <span data-ttu-id="ebb0c-123">Nun, Sie könnten eine Kopie der ursprünglichen verknüpften Liste anlegen und eine vollkommen neue Liste erstellen.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-123">Well, you might make a copy of the original linked list, and create a completely new list.</span></span> <span data-ttu-id="ebb0c-124">Sie könnten aber auch rein imperativen Code schreiben. Dieser würde dann das erste Element finden, das neue Element hinzufügen und dann in der verknüpften Liste zwei Knoten weitergehen und damit das Element übergehen, das Sie gerade hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-124">Or if you are writing purely imperative code, you might find the first item, add the new item, and then advance twice in the linked list, advancing over the element that you just added.</span></span>  
  
## <a name="adding-while-iterating"></a><span data-ttu-id="ebb0c-125">Hinzufügungen beim Durchlaufen</span><span class="sxs-lookup"><span data-stu-id="ebb0c-125">Adding While Iterating</span></span>  
 <span data-ttu-id="ebb0c-126">Angenommen, Sie möchten Code schreiben, der für jedes Element in einer Struktur ein Duplikat erstellt.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-126">For example, suppose you want to write some code that for every element in a tree, you want to create a duplicate element:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
For Each e As XElement In root.Elements()  
    root.Add(New XElement(e.Name, e.Value))  
Next  
```  
  
 <span data-ttu-id="ebb0c-127">Dieser Code führt zu einer Endlosschleife.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-127">This code goes into an infinite loop.</span></span> <span data-ttu-id="ebb0c-128">Die `foreach`-Anweisung durchläuft die `Elements()`-Achse und fügt dabei dem `doc`-Element neue Elemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-128">The `foreach` statement iterates through the `Elements()` axis, adding new elements to the `doc` element.</span></span> <span data-ttu-id="ebb0c-129">Das Ergebnis ist, dass die Anweisung auch die gerade hinzugefügten Elemente durchläuft</span><span class="sxs-lookup"><span data-stu-id="ebb0c-129">It ends up iterating also through the elements it just added.</span></span> <span data-ttu-id="ebb0c-130">und bei jedem Durchlaufen der Schleife neue Objekte zuweist. Irgendwann wird der gesamte verfügbare Arbeitsspeicher dafür in Beschlag genommen.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-130">And because it allocates new objects with every iteration of the loop, it will eventually consume all available memory.</span></span>  
  
 <span data-ttu-id="ebb0c-131">Dieses Problem können Sie beheben, indem Sie die Auflistung mit dem <xref:System.Linq.Enumerable.ToList%2A>-Standardabfrageoperator in den Arbeitsspeicher ziehen. Dies ist im Folgenden dargestellt:</span><span class="sxs-lookup"><span data-stu-id="ebb0c-131">You can fix this problem by pulling the collection into memory using the <xref:System.Linq.Enumerable.ToList%2A> standard query operator, as follows:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
For Each e As XElement In root.Elements().ToList()  
    root.Add(New XElement(e.Name, e.Value))  
Next  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="ebb0c-132">Jetzt funktioniert der Code.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-132">Now the code works.</span></span> <span data-ttu-id="ebb0c-133">Die resultierende XML-Struktur sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="ebb0c-133">The resulting XML tree is the following:</span></span>  
  
```xml  
<Root>  
  <A>1</A>  
  <B>2</B>  
  <C>3</C>  
  <A>1</A>  
  <B>2</B>  
  <C>3</C>  
</Root>  
```  
  
## <a name="deleting-while-iterating"></a><span data-ttu-id="ebb0c-134">Löschungen beim Durchlaufen</span><span class="sxs-lookup"><span data-stu-id="ebb0c-134">Deleting While Iterating</span></span>  
 <span data-ttu-id="ebb0c-135">Wenn Sie alle Knoten auf einer bestimmten Ebene löschen möchten, könnten Sie versucht sein, Code wie den folgenden zu schreiben:</span><span class="sxs-lookup"><span data-stu-id="ebb0c-135">If you want to delete all nodes at a certain level, you might be tempted to write code like the following:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
For Each e As XElement In root.Elements()  
    e.Remove()  
Next  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="ebb0c-136">Ein solcher Code würde aber nicht zum gewünschten Ergebnis führen.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-136">However, this does not do what you want.</span></span> <span data-ttu-id="ebb0c-137">Nachdem Sie das erste Element, A, entfernt haben, würde es aus der im Stamm enthaltenen XML-Struktur entfernt werden, sodass der Code in der <legacyBold>Elements</legacyBold>-Methode, der die Iteration vornimmt, das nächste Element nicht finden könnte.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-137">In this situation, after you have removed the first element, A, it is removed from the XML tree contained in root, and the code in the Elements method that is doing the iterating cannot find the next element.</span></span>  
  
 <span data-ttu-id="ebb0c-138">Der oben genannte Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="ebb0c-138">The preceding code produces the following output:</span></span>  
  
```xml  
<Root>  
  <B>2</B>  
  <C>3</C>  
</Root>  
```  
  
 <span data-ttu-id="ebb0c-139">Auch hier besteht die Lösung darin, <xref:System.Linq.Enumerable.ToList%2A> aufzurufen, um die Auflistung wie folgt zu materialisieren:</span><span class="sxs-lookup"><span data-stu-id="ebb0c-139">The solution again is to call <xref:System.Linq.Enumerable.ToList%2A> to materialize the collection, as follows:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
For Each e As XElement In root.Elements().ToList()  
    e.Remove()  
Next  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="ebb0c-140">Dies erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="ebb0c-140">This produces the following output:</span></span>  
  
```xml  
<Root />  
```  
  
 <span data-ttu-id="ebb0c-141">Alternativ dazu können Sie die Iteration ganz eliminieren, indem Sie für das übergeordnete Element <xref:System.Xml.Linq.XElement.RemoveAll%2A> aufrufen:</span><span class="sxs-lookup"><span data-stu-id="ebb0c-141">Alternatively, you can eliminate the iteration altogether by calling <xref:System.Xml.Linq.XElement.RemoveAll%2A> on the parent element:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
root.RemoveAll()  
Console.WriteLine(root)  
```  
  
## <a name="why-cant-linq-automatically-handle-this"></a><span data-ttu-id="ebb0c-142">Warum kann LINQ dieses Problem nicht automatisch lösen?</span><span class="sxs-lookup"><span data-stu-id="ebb0c-142">Why Can't LINQ Automatically Handle This?</span></span>  
 <span data-ttu-id="ebb0c-143">Eine Herangehensweise bestünde darin, immer alles in den Arbeitsspeicher zu holen, statt mit verzögerter Auswertung zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-143">One approach would be to always bring everything into memory instead of doing lazy evaluation.</span></span> <span data-ttu-id="ebb0c-144">Dies würde aber massive Leistungseinbußen und einen hohen Arbeitsspeicherbedarf mit sich bringen.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-144">However, it would be very expensive in terms of performance and memory use.</span></span> <span data-ttu-id="ebb0c-145">Im praktischen Einsatz würden LINQ und LINQ to XML bei dieser Variante scheitern.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-145">In fact, if LINQ and (LINQ to XML) were to take this approach, it would fail in real-world situations.</span></span>  
  
 <span data-ttu-id="ebb0c-146">Ein anderer möglicher Ansatz bestünde darin, eine gewisse Transaktionssyntax in LINQ einzubauen und den Compiler zu veranlassen, den Code zu analysieren und zu bestimmen, ob irgendeine Auflistung materialisiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-146">Another possible approach would be to put in some sort of transaction syntax into LINQ, and have the compiler attempt to analyze the code and determine if any particular collection needed to be materialized.</span></span> <span data-ttu-id="ebb0c-147">Der Versuch, allen Code zu bestimmen, der Nebenwirkungen hat, ist aber eine unglaublich komplexe Angelegenheit.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-147">However, attempting to determine all code that has side-effects is incredibly complex.</span></span> <span data-ttu-id="ebb0c-148">Betrachten Sie folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="ebb0c-148">Consider the following code:</span></span>  
  
```vb  
Dim z = _  
    From e In root.Elements() _  
    Where (TestSomeCondition(e)) _  
    Select DoMyProjection(e)  
```  
  
 <span data-ttu-id="ebb0c-149">Solch ein Analysecode müsste die Methoden <legacyBold>TestSomeCondition</legacyBold> und <legacyBold>DoMyProjection</legacyBold> sowie alle von diesen Methoden aufgerufenen Methoden analysieren, um zu bestimmen, ob Code mit Nebenwirkungen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-149">Such analysis code would need to analyze the methods TestSomeCondition and DoMyProjection, and all methods that those methods called, to determine if any code had side-effects.</span></span> <span data-ttu-id="ebb0c-150">Der Analysecode kann aber nicht nur einfach nach Code mit Nebenwirkungen suchen.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-150">But the analysis code could not just look for any code that had side-effects.</span></span> <span data-ttu-id="ebb0c-151">Er dürfte nur den Code auswählen, der in dieser Situation Nebenwirkungen auf die untergeordneten Elemente von `root` hat.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-151">It would need to select for just the code that had side-effects on the child elements of `root` in this situation.</span></span>  
  
 <span data-ttu-id="ebb0c-152">LINQ to XML unternimmt keine Versuche, eine solche Analyse durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-152">LINQ to XML does not attempt to do any such analysis.</span></span>  
  
 <span data-ttu-id="ebb0c-153">Für die Vermeidung dieser Probleme sind allein Sie zuständig.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-153">It is up to you to avoid these problems.</span></span>  
  
## <a name="guidance"></a><span data-ttu-id="ebb0c-154">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="ebb0c-154">Guidance</span></span>  
 <span data-ttu-id="ebb0c-155">Vermischen Sie deklarativen Code nicht mit imperativem Code.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-155">First, do not mix declarative and imperative code.</span></span>  
  
 <span data-ttu-id="ebb0c-156">Auch wenn Sie die Semantik Ihrer Auflistungen und die Semantik der Methoden, die die XML-Struktur ändern, exakt kennen und "cleveren" Code schreiben, der diese Art von Problemen vermeidet, muss Ihr Code zukünftig von anderen Entwicklern gewartet werden, die sich vielleicht mit dieser Problematik nicht so gut auskennen.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-156">Even if you know exactly the semantics of your collections and the semantics of the methods that modify the XML tree, if you write some clever code that avoids these categories of problems, your code will need to be maintained by other developers in the future, and they may not be as clear on the issues.</span></span> <span data-ttu-id="ebb0c-157">Wenn Sie deklarativen und imperativen Code mischen, ist der Code anfälliger.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-157">If you mix declarative and imperative coding styles, your code will be more brittle.</span></span>  
  
 <span data-ttu-id="ebb0c-158">Wenn Sie Code schreiben, der eine Auflistung so materialisiert, dass diese Probleme vermieden werden, versehen Sie ihn mit entsprechenden Kommentaren, um die für die Wartung zuständigen Programmierer über die Problematik zu informieren.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-158">If you write code that materializes a collection so that these problems are avoided, note it with comments as appropriate in your code, so that maintenance programmers will understand the issue.</span></span>  
  
 <span data-ttu-id="ebb0c-159">Wenn die Arbeitsgeschwindigkeit und andere Überlegungen es zulassen, sollten Sie immer nur deklarativen Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-159">Second, if performance and other considerations allow, use only declarative code.</span></span> <span data-ttu-id="ebb0c-160">Ändern Sie nicht Ihre vorhandene XML-Struktur.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-160">Don't modify your existing XML tree.</span></span> <span data-ttu-id="ebb0c-161">Generieren Sie stattdessen eine neue Struktur.</span><span class="sxs-lookup"><span data-stu-id="ebb0c-161">Generate a new one.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
Dim newRoot As XElement = New XElement("Root", _  
    root.Elements(), root.Elements())  
Console.WriteLine(newRoot)  
```  
  
## <a name="see-also"></a><span data-ttu-id="ebb0c-162">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ebb0c-162">See also</span></span>

- [<span data-ttu-id="ebb0c-163">Erweiterte LINQ to XML Programmierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebb0c-163">Advanced LINQ to XML Programming (Visual Basic)</span></span>](advanced-linq-to-xml-programming.md)
