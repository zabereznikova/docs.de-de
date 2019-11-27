---
title: Enum-Anweisung
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
ms.openlocfilehash: 48220fd1e88cf38e67db5dd3a2ad90638eb6b6df
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343718"
---
# <a name="enum-statement-visual-basic"></a><span data-ttu-id="9fb32-102">Enum-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9fb32-102">Enum Statement (Visual Basic)</span></span>

<span data-ttu-id="9fb32-103">Deklariert eine Enumeration und definiert die Werte ihrer Member.</span><span class="sxs-lookup"><span data-stu-id="9fb32-103">Declares an enumeration and defines the values of its members.</span></span>

## <a name="syntax"></a><span data-ttu-id="9fb32-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9fb32-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]
Enum enumerationname [ As datatype ]
   memberlist
End Enum
```

## <a name="parts"></a><span data-ttu-id="9fb32-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="9fb32-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="9fb32-106">Optional.</span><span class="sxs-lookup"><span data-stu-id="9fb32-106">Optional.</span></span> <span data-ttu-id="9fb32-107">Liste der Attribute, die auf diese Enumeration angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="9fb32-107">List of attributes that apply to this enumeration.</span></span> <span data-ttu-id="9fb32-108">Sie müssen die [Attribut Liste](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern ("`<`" und "`>`") einschließen.</span><span class="sxs-lookup"><span data-stu-id="9fb32-108">You must enclose the [attribute list](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>

  <span data-ttu-id="9fb32-109">Das <xref:System.FlagsAttribute>-Attribut gibt an, dass der Wert einer Instanz der-Enumeration mehrere Enumerationsmember enthalten kann und dass jeder Member ein Bitfeld im Enumerationswert darstellt.</span><span class="sxs-lookup"><span data-stu-id="9fb32-109">The <xref:System.FlagsAttribute> attribute indicates that the value of an instance of the enumeration can include multiple enumeration members, and that each member represents a bit field in the enumeration value.</span></span>

- `accessmodifier`

  <span data-ttu-id="9fb32-110">Optional.</span><span class="sxs-lookup"><span data-stu-id="9fb32-110">Optional.</span></span> <span data-ttu-id="9fb32-111">Gibt an, welcher Code auf diese Enumeration zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="9fb32-111">Specifies what code can access this enumeration.</span></span> <span data-ttu-id="9fb32-112">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="9fb32-112">Can be one of the following:</span></span>

  - [<span data-ttu-id="9fb32-113">Public</span><span class="sxs-lookup"><span data-stu-id="9fb32-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)

  - [<span data-ttu-id="9fb32-114">Protected</span><span class="sxs-lookup"><span data-stu-id="9fb32-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)

  - [<span data-ttu-id="9fb32-115">Friend</span><span class="sxs-lookup"><span data-stu-id="9fb32-115">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)

  - [<span data-ttu-id="9fb32-116">Private</span><span class="sxs-lookup"><span data-stu-id="9fb32-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)

  - [<span data-ttu-id="9fb32-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="9fb32-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="9fb32-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="9fb32-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

- `Shadows`

  <span data-ttu-id="9fb32-119">Optional.</span><span class="sxs-lookup"><span data-stu-id="9fb32-119">Optional.</span></span> <span data-ttu-id="9fb32-120">Gibt an, dass diese Enumeration ein identisch benanntes Programmier Element oder einen Satz überladener Elemente in einer Basisklasse erneut deklariert und verbirgt.</span><span class="sxs-lookup"><span data-stu-id="9fb32-120">Specifies that this enumeration redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="9fb32-121">Sie können Shadowing [nur für](../../../visual-basic/language-reference/modifiers/shadows.md) die Enumeration selbst angeben, nicht für Member.</span><span class="sxs-lookup"><span data-stu-id="9fb32-121">You can specify [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) only on the enumeration itself, not on any of its members.</span></span>

- `enumerationname`

  <span data-ttu-id="9fb32-122">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="9fb32-122">Required.</span></span> <span data-ttu-id="9fb32-123">Der Name der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="9fb32-123">Name of the enumeration.</span></span> <span data-ttu-id="9fb32-124">Informationen zu gültigen Namen finden Sie unter [deklarierte Element Namen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="9fb32-124">For information on valid names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `datatype`

  <span data-ttu-id="9fb32-125">Optional.</span><span class="sxs-lookup"><span data-stu-id="9fb32-125">Optional.</span></span> <span data-ttu-id="9fb32-126">Datentyp der Enumeration und aller zugehörigen Member.</span><span class="sxs-lookup"><span data-stu-id="9fb32-126">Data type of the enumeration and all its members.</span></span>

- `memberlist`

  <span data-ttu-id="9fb32-127">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="9fb32-127">Required.</span></span> <span data-ttu-id="9fb32-128">Liste der Element Konstanten, die in dieser Anweisung deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="9fb32-128">List of member constants being declared in this statement.</span></span> <span data-ttu-id="9fb32-129">Mehrere Elemente werden in einzelnen Quell Codezeilen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9fb32-129">Multiple members appear on individual source code lines.</span></span>

  <span data-ttu-id="9fb32-130">Jede `member` weist die folgende Syntax und Teile auf: `[<attribute list>] member name [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="9fb32-130">Each `member` has the following syntax and parts: `[<attribute list>] member name [ = initializer ]`</span></span>

  |<span data-ttu-id="9fb32-131">-Komponente</span><span class="sxs-lookup"><span data-stu-id="9fb32-131">Part</span></span>|<span data-ttu-id="9fb32-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9fb32-132">Description</span></span>|
  |---|---|
  |`membername`|<span data-ttu-id="9fb32-133">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="9fb32-133">Required.</span></span> <span data-ttu-id="9fb32-134">Der Name dieses Members.</span><span class="sxs-lookup"><span data-stu-id="9fb32-134">Name of this member.</span></span>|
  |`initializer`|<span data-ttu-id="9fb32-135">Optional.</span><span class="sxs-lookup"><span data-stu-id="9fb32-135">Optional.</span></span> <span data-ttu-id="9fb32-136">Ausdruck, der zum Zeitpunkt der Kompilierung ausgewertet und diesem Member zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9fb32-136">Expression that is evaluated at compile time and assigned to this member.</span></span>|

- <span data-ttu-id="9fb32-137">`End` `Enum`</span><span class="sxs-lookup"><span data-stu-id="9fb32-137">`End` `Enum`</span></span>

  <span data-ttu-id="9fb32-138">Beendet den `Enum`-Block.</span><span class="sxs-lookup"><span data-stu-id="9fb32-138">Terminates the `Enum` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="9fb32-139">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9fb32-139">Remarks</span></span>

<span data-ttu-id="9fb32-140">Wenn Sie über eine Reihe von unveränderlichen Werten verfügen, die logisch miteinander verknüpft sind, können Sie diese in einer Enumeration definieren.</span><span class="sxs-lookup"><span data-stu-id="9fb32-140">If you have a set of unchanging values that are logically related to each other, you can define them together in an enumeration.</span></span> <span data-ttu-id="9fb32-141">Dies stellt aussagekräftige Namen für die Enumeration und ihre Member bereit, die leichter zu merken sind als ihre Werte.</span><span class="sxs-lookup"><span data-stu-id="9fb32-141">This provides meaningful names for the enumeration and its members, which are easier to remember than their values.</span></span> <span data-ttu-id="9fb32-142">Sie können dann die Enumerationsmember an vielen Stellen in Ihrem Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="9fb32-142">You can then use the enumeration members in many places in your code.</span></span>

<span data-ttu-id="9fb32-143">Zu den Vorteilen der Verwendung von Enumerationen zählen die folgenden:</span><span class="sxs-lookup"><span data-stu-id="9fb32-143">The benefits of using enumerations include the following:</span></span>

- <span data-ttu-id="9fb32-144">Reduziert Fehler, die durch das übertragen oder falsch formatiping von Zahlen verursacht werden</span><span class="sxs-lookup"><span data-stu-id="9fb32-144">Reduces errors caused by transposing or mistyping numbers.</span></span>

- <span data-ttu-id="9fb32-145">Erleichtert das Ändern von Werten in der Zukunft.</span><span class="sxs-lookup"><span data-stu-id="9fb32-145">Makes it easy to change values in the future.</span></span>

- <span data-ttu-id="9fb32-146">Erleichtert das Lesen von Code, was bedeutet, dass es weniger wahrscheinlich ist, dass Fehler eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9fb32-146">Makes code easier to read, which means it is less likely that errors will be introduced.</span></span>

- <span data-ttu-id="9fb32-147">Gewährleistet die Vorwärtskompatibilität.</span><span class="sxs-lookup"><span data-stu-id="9fb32-147">Ensures forward compatibility.</span></span> <span data-ttu-id="9fb32-148">Wenn Sie Enumerationen verwenden, ist es wahrscheinlich, dass Ihr Code fehlschlägt, wenn Sie in der Zukunft die Werte ändern, die den Elementnamen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9fb32-148">If you use enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>

<span data-ttu-id="9fb32-149">Eine Enumeration verfügt über einen Namen, einen zugrunde liegenden Datentyp und einen Satz von Membern.</span><span class="sxs-lookup"><span data-stu-id="9fb32-149">An enumeration has a name, an underlying data type, and a set of members.</span></span> <span data-ttu-id="9fb32-150">Jeder Member stellt eine Konstante dar.</span><span class="sxs-lookup"><span data-stu-id="9fb32-150">Each member represents a constant.</span></span>

<span data-ttu-id="9fb32-151">Eine Enumeration, die auf Klassen-, Struktur-, Modul-oder Schnittstellen Ebene, außerhalb einer Prozedur deklariert wurde, ist eine *Member-Enumeration*.</span><span class="sxs-lookup"><span data-stu-id="9fb32-151">An enumeration declared at class, structure, module, or interface level, outside any procedure, is a *member enumeration*.</span></span> <span data-ttu-id="9fb32-152">Es ist ein Member der Klasse, der Struktur, des Moduls oder der Schnittstelle, die ihn deklariert.</span><span class="sxs-lookup"><span data-stu-id="9fb32-152">It is a member of the class, structure, module, or interface that declares it.</span></span>

<span data-ttu-id="9fb32-153">Auf Member-Enumerationen kann von überall in ihrer Klasse, Struktur, Modul oder Schnittstelle zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="9fb32-153">Member enumerations can be accessed from anywhere within their class, structure, module, or interface.</span></span> <span data-ttu-id="9fb32-154">Code außerhalb einer Klasse, Struktur oder eines Moduls muss den Namen einer Member-Enumeration mit dem Namen der Klasse, Struktur oder des Moduls qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="9fb32-154">Code outside a class, structure, or module must qualify a member enumeration's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="9fb32-155">Sie können verhindern, dass voll qualifizierte Namen verwendet werden, indem Sie der Quelldatei eine [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) -Anweisung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9fb32-155">You can avoid the need to use fully qualified names by adding an [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statement to the source file.</span></span>

<span data-ttu-id="9fb32-156">Eine Enumeration, die auf Namespace Ebene, außerhalb einer Klasse, Struktur, eines Moduls oder einer Schnittstelle deklariert wurde, ist ein Member des Namespace, in dem Sie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9fb32-156">An enumeration declared at namespace level, outside any class, structure, module, or interface, is a member of the namespace in which it appears.</span></span>

<span data-ttu-id="9fb32-157">Der *Deklarations Kontext* für eine Enumeration muss eine Quelldatei, ein Namespace, eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle sein, und es darf sich nicht um eine Prozedur handeln.</span><span class="sxs-lookup"><span data-stu-id="9fb32-157">The *declaration context* for an enumeration must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure.</span></span> <span data-ttu-id="9fb32-158">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="9fb32-158">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="9fb32-159">Sie können Attribute auf eine Enumeration als Ganzes anwenden, jedoch nicht auf die zugehörigen Elemente einzeln.</span><span class="sxs-lookup"><span data-stu-id="9fb32-159">You can apply attributes to an enumeration as a whole, but not to its members individually.</span></span> <span data-ttu-id="9fb32-160">Ein Attribut trägt Informationen zu den Metadaten der Assembly bei.</span><span class="sxs-lookup"><span data-stu-id="9fb32-160">An attribute contributes information to the assembly's metadata.</span></span>

## <a name="data-type"></a><span data-ttu-id="9fb32-161">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9fb32-161">Data Type</span></span>

<span data-ttu-id="9fb32-162">Die `Enum`-Anweisung kann den Datentyp einer Enumeration deklarieren.</span><span class="sxs-lookup"><span data-stu-id="9fb32-162">The `Enum` statement can declare the data type of an enumeration.</span></span> <span data-ttu-id="9fb32-163">Jeder Member nimmt den Datentyp der Enumeration an.</span><span class="sxs-lookup"><span data-stu-id="9fb32-163">Each member takes the enumeration's data type.</span></span> <span data-ttu-id="9fb32-164">Sie können `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`oder `UShort`angeben.</span><span class="sxs-lookup"><span data-stu-id="9fb32-164">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span></span>

<span data-ttu-id="9fb32-165">Wenn Sie `datatype` für die-Enumeration nicht angeben, nimmt jedes Element den Datentyp seines `initializer`an.</span><span class="sxs-lookup"><span data-stu-id="9fb32-165">If you do not specify `datatype` for the enumeration, each member takes the data type of its `initializer`.</span></span> <span data-ttu-id="9fb32-166">Wenn Sie sowohl `datatype` als auch `initializer`angeben, muss der Datentyp von `initializer` in `datatype`konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="9fb32-166">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="9fb32-167">Wenn weder `datatype` noch `initializer` vorhanden ist, wird der Datentyp standardmäßig `Integer`.</span><span class="sxs-lookup"><span data-stu-id="9fb32-167">If neither `datatype` nor `initializer` is present, the data type defaults to `Integer`.</span></span>

## <a name="initializing-members"></a><span data-ttu-id="9fb32-168">Initialisieren von Membern</span><span class="sxs-lookup"><span data-stu-id="9fb32-168">Initializing Members</span></span>

<span data-ttu-id="9fb32-169">Die `Enum`-Anweisung kann den Inhalt ausgewählter Elemente in `memberlist`initialisieren.</span><span class="sxs-lookup"><span data-stu-id="9fb32-169">The `Enum` statement can initialize the contents of selected members in `memberlist`.</span></span> <span data-ttu-id="9fb32-170">Mit `initializer` können Sie einen Ausdruck angeben, der dem Member zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="9fb32-170">You use `initializer` to supply an expression to be assigned to the member.</span></span>

<span data-ttu-id="9fb32-171">Wenn Sie `initializer` für ein Element nicht angeben, wird es von Visual Basic entweder mit 0 (null) initialisiert (wenn es sich um die erste `member` in `memberlist`) oder um einen Wert, der größer als der unmittelbar vorangehende `member`ist.</span><span class="sxs-lookup"><span data-stu-id="9fb32-171">If you do not specify `initializer` for a member, Visual Basic initializes it either to zero (if it is the first `member` in `memberlist`), or to a value greater by one than that of the immediately preceding `member`.</span></span>

<span data-ttu-id="9fb32-172">Der in jedem `initializer` angegebene Ausdruck kann eine beliebige Kombination von Literalen, anderen Konstanten sein, die bereits definiert sind, und Enumerationsmembern, die bereits definiert sind, einschließlich eines vorherigen Members dieser Enumeration.</span><span class="sxs-lookup"><span data-stu-id="9fb32-172">The expression supplied in each `initializer` can be any combination of literals, other constants that are already defined, and enumeration members that are already defined, including a previous member of this enumeration.</span></span> <span data-ttu-id="9fb32-173">Sie können arithmetische und logische Operatoren verwenden, um solche Elemente zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="9fb32-173">You can use arithmetic and logical operators to combine such elements.</span></span>

<span data-ttu-id="9fb32-174">In `initializer`können keine Variablen oder Funktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9fb32-174">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="9fb32-175">Sie können jedoch Konvertierungs Schlüsselwörter verwenden, z. b. `CByte` und `CShort`.</span><span class="sxs-lookup"><span data-stu-id="9fb32-175">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="9fb32-176">Sie können auch `AscW` verwenden, wenn Sie ihn mit einer Konstanten `String` oder einem `Char` Argument aufzurufen, da dieser zur Kompilierzeit ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9fb32-176">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>

<span data-ttu-id="9fb32-177">Enumerationen dürfen keine Gleit Komma Werte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="9fb32-177">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="9fb32-178">Wenn einem Element ein Gleit Komma Wert zugewiesen wird und `Option Strict` auf ON festgelegt ist, tritt ein Compilerfehler auf.</span><span class="sxs-lookup"><span data-stu-id="9fb32-178">If a member is assigned a floating-point value and `Option Strict` is set to on, a compiler error occurs.</span></span> <span data-ttu-id="9fb32-179">Wenn `Option Strict` deaktiviert ist, wird der Wert automatisch in den `Enum`-Typ konvertiert.</span><span class="sxs-lookup"><span data-stu-id="9fb32-179">If `Option Strict` is off, the value is automatically converted to the `Enum` type.</span></span>

<span data-ttu-id="9fb32-180">Wenn der Wert eines Members den zulässigen Bereich des zugrunde liegenden Datentyps überschreitet oder wenn Sie ein beliebiges Element mit dem maximalen Wert initialisieren, der durch den zugrunde liegenden Datentyp zulässig ist, meldet der Compiler einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="9fb32-180">If the value of a member exceeds the allowable range for the underlying data type, or if you initialize any member to the maximum value allowed by the underlying data type, the compiler reports an error.</span></span>

## <a name="modifiers"></a><span data-ttu-id="9fb32-181">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="9fb32-181">Modifiers</span></span>

<span data-ttu-id="9fb32-182">Klassen-, Struktur-, Modul-und Schnittstellenmember-Enumerationen werden standardmäßig auf Public Access eingestellt.</span><span class="sxs-lookup"><span data-stu-id="9fb32-182">Class, structure, module, and interface member enumerations default to public access.</span></span> <span data-ttu-id="9fb32-183">Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.</span><span class="sxs-lookup"><span data-stu-id="9fb32-183">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="9fb32-184">Namespace-Member-Enumerationen werden standardmäßig auf Friend-Zugriff.</span><span class="sxs-lookup"><span data-stu-id="9fb32-184">Namespace member enumerations default to friend access.</span></span> <span data-ttu-id="9fb32-185">Sie können Ihre Zugriffsebenen an Public, aber nicht an private oder geschützte Einstellungen anpassen.</span><span class="sxs-lookup"><span data-stu-id="9fb32-185">You can adjust their access levels to public, but not to private or protected.</span></span> <span data-ttu-id="9fb32-186">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="9fb32-186">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="9fb32-187">Alle Enumerationsmember haben öffentlichen Zugriff, und Sie können keine Zugriffsmodifizierer verwenden.</span><span class="sxs-lookup"><span data-stu-id="9fb32-187">All enumeration members have public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="9fb32-188">Wenn jedoch die Enumeration selbst über eine eingeschränktere Zugriffsebene verfügt, hat die angegebene enumerationszugriffsebene Vorrang.</span><span class="sxs-lookup"><span data-stu-id="9fb32-188">However, if the enumeration itself has a more restricted access level, the specified enumeration access level takes precedence.</span></span>

<span data-ttu-id="9fb32-189">Standardmäßig sind alle Enumerationen Typen, und ihre Felder sind Konstanten.</span><span class="sxs-lookup"><span data-stu-id="9fb32-189">By default, all enumerations are types and their fields are constants.</span></span> <span data-ttu-id="9fb32-190">Daher können die Schlüsselwörter `Shared`, `Static`und `ReadOnly` beim Deklarieren einer Enumeration oder ihrer Member nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9fb32-190">Therefore the `Shared`, `Static`, and `ReadOnly` keywords cannot be used when declaring an enumeration or its members.</span></span>

## <a name="assigning-multiple-values"></a><span data-ttu-id="9fb32-191">Zuweisen von mehreren Werten</span><span class="sxs-lookup"><span data-stu-id="9fb32-191">Assigning Multiple Values</span></span>

<span data-ttu-id="9fb32-192">Enumerationen stellen in der Regel gegenseitig ausschließende Werte dar.</span><span class="sxs-lookup"><span data-stu-id="9fb32-192">Enumerations typically represent mutually exclusive values.</span></span> <span data-ttu-id="9fb32-193">Indem Sie das <xref:System.FlagsAttribute>-Attribut in die `Enum` Deklaration einschließen, können Sie einer Instanz der-Enumeration stattdessen mehrere Werte zuweisen.</span><span class="sxs-lookup"><span data-stu-id="9fb32-193">By including the <xref:System.FlagsAttribute> attribute in the `Enum` declaration, you can instead assign multiple values to an instance of the enumeration.</span></span> <span data-ttu-id="9fb32-194">Das <xref:System.FlagsAttribute>-Attribut gibt an, dass die Enumeration als Bitfeld, d. h. als ein Satz von Flags, behandelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9fb32-194">The <xref:System.FlagsAttribute> attribute specifies that the enumeration be treated as a bit field, that is, a set of flags.</span></span> <span data-ttu-id="9fb32-195">Diese werden als *bitweise* Enumerationen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="9fb32-195">These are called *bitwise* enumerations.</span></span>

<span data-ttu-id="9fb32-196">Wenn Sie eine Enumeration mit dem <xref:System.FlagsAttribute>-Attribut deklarieren, empfiehlt es sich, für die-Werte die Kräfte 2, d. h. 1, 2, 4, 8, 16 usw., zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9fb32-196">When you declare an enumeration by using the <xref:System.FlagsAttribute> attribute, we recommend that you use powers of 2, that is, 1, 2, 4, 8, 16, and so on, for the values.</span></span> <span data-ttu-id="9fb32-197">Wir empfehlen auch, dass "None" der Name eines Members ist, dessen Wert 0 ist.</span><span class="sxs-lookup"><span data-stu-id="9fb32-197">We also recommend that "None" be the name of a member whose value is 0.</span></span> <span data-ttu-id="9fb32-198">Weitere Richtlinien finden Sie unter <xref:System.FlagsAttribute> und <xref:System.Enum>.</span><span class="sxs-lookup"><span data-stu-id="9fb32-198">For additional guidelines, see <xref:System.FlagsAttribute> and <xref:System.Enum>.</span></span>

## <a name="example"></a><span data-ttu-id="9fb32-199">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9fb32-199">Example</span></span>

<span data-ttu-id="9fb32-200">Im folgenden Beispiel wird veranschaulicht, wie Sie die Anweisung `Enum` verwenden.</span><span class="sxs-lookup"><span data-stu-id="9fb32-200">The following example shows how to use the `Enum` statement.</span></span> <span data-ttu-id="9fb32-201">Beachten Sie, dass der Member als `EggSizeEnum.Medium`und nicht als `Medium`bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="9fb32-201">Note that the member is referred to as `EggSizeEnum.Medium`, and not as `Medium`.</span></span>

[!code-vb[VbEnumsTask#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#41)]

## <a name="example"></a><span data-ttu-id="9fb32-202">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9fb32-202">Example</span></span>

<span data-ttu-id="9fb32-203">Die-Methode im folgenden Beispiel befindet sich außerhalb der `Egg`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="9fb32-203">The method in the following example is outside the `Egg` class.</span></span> <span data-ttu-id="9fb32-204">Daher ist `EggSizeEnum` voll qualifiziert als `Egg.EggSizeEnum`.</span><span class="sxs-lookup"><span data-stu-id="9fb32-204">Therefore, `EggSizeEnum` is fully qualified as `Egg.EggSizeEnum`.</span></span>

[!code-vb[VbEnumsTask#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#42)]

## <a name="example"></a><span data-ttu-id="9fb32-205">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9fb32-205">Example</span></span>

<span data-ttu-id="9fb32-206">Im folgenden Beispiel wird die `Enum`-Anweisung verwendet, um einen verknüpften Satz benannter konstanter Werte zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9fb32-206">The following example uses the `Enum` statement to define a related set of named constant values.</span></span> <span data-ttu-id="9fb32-207">In diesem Fall sind die Werte Farben, die Sie zum Entwerfen von Dateneingabe Formularen für eine Datenbank auswählen können.</span><span class="sxs-lookup"><span data-stu-id="9fb32-207">In this case, the values are colors you might choose to design data entry forms for a database.</span></span>

[!code-vb[VbEnumsTask#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#30)]

## <a name="example"></a><span data-ttu-id="9fb32-208">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9fb32-208">Example</span></span>

<span data-ttu-id="9fb32-209">Das folgende Beispiel zeigt Werte, die positive und negative Zahlen enthalten.</span><span class="sxs-lookup"><span data-stu-id="9fb32-209">The following example shows values that include both positive and negative numbers.</span></span>

[!code-vb[VbEnumsTask#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#31)]

## <a name="example"></a><span data-ttu-id="9fb32-210">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9fb32-210">Example</span></span>

<span data-ttu-id="9fb32-211">Im folgenden Beispiel wird eine `As`-Klausel verwendet, um die `datatype` einer Enumeration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9fb32-211">In the following example, an `As` clause is used to specify the `datatype` of an enumeration.</span></span>

[!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]

## <a name="example"></a><span data-ttu-id="9fb32-212">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9fb32-212">Example</span></span>

<span data-ttu-id="9fb32-213">Im folgenden Beispiel wird gezeigt, wie eine bitweise-Enumeration verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9fb32-213">The following example shows how to use a bitwise enumeration.</span></span> <span data-ttu-id="9fb32-214">Einer Instanz einer bitweisen Enumeration können mehrere Werte zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="9fb32-214">Multiple values can be assigned to an instance of a bitwise enumeration.</span></span> <span data-ttu-id="9fb32-215">Die `Enum`-Deklaration enthält das <xref:System.FlagsAttribute>-Attribut, das angibt, dass die Enumeration als ein Satz von Flags behandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9fb32-215">The `Enum` declaration includes the <xref:System.FlagsAttribute> attribute, which indicates that the enumeration can be treated as a set of flags.</span></span>

[!code-vb[VbEnumsTask#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#61)]

## <a name="example"></a><span data-ttu-id="9fb32-216">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9fb32-216">Example</span></span>

<span data-ttu-id="9fb32-217">Das folgende Beispiel durchläuft eine-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="9fb32-217">The following example iterates through an enumeration.</span></span> <span data-ttu-id="9fb32-218">Er verwendet die <xref:System.Enum.GetNames%2A>-Methode, um ein Array mit Elementnamen aus der-Enumeration abzurufen, und <xref:System.Enum.GetValues%2A>, um ein Array von Element Werten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9fb32-218">It uses the <xref:System.Enum.GetNames%2A> method to retrieve an array of member names from the enumeration, and <xref:System.Enum.GetValues%2A> to retrieve an array of member values.</span></span>

[!code-vb[VbEnumsTask#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#51)]

## <a name="see-also"></a><span data-ttu-id="9fb32-219">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9fb32-219">See also</span></span>

- <xref:System.Enum>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [<span data-ttu-id="9fb32-220">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9fb32-220">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="9fb32-221">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9fb32-221">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="9fb32-222">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="9fb32-222">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="9fb32-223">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="9fb32-223">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="9fb32-224">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="9fb32-224">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
