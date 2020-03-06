---
title: Bezeichnernamen
description: Lernen Sie die Regeln für gültige Bezeichnernamen in der C#-Programmiersprache kennen.
ms.date: 08/21/2018
ms.openlocfilehash: bef6e2ea285b5391af3350ae42a4105d140c6d1b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "77673367"
---
# <a name="identifier-names"></a><span data-ttu-id="f779a-103">Bezeichnernamen</span><span class="sxs-lookup"><span data-stu-id="f779a-103">Identifier names</span></span>

<span data-ttu-id="f779a-104">Ein **Bezeichner** ist der Name, den Sie einem Namespace, einem Member, einer Variable oder einem Typ (Klasse, Schnittstelle, Struktur, Delegat oder Enumeration) zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f779a-104">An **identifier** is the name you assign to a type (class, interface, struct, delegate, or enum), member, variable, or namespace.</span></span> <span data-ttu-id="f779a-105">Gültige Bezeichner müssen folgende Regeln einhalten:</span><span class="sxs-lookup"><span data-stu-id="f779a-105">Valid identifiers must follow these rules:</span></span>

- <span data-ttu-id="f779a-106">Bezeichner müssen mit einem Buchstaben oder mit `_` beginnen.</span><span class="sxs-lookup"><span data-stu-id="f779a-106">Identifiers must start with a letter, or `_`.</span></span>
- <span data-ttu-id="f779a-107">Bezeichner können Unicode-Buchstaben, Dezimalziffernzeichen, Unicode-Verbindungszeichen, Unicode-Kombinationszeichen oder Unicode-Formatierungszeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="f779a-107">Identifiers may contain Unicode letter characters, decimal digit characters, Unicode connecting characters, Unicode combining characters, or Unicode formatting characters.</span></span> <span data-ttu-id="f779a-108">Weitere Informationen zu den Kategorien von Unicode finden Sie in der [Unicode-Kategoriedatenbank](https://www.unicode.org/reports/tr44/).</span><span class="sxs-lookup"><span data-stu-id="f779a-108">For more information on Unicode categories, see the [Unicode Category Database](https://www.unicode.org/reports/tr44/).</span></span>
<span data-ttu-id="f779a-109">Sie können Bezeichner deklarieren, die mit C#-Schlüsselworten übereinstimmen, indem Sie das Präfix `@` für den Bezeichner verwenden.</span><span class="sxs-lookup"><span data-stu-id="f779a-109">You can declare identifiers that match C# keywords by using the `@` prefix on the identifier.</span></span> <span data-ttu-id="f779a-110">`@` ist nicht Teil des Namens des Bezeichners.</span><span class="sxs-lookup"><span data-stu-id="f779a-110">The `@` is not part of the identifier name.</span></span> <span data-ttu-id="f779a-111">Beispielsweise deklariert `@if` einen Bezeichner namens `if`.</span><span class="sxs-lookup"><span data-stu-id="f779a-111">For example, `@if` declares an identifier named `if`.</span></span> <span data-ttu-id="f779a-112">Diese [ausführlichen Bezeichner](../../language-reference/tokens/verbatim.md) dienen in erster Linie der Interoperabilität mit Bezeichnern, die in anderen Sprachen deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="f779a-112">These [verbatim identifiers](../../language-reference/tokens/verbatim.md) are primarily for interoperability with identifiers declared in other languages.</span></span>

<span data-ttu-id="f779a-113">Eine vollständige Definition der gültigen Bezeichner finden Sie im [Thema „Bezeichner“ in der C#-Sprachspezifikation](../../../../_csharplang/spec/lexical-structure.md#identifiers).</span><span class="sxs-lookup"><span data-stu-id="f779a-113">For a complete definition of valid identifiers, see the [Identifiers topic in the C# Language Specification](../../../../_csharplang/spec/lexical-structure.md#identifiers).</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="f779a-114">Namenskonventionen</span><span class="sxs-lookup"><span data-stu-id="f779a-114">Naming conventions</span></span>

<span data-ttu-id="f779a-115">Neben diesen Regeln gibt es mehrere [Namenskonventionen](../../../standard/design-guidelines/naming-guidelines.md) für Bezeichner, die in den .NET-APIs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f779a-115">In addition to the rules, there are a number of identifier [naming conventions](../../../standard/design-guidelines/naming-guidelines.md) used throughout the .NET APIs.</span></span> <span data-ttu-id="f779a-116">Gemäß der Konventionen verwenden C#-Programme `PascalCase` für Typnamen, Namespaces und alle öffentlichen Member.</span><span class="sxs-lookup"><span data-stu-id="f779a-116">By convention, C# programs use `PascalCase` for type names, namespaces, and all public members.</span></span> <span data-ttu-id="f779a-117">Darüber hinaus werden folgende Konventionen häufig angewandt:</span><span class="sxs-lookup"><span data-stu-id="f779a-117">In addition, the following conventions are common:</span></span>

- <span data-ttu-id="f779a-118">Schnittstellennamen beginnen mit einem großen `I`.</span><span class="sxs-lookup"><span data-stu-id="f779a-118">Interface names start with a capital `I`.</span></span>
- <span data-ttu-id="f779a-119">Attributtypen enden mit dem Wort `Attribute`.</span><span class="sxs-lookup"><span data-stu-id="f779a-119">Attribute types end with the word `Attribute`.</span></span>
- <span data-ttu-id="f779a-120">Enumerationstypen enthalten ein Substantiv im Singular für nicht Flags und ein Substantiv im Plural für Flags.</span><span class="sxs-lookup"><span data-stu-id="f779a-120">Enum types use a singular noun for non-flags, and a plural noun for flags.</span></span>
- <span data-ttu-id="f779a-121">Bezeichner sollten keine zwei aufeinanderfolgenden `_`-Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="f779a-121">Identifiers should not contain two consecutive `_` characters.</span></span> <span data-ttu-id="f779a-122">Diese Namen sind für Bezeichner reserviert, die der Compiler generiert.</span><span class="sxs-lookup"><span data-stu-id="f779a-122">Those names are reserved for compiler generated identifiers.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f779a-123">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="f779a-123">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f779a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f779a-124">See also</span></span>

- [<span data-ttu-id="f779a-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f779a-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f779a-126">Einblicke in ein C#-Programm</span><span class="sxs-lookup"><span data-stu-id="f779a-126">Inside a C# Program</span></span>](./index.md)
- [<span data-ttu-id="f779a-127">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f779a-127">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="f779a-128">Klassen</span><span class="sxs-lookup"><span data-stu-id="f779a-128">Classes</span></span>](../classes-and-structs/classes.md)
- [<span data-ttu-id="f779a-129">Strukturtypen</span><span class="sxs-lookup"><span data-stu-id="f779a-129">Structure types</span></span>](../../language-reference/builtin-types/struct.md)
- [<span data-ttu-id="f779a-130">Namespaces</span><span class="sxs-lookup"><span data-stu-id="f779a-130">Namespaces</span></span>](../namespaces/index.md)
- [<span data-ttu-id="f779a-131">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f779a-131">Interfaces</span></span>](../interfaces/index.md)
- [<span data-ttu-id="f779a-132">Delegaten</span><span class="sxs-lookup"><span data-stu-id="f779a-132">Delegates</span></span>](../delegates/index.md)
