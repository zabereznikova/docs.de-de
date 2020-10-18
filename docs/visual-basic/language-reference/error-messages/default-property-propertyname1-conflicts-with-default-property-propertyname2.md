---
title: Die "<propertyname1>"-Standardeigenschaft verursacht einen Konflikt mit der "<propertyname2>"-Standardeigenschaft in "<classname>" und sollte daher als "Shadows" deklariert werden.
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: 290971a3173c59f08fbd279b6fffe3bcb618cb72
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160606"
---
# <a name="bc40007-default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a><span data-ttu-id="ec34b-102">BC40007: die Default-Eigenschaft "" verursacht einen \<propertyname1> Konflikt mit der Standard Eigenschaft " \<propertyname2> " in "" \<classname> und sollte daher als "Shadows" deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="ec34b-102">BC40007: Default property '\<propertyname1>' conflicts with default property '\<propertyname2>' in '\<classname>' and so should be declared 'Shadows'</span></span>

<span data-ttu-id="ec34b-103">Eine Eigenschaft wird mit dem gleichen Namen wie eine Eigenschaft deklariert, die in der Basisklasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="ec34b-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="ec34b-104">In dieser Situation sollte die-Eigenschaft in dieser Klasse den Schatten der Basisklassen Eigenschaft überschatten.</span><span class="sxs-lookup"><span data-stu-id="ec34b-104">In this situation, the property in this class should shadow the base class property.</span></span>

 <span data-ttu-id="ec34b-105">Diese Meldung ist eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="ec34b-105">This message is a warning.</span></span> <span data-ttu-id="ec34b-106">`Shadows` wird standardmäßig angenommen.</span><span class="sxs-lookup"><span data-stu-id="ec34b-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="ec34b-107">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="ec34b-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="ec34b-108">**Fehler-ID:** BC40007</span><span class="sxs-lookup"><span data-stu-id="ec34b-108">**Error ID:** BC40007</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="ec34b-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="ec34b-109">To correct this error</span></span>

- <span data-ttu-id="ec34b-110">Fügen Sie das- `Shadows` Schlüsselwort zur Deklaration hinzu, oder ändern Sie den Namen der Eigenschaft, die deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="ec34b-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec34b-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec34b-111">See also</span></span>

- [<span data-ttu-id="ec34b-112">Schatten</span><span class="sxs-lookup"><span data-stu-id="ec34b-112">Shadows</span></span>](../modifiers/shadows.md)
- [<span data-ttu-id="ec34b-113">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ec34b-113">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
