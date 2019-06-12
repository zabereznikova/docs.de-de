---
title: <membername> kann den <typename>-Typ nicht außerhalb des Projekts über <containertype> '<containertypename>' verfügbar machen.
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: cb5191442ed8d3ee47c5116b10740e277ffa5bac
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661918"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a><span data-ttu-id="d2b87-102">'\<Membername >' kann nicht verfügbar machen '\<Typname >' außerhalb des Projekts durch \<Hiermit > '\<Containertypename >'</span><span class="sxs-lookup"><span data-stu-id="d2b87-102">'\<membername>' cannot expose type '\<typename>' outside the project through \<containertype> '\<containertypename>'</span></span>
<span data-ttu-id="d2b87-103">Eine Variable, Parameter der Prozedur oder Funktion zurückgegeben wird außerhalb des Containers verfügbar gemacht, aber sie wird deklariert, als Typ, der außerhalb des Containers nicht verfügbar gemacht werden muss.</span><span class="sxs-lookup"><span data-stu-id="d2b87-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="d2b87-104">Das folgende Codegerüst zeigt eine Situation, die diesen Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="d2b87-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="d2b87-105">Ein Typ, der deklariert wird `Protected`, `Friend`, `Protected Friend`, oder `Private` außerhalb der Deklarationskontext eingeschränkten Zugriff haben soll.</span><span class="sxs-lookup"><span data-stu-id="d2b87-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="d2b87-106">Verwenden sie, wie die Daten widerspricht Typ einer Variablen mit weniger eingeschränktem Zugriff diesen Zweck.</span><span class="sxs-lookup"><span data-stu-id="d2b87-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="d2b87-107">Im vorangehenden Code Skelett `exposedVar` ist `Public` und macht `privateClass` an Code, der keinen Zugriff darauf haben sollten.</span><span class="sxs-lookup"><span data-stu-id="d2b87-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="d2b87-108">**Fehler-ID:** BC30909</span><span class="sxs-lookup"><span data-stu-id="d2b87-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d2b87-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d2b87-109">To correct this error</span></span>  
  
- <span data-ttu-id="d2b87-110">Ändern Sie die Zugriffsebene der Variablen, Parameter der Prozedur oder Funktion zurückkehren, um die mindestens so restriktiv als die Zugriffsebene seines Datentyps sein.</span><span class="sxs-lookup"><span data-stu-id="d2b87-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2b87-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2b87-111">See also</span></span>

- [<span data-ttu-id="d2b87-112">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d2b87-112">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
