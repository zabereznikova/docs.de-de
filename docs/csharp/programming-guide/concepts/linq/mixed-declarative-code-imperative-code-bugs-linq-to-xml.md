---
title: Fehler durch Vermischung von deklarativem und imperativem Code (LINQ to XML) (C#)
description: LINQ to XML-Methoden können eine XML-Struktur direkt ändern. Das Durchlaufen einer der Achsen während der Änderung der XML-Struktur kann zu unkalkulierbaren Fehlern führen.
ms.date: 07/20/2015
ms.assetid: fada62d0-0680-4e73-945a-2b00d7a507af
ms.openlocfilehash: 4eaed10f0a2e64abeb7725dcd70816d75d8a0423
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165295"
---
# <a name="mixed-declarative-codeimperative-code-bugs-linq-to-xml-c"></a><span data-ttu-id="38d8e-104">Fehler durch Vermischung von deklarativem und imperativem Code (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="38d8e-104">Mixed Declarative Code/Imperative Code Bugs (LINQ to XML) (C#)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="38d8e-105">enthält verschiedene Methoden, mit denen Sie eine XML-Struktur direkt ändern können.</span><span class="sxs-lookup"><span data-stu-id="38d8e-105">contains various methods that allow you to modify an XML tree directly.</span></span> <span data-ttu-id="38d8e-106">Sie können Elemente hinzufügen, Elemente löschen, den Inhalt eines Elements ändern, Attribute hinzufügen usw.</span><span class="sxs-lookup"><span data-stu-id="38d8e-106">You can add elements, delete elements, change the contents of an element, add attributes, and so on.</span></span> <span data-ttu-id="38d8e-107">Diese Programmierschnittstelle wird in [Ändern von XML-Strukturen (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="38d8e-107">This programming interface is described in [Modifying XML Trees (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span></span> <span data-ttu-id="38d8e-108">Wenn Sie eine Iteration durch eine der Achsen, z. B. <xref:System.Xml.Linq.XContainer.Elements%2A> durchlaufen, und Sie dabei die XML-Struktur ändern, kann es zu einer Reihe eigenartiger Fehler kommen.</span><span class="sxs-lookup"><span data-stu-id="38d8e-108">If you are iterating through one of the axes, such as <xref:System.Xml.Linq.XContainer.Elements%2A>, and you are modifying the XML tree as you iterate through the axis, you can end up with some strange bugs.</span></span>  
  
 <span data-ttu-id="38d8e-109">Dieses Problem wird manchmal als "Halloween-Problem" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="38d8e-109">This problem is sometimes known as "The Halloween Problem".</span></span>  
  
## <a name="definition-of-the-problem"></a><span data-ttu-id="38d8e-110">Definition des Problems</span><span class="sxs-lookup"><span data-stu-id="38d8e-110">Definition of the Problem</span></span>  
 <span data-ttu-id="38d8e-111">Wenn Sie unter Verwendung von LINQ Code schreiben, der eine Auflistung durchläuft, schreiben Sie Code in einem deklarativen Stil.</span><span class="sxs-lookup"><span data-stu-id="38d8e-111">When you write some code using LINQ that iterates through a collection, you are writing code in a declarative style.</span></span> <span data-ttu-id="38d8e-112">Dabei beschreiben Sie eher, *was* Sie möchten, statt zu beschreiben, *wie* Sie es möchten.</span><span class="sxs-lookup"><span data-stu-id="38d8e-112">It is more akin to describing *what* you want, rather that *how* you want to get it done.</span></span> <span data-ttu-id="38d8e-113">Wenn Sie Code schreiben würden, der 1.) das erste Element abruft, 2.) das Element auf bestimmte Bedingungen testet, 3.) das Element modifiziert und 4.) das Element dann wieder in die Liste setzt, wäre dies imperativer Code.</span><span class="sxs-lookup"><span data-stu-id="38d8e-113">If you write code that 1) gets the first element, 2) tests it for some condition, 3) modifies it, and 4) puts it back into the list, then this would be imperative code.</span></span> <span data-ttu-id="38d8e-114">Sie würden dem Computer damit sagen, *wie* er die von Ihnen gestellte Aufgabe ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="38d8e-114">You are telling the computer *how* to do what you want done.</span></span>  
  
 <span data-ttu-id="38d8e-115">Wenn nun diese Formen von Code in ein und derselben Operation miteinander vermischt werden, treten Probleme auf.</span><span class="sxs-lookup"><span data-stu-id="38d8e-115">Mixing these styles of code in the same operation is what leads to problems.</span></span> <span data-ttu-id="38d8e-116">Nehmen wir einmal die folgende Situation:</span><span class="sxs-lookup"><span data-stu-id="38d8e-116">Consider the following:</span></span>  
  
 <span data-ttu-id="38d8e-117">Stellen Sie sich vor, Sie haben eine verknüpfte Liste mit drei Elementen darin (a, b und c):</span><span class="sxs-lookup"><span data-stu-id="38d8e-117">Suppose you have a linked list with three items in it (a, b, and c):</span></span>  
  
 `a -> b -> c`  
  
 <span data-ttu-id="38d8e-118">Stellen Sie sich nun vor, Sie möchten die verknüpfte Liste durchgehen und drei neue Elemente (a', b' und c') hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="38d8e-118">Now, suppose that you want to move through the linked list, adding three new items (a', b', and c').</span></span> <span data-ttu-id="38d8e-119">Die resultierende verknüpfte Liste soll dann wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="38d8e-119">You want the resulting linked list to look like this:</span></span>  
  
 `a -> a' -> b -> b' -> c -> c'`  
  
 <span data-ttu-id="38d8e-120">Sie schreiben also Code, der die Liste durchläuft, und der sofort anschließend für jedes Element ein neues Element hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="38d8e-120">So you write code that iterates through the list, and for every item, adds a new item right after it.</span></span> <span data-ttu-id="38d8e-121">Nun geschieht Folgendes: Ihr Code sieht zuerst das `a`-Element und fügt dahinter `a'` ein.</span><span class="sxs-lookup"><span data-stu-id="38d8e-121">What happens is that your code will first see the `a` element, and insert `a'` after it.</span></span> <span data-ttu-id="38d8e-122">Der Code geht dann zum nächsten Knoten in der Liste, dieser Knoten ist aber jetzt `a'`.</span><span class="sxs-lookup"><span data-stu-id="38d8e-122">Now, your code will move to the next node in the list, which is now `a'`!</span></span> <span data-ttu-id="38d8e-123">Das stört den Code nicht, und er fügt der Liste ein neues Element, also `a''`, hinzu.</span><span class="sxs-lookup"><span data-stu-id="38d8e-123">It happily adds a new item to the list, `a''`.</span></span>  
  
 <span data-ttu-id="38d8e-124">Wie würden Sie dieses Problem im richtigen Leben lösen?</span><span class="sxs-lookup"><span data-stu-id="38d8e-124">How would you solve this in the real world?</span></span> <span data-ttu-id="38d8e-125">Nun, Sie könnten eine Kopie der ursprünglichen verknüpften Liste anlegen und eine vollkommen neue Liste erstellen.</span><span class="sxs-lookup"><span data-stu-id="38d8e-125">Well, you might make a copy of the original linked list, and create a completely new list.</span></span> <span data-ttu-id="38d8e-126">Sie könnten aber auch rein imperativen Code schreiben. Dieser würde dann das erste Element finden, das neue Element hinzufügen und dann in der verknüpften Liste zwei Knoten weitergehen und damit das Element übergehen, das Sie gerade hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="38d8e-126">Or if you are writing purely imperative code, you might find the first item, add the new item, and then advance twice in the linked list, advancing over the element that you just added.</span></span>  
  
## <a name="adding-while-iterating"></a><span data-ttu-id="38d8e-127">Hinzufügungen beim Durchlaufen</span><span class="sxs-lookup"><span data-stu-id="38d8e-127">Adding While Iterating</span></span>  
 <span data-ttu-id="38d8e-128">Angenommen, Sie möchten Code schreiben, der für jedes Element in einer Struktur ein Duplikat erstellt.</span><span class="sxs-lookup"><span data-stu-id="38d8e-128">For example, suppose you want to write some code that for every element in a tree, you want to create a duplicate element:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
foreach (XElement e in root.Elements())  
    root.Add(new XElement(e.Name, (string)e));  
```  
  
 <span data-ttu-id="38d8e-129">Dieser Code führt zu einer Endlosschleife.</span><span class="sxs-lookup"><span data-stu-id="38d8e-129">This code goes into an infinite loop.</span></span> <span data-ttu-id="38d8e-130">Die `foreach`-Anweisung durchläuft die `Elements()`-Achse und fügt dabei dem `doc`-Element neue Elemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="38d8e-130">The `foreach` statement iterates through the `Elements()` axis, adding new elements to the `doc` element.</span></span> <span data-ttu-id="38d8e-131">Das Ergebnis ist, dass die Anweisung auch die gerade hinzugefügten Elemente durchläuft</span><span class="sxs-lookup"><span data-stu-id="38d8e-131">It ends up iterating also through the elements it just added.</span></span> <span data-ttu-id="38d8e-132">und bei jedem Durchlaufen der Schleife neue Objekte zuweist. Irgendwann wird der gesamte verfügbare Arbeitsspeicher dafür in Beschlag genommen.</span><span class="sxs-lookup"><span data-stu-id="38d8e-132">And because it allocates new objects with every iteration of the loop, it will eventually consume all available memory.</span></span>  
  
 <span data-ttu-id="38d8e-133">Dieses Problem können Sie beheben, indem Sie die Auflistung mit dem <xref:System.Linq.Enumerable.ToList%2A>-Standardabfrageoperator in den Arbeitsspeicher ziehen. Dies ist im Folgenden dargestellt:</span><span class="sxs-lookup"><span data-stu-id="38d8e-133">You can fix this problem by pulling the collection into memory using the <xref:System.Linq.Enumerable.ToList%2A> standard query operator, as follows:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
foreach (XElement e in root.Elements().ToList())  
    root.Add(new XElement(e.Name, (string)e));  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="38d8e-134">Jetzt funktioniert der Code.</span><span class="sxs-lookup"><span data-stu-id="38d8e-134">Now the code works.</span></span> <span data-ttu-id="38d8e-135">Die resultierende XML-Struktur sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="38d8e-135">The resulting XML tree is the following:</span></span>  
  
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
  
## <a name="deleting-while-iterating"></a><span data-ttu-id="38d8e-136">Löschungen beim Durchlaufen</span><span class="sxs-lookup"><span data-stu-id="38d8e-136">Deleting While Iterating</span></span>  
 <span data-ttu-id="38d8e-137">Wenn Sie alle Knoten auf einer bestimmten Ebene löschen möchten, könnten Sie versucht sein, Code wie den folgenden zu schreiben:</span><span class="sxs-lookup"><span data-stu-id="38d8e-137">If you want to delete all nodes at a certain level, you might be tempted to write code like the following:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
foreach (XElement e in root.Elements())  
    e.Remove();  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="38d8e-138">Ein solcher Code würde aber nicht zum gewünschten Ergebnis führen.</span><span class="sxs-lookup"><span data-stu-id="38d8e-138">However, this does not do what you want.</span></span> <span data-ttu-id="38d8e-139">Nachdem Sie das erste Element, A, entfernt haben, würde es aus der im Stamm enthaltenen XML-Struktur entfernt werden, sodass der Code in der <legacyBold>Elements</legacyBold>-Methode, der die Iteration vornimmt, das nächste Element nicht finden könnte.</span><span class="sxs-lookup"><span data-stu-id="38d8e-139">In this situation, after you have removed the first element, A, it is removed from the XML tree contained in root, and the code in the Elements method that is doing the iterating cannot find the next element.</span></span>  
  
 <span data-ttu-id="38d8e-140">Der oben genannte Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="38d8e-140">The preceding code produces the following output:</span></span>  
  
```xml  
<Root>  
  <B>2</B>  
  <C>3</C>  
</Root>  
```  
  
 <span data-ttu-id="38d8e-141">Auch hier besteht die Lösung darin, <xref:System.Linq.Enumerable.ToList%2A> aufzurufen, um die Auflistung wie folgt zu materialisieren:</span><span class="sxs-lookup"><span data-stu-id="38d8e-141">The solution again is to call <xref:System.Linq.Enumerable.ToList%2A> to materialize the collection, as follows:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
foreach (XElement e in root.Elements().ToList())  
    e.Remove();  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="38d8e-142">Dies erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="38d8e-142">This produces the following output:</span></span>  
  
```xml  
<Root />  
```  
  
 <span data-ttu-id="38d8e-143">Alternativ dazu können Sie die Iteration ganz eliminieren, indem Sie für das übergeordnete Element <xref:System.Xml.Linq.XElement.RemoveAll%2A> aufrufen:</span><span class="sxs-lookup"><span data-stu-id="38d8e-143">Alternatively, you can eliminate the iteration altogether by calling <xref:System.Xml.Linq.XElement.RemoveAll%2A> on the parent element:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
root.RemoveAll();  
Console.WriteLine(root);  
```  
  
## <a name="why-cant-linq-automatically-handle-this"></a><span data-ttu-id="38d8e-144">Warum kann LINQ dieses Problem nicht automatisch lösen?</span><span class="sxs-lookup"><span data-stu-id="38d8e-144">Why Can't LINQ Automatically Handle This?</span></span>  
 <span data-ttu-id="38d8e-145">Eine Herangehensweise bestünde darin, immer alles in den Arbeitsspeicher zu holen, statt mit verzögerter Auswertung zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="38d8e-145">One approach would be to always bring everything into memory instead of doing lazy evaluation.</span></span> <span data-ttu-id="38d8e-146">Dies würde aber massive Leistungseinbußen und einen hohen Arbeitsspeicherbedarf mit sich bringen.</span><span class="sxs-lookup"><span data-stu-id="38d8e-146">However, it would be very expensive in terms of performance and memory use.</span></span> <span data-ttu-id="38d8e-147">Im praktischen Einsatz würden LINQ und LINQ to XML bei dieser Variante scheitern.</span><span class="sxs-lookup"><span data-stu-id="38d8e-147">In fact, if LINQ and (LINQ to XML) were to take this approach, it would fail in real-world situations.</span></span>  
  
 <span data-ttu-id="38d8e-148">Ein anderer möglicher Ansatz bestünde darin, eine gewisse Transaktionssyntax in LINQ einzubauen und den Compiler zu veranlassen, den Code zu analysieren und zu bestimmen, ob irgendeine Auflistung materialisiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="38d8e-148">Another possible approach would be to put in some sort of transaction syntax into LINQ, and have the compiler attempt to analyze the code and determine if any particular collection needed to be materialized.</span></span> <span data-ttu-id="38d8e-149">Der Versuch, allen Code zu bestimmen, der Nebenwirkungen hat, ist aber eine unglaublich komplexe Angelegenheit.</span><span class="sxs-lookup"><span data-stu-id="38d8e-149">However, attempting to determine all code that has side-effects is incredibly complex.</span></span> <span data-ttu-id="38d8e-150">Betrachten Sie folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="38d8e-150">Consider the following code:</span></span>  
  
```csharp  
var z =  
    from e in root.Elements()  
    where TestSomeCondition(e)  
    select DoMyProjection(e);  
```  
  
 <span data-ttu-id="38d8e-151">Solch ein Analysecode müsste die Methoden <legacyBold>TestSomeCondition</legacyBold> und <legacyBold>DoMyProjection</legacyBold> sowie alle von diesen Methoden aufgerufenen Methoden analysieren, um zu bestimmen, ob Code mit Nebenwirkungen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="38d8e-151">Such analysis code would need to analyze the methods TestSomeCondition and DoMyProjection, and all methods that those methods called, to determine if any code had side-effects.</span></span> <span data-ttu-id="38d8e-152">Der Analysecode kann aber nicht nur einfach nach Code mit Nebenwirkungen suchen.</span><span class="sxs-lookup"><span data-stu-id="38d8e-152">But the analysis code could not just look for any code that had side-effects.</span></span> <span data-ttu-id="38d8e-153">Er dürfte nur den Code auswählen, der in dieser Situation Nebenwirkungen auf die untergeordneten Elemente von `root` hat.</span><span class="sxs-lookup"><span data-stu-id="38d8e-153">It would need to select for just the code that had side-effects on the child elements of `root` in this situation.</span></span>  
  
 <span data-ttu-id="38d8e-154">LINQ to XML unternimmt keine Versuche, eine solche Analyse durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="38d8e-154">LINQ to XML does not attempt to do any such analysis.</span></span>  
  
 <span data-ttu-id="38d8e-155">Für die Vermeidung dieser Probleme sind allein Sie zuständig.</span><span class="sxs-lookup"><span data-stu-id="38d8e-155">It is up to you to avoid these problems.</span></span>  
  
## <a name="guidance"></a><span data-ttu-id="38d8e-156">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="38d8e-156">Guidance</span></span>  
 <span data-ttu-id="38d8e-157">Vermischen Sie deklarativen Code nicht mit imperativem Code.</span><span class="sxs-lookup"><span data-stu-id="38d8e-157">First, do not mix declarative and imperative code.</span></span>  
  
 <span data-ttu-id="38d8e-158">Auch wenn Sie die Semantik Ihrer Auflistungen und die Semantik der Methoden, die die XML-Struktur ändern, exakt kennen und "cleveren" Code schreiben, der diese Art von Problemen vermeidet, muss Ihr Code zukünftig von anderen Entwicklern gewartet werden, die sich vielleicht mit dieser Problematik nicht so gut auskennen.</span><span class="sxs-lookup"><span data-stu-id="38d8e-158">Even if you know exactly the semantics of your collections and the semantics of the methods that modify the XML tree, if you write some clever code that avoids these categories of problems, your code will need to be maintained by other developers in the future, and they may not be as clear on the issues.</span></span> <span data-ttu-id="38d8e-159">Wenn Sie deklarativen und imperativen Code mischen, ist der Code anfälliger.</span><span class="sxs-lookup"><span data-stu-id="38d8e-159">If you mix declarative and imperative coding styles, your code will be more brittle.</span></span>  
  
 <span data-ttu-id="38d8e-160">Wenn Sie Code schreiben, der eine Auflistung so materialisiert, dass diese Probleme vermieden werden, versehen Sie ihn mit entsprechenden Kommentaren, um die für die Wartung zuständigen Programmierer über die Problematik zu informieren.</span><span class="sxs-lookup"><span data-stu-id="38d8e-160">If you write code that materializes a collection so that these problems are avoided, note it with comments as appropriate in your code, so that maintenance programmers will understand the issue.</span></span>  
  
 <span data-ttu-id="38d8e-161">Wenn die Arbeitsgeschwindigkeit und andere Überlegungen es zulassen, sollten Sie immer nur deklarativen Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="38d8e-161">Second, if performance and other considerations allow, use only declarative code.</span></span> <span data-ttu-id="38d8e-162">Ändern Sie nicht Ihre vorhandene XML-Struktur.</span><span class="sxs-lookup"><span data-stu-id="38d8e-162">Don't modify your existing XML tree.</span></span> <span data-ttu-id="38d8e-163">Generieren Sie stattdessen eine neue Struktur.</span><span class="sxs-lookup"><span data-stu-id="38d8e-163">Generate a new one.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
XElement newRoot = new XElement("Root",  
    root.Elements(),  
    root.Elements()  
);  
Console.WriteLine(newRoot);  
```  
