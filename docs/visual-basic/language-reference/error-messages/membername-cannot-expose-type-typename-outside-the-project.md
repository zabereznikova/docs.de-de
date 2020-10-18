---
title: <membername> kann den <typename>-Typ nicht außerhalb des Projekts über <containertype> "<containertypename>" verfügbar machen.
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: a3972eabfe297b89c0e4d0f36943ac58e5bdf688
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162465"
---
# <a name="bc30909-membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a><span data-ttu-id="ab2d2-102">BC30909: " \<membername> " kann den Typ " \<typename> " nicht außerhalb des Projekts über \<containertype> " \<containertypename> " verfügbar machen</span><span class="sxs-lookup"><span data-stu-id="ab2d2-102">BC30909: '\<membername>' cannot expose type '\<typename>' outside the project through \<containertype> '\<containertypename>'</span></span>

<span data-ttu-id="ab2d2-103">Eine Variable, ein Prozedur Parameter oder eine Funktions Rückgabe wird außerhalb ihres Containers verfügbar gemacht, Sie wird jedoch als Typ deklariert, der nicht außerhalb des Containers verfügbar gemacht werden darf.</span><span class="sxs-lookup"><span data-stu-id="ab2d2-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>

 <span data-ttu-id="ab2d2-104">Der folgende Skelett Code zeigt eine Situation, die diesen Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="ab2d2-104">The following skeleton code shows a situation that generates this error.</span></span>

```vb
Private Class privateClass
End Class
Public Class mainClass
    Public exposedVar As New privateClass
End Class
```

 <span data-ttu-id="ab2d2-105">Ein Typ, der als `Protected` ,, oder deklariert ist, soll `Friend` `Protected Friend` `Private` eingeschränkten Zugriff außerhalb des Deklarations Kontexts haben.</span><span class="sxs-lookup"><span data-stu-id="ab2d2-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="ab2d2-106">Die Verwendung als Datentyp einer Variablen mit weniger eingeschränktem Zugriff würde diesen Zweck zunichte machen.</span><span class="sxs-lookup"><span data-stu-id="ab2d2-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="ab2d2-107">Im obigen Skelett Code ist, `exposedVar` `Public` und würde für Code verfügbar machen, `privateClass` der keinen Zugriff darauf haben sollte.</span><span class="sxs-lookup"><span data-stu-id="ab2d2-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>

 <span data-ttu-id="ab2d2-108">**Fehler-ID:** BC30909</span><span class="sxs-lookup"><span data-stu-id="ab2d2-108">**Error ID:** BC30909</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="ab2d2-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="ab2d2-109">To correct this error</span></span>

- <span data-ttu-id="ab2d2-110">Ändern Sie die Zugriffsebene der Variablen, des Prozedur Parameters oder der Funktions Rückgabe so, dass Sie mindestens so restriktiv ist wie die Zugriffsebene des Datentyps.</span><span class="sxs-lookup"><span data-stu-id="ab2d2-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab2d2-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab2d2-111">See also</span></span>

- [<span data-ttu-id="ab2d2-112">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ab2d2-112">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
