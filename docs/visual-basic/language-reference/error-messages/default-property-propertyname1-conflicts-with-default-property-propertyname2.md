---
title: Die '<propertyname1>'-Standardeigenschaft verursacht einen Konflikt mit der '<propertyname2>'-Standardeigenschaft in '<classname>' und sollte daher als 'Shadows' deklariert werden.
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: c964003217e7b96cf25288e2ae6ae6a2fb07a6c3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651380"
---
# <a name="default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a><span data-ttu-id="a6b98-102">Default-Eigenschaft '\<eigenschaftsname1 >' verursacht einen Konflikt mit Default-Eigenschaft '\<propertyname2 >' in '\<Klassenname >' und daher als'Shadows'deklariert werden soll</span><span class="sxs-lookup"><span data-stu-id="a6b98-102">Default property '\<propertyname1>' conflicts with default property '\<propertyname2>' in '\<classname>' and so should be declared 'Shadows'</span></span>
<span data-ttu-id="a6b98-103">Eine Eigenschaft wird mit dem gleichen Namen wie eine Eigenschaft in der Basisklasse deklariert.</span><span class="sxs-lookup"><span data-stu-id="a6b98-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="a6b98-104">In diesem Fall muss die Eigenschaft in dieser Klasse als Eigenschaft der Basisklasse überschatten.</span><span class="sxs-lookup"><span data-stu-id="a6b98-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="a6b98-105">Diese Meldung ist eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="a6b98-105">This message is a warning.</span></span> <span data-ttu-id="a6b98-106">`Shadows` wird standardmäßig angenommen.</span><span class="sxs-lookup"><span data-stu-id="a6b98-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="a6b98-107">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="a6b98-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="a6b98-108">**Fehler-ID:** BC40007</span><span class="sxs-lookup"><span data-stu-id="a6b98-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a6b98-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a6b98-109">To correct this error</span></span>  
  
- <span data-ttu-id="a6b98-110">Hinzufügen der `Shadows` Schlüsselwort, um die Deklaration, oder ändern, die der Namen der Eigenschaft deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="a6b98-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6b98-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6b98-111">See also</span></span>

- [<span data-ttu-id="a6b98-112">Shadows</span><span class="sxs-lookup"><span data-stu-id="a6b98-112">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="a6b98-113">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a6b98-113">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
