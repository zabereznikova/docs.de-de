---
title: Enum-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Enum
helpviewer_keywords:
- enumerated constants [Visual Basic]
- Enum statement [Visual Basic]
- Private keyword [Visual Basic], Enum statements
- Public keyword [Visual Basic], in Enum statement
- variables [Visual Basic], enumeration
- constants [Visual Basic], enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
ms.openlocfilehash: 89de51f2551437d102ccdc5a0f1ff5f23b53e47f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="enum-statement-visual-basic"></a><span data-ttu-id="3550f-102">Enum-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3550f-102">Enum Statement (Visual Basic)</span></span>
<span data-ttu-id="3550f-103">Deklariert eine Enumeration und die Werte der Member definiert.</span><span class="sxs-lookup"><span data-stu-id="3550f-103">Declares an enumeration and defines the values of its members.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3550f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3550f-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]   
Enum enumerationname [ As datatype ]   
   memberlist  
End Enum  
```  
  
## <a name="parts"></a><span data-ttu-id="3550f-105">Teile</span><span class="sxs-lookup"><span data-stu-id="3550f-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="3550f-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3550f-106">Optional.</span></span> <span data-ttu-id="3550f-107">Liste der Attribute, die für diese Enumeration gelten.</span><span class="sxs-lookup"><span data-stu-id="3550f-107">List of attributes that apply to this enumeration.</span></span> <span data-ttu-id="3550f-108">Setzen Sie die [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern ("`<`"und"`>`").</span><span class="sxs-lookup"><span data-stu-id="3550f-108">You must enclose the [attribute list](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
     <span data-ttu-id="3550f-109">Die <xref:System.FlagsAttribute> Attribut gibt an, dass der Wert einer Instanz der Enumeration mehrere Enumerationsmember enthalten kann und dass jedes Element ein Bitfeld in die Enumerationswert darstellt.</span><span class="sxs-lookup"><span data-stu-id="3550f-109">The <xref:System.FlagsAttribute> attribute indicates that the value of an instance of the enumeration can include multiple enumeration members, and that each member represents a bit field in the enumeration value.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="3550f-110">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3550f-110">Optional.</span></span> <span data-ttu-id="3550f-111">Gibt an, welcher Code auf diese Enumeration zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="3550f-111">Specifies what code can access this enumeration.</span></span> <span data-ttu-id="3550f-112">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="3550f-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="3550f-113">Public</span><span class="sxs-lookup"><span data-stu-id="3550f-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="3550f-114">Protected</span><span class="sxs-lookup"><span data-stu-id="3550f-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="3550f-115">Friend</span><span class="sxs-lookup"><span data-stu-id="3550f-115">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="3550f-116">Private</span><span class="sxs-lookup"><span data-stu-id="3550f-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
     <span data-ttu-id="3550f-117">Sie können angeben, `Protected``Friend` den Zugriff von Code in der Enumeration-Klasse, einer abgeleiteten Klasse oder derselben Assembly ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="3550f-117">You can specify `Protected``Friend` to allow access from code within the enumeration's class, a derived class, or the same assembly.</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="3550f-118">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3550f-118">Optional.</span></span> <span data-ttu-id="3550f-119">Gibt an, dass diese Enumeration erneut deklariert und ein identisch benanntes Programmierelement oder einen Satz überladener Elemente in einer Basisklasse ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="3550f-119">Specifies that this enumeration redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="3550f-120">Sie können angeben, [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md) nur auf die Enumeration selbst sein, nicht auf eines ihrer Elemente.</span><span class="sxs-lookup"><span data-stu-id="3550f-120">You can specify [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) only on the enumeration itself, not on any of its members.</span></span>  
  
-   `enumerationname`  
  
     <span data-ttu-id="3550f-121">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3550f-121">Required.</span></span> <span data-ttu-id="3550f-122">Der Name der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="3550f-122">Name of the enumeration.</span></span> <span data-ttu-id="3550f-123">Informationen zu gültigen Namen finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="3550f-123">For information on valid names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `datatype`  
  
     <span data-ttu-id="3550f-124">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3550f-124">Optional.</span></span> <span data-ttu-id="3550f-125">Der Datentyp der Enumeration und allen zugehörigen Membern.</span><span class="sxs-lookup"><span data-stu-id="3550f-125">Data type of the enumeration and all its members.</span></span>  
  
-   `memberlist`  
  
     <span data-ttu-id="3550f-126">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3550f-126">Required.</span></span> <span data-ttu-id="3550f-127">Liste der Memberkonstanten, die in dieser Anweisung deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="3550f-127">List of member constants being declared in this statement.</span></span> <span data-ttu-id="3550f-128">Mehrere Elemente, die auf einzelne Quellcodezeilen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3550f-128">Multiple members appear on individual source code lines.</span></span>  
  
     <span data-ttu-id="3550f-129">Jede `member` hat die folgende Syntax und Bestandteile: `[<attribute list>] member name [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="3550f-129">Each `member` has the following syntax and parts: `[<attribute list>] member name [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="3550f-130">Segment</span><span class="sxs-lookup"><span data-stu-id="3550f-130">Part</span></span>|<span data-ttu-id="3550f-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3550f-131">Description</span></span>|  
    |---|---|  
    |`membername`|<span data-ttu-id="3550f-132">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3550f-132">Required.</span></span> <span data-ttu-id="3550f-133">Der Name dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="3550f-133">Name of this member.</span></span>|  
    |`initializer`|<span data-ttu-id="3550f-134">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3550f-134">Optional.</span></span> <span data-ttu-id="3550f-135">Ausdruck, der zur Kompilierzeit ausgewertet und bei diesem Member zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3550f-135">Expression that is evaluated at compile time and assigned to this member.</span></span>|  
  
-   <span data-ttu-id="3550f-136">`End` `Enum`</span><span class="sxs-lookup"><span data-stu-id="3550f-136">`End` `Enum`</span></span>  
  
     <span data-ttu-id="3550f-137">Beendet den `Enum`-Block.</span><span class="sxs-lookup"><span data-stu-id="3550f-137">Terminates the `Enum` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3550f-138">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3550f-138">Remarks</span></span>  
 <span data-ttu-id="3550f-139">Wenn Sie einen Satz von unveränderlicher Werte, die logisch miteinander verknüpft sind verfügen, können Sie diese zusammen in einer Enumeration definieren.</span><span class="sxs-lookup"><span data-stu-id="3550f-139">If you have a set of unchanging values that are logically related to each other, you can define them together in an enumeration.</span></span> <span data-ttu-id="3550f-140">Dies bietet aussagekräftige Namen für die Enumeration und ihre Member, die leichter zu merken als ihre Werte sind.</span><span class="sxs-lookup"><span data-stu-id="3550f-140">This provides meaningful names for the enumeration and its members, which are easier to remember than their values.</span></span> <span data-ttu-id="3550f-141">Sie können dann Enumerationsmember an vielen Stellen im Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="3550f-141">You can then use the enumeration members in many places in your code.</span></span>  
  
 <span data-ttu-id="3550f-142">Die Vorteile der Verwendung von Enumerationen umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3550f-142">The benefits of using enumerations include the following:</span></span>  
  
-   <span data-ttu-id="3550f-143">Fehler durch Transponieren oder falsch eingegebene Zahlen wird reduziert.</span><span class="sxs-lookup"><span data-stu-id="3550f-143">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="3550f-144">Vereinfacht die Werte in der Zukunft ändern.</span><span class="sxs-lookup"><span data-stu-id="3550f-144">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="3550f-145">Macht Code einfacher zu lesen, was bedeutet, dass es weniger wahrscheinlich ist, dass Fehler eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3550f-145">Makes code easier to read, which means it is less likely that errors will be introduced.</span></span>  
  
-   <span data-ttu-id="3550f-146">Stellt Aufwärtskompatibilität sicher.</span><span class="sxs-lookup"><span data-stu-id="3550f-146">Ensures forward compatibility.</span></span> <span data-ttu-id="3550f-147">Bei Verwendung von Enumerationen ist der Code weniger wahrscheinlich, dass Sie einen Fehler, wenn in der Zukunft jemand die Namen der entsprechenden Werte ändert.</span><span class="sxs-lookup"><span data-stu-id="3550f-147">If you use enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
 <span data-ttu-id="3550f-148">Eine Enumeration verfügt über einen Namen, einen zugrunde liegenden Datentyp und eine Menge von Elementen.</span><span class="sxs-lookup"><span data-stu-id="3550f-148">An enumeration has a name, an underlying data type, and a set of members.</span></span> <span data-ttu-id="3550f-149">Jedes Element stellt eine Konstante dar.</span><span class="sxs-lookup"><span data-stu-id="3550f-149">Each member represents a constant.</span></span>  
  
 <span data-ttu-id="3550f-150">Eine Enumeration, die auf die Klasse, Struktur, Modul oder Schnittstellenebene außerhalb einer Prozedur deklariert ist ein *Memberenumeration*.</span><span class="sxs-lookup"><span data-stu-id="3550f-150">An enumeration declared at class, structure, module, or interface level, outside any procedure, is a *member enumeration*.</span></span> <span data-ttu-id="3550f-151">Es ist ein Mitglied der Klasse, Struktur, Modul oder Schnittstelle, die es deklariert.</span><span class="sxs-lookup"><span data-stu-id="3550f-151">It is a member of the class, structure, module, or interface that declares it.</span></span>  
  
 <span data-ttu-id="3550f-152">Memberenumerationen können von überall innerhalb ihrer Klasse, Struktur, Modul oder Schnittstelle zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="3550f-152">Member enumerations can be accessed from anywhere within their class, structure, module, or interface.</span></span> <span data-ttu-id="3550f-153">Code außerhalb einer Klasse, einer Struktur oder eines Moduls muss ein der Memberenumeration den Namen mit dem Namen der Klasse, der Struktur oder des Moduls qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="3550f-153">Code outside a class, structure, or module must qualify a member enumeration's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="3550f-154">Sie können vermeiden, dass durch Hinzufügen von vollqualifizierte Namen verwenden ein [Importe](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) Anweisung zur Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="3550f-154">You can avoid the need to use fully qualified names by adding an [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statement to the source file.</span></span>  
  
 <span data-ttu-id="3550f-155">Eine Enumeration, die auf Namespaceebene außerhalb einer Klasse, Struktur, Modul oder Schnittstelle deklariert ist, ein Mitglied der Namespace, in dem er angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3550f-155">An enumeration declared at namespace level, outside any class, structure, module, or interface, is a member of the namespace in which it appears.</span></span>  
  
 <span data-ttu-id="3550f-156">Die *Deklarationskontext* für eine Enumeration muss eine Quelldatei, Namespace, Klasse, Struktur, Modul oder Schnittstelle, und nicht mit einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="3550f-156">The *declaration context* for an enumeration must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure.</span></span> <span data-ttu-id="3550f-157">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="3550f-157">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="3550f-158">Sie können Attribute auf eine Enumeration als Ganzes, aber nicht auf ihre Member einzeln anwenden.</span><span class="sxs-lookup"><span data-stu-id="3550f-158">You can apply attributes to an enumeration as a whole, but not to its members individually.</span></span> <span data-ttu-id="3550f-159">Ein Attribut trägt dazu bei Informationen zu den Metadaten der Assembly.</span><span class="sxs-lookup"><span data-stu-id="3550f-159">An attribute contributes information to the assembly's metadata.</span></span>  
  
## <a name="data-type"></a><span data-ttu-id="3550f-160">Datentyp</span><span class="sxs-lookup"><span data-stu-id="3550f-160">Data Type</span></span>  
 <span data-ttu-id="3550f-161">Die `Enum` -Anweisung kann den Datentyp einer Enumeration deklarieren.</span><span class="sxs-lookup"><span data-stu-id="3550f-161">The `Enum` statement can declare the data type of an enumeration.</span></span> <span data-ttu-id="3550f-162">Jedes Element hat den Enumerationsdatentyp.</span><span class="sxs-lookup"><span data-stu-id="3550f-162">Each member takes the enumeration's data type.</span></span> <span data-ttu-id="3550f-163">Sie können angeben, `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, oder `UShort`.</span><span class="sxs-lookup"><span data-stu-id="3550f-163">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span></span>  
  
 <span data-ttu-id="3550f-164">Wenn Sie keinen angeben `datatype` für die Enumeration jedes Element hat den Datentyp des seine `initializer`.</span><span class="sxs-lookup"><span data-stu-id="3550f-164">If you do not specify `datatype` for the enumeration, each member takes the data type of its `initializer`.</span></span> <span data-ttu-id="3550f-165">Wenn Sie beide angeben `datatype` und `initializer`, der Datentyp des `initializer` konvertierbar sein muss `datatype`.</span><span class="sxs-lookup"><span data-stu-id="3550f-165">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="3550f-166">Wenn weder `datatype` noch `initializer` vorhanden ist, der Datentyp der Standardwert ist `Integer`.</span><span class="sxs-lookup"><span data-stu-id="3550f-166">If neither `datatype` nor `initializer` is present, the data type defaults to `Integer`.</span></span>  
  
## <a name="initializing-members"></a><span data-ttu-id="3550f-167">Initialisieren von Membern</span><span class="sxs-lookup"><span data-stu-id="3550f-167">Initializing Members</span></span>  
 <span data-ttu-id="3550f-168">Die `Enum` -Anweisung kann den Inhalt der ausgewählten Elemente in initialisieren `memberlist`.</span><span class="sxs-lookup"><span data-stu-id="3550f-168">The `Enum` statement can initialize the contents of selected members in `memberlist`.</span></span> <span data-ttu-id="3550f-169">Verwenden Sie `initializer` , geben Sie einen Ausdruck, der das Element zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="3550f-169">You use `initializer` to supply an expression to be assigned to the member.</span></span>  
  
 <span data-ttu-id="3550f-170">Wenn Sie keinen angeben `initializer` für einen Member, Visual Basic initialisiert es entweder 0 (null) (wird jedoch die erste `member` in `memberlist`), oder auf einen Wert, der um eins größer als die des unmittelbar vorangehenden `member`.</span><span class="sxs-lookup"><span data-stu-id="3550f-170">If you do not specify `initializer` for a member, Visual Basic initializes it either to zero (if it is the first `member` in `memberlist`), or to a value greater by one than that of the immediately preceding `member`.</span></span>  
  
 <span data-ttu-id="3550f-171">Der Ausdruck, der in jedem angegebenen `initializer` kann eine beliebige Kombination von Literalen, anderen, bereits definierte, Konstanten und Enumerationsmembern, die bereits definiert sind, einschließlich eines vorherigen Members dieser Enumeration.</span><span class="sxs-lookup"><span data-stu-id="3550f-171">The expression supplied in each `initializer` can be any combination of literals, other constants that are already defined, and enumeration members that are already defined, including a previous member of this enumeration.</span></span> <span data-ttu-id="3550f-172">Sie können arithmetische und logische Operatoren verwenden, solche Elemente kombinieren.</span><span class="sxs-lookup"><span data-stu-id="3550f-172">You can use arithmetic and logical operators to combine such elements.</span></span>  
  
 <span data-ttu-id="3550f-173">Sie können keine Variablen oder Funktionen in `initializer`.</span><span class="sxs-lookup"><span data-stu-id="3550f-173">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="3550f-174">Sie können jedoch Konvertierungsschlüsselwörter wie z. B. `CByte` und `CShort`.</span><span class="sxs-lookup"><span data-stu-id="3550f-174">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="3550f-175">Sie können auch `AscW` Aufruf mit einer Konstanten `String` oder `Char` Argument, da, die zur Kompilierzeit ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3550f-175">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>  
  
 <span data-ttu-id="3550f-176">Enumerationen können keine Gleitkommawerte haben.</span><span class="sxs-lookup"><span data-stu-id="3550f-176">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="3550f-177">Wenn ein Element ein Gleitkommawerts zugewiesen ist und `Option Strict` für auf festgelegt ist, tritt ein Compilerfehler auf.</span><span class="sxs-lookup"><span data-stu-id="3550f-177">If a member is assigned a floating-point value and `Option Strict` is set to on, a compiler error occurs.</span></span> <span data-ttu-id="3550f-178">Wenn `Option Strict` deaktiviert ist, wird automatisch konvertierte Wert der `Enum` Typ.</span><span class="sxs-lookup"><span data-stu-id="3550f-178">If `Option Strict` is off, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="3550f-179">Wenn der Wert eines Members des zulässigen Bereichs für den zugrunde liegenden Datentyp überschreitet, oder wenn Sie Member mit dem vom zugrunde liegenden Datentyp zulässigen Höchstwert initialisieren, meldet der Compiler einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="3550f-179">If the value of a member exceeds the allowable range for the underlying data type, or if you initialize any member to the maximum value allowed by the underlying data type, the compiler reports an error.</span></span>  
  
## <a name="modifiers"></a><span data-ttu-id="3550f-180">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="3550f-180">Modifiers</span></span>  
 <span data-ttu-id="3550f-181">Klasse, Struktur, Modul und Schnittstellenmember Enumerationen standardmäßig öffentlichen Zugriff auf.</span><span class="sxs-lookup"><span data-stu-id="3550f-181">Class, structure, module, and interface member enumerations default to public access.</span></span> <span data-ttu-id="3550f-182">Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.</span><span class="sxs-lookup"><span data-stu-id="3550f-182">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="3550f-183">Namespace Member Enumerationen standardmäßig Friend-Zugriff.</span><span class="sxs-lookup"><span data-stu-id="3550f-183">Namespace member enumerations default to friend access.</span></span> <span data-ttu-id="3550f-184">Sie können ihre Zugriffsebenen öffentlich, jedoch nicht auf private oder geschützte anpassen.</span><span class="sxs-lookup"><span data-stu-id="3550f-184">You can adjust their access levels to public, but not to private or protected.</span></span> <span data-ttu-id="3550f-185">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="3550f-185">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="3550f-186">Alle Enumerationsmember verfügen über öffentlichen Zugriff und können keine Zugriffsmodifizierer auf diesen.</span><span class="sxs-lookup"><span data-stu-id="3550f-186">All enumeration members have public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="3550f-187">Wenn die Enumeration selbst eine restriktivere Zugriffsebene verfügt, hat die Zugriffsebene für die angegebene Enumeration jedoch Vorrang vor.</span><span class="sxs-lookup"><span data-stu-id="3550f-187">However, if the enumeration itself has a more restricted access level, the specified enumeration access level takes precedence.</span></span>  
  
 <span data-ttu-id="3550f-188">Standardmäßig sind alle Enumerationen Typen und ihre Felder sind Konstanten.</span><span class="sxs-lookup"><span data-stu-id="3550f-188">By default, all enumerations are types and their fields are constants.</span></span> <span data-ttu-id="3550f-189">Aus diesem Grund die `Shared`, `Static`, und `ReadOnly` Schlüsselwörter nicht verwendet werden, wenn Sie eine Enumeration oder der entsprechenden Member deklarieren.</span><span class="sxs-lookup"><span data-stu-id="3550f-189">Therefore the `Shared`, `Static`, and `ReadOnly` keywords cannot be used when declaring an enumeration or its members.</span></span>  
  
## <a name="assigning-multiple-values"></a><span data-ttu-id="3550f-190">Zuweisen von mehreren Werten</span><span class="sxs-lookup"><span data-stu-id="3550f-190">Assigning Multiple Values</span></span>  
 <span data-ttu-id="3550f-191">Enumerationen werden in der Regel sich gegenseitig ausschließende Werte darstellen.</span><span class="sxs-lookup"><span data-stu-id="3550f-191">Enumerations typically represent mutually exclusive values.</span></span> <span data-ttu-id="3550f-192">Durch Einschließen der <xref:System.FlagsAttribute> Attribut in der `Enum` Deklaration enthalten sein, Sie können stattdessen weisen mehrere Werte mit einer Instanz der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="3550f-192">By including the <xref:System.FlagsAttribute> attribute in the `Enum` declaration, you can instead assign multiple values to an instance of the enumeration.</span></span> <span data-ttu-id="3550f-193">Die <xref:System.FlagsAttribute> Attribut gibt an, dass die Enumeration als Bitfeld, d. h. als Gruppe von Flags behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="3550f-193">The <xref:System.FlagsAttribute> attribute specifies that the enumeration be treated as a bit field, that is, a set of flags.</span></span> <span data-ttu-id="3550f-194">Diese heißen *bitweise* Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="3550f-194">These are called *bitwise* enumerations.</span></span>  
  
 <span data-ttu-id="3550f-195">Wenn Sie eine Enumeration deklarieren, indem die <xref:System.FlagsAttribute> -Attribut, wir empfehlen die Verwendung Potenzen von 2, die ist, 1, 2, 4, 8, 16 usw., für die Werte.</span><span class="sxs-lookup"><span data-stu-id="3550f-195">When you declare an enumeration by using the <xref:System.FlagsAttribute> attribute, we recommend that you use powers of 2, that is, 1, 2, 4, 8, 16, and so on, for the values.</span></span> <span data-ttu-id="3550f-196">Wir empfehlen außerdem, dass "None" der Name eines Elements, dessen Wert 0 ist.</span><span class="sxs-lookup"><span data-stu-id="3550f-196">We also recommend that "None" be the name of a member whose value is 0.</span></span> <span data-ttu-id="3550f-197">Zusätzliche Richtlinien finden Sie unter <xref:System.FlagsAttribute> und <xref:System.Enum>.</span><span class="sxs-lookup"><span data-stu-id="3550f-197">For additional guidelines, see <xref:System.FlagsAttribute> and <xref:System.Enum>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3550f-198">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3550f-198">Example</span></span>  
 <span data-ttu-id="3550f-199">Das folgende Beispiel zeigt, wie Sie die `Enum` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="3550f-199">The following example shows how to use the `Enum` statement.</span></span> <span data-ttu-id="3550f-200">Beachten Sie, die das Element so genannte `EggSizeEnum.Medium`, und nicht als `Medium`.</span><span class="sxs-lookup"><span data-stu-id="3550f-200">Note that the member is referred to as `EggSizeEnum.Medium`, and not as `Medium`.</span></span>  
  
 [!code-vb[VbEnumsTask#41](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="3550f-201">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3550f-201">Example</span></span>  
 <span data-ttu-id="3550f-202">Die Methode im folgenden Beispiel wird außerhalb der `Egg` Klasse.</span><span class="sxs-lookup"><span data-stu-id="3550f-202">The method in the following example is outside the `Egg` class.</span></span> <span data-ttu-id="3550f-203">Aus diesem Grund `EggSizeEnum` ist vollqualifizierte als `Egg.EggSizeEnum`.</span><span class="sxs-lookup"><span data-stu-id="3550f-203">Therefore, `EggSizeEnum` is fully qualified as `Egg.EggSizeEnum`.</span></span>  
  
 [!code-vb[VbEnumsTask#42](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="3550f-204">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3550f-204">Example</span></span>  
 <span data-ttu-id="3550f-205">Im folgenden Beispiel wird die `Enum` Anweisung zum Definieren eines Gruppe verwandten benannte Konstanten.</span><span class="sxs-lookup"><span data-stu-id="3550f-205">The following example uses the `Enum` statement to define a related set of named constant values.</span></span> <span data-ttu-id="3550f-206">In diesem Fall sind die Werte, Farben, die Sie auswählen können, um Dateneingabeformulare für eine Datenbank entwerfen.</span><span class="sxs-lookup"><span data-stu-id="3550f-206">In this case, the values are colors you might choose to design data entry forms for a database.</span></span>  
  
 [!code-vb[VbEnumsTask#30](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="3550f-207">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3550f-207">Example</span></span>  
 <span data-ttu-id="3550f-208">Das folgende Beispiel zeigt die Werte, die positive und negative Zahlen enthalten.</span><span class="sxs-lookup"><span data-stu-id="3550f-208">The following example shows values that include both positive and negative numbers.</span></span>  
  
 [!code-vb[VbEnumsTask#31](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="3550f-209">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3550f-209">Example</span></span>  
 <span data-ttu-id="3550f-210">Im folgenden Beispiel ein `As` -Klausel zur Angabe der `datatype` einer Enumeration.</span><span class="sxs-lookup"><span data-stu-id="3550f-210">In the following example, an `As` clause is used to specify the `datatype` of an enumeration.</span></span>  
  
 [!code-vb[VbEnumsTask#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_5.vb)]  
  
## <a name="example"></a><span data-ttu-id="3550f-211">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3550f-211">Example</span></span>  
 <span data-ttu-id="3550f-212">Im folgende Beispiel wird gezeigt, wie eine bitweise Enumeration verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3550f-212">The following example shows how to use a bitwise enumeration.</span></span> <span data-ttu-id="3550f-213">Eine Instanz eine bitweise Enumeration können mehrere Werte zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="3550f-213">Multiple values can be assigned to an instance of a bitwise enumeration.</span></span> <span data-ttu-id="3550f-214">Die `Enum` Deklaration enthält die <xref:System.FlagsAttribute> -Attribut, das zeigt an, dass die Enumeration als eine Gruppe von Flags, behandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="3550f-214">The `Enum` declaration includes the <xref:System.FlagsAttribute> attribute, which indicates that the enumeration can be treated as a set of flags.</span></span>  
  
 [!code-vb[VbEnumsTask#61](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_6.vb)]  
  
## <a name="example"></a><span data-ttu-id="3550f-215">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3550f-215">Example</span></span>  
 <span data-ttu-id="3550f-216">Das folgende Beispiel durchläuft eine Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="3550f-216">The following example iterates through an enumeration.</span></span> <span data-ttu-id="3550f-217">Er verwendet die <xref:System.Enum.GetNames%2A> Methode, um ein Array von Elementnamen aus der Enumeration abzurufen und <xref:System.Enum.GetValues%2A> zum Abrufen eines Arrays von Elementwerten.</span><span class="sxs-lookup"><span data-stu-id="3550f-217">It uses the <xref:System.Enum.GetNames%2A> method to retrieve an array of member names from the enumeration, and <xref:System.Enum.GetValues%2A> to retrieve an array of member values.</span></span>  
  
 [!code-vb[VbEnumsTask#51](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_7.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3550f-218">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3550f-218">See Also</span></span>  
 <xref:System.Enum>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 [<span data-ttu-id="3550f-219">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3550f-219">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="3550f-220">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3550f-220">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="3550f-221">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="3550f-221">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="3550f-222">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="3550f-222">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="3550f-223">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="3550f-223">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
