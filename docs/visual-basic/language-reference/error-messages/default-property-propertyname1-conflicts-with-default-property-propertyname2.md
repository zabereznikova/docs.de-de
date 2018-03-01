---
title: Standardeigenschaft &#39; &lt;eigenschaftsname1&gt;&#39; steht in Konflikt mit der Standardeigenschaft &#39;&lt; propertyName2&gt;&#39; in &#39;&lt; Klassenname&gt;&#39; und sollte daher deklariert werden &#39; Shadows &#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: af92c06f6d07b6ea64a05b9043547a46e3679111
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a><span data-ttu-id="9a7c6-102">Standardeigenschaft &#39; &lt;eigenschaftsname1&gt;&#39; steht in Konflikt mit der Standardeigenschaft &#39;&lt; propertyName2&gt;&#39; in &#39;&lt; Klassenname&gt;&#39; und sollte daher deklariert werden &#39; Shadows &#39;</span><span class="sxs-lookup"><span data-stu-id="9a7c6-102">Default property &#39;&lt;propertyname1&gt;&#39; conflicts with default property &#39;&lt;propertyname2&gt;&#39; in &#39;&lt;classname&gt;&#39; and so should be declared &#39;Shadows&#39;</span></span>
<span data-ttu-id="9a7c6-103">Mit dem gleichen Namen wie eine in der Basisklasse definierte Eigenschaft ist eine Eigenschaft deklariert.</span><span class="sxs-lookup"><span data-stu-id="9a7c6-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="9a7c6-104">In diesem Fall muss die Eigenschaft in dieser Klasse die Eigenschaft der Basisklasse überschatten.</span><span class="sxs-lookup"><span data-stu-id="9a7c6-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="9a7c6-105">Diese Meldung ist eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="9a7c6-105">This message is a warning.</span></span> <span data-ttu-id="9a7c6-106">`Shadows` wird standardmäßig angenommen.</span><span class="sxs-lookup"><span data-stu-id="9a7c6-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="9a7c6-107">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="9a7c6-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="9a7c6-108">**Fehler-ID:** BC40007</span><span class="sxs-lookup"><span data-stu-id="9a7c6-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9a7c6-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="9a7c6-109">To correct this error</span></span>  
  
-   <span data-ttu-id="9a7c6-110">Hinzufügen der `Shadows` Schlüsselwort, um die Deklaration, oder ändern Sie der Namen der Eigenschaft deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="9a7c6-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a7c6-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a7c6-111">See Also</span></span>  
 [<span data-ttu-id="9a7c6-112">Shadows</span><span class="sxs-lookup"><span data-stu-id="9a7c6-112">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="9a7c6-113">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9a7c6-113">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
