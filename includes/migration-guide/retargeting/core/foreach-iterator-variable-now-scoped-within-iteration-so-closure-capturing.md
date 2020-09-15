---
ms.openlocfilehash: 9a2d6a25a8ab1b8bf65b947557802e0805a7f826
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617202"
---
### <a name="foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a><span data-ttu-id="44e44-101">Der Gültigkeitsbereich der Foreach-Iteratorvariable ist jetzt auf die Iteration beschränkt, weswegen sich die Semantik für die Abschlusserfassung (in C# 5) unterscheidet</span><span class="sxs-lookup"><span data-stu-id="44e44-101">Foreach iterator variable is now scoped within the iteration, so closure capturing semantics are different (in C#5)</span></span>

#### <a name="details"></a><span data-ttu-id="44e44-102">Details</span><span class="sxs-lookup"><span data-stu-id="44e44-102">Details</span></span>

<span data-ttu-id="44e44-103">Ab C# 5 (Visual Studio 2012) ist der Gültigkeitsbereich von `foreach`-Iteratorvariablen auf die Iteration beschränkt.</span><span class="sxs-lookup"><span data-stu-id="44e44-103">Beginning with C# 5 (Visual Studio 2012), `foreach` iterator variables are scoped within the iteration.</span></span> <span data-ttu-id="44e44-104">Dies kann zu Fehlern führen, wenn der Code zuvor davon abhängig war, dass die Variablen nicht in den `foreach`-Abschluss einbezogen wurden.</span><span class="sxs-lookup"><span data-stu-id="44e44-104">This can cause breaks if code was previously depending on the variables to not be included in the `foreach`'s closure.</span></span> <span data-ttu-id="44e44-105">Diese Änderung führt dazu, dass eine an einen Delegaten übergebene Iteratorvariable als der Wert behandelt wird, den sie zum Zeitpunkt der Erstellung des Delegaten aufwies, anstatt sie als den Wert zu behandeln, den sie zum Zeitpunkt aufwies, als der Delegat aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="44e44-105">The symptom of this change is that an iterator variable passed to a delegate is treated as the value it has at the time the delegate is created, rather than the value it has at the time the delegate is invoked.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="44e44-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="44e44-106">Suggestion</span></span>

<span data-ttu-id="44e44-107">Idealerweise sollte der Code aktualisiert werden, um das neue Compilerverhalten zu erwarten.</span><span class="sxs-lookup"><span data-stu-id="44e44-107">Ideally, code should be updated to expect the new compiler behavior.</span></span> <span data-ttu-id="44e44-108">Wenn die alte Semantik erforderlich ist, kann die Iteratorvariable durch eine separate Variable ersetzt werden, die explizit außerhalb des Gültigkeitsbereichs der Schleife platziert wird.</span><span class="sxs-lookup"><span data-stu-id="44e44-108">If the old semantics are required, the iterator variable can be replaced with a separate variable which is explicitly placed outside of the loop's scope.</span></span>

| <span data-ttu-id="44e44-109">name</span><span class="sxs-lookup"><span data-stu-id="44e44-109">Name</span></span>    | <span data-ttu-id="44e44-110">Wert</span><span class="sxs-lookup"><span data-stu-id="44e44-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="44e44-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="44e44-111">Scope</span></span>   | <span data-ttu-id="44e44-112">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="44e44-112">Major</span></span>       |
| <span data-ttu-id="44e44-113">Version</span><span class="sxs-lookup"><span data-stu-id="44e44-113">Version</span></span> | <span data-ttu-id="44e44-114">4.5</span><span class="sxs-lookup"><span data-stu-id="44e44-114">4.5</span></span>         |
| <span data-ttu-id="44e44-115">Typ</span><span class="sxs-lookup"><span data-stu-id="44e44-115">Type</span></span>    | <span data-ttu-id="44e44-116">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="44e44-116">Retargeting</span></span> |
