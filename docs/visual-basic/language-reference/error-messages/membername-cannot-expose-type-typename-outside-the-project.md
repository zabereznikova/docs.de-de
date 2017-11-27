---
title: "&#39; &lt;Membername&gt;&#39; kann nicht verfügbar zu machen, geben Sie &#39;&lt; TypeName&gt;&#39; außerhalb des Projekts durch &lt;Containertype&gt; &#39;&lt; Containertypename&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords: BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fd64c815286a5ffec111bcf1f68674a8e3558403
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="39ltmembernamegt39-cannot-expose-type-39lttypenamegt39-outside-the-project-through-ltcontainertypegt-39ltcontainertypenamegt39"></a><span data-ttu-id="e91cd-102">&#39; &lt;Membername&gt;&#39; kann nicht verfügbar zu machen, geben Sie &#39;&lt; TypeName&gt;&#39; außerhalb des Projekts durch &lt;Containertype&gt; &#39;&lt; Containertypename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="e91cd-102">&#39;&lt;membername&gt;&#39; cannot expose type &#39;&lt;typename&gt;&#39; outside the project through &lt;containertype&gt; &#39;&lt;containertypename&gt;&#39;</span></span>
<span data-ttu-id="e91cd-103">Eine Variable, Prozedurparameter oder Funktionsrückgabe wird außerhalb des zugehörigen Containers verfügbar gemacht, aber es ist deklariert, als ein Typ, der außerhalb des Containers nicht verfügbar gemacht werden muss.</span><span class="sxs-lookup"><span data-stu-id="e91cd-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="e91cd-104">Die folgenden Codegerüst zeigt eine Situation, die diesen Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="e91cd-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="e91cd-105">Ein Typ, der deklariert wird `Protected`, `Friend`, `Protected Friend`, oder `Private` soll beschränkten Zugriff außerhalb seines Deklarationskontexts haben.</span><span class="sxs-lookup"><span data-stu-id="e91cd-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="e91cd-106">Die Daten unter widerspricht Typ einer Variablen mit weniger eingeschränktem Zugriff diesen Zweck.</span><span class="sxs-lookup"><span data-stu-id="e91cd-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="e91cd-107">Im vorangehenden Code Skelett `exposedVar` ist `Public` und Verfügbarmachen von würde `privateClass` an Code, der keinen Zugriff darauf haben sollten.</span><span class="sxs-lookup"><span data-stu-id="e91cd-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="e91cd-108">**Fehler-ID:** BC30909</span><span class="sxs-lookup"><span data-stu-id="e91cd-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e91cd-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="e91cd-109">To correct this error</span></span>  
  
-   <span data-ttu-id="e91cd-110">Ändern Sie die Zugriffsebene der Variablen, Parameter der Prozedur oder Funktion zurück, um mindestens so restriktiv wie die Zugriffsebene für die Angabe des Datentyps werden.</span><span class="sxs-lookup"><span data-stu-id="e91cd-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e91cd-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e91cd-111">See Also</span></span>  
 [<span data-ttu-id="e91cd-112">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e91cd-112">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
