---
title: Shared
ms.date: 07/20/2015
f1_keywords:
- vb.Shared
helpviewer_keywords:
- Shared keyword [Visual Basic]
- members [Visual Basic], shared
- shared members
- nonshared
- shared [elements VB]
- elements [Visual Basic], shared
ms.assetid: 2bf7cf2c-b0dd-485e-8749-b5d674dab4cd
ms.openlocfilehash: bc63de4bda1e8e605e25fbe293686c187dd4d005
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290992"
---
# <a name="shared-visual-basic"></a><span data-ttu-id="1093f-102">Shared (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1093f-102">Shared (Visual Basic)</span></span>

<span data-ttu-id="1093f-103">Gibt an, dass mindestens ein deklariertes Programmier Element einer Klasse oder Struktur sehr groß zugeordnet ist, nicht mit einer bestimmten Instanz der Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="1093f-103">Specifies that one or more declared programming elements are associated with a class or structure at large, and not with a specific instance of the class or structure.</span></span>

## <a name="when-to-use-shared"></a><span data-ttu-id="1093f-104">Verwendungszwecke von Shared</span><span class="sxs-lookup"><span data-stu-id="1093f-104">When to Use Shared</span></span>

<span data-ttu-id="1093f-105">Wenn Sie ein Member einer Klasse oder Struktur freigeben, ist es für jede Instanz verfügbar und nicht für *nicht freigegebene*, wobei jede Instanz eine eigene Kopie beibehält.</span><span class="sxs-lookup"><span data-stu-id="1093f-105">Sharing a member of a class or structure makes it available to every instance, rather than *non-shared*, where each instance keeps its own copy.</span></span> <span data-ttu-id="1093f-106">Dies ist beispielsweise hilfreich, wenn der Wert einer Variablen für die gesamte Anwendung gilt.</span><span class="sxs-lookup"><span data-stu-id="1093f-106">This is useful, for example, if the value of a variable applies to the entire application.</span></span> <span data-ttu-id="1093f-107">Wenn Sie diese Variable als deklarieren `Shared` , greifen alle Instanzen auf denselben Speicherort zu, und wenn eine Instanz den Wert der Variablen ändert, greifen alle Instanzen auf den aktualisierten Wert zu.</span><span class="sxs-lookup"><span data-stu-id="1093f-107">If you declare that variable to be `Shared`, then all instances access the same storage location, and if one instance changes the variable's value, all instances access the updated value.</span></span>

<span data-ttu-id="1093f-108">Durch die Freigabe wird die Zugriffsebene eines Members nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="1093f-108">Sharing does not alter the access level of a member.</span></span> <span data-ttu-id="1093f-109">Beispielsweise kann ein Klassenmember freigegeben und privat (nur innerhalb der Klasse zugänglich) oder nicht freigegeben und öffentlich sein.</span><span class="sxs-lookup"><span data-stu-id="1093f-109">For example, a class member can be shared and private (accessible only from within the class), or non-shared and public.</span></span> <span data-ttu-id="1093f-110">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="1093f-110">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

## <a name="rules"></a><span data-ttu-id="1093f-111">Regeln</span><span class="sxs-lookup"><span data-stu-id="1093f-111">Rules</span></span>

- <span data-ttu-id="1093f-112">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="1093f-112">**Declaration Context.**</span></span> <span data-ttu-id="1093f-113">Sie können `Shared` nur auf Modulebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="1093f-113">You can use `Shared` only at module level.</span></span> <span data-ttu-id="1093f-114">Dies bedeutet, dass der Deklarations Kontext für ein- `Shared` Element eine Klasse oder Struktur sein muss und weder eine Quelldatei, ein Namespace noch eine Prozedur sein darf.</span><span class="sxs-lookup"><span data-stu-id="1093f-114">This means the declaration context for a `Shared` element must be a class or structure, and cannot be a source file, namespace, or procedure.</span></span>

- <span data-ttu-id="1093f-115">**Kombinierte Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="1093f-115">**Combined Modifiers.**</span></span> <span data-ttu-id="1093f-116">Sie können nicht `Shared` zusammen mit [über](../../../visual-basic/language-reference/modifiers/overrides.md)schreibungen, [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)oder [static](../../../visual-basic/language-reference/modifiers/static.md) in derselben Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="1093f-116">You cannot specify `Shared` together with [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), or [Static](../../../visual-basic/language-reference/modifiers/static.md) in the same declaration.</span></span>

- <span data-ttu-id="1093f-117">**Den.**</span><span class="sxs-lookup"><span data-stu-id="1093f-117">**Accessing.**</span></span> <span data-ttu-id="1093f-118">Sie greifen auf ein frei gegebenes Element zu, indem Sie es mit seinem Klassen-oder Struktur Namen qualifizieren, nicht mit dem Variablennamen einer bestimmten Instanz der Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="1093f-118">You access a shared element by qualifying it with its class or structure name, not with the variable name of a specific instance of its class or structure.</span></span> <span data-ttu-id="1093f-119">Sie müssen nicht einmal eine Instanz einer Klasse oder Struktur erstellen, um auf die freigegebenen Member zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="1093f-119">You do not even have to create an instance of a class or structure to access its shared members.</span></span>

     <span data-ttu-id="1093f-120">Im folgenden Beispiel wird die von der-Struktur verfügbar gemachte freigegebene Prozedur aufgerufen <xref:System.Double.IsNaN%2A> <xref:System.Double> .</span><span class="sxs-lookup"><span data-stu-id="1093f-120">The following example calls the shared procedure <xref:System.Double.IsNaN%2A> exposed by the <xref:System.Double> structure.</span></span>

     ```vb
     If Double.IsNaN(result) Then Console.WriteLine("Result is mathematically undefined.")
     ```

- <span data-ttu-id="1093f-121">**Implizite Freigabe.**</span><span class="sxs-lookup"><span data-stu-id="1093f-121">**Implicit Sharing.**</span></span> <span data-ttu-id="1093f-122">Sie können den- `Shared` Modifizierer nicht in einer Konstanten [Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)verwenden, aber Konstanten werden implizit freigegeben.</span><span class="sxs-lookup"><span data-stu-id="1093f-122">You cannot use the `Shared` modifier in a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md), but constants are implicitly shared.</span></span> <span data-ttu-id="1093f-123">Ebenso ist es nicht möglich, einen Member eines Moduls oder einer Schnittstelle so zu deklarieren `Shared` , dass Sie implizit freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1093f-123">Similarly, you cannot declare a member of a module or an interface to be `Shared`, but they are implicitly shared.</span></span>

## <a name="behavior"></a><span data-ttu-id="1093f-124">Verhalten</span><span class="sxs-lookup"><span data-stu-id="1093f-124">Behavior</span></span>

- <span data-ttu-id="1093f-125">**Speicher.**</span><span class="sxs-lookup"><span data-stu-id="1093f-125">**Storage.**</span></span> <span data-ttu-id="1093f-126">Eine freigegebene Variable oder ein frei gegebenes Ereignis wird im Arbeitsspeicher nur einmal gespeichert, unabhängig davon, wie viele oder wenige Instanzen Sie von der Klasse oder Struktur erstellen.</span><span class="sxs-lookup"><span data-stu-id="1093f-126">A shared variable or event is stored in memory only once, no matter how many or few instances you create of its class or structure.</span></span> <span data-ttu-id="1093f-127">Entsprechend enthält eine freigegebene Prozedur oder Eigenschaft nur einen Satz von lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="1093f-127">Similarly, a shared procedure or property holds only one set of local variables.</span></span>

- <span data-ttu-id="1093f-128">**Zugreifen über eine Instanzvariable.**</span><span class="sxs-lookup"><span data-stu-id="1093f-128">**Accessing through an Instance Variable.**</span></span> <span data-ttu-id="1093f-129">Sie können auf ein frei gegebenes Element zugreifen, indem Sie es mit dem Namen einer Variablen qualifizieren, die eine bestimmte Instanz der Klasse oder Struktur enthält.</span><span class="sxs-lookup"><span data-stu-id="1093f-129">It is possible to access a shared element by qualifying it with the name of a variable that contains a specific instance of its class or structure.</span></span> <span data-ttu-id="1093f-130">Obwohl dies in der Regel erwartungsgemäß funktioniert, generiert der Compiler eine Warnmeldung und ermöglicht den Zugriff über den Klassen-oder Struktur Namen anstelle der Variablen.</span><span class="sxs-lookup"><span data-stu-id="1093f-130">Although this usually works as expected, the compiler generates a warning message and makes the access through the class or structure name instead of the variable.</span></span>

- <span data-ttu-id="1093f-131">**Zugreifen über einen Instanzausdruck.**</span><span class="sxs-lookup"><span data-stu-id="1093f-131">**Accessing through an Instance Expression.**</span></span> <span data-ttu-id="1093f-132">Wenn Sie über einen Ausdruck, der eine Instanz der Klasse oder Struktur zurückgibt, auf ein frei gegebenes Element zugreifen, übernimmt der Compiler den Zugriff über den Klassen-oder Struktur Namen, anstatt den Ausdruck auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="1093f-132">If you access a shared element through an expression that returns an instance of its class or structure, the compiler makes the access through the class or structure name instead of evaluating the expression.</span></span> <span data-ttu-id="1093f-133">Dies führt zu unerwarteten Ergebnissen, wenn Sie den Ausdruck zum Ausführen anderer Aktionen und zum Zurückgeben der Instanz vorgesehen haben.</span><span class="sxs-lookup"><span data-stu-id="1093f-133">This produces unexpected results if you intended the expression to perform other actions as well as returning the instance.</span></span> <span data-ttu-id="1093f-134">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1093f-134">The following example illustrates this.</span></span>
  
    ```vb
    Sub Main()
        ' The following line is the preferred way to access Total.
        ShareTotal.Total = 10

        ' The following line generates a compiler warning message and
        ' accesses total through class ShareTotal instead of through
        ' the variable instanceVar. This works as expected and adds
        ' 100 to Total.
        Dim instanceVar As New ShareTotal
        instanceVar.Total += 100

        ' The following line generates a compiler warning message and
        ' accesses total through class ShareTotal instead of calling
        ' ReturnClass(). This adds 1000 to total but does not work as
        ' expected, because the WriteLine in ReturnClass() does not run.
        Console.WriteLine("Value of total is " & CStr(ShareTotal.Total))
        ReturnClass().Total += 1000
    End Sub

    Public Function ReturnClass() As ShareTotal
        Console.WriteLine("Function ReturnClass() called")
        Return New ShareTotal
    End Function

    Public Class ShareTotal
        Public Shared Property Total As Integer
    End Class
    ```

     <span data-ttu-id="1093f-135">Im vorherigen Beispiel generiert der Compiler eine Warnmeldung, wenn der Code über eine-Instanz auf die freigegebene Eigenschaft zugreift `Total` .</span><span class="sxs-lookup"><span data-stu-id="1093f-135">In the preceding example, the compiler generates a warning message both times the code accesses the shared property `Total` through an instance.</span></span> <span data-ttu-id="1093f-136">In jedem Fall wird der Zugriff direkt über die-Klasse gewährt, und es werden keine `ShareTotal` -Instanzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="1093f-136">In each case it makes the access directly through the class `ShareTotal` and does not make use of any instance.</span></span> <span data-ttu-id="1093f-137">Im Fall des beabsichtigten Aufrufs der Prozedur `ReturnClass` bedeutet dies, dass nicht einmal ein Aufruf von generiert wird `ReturnClass` , sodass die zusätzliche Aktion zum Anzeigen von "Function returnClass ()" nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1093f-137">In the case of the intended call to the procedure `ReturnClass`, this means it does not even generate a call to `ReturnClass`, so the additional action of displaying "Function ReturnClass() called" is not performed.</span></span>

<span data-ttu-id="1093f-138">Der `Shared`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="1093f-138">The `Shared` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="1093f-139">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1093f-139">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="1093f-140">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1093f-140">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="1093f-141">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1093f-141">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="1093f-142">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="1093f-142">Operator Statement</span></span>](../operator-statement.md)
- [<span data-ttu-id="1093f-143">Property Statement</span><span class="sxs-lookup"><span data-stu-id="1093f-143">Property Statement</span></span>](../property-statement.md)
- [<span data-ttu-id="1093f-144">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1093f-144">Sub Statement</span></span>](../sub-statement.md)
  
## <a name="see-also"></a><span data-ttu-id="1093f-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1093f-145">See also</span></span>

- [<span data-ttu-id="1093f-146">Shadows</span><span class="sxs-lookup"><span data-stu-id="1093f-146">Shadows</span></span>](shadows.md)
- [<span data-ttu-id="1093f-147">Kum</span><span class="sxs-lookup"><span data-stu-id="1093f-147">Static</span></span>](static.md)
- [<span data-ttu-id="1093f-148">Lebensdauer in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1093f-148">Lifetime in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="1093f-149">Verfahren</span><span class="sxs-lookup"><span data-stu-id="1093f-149">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="1093f-150">Strukturen</span><span class="sxs-lookup"><span data-stu-id="1093f-150">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="1093f-151">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="1093f-151">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
