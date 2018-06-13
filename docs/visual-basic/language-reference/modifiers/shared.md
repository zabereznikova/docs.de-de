---
title: Shared (Visual Basic)
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
ms.openlocfilehash: b15dd08d69f372317b9140001e8072eeb66d44ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604548"
---
# <a name="shared-visual-basic"></a><span data-ttu-id="17def-102">Shared (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17def-102">Shared (Visual Basic)</span></span>
<span data-ttu-id="17def-103">Gibt an, dass eine oder mehrere deklarierte Programmierelemente einer Klasse oder Struktur an größeren, und nicht mit einer bestimmten Instanz der Klasse oder Struktur zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="17def-103">Specifies that one or more declared programming elements are associated with a class or structure at large, and not with a specific instance of the class or structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17def-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="17def-104">Remarks</span></span>  
  
## <a name="when-to-use-shared"></a><span data-ttu-id="17def-105">Verwendung von Shared</span><span class="sxs-lookup"><span data-stu-id="17def-105">When to Use Shared</span></span>  
 <span data-ttu-id="17def-106">Einen Member einer Klasse oder Struktur Freigabe verfügbar gemacht, jede Instanz statt *nicht freigegebene*, wobei jede Instanz eine eigene Kopie beibehält.</span><span class="sxs-lookup"><span data-stu-id="17def-106">Sharing a member of a class or structure makes it available to every instance, rather than *nonshared*, where each instance keeps its own copy.</span></span> <span data-ttu-id="17def-107">Dies ist beispielsweise hilfreich, der Wert einer Variablen für die gesamte Anwendung gilt.</span><span class="sxs-lookup"><span data-stu-id="17def-107">This is useful, for example, if the value of a variable applies to the entire application.</span></span> <span data-ttu-id="17def-108">Wenn Sie diese Variable zu deklarieren `Shared`, klicken Sie dann alle Instanzen am gleichen Speicherort, und wenn eine Instanz den Wert der Variablen ändert, alle Instanzen auf zugreifen den aktualisierten Wert.</span><span class="sxs-lookup"><span data-stu-id="17def-108">If you declare that variable to be `Shared`, then all instances access the same storage location, and if one instance changes the variable's value, all instances access the updated value.</span></span>  
  
 <span data-ttu-id="17def-109">Freigeben, wird die Zugriffsebene eines Members nicht verändert.</span><span class="sxs-lookup"><span data-stu-id="17def-109">Sharing does not alter the access level of a member.</span></span> <span data-ttu-id="17def-110">Ein Klassenmember kann z. B. freigegeben werden und in "Privat" (kann nur zugegriffen werden innerhalb der Klasse), oder nicht freigegeben und öffentlich.</span><span class="sxs-lookup"><span data-stu-id="17def-110">For example, a class member can be shared and private (accessible only from within the class), or nonshared and public.</span></span> <span data-ttu-id="17def-111">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="17def-111">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="17def-112">Regeln</span><span class="sxs-lookup"><span data-stu-id="17def-112">Rules</span></span>  
  
-   <span data-ttu-id="17def-113">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="17def-113">**Declaration Context.**</span></span> <span data-ttu-id="17def-114">Sie können `Shared` nur auf Modulebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="17def-114">You can use `Shared` only at module level.</span></span> <span data-ttu-id="17def-115">Dies bedeutet, dass der Deklarationskontext für eine `Shared` Element einer Klasse oder Struktur, und eine Quelldatei, Namespace oder Prozedur nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="17def-115">This means the declaration context for a `Shared` element must be a class or structure, and cannot be a source file, namespace, or procedure.</span></span>  
  
-   <span data-ttu-id="17def-116">**Kombinierte Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="17def-116">**Combined Modifiers.**</span></span> <span data-ttu-id="17def-117">Sie können keine angeben `Shared` zusammen mit [überschreibt](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), oder [ Statische](../../../visual-basic/language-reference/modifiers/static.md) in der gleichen Deklaration.</span><span class="sxs-lookup"><span data-stu-id="17def-117">You cannot specify `Shared` together with [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), or [Static](../../../visual-basic/language-reference/modifiers/static.md) in the same declaration.</span></span>  
  
-   <span data-ttu-id="17def-118">**Beim Zugriff auf.**</span><span class="sxs-lookup"><span data-stu-id="17def-118">**Accessing.**</span></span> <span data-ttu-id="17def-119">Sie greifen auf eine freigegebene Element durch die Qualifizierung mit dem Namen Klasse oder Struktur, nicht mit dem Variablennamen einer bestimmten Instanz ihrer Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="17def-119">You access a shared element by qualifying it with its class or structure name, not with the variable name of a specific instance of its class or structure.</span></span> <span data-ttu-id="17def-120">Sie müssen auch keinen zum Erstellen einer Instanz einer Klasse oder Struktur, um ihre freigegebenen Member zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="17def-120">You do not even have to create an instance of a class or structure to access its shared members.</span></span>  
  
     <span data-ttu-id="17def-121">Im folgenden Beispiel wird die freigegebene Prozedur <xref:System.Double.IsNaN%2A> verfügbar gemacht werden, indem Sie die <xref:System.Double> Struktur.</span><span class="sxs-lookup"><span data-stu-id="17def-121">The following example calls the shared procedure <xref:System.Double.IsNaN%2A> exposed by the <xref:System.Double> structure.</span></span>  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
-   <span data-ttu-id="17def-122">**Implizite Freigabe.**</span><span class="sxs-lookup"><span data-stu-id="17def-122">**Implicit Sharing.**</span></span> <span data-ttu-id="17def-123">Können keine der `Shared` -Modifizierer in einer [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md), aber Konstanten sind implizit freigegeben.</span><span class="sxs-lookup"><span data-stu-id="17def-123">You cannot use the `Shared` modifier in a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md), but constants are implicitly shared.</span></span> <span data-ttu-id="17def-124">Auf ähnliche Weise kann nicht Mitglied von einem Modul oder eine Schnittstelle sein deklariert `Shared`, aber sie werden implizit freigegeben.</span><span class="sxs-lookup"><span data-stu-id="17def-124">Similarly, you cannot declare a member of a module or an interface to be `Shared`, but they are implicitly shared.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="17def-125">Verhalten</span><span class="sxs-lookup"><span data-stu-id="17def-125">Behavior</span></span>  
  
-   <span data-ttu-id="17def-126">**Speicher.**</span><span class="sxs-lookup"><span data-stu-id="17def-126">**Storage.**</span></span> <span data-ttu-id="17def-127">Eine freigegebene Variable oder ein Ereignis wird nur einmal auf, unabhängig davon, wie viele Instanzen der Klasse oder Struktur erstellen im Arbeitsspeicher gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="17def-127">A shared variable or event is stored in memory only once, no matter how many or few instances you create of its class or structure.</span></span> <span data-ttu-id="17def-128">Auf ähnliche Weise werden für eine freigegebene Prozedur oder Eigenschaft nur einen Satz von lokalen Variablen enthält.</span><span class="sxs-lookup"><span data-stu-id="17def-128">Similarly, a shared procedure or property holds only one set of local variables.</span></span>  
  
-   <span data-ttu-id="17def-129">**Zugreifen auf über eine Instanzvariable.**</span><span class="sxs-lookup"><span data-stu-id="17def-129">**Accessing through an Instance Variable.**</span></span> <span data-ttu-id="17def-130">Es ist möglich, die Zugriff auf eine freigegebene Element durch die Qualifizierung mit dem Namen einer Variablen, die eine bestimmte Instanz ihrer Klasse oder Struktur enthält.</span><span class="sxs-lookup"><span data-stu-id="17def-130">It is possible to access a shared element by qualifying it with the name of a variable that contains a specific instance of its class or structure.</span></span> <span data-ttu-id="17def-131">Obwohl dies in der Regel funktioniert wie erwartet, wird der Compiler eine Warnung generiert, und führt den Zugriff über den Namen der Klasse oder Struktur anstelle der Variablen.</span><span class="sxs-lookup"><span data-stu-id="17def-131">Although this usually works as expected, the compiler generates a warning message and makes the access through the class or structure name instead of the variable.</span></span>  
  
-   <span data-ttu-id="17def-132">**Zugriff über einen Instanzausdruck.**</span><span class="sxs-lookup"><span data-stu-id="17def-132">**Accessing through an Instance Expression.**</span></span> <span data-ttu-id="17def-133">Wenn Sie ein freigegebene Element durch einen Ausdruck, die eine Instanz der Klasse oder Struktur zurückgegeben wird zuzugreifen, führt der Compiler den Zugriff durch den Namen der Klasse oder Struktur anstelle von Auswertung des Ausdrucks an.</span><span class="sxs-lookup"><span data-stu-id="17def-133">If you access a shared element through an expression that returns an instance of its class or structure, the compiler makes the access through the class or structure name instead of evaluating the expression.</span></span> <span data-ttu-id="17def-134">Dies erzeugt unerwartete Ergebnisse, wenn Sie den Ausdruck zum Ausführen von anderen Aktionen sowie das Zurückgeben der Instanz, für die Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="17def-134">This produces unexpected results if you intended the expression to perform other actions as well as returning the instance.</span></span> <span data-ttu-id="17def-135">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="17def-135">The following example illustrates this.</span></span>  
  
    ```  
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
  
     <span data-ttu-id="17def-136">Im vorherigen Beispiel generiert der Compiler eine Warnung beide Zeitangaben, die der Code greift auf die freigegebene Variable `total` über eine Instanz.</span><span class="sxs-lookup"><span data-stu-id="17def-136">In the preceding example, the compiler generates a warning message both times the code accesses the shared variable `total` through an instance.</span></span> <span data-ttu-id="17def-137">In jedem Fall den Zugriff direkt über die Klasse vereinfacht `shareTotal` und führt nicht dazu, dass eine Instanz verwenden.</span><span class="sxs-lookup"><span data-stu-id="17def-137">In each case it makes the access directly through the class `shareTotal` and does not make use of any instance.</span></span> <span data-ttu-id="17def-138">Im Fall von der beabsichtigten Aufruf der Prozedur `returnClass`, dies bedeutet, dass es selbst generiert keinen Aufruf von `returnClass`, sodass die zusätzliche Aktion zum Anzeigen von "Function returnClass() called" nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="17def-138">In the case of the intended call to the procedure `returnClass`, this means it does not even generate a call to `returnClass`, so the additional action of displaying "Function returnClass() called" is not performed.</span></span>  
  
 <span data-ttu-id="17def-139">Der `Shared`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="17def-139">The `Shared` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="17def-140">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="17def-140">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="17def-141">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="17def-141">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="17def-142">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="17def-142">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="17def-143">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="17def-143">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="17def-144">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="17def-144">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="17def-145">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="17def-145">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="17def-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17def-146">See Also</span></span>  
 [<span data-ttu-id="17def-147">Shadows</span><span class="sxs-lookup"><span data-stu-id="17def-147">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="17def-148">Static</span><span class="sxs-lookup"><span data-stu-id="17def-148">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)  
 [<span data-ttu-id="17def-149">Lebensdauer in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="17def-149">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [<span data-ttu-id="17def-150">Verfahren</span><span class="sxs-lookup"><span data-stu-id="17def-150">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="17def-151">Strukturen</span><span class="sxs-lookup"><span data-stu-id="17def-151">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="17def-152">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="17def-152">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
