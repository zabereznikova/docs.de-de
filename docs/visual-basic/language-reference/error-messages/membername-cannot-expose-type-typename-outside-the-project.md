---
title: <membername> kann den <typename>-Typ nicht außerhalb des Projekts über <containertype> "<containertypename>" verfügbar machen.
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 729a9f385d94412469d318cb804d216827eeb0fd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397284"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a><span data-ttu-id="df68d-102">\<membername> kann den \<typename>-Typ nicht außerhalb des Projekts über \<containertype> "\<containertypename>" verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="df68d-102">'\<membername>' cannot expose type '\<typename>' outside the project through \<containertype> '\<containertypename>'</span></span>
<span data-ttu-id="df68d-103">Eine Variable, ein Prozedur Parameter oder eine Funktions Rückgabe wird außerhalb ihres Containers verfügbar gemacht, Sie wird jedoch als Typ deklariert, der nicht außerhalb des Containers verfügbar gemacht werden darf.</span><span class="sxs-lookup"><span data-stu-id="df68d-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="df68d-104">Der folgende Skelett Code zeigt eine Situation, die diesen Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="df68d-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```vb  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="df68d-105">Ein Typ, der als `Protected` ,, oder deklariert ist, soll `Friend` `Protected Friend` `Private` eingeschränkten Zugriff außerhalb des Deklarations Kontexts haben.</span><span class="sxs-lookup"><span data-stu-id="df68d-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="df68d-106">Die Verwendung als Datentyp einer Variablen mit weniger eingeschränktem Zugriff würde diesen Zweck zunichte machen.</span><span class="sxs-lookup"><span data-stu-id="df68d-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="df68d-107">Im obigen Skelett Code ist, `exposedVar` `Public` und würde für Code verfügbar machen, `privateClass` der keinen Zugriff darauf haben sollte.</span><span class="sxs-lookup"><span data-stu-id="df68d-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="df68d-108">**Fehler-ID:** BC30909</span><span class="sxs-lookup"><span data-stu-id="df68d-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="df68d-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="df68d-109">To correct this error</span></span>  
  
- <span data-ttu-id="df68d-110">Ändern Sie die Zugriffsebene der Variablen, des Prozedur Parameters oder der Funktions Rückgabe so, dass Sie mindestens so restriktiv ist wie die Zugriffsebene des Datentyps.</span><span class="sxs-lookup"><span data-stu-id="df68d-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df68d-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="df68d-111">See also</span></span>

- [<span data-ttu-id="df68d-112">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="df68d-112">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
