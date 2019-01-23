---
title: Default-Eigenschaft &#39; &lt;eigenschaftsname1&gt; &#39; verursacht einen Konflikt mit Default-Eigenschaft &#39; &lt;propertyname2&gt; &#39; in &#39; &lt;Classname&gt; &#39;und sollte daher deklariert werden &#39;Schatten&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: 3099467fa3c5a162c13c9235fb8d55375953ba3a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521425"
---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a><span data-ttu-id="c64b4-102">Default-Eigenschaft &#39; &lt;eigenschaftsname1&gt; &#39; verursacht einen Konflikt mit Default-Eigenschaft &#39; &lt;propertyname2&gt; &#39; in &#39; &lt;Classname&gt; &#39;und sollte daher deklariert werden &#39;Schatten&#39;</span><span class="sxs-lookup"><span data-stu-id="c64b4-102">Default property &#39;&lt;propertyname1&gt;&#39; conflicts with default property &#39;&lt;propertyname2&gt;&#39; in &#39;&lt;classname&gt;&#39; and so should be declared &#39;Shadows&#39;</span></span>
<span data-ttu-id="c64b4-103">Eine Eigenschaft wird mit dem gleichen Namen wie eine Eigenschaft in der Basisklasse deklariert.</span><span class="sxs-lookup"><span data-stu-id="c64b4-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="c64b4-104">In diesem Fall muss die Eigenschaft in dieser Klasse als Eigenschaft der Basisklasse überschatten.</span><span class="sxs-lookup"><span data-stu-id="c64b4-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="c64b4-105">Diese Meldung ist eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="c64b4-105">This message is a warning.</span></span> <span data-ttu-id="c64b4-106">`Shadows` wird standardmäßig angenommen.</span><span class="sxs-lookup"><span data-stu-id="c64b4-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="c64b4-107">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="c64b4-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="c64b4-108">**Fehler-ID:** BC40007</span><span class="sxs-lookup"><span data-stu-id="c64b4-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c64b4-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c64b4-109">To correct this error</span></span>  
  
-   <span data-ttu-id="c64b4-110">Hinzufügen der `Shadows` Schlüsselwort, um die Deklaration, oder ändern, die der Namen der Eigenschaft deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="c64b4-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c64b4-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c64b4-111">See also</span></span>
- [<span data-ttu-id="c64b4-112">Shadows</span><span class="sxs-lookup"><span data-stu-id="c64b4-112">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="c64b4-113">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c64b4-113">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
