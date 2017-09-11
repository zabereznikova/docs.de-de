---
title: Default-Eigenschaft &quot;&lt;propertyname1&gt;&quot;steht in Konflikt mit der Standardeigenschaft&quot;&lt;propertyname2&gt;&quot;in&quot;&lt;Classname&gt;&quot;und sollte daher als&quot;Shadows&quot;deklariert werden | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40007
- bc40007
dev_langs:
- VB
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6eac9e0fdc468e27afac82a8a7c9b2251a8f7317
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a><span data-ttu-id="2090c-102">Default-Eigenschaft '&lt;propertyname1&gt;"steht in Konflikt mit der Standardeigenschaft"&lt;propertyname2&gt;"in"&lt;Classname&gt;"und sollte daher als"Shadows"deklariert werden</span><span class="sxs-lookup"><span data-stu-id="2090c-102">Default property &#39;&lt;propertyname1&gt;&#39; conflicts with default property &#39;&lt;propertyname2&gt;&#39; in &#39;&lt;classname&gt;&#39; and so should be declared &#39;Shadows&#39;</span></span>
<span data-ttu-id="2090c-103">Eine Eigenschaft wird mit den gleichen Namen wie eine Eigenschaft in der Basisklasse deklariert.</span><span class="sxs-lookup"><span data-stu-id="2090c-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="2090c-104">In diesem Fall muss die Eigenschaft in dieser Klasse die Eigenschaft der Basisklasse überschatten.</span><span class="sxs-lookup"><span data-stu-id="2090c-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="2090c-105">Diese Meldung ist eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="2090c-105">This message is a warning.</span></span> <span data-ttu-id="2090c-106">`Shadows`wird standardmäßig angenommen.</span><span class="sxs-lookup"><span data-stu-id="2090c-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="2090c-107">Weitere Informationen zum Ausblenden von Warnungen oder Warnungen als Fehler behandeln, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="2090c-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="2090c-108">**Fehler-ID:** BC40007</span><span class="sxs-lookup"><span data-stu-id="2090c-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2090c-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="2090c-109">To correct this error</span></span>  
  
-   <span data-ttu-id="2090c-110">Hinzufügen der `Shadows` Schlüsselwort auf die Deklaration, oder ändern Sie der Namen der Eigenschaft deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="2090c-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2090c-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2090c-111">See Also</span></span>  
 <span data-ttu-id="2090c-112">[Schatten](../../../visual-basic/language-reference/modifiers/shadows.md) </span><span class="sxs-lookup"><span data-stu-id="2090c-112">[Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) </span></span>  
<span data-ttu-id="2090c-113"> [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)</span><span class="sxs-lookup"><span data-stu-id="2090c-113"> [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)</span></span>
