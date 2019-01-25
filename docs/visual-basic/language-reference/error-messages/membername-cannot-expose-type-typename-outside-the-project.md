---
title: '&#39;&lt;Membername&gt; &#39; kann nicht verfügbar machen &#39; &lt;Typename&gt; &#39; außerhalb des Projekts durch &lt;Hiermit&gt; &#39; &lt;Containertypename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 39d316aca5ec306de4b1e43e2eb2d1495f5525d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672343"
---
# <a name="39ltmembernamegt39-cannot-expose-type-39lttypenamegt39-outside-the-project-through-ltcontainertypegt-39ltcontainertypenamegt39"></a><span data-ttu-id="322d9-102">&#39;&lt;Membername&gt; &#39; kann nicht verfügbar machen &#39; &lt;Typename&gt; &#39; außerhalb des Projekts durch &lt;Hiermit&gt; &#39; &lt;Containertypename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="322d9-102">&#39;&lt;membername&gt;&#39; cannot expose type &#39;&lt;typename&gt;&#39; outside the project through &lt;containertype&gt; &#39;&lt;containertypename&gt;&#39;</span></span>
<span data-ttu-id="322d9-103">Eine Variable, Parameter der Prozedur oder Funktion zurückgegeben wird außerhalb des Containers verfügbar gemacht, aber sie wird deklariert, als Typ, der außerhalb des Containers nicht verfügbar gemacht werden muss.</span><span class="sxs-lookup"><span data-stu-id="322d9-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="322d9-104">Das folgende Codegerüst zeigt eine Situation, die diesen Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="322d9-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="322d9-105">Ein Typ, der deklariert wird `Protected`, `Friend`, `Protected Friend`, oder `Private` außerhalb der Deklarationskontext eingeschränkten Zugriff haben soll.</span><span class="sxs-lookup"><span data-stu-id="322d9-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="322d9-106">Verwenden sie, wie die Daten widerspricht Typ einer Variablen mit weniger eingeschränktem Zugriff diesen Zweck.</span><span class="sxs-lookup"><span data-stu-id="322d9-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="322d9-107">Im vorangehenden Code Skelett `exposedVar` ist `Public` und macht `privateClass` an Code, der keinen Zugriff darauf haben sollten.</span><span class="sxs-lookup"><span data-stu-id="322d9-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="322d9-108">**Fehler-ID:** BC30909</span><span class="sxs-lookup"><span data-stu-id="322d9-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="322d9-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="322d9-109">To correct this error</span></span>  
  
-   <span data-ttu-id="322d9-110">Ändern Sie die Zugriffsebene der Variablen, Parameter der Prozedur oder Funktion zurückkehren, um die mindestens so restriktiv als die Zugriffsebene seines Datentyps sein.</span><span class="sxs-lookup"><span data-stu-id="322d9-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="322d9-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="322d9-111">See also</span></span>
- [<span data-ttu-id="322d9-112">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="322d9-112">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
