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
ms.openlocfilehash: fa97a374d4570e014222bf44844271b3394453da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638128"
---
# <a name="enum-statement-visual-basic"></a><span data-ttu-id="a7ff5-102">Enum-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7ff5-102">Enum Statement (Visual Basic)</span></span>

<span data-ttu-id="a7ff5-103">Deklariert eine Enumeration und definiert die Werte ihrer Member.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-103">Declares an enumeration and defines the values of its members.</span></span>

## <a name="syntax"></a><span data-ttu-id="a7ff5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7ff5-104">Syntax</span></span>

```
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]
Enum enumerationname [ As datatype ]
   memberlist
End Enum
```

## <a name="parts"></a><span data-ttu-id="a7ff5-105">Teile</span><span class="sxs-lookup"><span data-stu-id="a7ff5-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="a7ff5-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-106">Optional.</span></span> <span data-ttu-id="a7ff5-107">Liste der Attribute, die auf diese Enumeration anwenden.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-107">List of attributes that apply to this enumeration.</span></span> <span data-ttu-id="a7ff5-108">Setzen Sie die [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern ("`<`"und"`>`").</span><span class="sxs-lookup"><span data-stu-id="a7ff5-108">You must enclose the [attribute list](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>

  <span data-ttu-id="a7ff5-109">Die <xref:System.FlagsAttribute> -Attribut gibt an, dass der Wert einer Instanz der Enumeration mehrere Enumerationsmember enthalten kann und jedes Element ein Bit-Feld in der Enumerationswert darstellt.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-109">The <xref:System.FlagsAttribute> attribute indicates that the value of an instance of the enumeration can include multiple enumeration members, and that each member represents a bit field in the enumeration value.</span></span>

- `accessmodifier`

  <span data-ttu-id="a7ff5-110">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-110">Optional.</span></span> <span data-ttu-id="a7ff5-111">Gibt an, welcher Code auf diese Enumeration zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-111">Specifies what code can access this enumeration.</span></span> <span data-ttu-id="a7ff5-112">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="a7ff5-112">Can be one of the following:</span></span>

  - [<span data-ttu-id="a7ff5-113">Public</span><span class="sxs-lookup"><span data-stu-id="a7ff5-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)

  - [<span data-ttu-id="a7ff5-114">Protected</span><span class="sxs-lookup"><span data-stu-id="a7ff5-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)

  - [<span data-ttu-id="a7ff5-115">Friend</span><span class="sxs-lookup"><span data-stu-id="a7ff5-115">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)

  - [<span data-ttu-id="a7ff5-116">Private</span><span class="sxs-lookup"><span data-stu-id="a7ff5-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)

  - [<span data-ttu-id="a7ff5-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="a7ff5-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="a7ff5-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="a7ff5-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

- `Shadows`

  <span data-ttu-id="a7ff5-119">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-119">Optional.</span></span> <span data-ttu-id="a7ff5-120">Gibt an, dass diese Enumeration wird ausgeblendet, ein identisch benanntes Programmierelement oder einen Satz überladener Elemente in einer Basisklasse erneut deklariert.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-120">Specifies that this enumeration redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="a7ff5-121">Sie können angeben, [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) nur auf die Enumeration selbst, nicht auf einem ihrer Member.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-121">You can specify [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) only on the enumeration itself, not on any of its members.</span></span>

- `enumerationname`

  <span data-ttu-id="a7ff5-122">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-122">Required.</span></span> <span data-ttu-id="a7ff5-123">Der Name der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-123">Name of the enumeration.</span></span> <span data-ttu-id="a7ff5-124">Weitere Informationen zu gültigen Namen finden Sie unter [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="a7ff5-124">For information on valid names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `datatype`

  <span data-ttu-id="a7ff5-125">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-125">Optional.</span></span> <span data-ttu-id="a7ff5-126">Der Datentyp der Enumeration und allen zugehörigen Membern.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-126">Data type of the enumeration and all its members.</span></span>

- `memberlist`

  <span data-ttu-id="a7ff5-127">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-127">Required.</span></span> <span data-ttu-id="a7ff5-128">Liste der Memberkonstanten, die in dieser Anweisung deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-128">List of member constants being declared in this statement.</span></span> <span data-ttu-id="a7ff5-129">Mehrere Elemente, die auf einzelne Quellcodezeilen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-129">Multiple members appear on individual source code lines.</span></span>

  <span data-ttu-id="a7ff5-130">Jede `member` hat die folgende Syntax und Bestandteile: `[<attribute list>] member name [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="a7ff5-130">Each `member` has the following syntax and parts: `[<attribute list>] member name [ = initializer ]`</span></span>

  |<span data-ttu-id="a7ff5-131">Segment</span><span class="sxs-lookup"><span data-stu-id="a7ff5-131">Part</span></span>|<span data-ttu-id="a7ff5-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7ff5-132">Description</span></span>|
  |---|---|
  |`membername`|<span data-ttu-id="a7ff5-133">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-133">Required.</span></span> <span data-ttu-id="a7ff5-134">Der Name des Elements.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-134">Name of this member.</span></span>|
  |`initializer`|<span data-ttu-id="a7ff5-135">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-135">Optional.</span></span> <span data-ttu-id="a7ff5-136">Ein Ausdruck, der zur Kompilierzeit ausgewertet und auf diesen Member zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-136">Expression that is evaluated at compile time and assigned to this member.</span></span>|

- <span data-ttu-id="a7ff5-137">`End` `Enum`</span><span class="sxs-lookup"><span data-stu-id="a7ff5-137">`End` `Enum`</span></span>

  <span data-ttu-id="a7ff5-138">Beendet den `Enum`-Block.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-138">Terminates the `Enum` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="a7ff5-139">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a7ff5-139">Remarks</span></span>

<span data-ttu-id="a7ff5-140">Wenn Sie einen Satz von unveränderlichen Werten, die logisch miteinander verknüpft sind verfügen, können Sie diese zusammen in einer Enumeration definieren.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-140">If you have a set of unchanging values that are logically related to each other, you can define them together in an enumeration.</span></span> <span data-ttu-id="a7ff5-141">Dadurch aussagekräftige Namen für die Enumeration und ihre Member, die leichter merken als ihre Werte sind.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-141">This provides meaningful names for the enumeration and its members, which are easier to remember than their values.</span></span> <span data-ttu-id="a7ff5-142">Sie können dann ein Member der Enumeration an vielen Stellen in Ihrem Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-142">You can then use the enumeration members in many places in your code.</span></span>

<span data-ttu-id="a7ff5-143">Die Vorteile der Verwendung von Enumerationen umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a7ff5-143">The benefits of using enumerations include the following:</span></span>

- <span data-ttu-id="a7ff5-144">Fehler aufgrund eines Transponieren oder falsch eingegebene Zahlen wird reduziert.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-144">Reduces errors caused by transposing or mistyping numbers.</span></span>

- <span data-ttu-id="a7ff5-145">Erleichtert die Werte in der Zukunft ändern.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-145">Makes it easy to change values in the future.</span></span>

- <span data-ttu-id="a7ff5-146">Macht Code einfacher zu lesen, was bedeutet, dass es weniger wahrscheinlich ist, dass Fehler eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-146">Makes code easier to read, which means it is less likely that errors will be introduced.</span></span>

- <span data-ttu-id="a7ff5-147">Stellt Aufwärtskompatibilität sicher.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-147">Ensures forward compatibility.</span></span> <span data-ttu-id="a7ff5-148">Bei Verwendung von Enumerationen ist der Code weniger wahrscheinlich fehlschlägt, wenn in der Zukunft jemand die Namen der entsprechenden Werte ändert.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-148">If you use enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>

<span data-ttu-id="a7ff5-149">Eine Enumeration verfügt über einen Namen, einen zugrunde liegenden Datentyp und eine Menge von Elementen.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-149">An enumeration has a name, an underlying data type, and a set of members.</span></span> <span data-ttu-id="a7ff5-150">Jedes Element stellt eine Konstante dar.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-150">Each member represents a constant.</span></span>

<span data-ttu-id="a7ff5-151">Eine Enumeration, die auf die Klasse, Struktur, Modul oder Schnittstellenebene außerhalb einer Prozedur, deklariert ist eine *von Memberenumeration*.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-151">An enumeration declared at class, structure, module, or interface level, outside any procedure, is a *member enumeration*.</span></span> <span data-ttu-id="a7ff5-152">Es ist ein Mitglied der Klasse, Struktur, Modul oder Schnittstelle, die es deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-152">It is a member of the class, structure, module, or interface that declares it.</span></span>

<span data-ttu-id="a7ff5-153">Memberenumerationen können von überall innerhalb ihrer Klasse, Struktur, Modul oder Schnittstelle zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-153">Member enumerations can be accessed from anywhere within their class, structure, module, or interface.</span></span> <span data-ttu-id="a7ff5-154">Code außerhalb einer Klasse, einer Struktur oder eines Moduls muss ein der Memberenumeration den Namen durch den Namen dieser Klasse, Struktur oder Modul qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-154">Code outside a class, structure, or module must qualify a member enumeration's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="a7ff5-155">Sie können vermeiden, müssen vollqualifizierte Namen verwenden, durch das Hinzufügen einer [Importe](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) Anweisung, um die Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-155">You can avoid the need to use fully qualified names by adding an [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statement to the source file.</span></span>

<span data-ttu-id="a7ff5-156">Eine Enumeration, die auf Namespace-Ebene, außerhalb jeder Klasse, Struktur, Modul oder Schnittstelle, deklariert ist, ein Mitglied der Namespace, in dem er angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-156">An enumeration declared at namespace level, outside any class, structure, module, or interface, is a member of the namespace in which it appears.</span></span>

<span data-ttu-id="a7ff5-157">Die *Deklarationskontext* für eine Enumeration, eine Quelldatei, Namespace, Klasse, Struktur, Modul oder Schnittstelle sein muss, und keine Prozedur sein.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-157">The *declaration context* for an enumeration must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure.</span></span> <span data-ttu-id="a7ff5-158">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a7ff5-158">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="a7ff5-159">Sie können Attribute auf eine Enumeration als Ganzes, aber nicht auf ihre Member einzeln anwenden.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-159">You can apply attributes to an enumeration as a whole, but not to its members individually.</span></span> <span data-ttu-id="a7ff5-160">Ein Attribut fügt Informationen an den Metadaten der Assembly.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-160">An attribute contributes information to the assembly's metadata.</span></span>

## <a name="data-type"></a><span data-ttu-id="a7ff5-161">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a7ff5-161">Data Type</span></span>

<span data-ttu-id="a7ff5-162">Die `Enum` -Anweisung kann den Datentyp einer Enumeration deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-162">The `Enum` statement can declare the data type of an enumeration.</span></span> <span data-ttu-id="a7ff5-163">Jedes Element hat den Enumerationstyp Daten.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-163">Each member takes the enumeration's data type.</span></span> <span data-ttu-id="a7ff5-164">Sie können angeben, `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, oder `UShort`.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-164">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span></span>

<span data-ttu-id="a7ff5-165">Wenn Sie keinen angeben `datatype` für die Enumeration nimmt jedes Element den Datentyp des seine `initializer`.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-165">If you do not specify `datatype` for the enumeration, each member takes the data type of its `initializer`.</span></span> <span data-ttu-id="a7ff5-166">Wenn Sie beide angeben `datatype` und `initializer`, der Datentyp des `initializer` müssen konvertierbar sein `datatype`.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-166">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="a7ff5-167">Wenn weder `datatype` noch `initializer` vorhanden ist, geben Sie die Daten standardmäßig `Integer`.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-167">If neither `datatype` nor `initializer` is present, the data type defaults to `Integer`.</span></span>

## <a name="initializing-members"></a><span data-ttu-id="a7ff5-168">Initialisieren von Membern</span><span class="sxs-lookup"><span data-stu-id="a7ff5-168">Initializing Members</span></span>

<span data-ttu-id="a7ff5-169">Die `Enum` -Anweisung kann den Inhalt der ausgewählten Elemente in initialisieren `memberlist`.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-169">The `Enum` statement can initialize the contents of selected members in `memberlist`.</span></span> <span data-ttu-id="a7ff5-170">Verwenden Sie `initializer` , geben Sie einen Ausdruck, der das Element zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-170">You use `initializer` to supply an expression to be assigned to the member.</span></span>

<span data-ttu-id="a7ff5-171">Wenn Sie keinen angeben `initializer` für einen Member, Visual Basic initialisiert es entweder auf 0 (null) (ist dies die erste `member` in `memberlist`), oder auf einen Wert, der um eins größer als der, der unmittelbar vorhergehende `member`.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-171">If you do not specify `initializer` for a member, Visual Basic initializes it either to zero (if it is the first `member` in `memberlist`), or to a value greater by one than that of the immediately preceding `member`.</span></span>

<span data-ttu-id="a7ff5-172">Der Ausdruck, der in jeder bereitgestellten `initializer` kann eine beliebige Kombination aus Literalen, andere Konstanten, die bereits definiert sind und Enumerationsmember, der bereits definiert wurden, einschließlich der einen früheren Member dieser Enumeration sein.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-172">The expression supplied in each `initializer` can be any combination of literals, other constants that are already defined, and enumeration members that are already defined, including a previous member of this enumeration.</span></span> <span data-ttu-id="a7ff5-173">Sie können arithmetische und logische Operatoren verwenden, zur Kombination dieser Elemente.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-173">You can use arithmetic and logical operators to combine such elements.</span></span>

<span data-ttu-id="a7ff5-174">Sie können keine Variablen oder Funktionen in `initializer`.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-174">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="a7ff5-175">Sie können jedoch Konvertierungsschlüsselwörter wie z. B. `CByte` und `CShort`.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-175">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="a7ff5-176">Sie können auch `AscW` Aufruf mit einer Konstanten `String` oder `Char` -Argument, das zum Zeitpunkt der Kompilierung ausgewertet werden können.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-176">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>

<span data-ttu-id="a7ff5-177">Enumerationen dürfen keine Gleitkommawerte haben.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-177">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="a7ff5-178">Wenn ein Member ein Gleitkommawerts zugewiesen ist und `Option Strict` auf festgelegt ist, tritt ein Compilerfehler auf.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-178">If a member is assigned a floating-point value and `Option Strict` is set to on, a compiler error occurs.</span></span> <span data-ttu-id="a7ff5-179">Wenn `Option Strict` deaktiviert ist, wird automatisch konvertierte Wert der `Enum` Typ.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-179">If `Option Strict` is off, the value is automatically converted to the `Enum` type.</span></span>

<span data-ttu-id="a7ff5-180">Wenn der Wert eines Members des zulässigen Bereichs für den zugrunde liegenden Daten überschreitet oder Member, der zulässige Höchstwert von den zugrunde liegenden Datentyp initialisiert, meldet der Compiler einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-180">If the value of a member exceeds the allowable range for the underlying data type, or if you initialize any member to the maximum value allowed by the underlying data type, the compiler reports an error.</span></span>

## <a name="modifiers"></a><span data-ttu-id="a7ff5-181">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="a7ff5-181">Modifiers</span></span>

<span data-ttu-id="a7ff5-182">Klasse, Struktur, Modul und Schnittstelle Member standardmäßig öffentlichen Zugriff auf Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-182">Class, structure, module, and interface member enumerations default to public access.</span></span> <span data-ttu-id="a7ff5-183">Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-183">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="a7ff5-184">Namespace Members Enumerationen standardmäßig Friend-Zugriff.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-184">Namespace member enumerations default to friend access.</span></span> <span data-ttu-id="a7ff5-185">Sie können ihre Zugriffsebenen auf öffentliche, aber nicht auf private oder geschützte anpassen.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-185">You can adjust their access levels to public, but not to private or protected.</span></span> <span data-ttu-id="a7ff5-186">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a7ff5-186">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="a7ff5-187">Alle Enumerationsmember verfügen über öffentlichen Zugriff und können keine Zugriffsmodifizierer auf diesen.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-187">All enumeration members have public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="a7ff5-188">Wenn die Enumeration selbst eine restriktivere Zugriffsebene verfügt, hat die Zugriffsebene für die angegebene Enumeration jedoch Vorrang vor.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-188">However, if the enumeration itself has a more restricted access level, the specified enumeration access level takes precedence.</span></span>

<span data-ttu-id="a7ff5-189">Standardmäßig sind alle Enumerationen Typen und deren Felder sind Konstanten.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-189">By default, all enumerations are types and their fields are constants.</span></span> <span data-ttu-id="a7ff5-190">Aus diesem Grund die `Shared`, `Static`, und `ReadOnly` Schlüsselwörter können nicht verwendet werden, wenn Sie eine Enumeration oder der entsprechenden Member deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-190">Therefore the `Shared`, `Static`, and `ReadOnly` keywords cannot be used when declaring an enumeration or its members.</span></span>

## <a name="assigning-multiple-values"></a><span data-ttu-id="a7ff5-191">Zuweisen von mehreren Werten</span><span class="sxs-lookup"><span data-stu-id="a7ff5-191">Assigning Multiple Values</span></span>

<span data-ttu-id="a7ff5-192">Enumerationen stellen in der Regel sich gegenseitig ausschließende Werte dar.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-192">Enumerations typically represent mutually exclusive values.</span></span> <span data-ttu-id="a7ff5-193">Durch Einschließen der <xref:System.FlagsAttribute> -Attribut in der `Enum` Deklaration, Sie können stattdessen weisen mehrere Werte mit einer Instanz der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-193">By including the <xref:System.FlagsAttribute> attribute in the `Enum` declaration, you can instead assign multiple values to an instance of the enumeration.</span></span> <span data-ttu-id="a7ff5-194">Die <xref:System.FlagsAttribute> Attribut gibt an, dass die Enumeration als Bitfeld, d. h. einen Satz von Flags behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-194">The <xref:System.FlagsAttribute> attribute specifies that the enumeration be treated as a bit field, that is, a set of flags.</span></span> <span data-ttu-id="a7ff5-195">Diese heißen *bitweise* Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-195">These are called *bitwise* enumerations.</span></span>

<span data-ttu-id="a7ff5-196">Wenn Sie eine Enumeration deklarieren, indem die <xref:System.FlagsAttribute> -Attribut, es wird empfohlen, dass Sie die Potenzen von 2, das, 1, 2, 4, 8, 16 und So weiter, für die Werte verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-196">When you declare an enumeration by using the <xref:System.FlagsAttribute> attribute, we recommend that you use powers of 2, that is, 1, 2, 4, 8, 16, and so on, for the values.</span></span> <span data-ttu-id="a7ff5-197">Außerdem wird empfohlen, dass "None" der Name eines Members, dessen Wert 0 ist.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-197">We also recommend that "None" be the name of a member whose value is 0.</span></span> <span data-ttu-id="a7ff5-198">Zusätzliche Richtlinien finden Sie unter <xref:System.FlagsAttribute> und <xref:System.Enum>.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-198">For additional guidelines, see <xref:System.FlagsAttribute> and <xref:System.Enum>.</span></span>

## <a name="example"></a><span data-ttu-id="a7ff5-199">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a7ff5-199">Example</span></span>

<span data-ttu-id="a7ff5-200">Im folgenden Beispiel wird veranschaulicht, wie Sie die Anweisung `Enum` verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-200">The following example shows how to use the `Enum` statement.</span></span> <span data-ttu-id="a7ff5-201">Beachten Sie, die das Element als bezeichnet `EggSizeEnum.Medium`, und nicht als `Medium`.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-201">Note that the member is referred to as `EggSizeEnum.Medium`, and not as `Medium`.</span></span>

[!code-vb[VbEnumsTask#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#41)]

## <a name="example"></a><span data-ttu-id="a7ff5-202">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a7ff5-202">Example</span></span>

<span data-ttu-id="a7ff5-203">Die Methode im folgenden Beispiel befindet sich außerhalb der `Egg` Klasse.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-203">The method in the following example is outside the `Egg` class.</span></span> <span data-ttu-id="a7ff5-204">Aus diesem Grund `EggSizeEnum` ist als vollqualifizierte `Egg.EggSizeEnum`.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-204">Therefore, `EggSizeEnum` is fully qualified as `Egg.EggSizeEnum`.</span></span>

[!code-vb[VbEnumsTask#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#42)]

## <a name="example"></a><span data-ttu-id="a7ff5-205">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a7ff5-205">Example</span></span>

<span data-ttu-id="a7ff5-206">Im folgenden Beispiel wird die `Enum` Anweisung, um eine zusammengehörige Gruppe von definieren benannte Konstanten.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-206">The following example uses the `Enum` statement to define a related set of named constant values.</span></span> <span data-ttu-id="a7ff5-207">In diesem Fall sind die Werte, Farben, die Sie auswählen können, um Dateneingabeformulare für eine Datenbank entwerfen.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-207">In this case, the values are colors you might choose to design data entry forms for a database.</span></span>

[!code-vb[VbEnumsTask#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#30)]

## <a name="example"></a><span data-ttu-id="a7ff5-208">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a7ff5-208">Example</span></span>

<span data-ttu-id="a7ff5-209">Das folgende Beispiel zeigt die Werte, die positive und negative Zahlen enthalten.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-209">The following example shows values that include both positive and negative numbers.</span></span>

[!code-vb[VbEnumsTask#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#31)]

## <a name="example"></a><span data-ttu-id="a7ff5-210">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a7ff5-210">Example</span></span>

<span data-ttu-id="a7ff5-211">Im folgenden Beispiel eine `As` -Klausel wird verwendet, an die `datatype` einer Enumeration.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-211">In the following example, an `As` clause is used to specify the `datatype` of an enumeration.</span></span>

[!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]

## <a name="example"></a><span data-ttu-id="a7ff5-212">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a7ff5-212">Example</span></span>

<span data-ttu-id="a7ff5-213">Das folgende Beispiel zeigt, wie eine bitweise Enumeration verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-213">The following example shows how to use a bitwise enumeration.</span></span> <span data-ttu-id="a7ff5-214">Eine Instanz einer Enumeration bitweise können mehrere Werte zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-214">Multiple values can be assigned to an instance of a bitwise enumeration.</span></span> <span data-ttu-id="a7ff5-215">Die `Enum` Deklaration enthält die <xref:System.FlagsAttribute> -Attribut, das gibt an, dass die Enumeration als ein Satz von Flags behandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-215">The `Enum` declaration includes the <xref:System.FlagsAttribute> attribute, which indicates that the enumeration can be treated as a set of flags.</span></span>

[!code-vb[VbEnumsTask#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#61)]

## <a name="example"></a><span data-ttu-id="a7ff5-216">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a7ff5-216">Example</span></span>

<span data-ttu-id="a7ff5-217">Das folgende Beispiel durchläuft eine Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-217">The following example iterates through an enumeration.</span></span> <span data-ttu-id="a7ff5-218">Er verwendet die <xref:System.Enum.GetNames%2A> Methode, um ein Array von Namen aus der Enumeration abzurufen und <xref:System.Enum.GetValues%2A> um ein Array von Memberwerten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-218">It uses the <xref:System.Enum.GetNames%2A> method to retrieve an array of member names from the enumeration, and <xref:System.Enum.GetValues%2A> to retrieve an array of member values.</span></span>

[!code-vb[VbEnumsTask#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#51)]

## <a name="see-also"></a><span data-ttu-id="a7ff5-219">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7ff5-219">See also</span></span>

- <xref:System.Enum>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [<span data-ttu-id="a7ff5-220">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a7ff5-220">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="a7ff5-221">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a7ff5-221">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="a7ff5-222">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="a7ff5-222">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="a7ff5-223">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="a7ff5-223">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="a7ff5-224">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="a7ff5-224">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
