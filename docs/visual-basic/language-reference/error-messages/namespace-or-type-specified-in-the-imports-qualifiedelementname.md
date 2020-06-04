---
title: Der in Imports '<qualifiedelementname>' angegebene Namespace oder Typ enthält keine öffentlichen Member oder kann nicht gefunden werden
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: 8675d9c3b202200c89e12e7a5f51a19d9e3e0e64
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409464"
---
# <a name="namespace-or-type-specified-in-the-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="c1f3d-102">Der in Imports '\<qualifiedelementname>' angegebene Namespace oder Typ enthält keine öffentlichen Member oder kann nicht gefunden werden</span><span class="sxs-lookup"><span data-stu-id="c1f3d-102">Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found</span></span>

<span data-ttu-id="c1f3d-103">Der in den Importen ' ' angegebene Namespace oder Typ \<qualifiedelementname> enthält keinen öffentlichen Member oder kann nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="c1f3d-103">Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="c1f3d-104">Stellen Sie sicher, dass der Namespace oder der Typ definiert ist und mindestens einen öffentlichen Member enthält.</span><span class="sxs-lookup"><span data-stu-id="c1f3d-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="c1f3d-105">Stellen Sie sicher, dass der Alias Name keine anderen Aliase enthält.</span><span class="sxs-lookup"><span data-stu-id="c1f3d-105">Make sure the alias name doesn't contain other aliases.</span></span>

<span data-ttu-id="c1f3d-106">Eine- `Imports` Anweisung gibt ein enthaltende Element an, das entweder nicht gefunden werden kann oder keine Member definiert `Public` .</span><span class="sxs-lookup"><span data-stu-id="c1f3d-106">An `Imports` statement specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>

<span data-ttu-id="c1f3d-107">Ein *enthaltende Element* kann ein Namespace, eine Klasse, eine Struktur, ein Modul, eine Schnittstelle oder eine Enumeration sein.</span><span class="sxs-lookup"><span data-stu-id="c1f3d-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="c1f3d-108">Das enthaltende Element enthält Member, z. b. Variablen, Prozeduren oder andere enthaltende Elemente.</span><span class="sxs-lookup"><span data-stu-id="c1f3d-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>

<span data-ttu-id="c1f3d-109">Der Zweck des Importierens besteht darin, dass Ihr Code auf Namespaces oder Typmember zugreifen kann, ohne Sie qualifizieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="c1f3d-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="c1f3d-110">Das Projekt muss möglicherweise auch einen Verweis auf den Namespace oder den Typ hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c1f3d-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="c1f3d-111">Weitere Informationen finden Sie unter "Importieren enthaltender Elemente" in [Verweise auf deklarierte Elemente](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="c1f3d-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

<span data-ttu-id="c1f3d-112">Wenn der Compiler das angegebene enthaltende Element nicht finden kann, kann er keine Verweise auflösen, die ihn verwenden.</span><span class="sxs-lookup"><span data-stu-id="c1f3d-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="c1f3d-113">Wenn das-Element gefunden wird, aber das-Element keine Member verfügbar macht `Public` , kann kein Verweis erfolgreich sein.</span><span class="sxs-lookup"><span data-stu-id="c1f3d-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="c1f3d-114">In beiden Fällen ist es bedeutungslos, das-Element zu importieren.</span><span class="sxs-lookup"><span data-stu-id="c1f3d-114">In either case it is meaningless to import the element.</span></span>

<span data-ttu-id="c1f3d-115">Beachten Sie, dass Sie, wenn Sie ein enthaltenes Element importieren und ihm einen importieralias zuweisen, diesen Importalias nicht verwenden können, um ein anderes Element zu importieren.</span><span class="sxs-lookup"><span data-stu-id="c1f3d-115">Keep in mind that if you import a containing element and assign an import alias to it, then you cannot use that import alias to import another element.</span></span> <span data-ttu-id="c1f3d-116">Der folgende Code generiert einen Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="c1f3d-116">The following code generates a compiler error.</span></span>

```vb
Imports winfrm = System.Windows.Forms

' The following statement is INVALID  because it reuses an import alias.

Imports behave = winfrm.Design.Behavior`
```

<span data-ttu-id="c1f3d-117">**Fehler-ID:** BC40056</span><span class="sxs-lookup"><span data-stu-id="c1f3d-117">**Error ID:** BC40056</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="c1f3d-118">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c1f3d-118">To correct this error</span></span>

1. <span data-ttu-id="c1f3d-119">Stellen Sie sicher, dass das enthaltende Element über Ihr Projekt zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="c1f3d-119">Verify that the containing element is accessible from your project.</span></span>

2. <span data-ttu-id="c1f3d-120">Vergewissern Sie sich, dass die Spezifikation des enthaltenden Elements keinen importtalias aus einem anderen Import enthält.</span><span class="sxs-lookup"><span data-stu-id="c1f3d-120">Verify that the specification of the containing element does not include any import alias from another import.</span></span>

3. <span data-ttu-id="c1f3d-121">Vergewissern Sie sich, dass das enthaltende Element mindestens einen Member verfügbar macht `Public` .</span><span class="sxs-lookup"><span data-stu-id="c1f3d-121">Verify that the containing element exposes at least one `Public` member.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1f3d-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1f3d-122">See also</span></span>

- [<span data-ttu-id="c1f3d-123">Imports-Anweisung (.NET-Namespace und Typ)</span><span class="sxs-lookup"><span data-stu-id="c1f3d-123">Imports Statement (.NET Namespace and Type)</span></span>](../statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="c1f3d-124">Namespace-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c1f3d-124">Namespace Statement</span></span>](../statements/namespace-statement.md)
- [<span data-ttu-id="c1f3d-125">Öffentlich</span><span class="sxs-lookup"><span data-stu-id="c1f3d-125">Public</span></span>](../modifiers/public.md)
- [<span data-ttu-id="c1f3d-126">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c1f3d-126">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="c1f3d-127">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="c1f3d-127">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
