---
title: Die "<propertyname1>"-Standardeigenschaft verursacht einen Konflikt mit der "<propertyname2>"-Standardeigenschaft in "<classname>" und sollte daher als "Shadows" deklariert werden.
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: b857a9ae7875a156179602cbe77558333d07b7b9
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874517"
---
# <a name="default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a><span data-ttu-id="fed9d-102">Die "\<propertyname1>"-Standardeigenschaft verursacht einen Konflikt mit der "\<propertyname2>"-Standardeigenschaft in "\<classname>" und sollte daher als "Shadows" deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="fed9d-102">Default property '\<propertyname1>' conflicts with default property '\<propertyname2>' in '\<classname>' and so should be declared 'Shadows'</span></span>

<span data-ttu-id="fed9d-103">Eine Eigenschaft wird mit dem gleichen Namen wie eine Eigenschaft deklariert, die in der Basisklasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="fed9d-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="fed9d-104">In dieser Situation sollte die-Eigenschaft in dieser Klasse den Schatten der Basisklassen Eigenschaft überschatten.</span><span class="sxs-lookup"><span data-stu-id="fed9d-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="fed9d-105">Diese Meldung ist eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="fed9d-105">This message is a warning.</span></span> <span data-ttu-id="fed9d-106">`Shadows` wird standardmäßig angenommen.</span><span class="sxs-lookup"><span data-stu-id="fed9d-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="fed9d-107">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="fed9d-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="fed9d-108">**Fehler-ID:** BC40007</span><span class="sxs-lookup"><span data-stu-id="fed9d-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fed9d-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="fed9d-109">To correct this error</span></span>  
  
- <span data-ttu-id="fed9d-110">Fügen Sie das- `Shadows` Schlüsselwort zur Deklaration hinzu, oder ändern Sie den Namen der Eigenschaft, die deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="fed9d-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed9d-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fed9d-111">See also</span></span>

- [<span data-ttu-id="fed9d-112">Shadows</span><span class="sxs-lookup"><span data-stu-id="fed9d-112">Shadows</span></span>](../modifiers/shadows.md)
- [<span data-ttu-id="fed9d-113">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fed9d-113">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
