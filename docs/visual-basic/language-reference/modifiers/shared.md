---
title: freigegebene
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
ms.openlocfilehash: 98fa25d2283408dfb80e82fbc620a1b284e5c530
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349120"
---
# <a name="shared-visual-basic"></a><span data-ttu-id="4192c-102">Shared (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4192c-102">Shared (Visual Basic)</span></span>
<span data-ttu-id="4192c-103">Gibt an, dass mindestens ein deklariertes Programmier Element einer Klasse oder Struktur sehr groß zugeordnet ist, nicht mit einer bestimmten Instanz der Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="4192c-103">Specifies that one or more declared programming elements are associated with a class or structure at large, and not with a specific instance of the class or structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4192c-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4192c-104">Remarks</span></span>  
  
## <a name="when-to-use-shared"></a><span data-ttu-id="4192c-105">Verwendungszwecke von Shared</span><span class="sxs-lookup"><span data-stu-id="4192c-105">When to Use Shared</span></span>  
 <span data-ttu-id="4192c-106">Wenn Sie ein Member einer Klasse oder Struktur freigeben, ist es für jede Instanz verfügbar und nicht für die *nicht freigegebene*Instanz, wobei jede Instanz eine eigene Kopie beibehält.</span><span class="sxs-lookup"><span data-stu-id="4192c-106">Sharing a member of a class or structure makes it available to every instance, rather than *nonshared*, where each instance keeps its own copy.</span></span> <span data-ttu-id="4192c-107">Dies ist beispielsweise hilfreich, wenn der Wert einer Variablen für die gesamte Anwendung gilt.</span><span class="sxs-lookup"><span data-stu-id="4192c-107">This is useful, for example, if the value of a variable applies to the entire application.</span></span> <span data-ttu-id="4192c-108">Wenn Sie diese Variable als `Shared`deklarieren, greifen alle Instanzen auf denselben Speicherort zu, und wenn eine Instanz den Wert der Variablen ändert, greifen alle Instanzen auf den aktualisierten Wert zu.</span><span class="sxs-lookup"><span data-stu-id="4192c-108">If you declare that variable to be `Shared`, then all instances access the same storage location, and if one instance changes the variable's value, all instances access the updated value.</span></span>  
  
 <span data-ttu-id="4192c-109">Durch die Freigabe wird die Zugriffsebene eines Members nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="4192c-109">Sharing does not alter the access level of a member.</span></span> <span data-ttu-id="4192c-110">Beispielsweise kann ein Klassenmember freigegeben und privat (nur innerhalb der Klasse zugänglich) oder nicht freigegeben und öffentlich sein.</span><span class="sxs-lookup"><span data-stu-id="4192c-110">For example, a class member can be shared and private (accessible only from within the class), or nonshared and public.</span></span> <span data-ttu-id="4192c-111">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4192c-111">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="4192c-112">Regeln</span><span class="sxs-lookup"><span data-stu-id="4192c-112">Rules</span></span>  
  
- <span data-ttu-id="4192c-113">**Deklarations Kontext.**</span><span class="sxs-lookup"><span data-stu-id="4192c-113">**Declaration Context.**</span></span> <span data-ttu-id="4192c-114">Sie können `Shared` nur auf Modulebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="4192c-114">You can use `Shared` only at module level.</span></span> <span data-ttu-id="4192c-115">Dies bedeutet, dass der Deklarations Kontext für ein `Shared` Element eine Klasse oder Struktur sein muss und weder eine Quelldatei, ein Namespace noch eine Prozedur sein darf.</span><span class="sxs-lookup"><span data-stu-id="4192c-115">This means the declaration context for a `Shared` element must be a class or structure, and cannot be a source file, namespace, or procedure.</span></span>  
  
- <span data-ttu-id="4192c-116">**Kombinierte modifiziererer.**</span><span class="sxs-lookup"><span data-stu-id="4192c-116">**Combined Modifiers.**</span></span> <span data-ttu-id="4192c-117">Sie können `Shared` nicht zusammen mit [über](../../../visual-basic/language-reference/modifiers/overrides.md)schreibungen, [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)oder [static](../../../visual-basic/language-reference/modifiers/static.md) in derselben Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="4192c-117">You cannot specify `Shared` together with [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), or [Static](../../../visual-basic/language-reference/modifiers/static.md) in the same declaration.</span></span>  
  
- <span data-ttu-id="4192c-118">**Den.**</span><span class="sxs-lookup"><span data-stu-id="4192c-118">**Accessing.**</span></span> <span data-ttu-id="4192c-119">Sie greifen auf ein frei gegebenes Element zu, indem Sie es mit seinem Klassen-oder Struktur Namen qualifizieren, nicht mit dem Variablennamen einer bestimmten Instanz der Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="4192c-119">You access a shared element by qualifying it with its class or structure name, not with the variable name of a specific instance of its class or structure.</span></span> <span data-ttu-id="4192c-120">Sie müssen nicht einmal eine Instanz einer Klasse oder Struktur erstellen, um auf die freigegebenen Member zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4192c-120">You do not even have to create an instance of a class or structure to access its shared members.</span></span>  
  
     <span data-ttu-id="4192c-121">Im folgenden Beispiel wird die freigegebene Prozedur aufgerufen <xref:System.Double.IsNaN%2A> die von der <xref:System.Double>-Struktur verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="4192c-121">The following example calls the shared procedure <xref:System.Double.IsNaN%2A> exposed by the <xref:System.Double> structure.</span></span>  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
- <span data-ttu-id="4192c-122">**Implizite Freigabe.**</span><span class="sxs-lookup"><span data-stu-id="4192c-122">**Implicit Sharing.**</span></span> <span data-ttu-id="4192c-123">Sie können den `Shared` Modifizierer nicht in einer Konstanten [Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)verwenden, aber Konstanten werden implizit freigegeben.</span><span class="sxs-lookup"><span data-stu-id="4192c-123">You cannot use the `Shared` modifier in a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md), but constants are implicitly shared.</span></span> <span data-ttu-id="4192c-124">Entsprechend können Sie keinen Member eines Moduls oder einer Schnittstelle deklarieren, um `Shared`zu werden, aber Sie sind implizit freigegeben.</span><span class="sxs-lookup"><span data-stu-id="4192c-124">Similarly, you cannot declare a member of a module or an interface to be `Shared`, but they are implicitly shared.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="4192c-125">Verhalten</span><span class="sxs-lookup"><span data-stu-id="4192c-125">Behavior</span></span>  
  
- <span data-ttu-id="4192c-126">**Speicher.**</span><span class="sxs-lookup"><span data-stu-id="4192c-126">**Storage.**</span></span> <span data-ttu-id="4192c-127">Eine freigegebene Variable oder ein frei gegebenes Ereignis wird im Arbeitsspeicher nur einmal gespeichert, unabhängig davon, wie viele oder wenige Instanzen Sie von der Klasse oder Struktur erstellen.</span><span class="sxs-lookup"><span data-stu-id="4192c-127">A shared variable or event is stored in memory only once, no matter how many or few instances you create of its class or structure.</span></span> <span data-ttu-id="4192c-128">Entsprechend enthält eine freigegebene Prozedur oder Eigenschaft nur einen Satz von lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="4192c-128">Similarly, a shared procedure or property holds only one set of local variables.</span></span>  
  
- <span data-ttu-id="4192c-129">**Zugreifen über eine Instanzvariable.**</span><span class="sxs-lookup"><span data-stu-id="4192c-129">**Accessing through an Instance Variable.**</span></span> <span data-ttu-id="4192c-130">Sie können auf ein frei gegebenes Element zugreifen, indem Sie es mit dem Namen einer Variablen qualifizieren, die eine bestimmte Instanz der Klasse oder Struktur enthält.</span><span class="sxs-lookup"><span data-stu-id="4192c-130">It is possible to access a shared element by qualifying it with the name of a variable that contains a specific instance of its class or structure.</span></span> <span data-ttu-id="4192c-131">Obwohl dies in der Regel erwartungsgemäß funktioniert, generiert der Compiler eine Warnmeldung und ermöglicht den Zugriff über den Klassen-oder Struktur Namen anstelle der Variablen.</span><span class="sxs-lookup"><span data-stu-id="4192c-131">Although this usually works as expected, the compiler generates a warning message and makes the access through the class or structure name instead of the variable.</span></span>  
  
- <span data-ttu-id="4192c-132">**Zugreifen über einen Instanzausdruck.**</span><span class="sxs-lookup"><span data-stu-id="4192c-132">**Accessing through an Instance Expression.**</span></span> <span data-ttu-id="4192c-133">Wenn Sie über einen Ausdruck, der eine Instanz der Klasse oder Struktur zurückgibt, auf ein frei gegebenes Element zugreifen, übernimmt der Compiler den Zugriff über den Klassen-oder Struktur Namen, anstatt den Ausdruck auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="4192c-133">If you access a shared element through an expression that returns an instance of its class or structure, the compiler makes the access through the class or structure name instead of evaluating the expression.</span></span> <span data-ttu-id="4192c-134">Dies führt zu unerwarteten Ergebnissen, wenn Sie den Ausdruck zum Ausführen anderer Aktionen und zum Zurückgeben der Instanz vorgesehen haben.</span><span class="sxs-lookup"><span data-stu-id="4192c-134">This produces unexpected results if you intended the expression to perform other actions as well as returning the instance.</span></span> <span data-ttu-id="4192c-135">Das folgende Beispiel veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="4192c-135">The following example illustrates this.</span></span>  
  
    ```vb
    Sub main()  
        shareTotal.total = 10  
        ' The preceding line is the preferred way to access total.  
        Dim instanceVar As New shareTotal  
        instanceVar.total += 100  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of through  
        ' the variable instanceVar. This works as expected and adds  
        ' 100 to total.  
        returnClass().total += 1000  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of calling  
        ' returnClass(). This adds 1000 to total but does not work as  
        ' expected, because the MsgBox in returnClass() does not run.  
        MsgBox("Value of total is " & CStr(shareTotal.total))  
    End Sub  
    Public Function returnClass() As shareTotal  
        MsgBox("Function returnClass() called")  
        Return New shareTotal  
    End Function  
    Public Class shareTotal  
        Public Shared total As Integer  
    End Class  
    ```  
  
     <span data-ttu-id="4192c-136">Im vorherigen Beispiel generiert der Compiler eine Warnmeldung, wenn der Code auf die freigegebene Variable `total` über eine-Instanz zugreift.</span><span class="sxs-lookup"><span data-stu-id="4192c-136">In the preceding example, the compiler generates a warning message both times the code accesses the shared variable `total` through an instance.</span></span> <span data-ttu-id="4192c-137">In jedem Fall wird der Zugriff direkt über die-Klasse `shareTotal`, und es werden keine-Instanzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4192c-137">In each case it makes the access directly through the class `shareTotal` and does not make use of any instance.</span></span> <span data-ttu-id="4192c-138">Im Fall des beabsichtigten Aufrufs der Prozedur `returnClass`bedeutet dies, dass nicht einmal ein Aufruf an `returnClass`generiert wird, sodass die zusätzliche Aktion zum Anzeigen von "Function returnClass ()" nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4192c-138">In the case of the intended call to the procedure `returnClass`, this means it does not even generate a call to `returnClass`, so the additional action of displaying "Function returnClass() called" is not performed.</span></span>  
  
 <span data-ttu-id="4192c-139">Der `Shared`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="4192c-139">The `Shared` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="4192c-140">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4192c-140">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="4192c-141">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4192c-141">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="4192c-142">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4192c-142">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="4192c-143">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="4192c-143">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="4192c-144">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4192c-144">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="4192c-145">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4192c-145">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="4192c-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4192c-146">See also</span></span>

- [<span data-ttu-id="4192c-147">Shadows</span><span class="sxs-lookup"><span data-stu-id="4192c-147">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="4192c-148">Static</span><span class="sxs-lookup"><span data-stu-id="4192c-148">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)
- [<span data-ttu-id="4192c-149">Lebensdauer in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4192c-149">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="4192c-150">Verfahren</span><span class="sxs-lookup"><span data-stu-id="4192c-150">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="4192c-151">Strukturen</span><span class="sxs-lookup"><span data-stu-id="4192c-151">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="4192c-152">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="4192c-152">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
