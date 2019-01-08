---
title: using-Anweisung – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: df116a200795fd20405381fd71e82d1d6fe662bc
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614388"
---
# <a name="using-statement-c-reference"></a><span data-ttu-id="39168-102">using-Anweisung (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="39168-102">using statement (C# Reference)</span></span>

<span data-ttu-id="39168-103">Bietet eine praktische Syntax, die den ordnungsgemäßen Einsatz von <xref:System.IDisposable>-Objekten sicherstellt</span><span class="sxs-lookup"><span data-stu-id="39168-103">Provides a convenient syntax that ensures the correct use of <xref:System.IDisposable> objects.</span></span>

## <a name="example"></a><span data-ttu-id="39168-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39168-104">Example</span></span>

<span data-ttu-id="39168-105">Im folgenden Beispiel wird veranschaulicht, wie Sie die Anweisung `using` verwenden.</span><span class="sxs-lookup"><span data-stu-id="39168-105">The following example shows how to use the `using` statement.</span></span>

[!code-csharp[csrefKeywordsNamespace#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#4)]

## <a name="remarks"></a><span data-ttu-id="39168-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="39168-106">Remarks</span></span>

<span data-ttu-id="39168-107"><xref:System.IO.File> und <xref:System.Drawing.Font> sind Beispiele für verwaltete Typen, die auf nicht verwaltete Ressourcen zugreifen (in diesem Fall Dateihandles und Gerätekontexte).</span><span class="sxs-lookup"><span data-stu-id="39168-107"><xref:System.IO.File> and <xref:System.Drawing.Font> are examples of managed types that access unmanaged resources (in this case file handles and device contexts).</span></span> <span data-ttu-id="39168-108">Es gibt viele andere Arten von nicht verwalteten Ressourcen und Klassenbibliothekstypen, die sie einschließen.</span><span class="sxs-lookup"><span data-stu-id="39168-108">There are many other kinds of unmanaged resources and class library types that encapsulate them.</span></span> <span data-ttu-id="39168-109">Alle Typen dieser Art müssen die <xref:System.IDisposable>-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="39168-109">All such types must implement the <xref:System.IDisposable> interface.</span></span>

<span data-ttu-id="39168-110">Wenn die Lebensdauer eines `IDisposable`-Objekts auf eine einzige Methode beschränkt ist, sollten Sie es in der `using`-Anweisung deklarieren und instanziieren.</span><span class="sxs-lookup"><span data-stu-id="39168-110">When the lifetime of an `IDisposable` object is limited to a single method, you should declare and instantiate it in the `using` statement.</span></span> <span data-ttu-id="39168-111">Die `using`-Anweisung ruft die Methode <xref:System.IDisposable.Dispose%2A> ordnungsgemäß für das Objekt auf. Wenn Sie sie, wie vorher gezeigt, verwenden, führt dies auch dazu, dass das Objekt den gültigen Bereich verlässt, sobald <xref:System.IDisposable.Dispose%2A> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="39168-111">The `using` statement calls the <xref:System.IDisposable.Dispose%2A> method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as <xref:System.IDisposable.Dispose%2A> is called.</span></span> <span data-ttu-id="39168-112">Innerhalb des `using`-Blocks ist das Objekt schreibgeschützt und kann nicht geändert oder neu zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="39168-112">Within the `using` block, the object is read-only and cannot be modified or reassigned.</span></span>

<span data-ttu-id="39168-113">Mit der Anweisung `using` wird sichergestellt, dass <xref:System.IDisposable.Dispose%2A> aufgerufen wird, selbst wenn eine Ausnahme im `using`-Block auftritt.</span><span class="sxs-lookup"><span data-stu-id="39168-113">The `using` statement ensures that <xref:System.IDisposable.Dispose%2A> is called even if an exception occurs within the `using` block.</span></span> <span data-ttu-id="39168-114">Sie können das gleiche Ergebnis erzielen, indem Sie das Objekt in einen `try`-Block einfügen und dann <xref:System.IDisposable.Dispose%2A> in einem `finally`-Block aufrufen. So übersetzt der Compiler die Anweisung `using`.</span><span class="sxs-lookup"><span data-stu-id="39168-114">You can achieve the same result by putting the object inside a `try` block and then calling <xref:System.IDisposable.Dispose%2A> in a `finally` block; in fact, this is how the `using` statement is translated by the compiler.</span></span> <span data-ttu-id="39168-115">Das vorherige Codebeispiel wird zur Kompilierzeit auf den folgenden Code erweitert (beachten Sie die zusätzlichen geschweiften Klammern zum Erstellen des eingeschränkten Gültigkeitsbereichs für das Objekt):</span><span class="sxs-lookup"><span data-stu-id="39168-115">The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):</span></span>

[!code-csharp[csrefKeywordsNamespace#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#5)]

<span data-ttu-id="39168-116">Weitere Informationen über die Anweisung `try`-`finally` finden Sie im Artikel zu [try-finally](try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="39168-116">For more information about the `try`-`finally` statement, see the [try-finally](try-finally.md) topic.</span></span>

<span data-ttu-id="39168-117">Wie im folgenden Beispiel gezeigt, können mehrere Instanzen eines Typs in einer `using`-Anweisung deklariert werden:</span><span class="sxs-lookup"><span data-stu-id="39168-117">Multiple instances of a type can be declared in the `using` statement, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsNamespace#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#6)]

<span data-ttu-id="39168-118">Sie können das Ressourcenobjekt instanziieren und die Variable an die `using`-Anweisung übergeben; dies wird jedoch nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="39168-118">You can instantiate the resource object and then pass the variable to the `using` statement, but this is not a best practice.</span></span> <span data-ttu-id="39168-119">In diesem Fall verbleibt das Objekt im Gültigkeitsbereich, nachdem das Steuerelement den `using`-Block verlassen hat, obwohl es wahrscheinlich keinen Zugriff auf dessen nicht verwaltete Ressourcen hat.</span><span class="sxs-lookup"><span data-stu-id="39168-119">In this case, after control leaves the `using` block, the object remains in scope but probably has no access to its unmanaged resources.</span></span> <span data-ttu-id="39168-120">Das heißt, dass es nicht mehr vollständig initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="39168-120">In other words, it's not fully initialized anymore.</span></span> <span data-ttu-id="39168-121">Wenn Sie versuchen, das Objekt außerhalb des `using`-Blocks zu verwenden, riskieren Sie, dass eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="39168-121">If you try to use the object outside the `using` block, you risk causing an exception to be thrown.</span></span> <span data-ttu-id="39168-122">Aus diesem Grund ist es im Allgemeinen besser, das Objekt in der `using`-Anweisung zu instanziieren und dessen Bereich auf den `using`-Block zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="39168-122">For this reason, it's generally better to instantiate the object in the `using` statement and limit its scope to the `using` block.</span></span>

[!code-csharp[csrefKeywordsNamespace#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#7)]

<span data-ttu-id="39168-123">Weitere Informationen zum Verwerfen von `IDisposable`-Objekten finden Sie unter [Verwenden von Objekten, die IDisposable implementieren](../../../standard/garbage-collection/using-objects.md).</span><span class="sxs-lookup"><span data-stu-id="39168-123">For more information about disposing of `IDisposable` objects, see [Using objects that implement IDisposable](../../../standard/garbage-collection/using-objects.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="39168-124">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="39168-124">C# language specification</span></span>

<span data-ttu-id="39168-125">Weitere Informationen finden Sie unter [Die using-Anweisung](~/_csharplang/spec/statements.md#the-using-statement) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="39168-125">For more information, see [The using statement](~/_csharplang/spec/statements.md#the-using-statement) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="39168-126">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="39168-126">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="39168-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39168-127">See also</span></span>

- [<span data-ttu-id="39168-128">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="39168-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="39168-129">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="39168-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="39168-130">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="39168-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="39168-131">using-Direktive</span><span class="sxs-lookup"><span data-stu-id="39168-131">using Directive</span></span>](using-directive.md)
- [<span data-ttu-id="39168-132">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="39168-132">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="39168-133">Verwenden von Objekten, die IDisposable implementieren</span><span class="sxs-lookup"><span data-stu-id="39168-133">Using objects that implement IDisposable</span></span>](../../../standard/garbage-collection/using-objects.md)
- [<span data-ttu-id="39168-134">IDisposable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="39168-134">IDisposable interface</span></span>](xref:System.IDisposable)