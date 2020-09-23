---
title: Die Verwendung der Standardinstanz einer Klasse im Klassenkonstruktor kann zu einem unendlichen rekursiven Aufruf führen.
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: 5d239fdb7dcc5c488bf0341043b810ec7dadc083
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100320"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a><span data-ttu-id="ef18b-102">Die Verwendung der Standardinstanz einer Klasse im Klassenkonstruktor kann zu einem unendlichen rekursiven Aufruf führen.</span><span class="sxs-lookup"><span data-stu-id="ef18b-102">Use of Default Instance of a class in the class constructor could lead to infinite recursive call</span></span>

<span data-ttu-id="ef18b-103">Eine Standardinstanz einer Klasse wurde im Konstruktor der Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="ef18b-103">A default instance of a class has been used in the constructor of the class.</span></span> <span data-ttu-id="ef18b-104">Dies kann zu einem unendlichen rekursiven Aufruf, auch bekannt als Endlosschleife, führen.</span><span class="sxs-lookup"><span data-stu-id="ef18b-104">This can lead to an infinite recursive call, also known as an infinite loop.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ef18b-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="ef18b-105">To correct this error</span></span>  
  
- <span data-ttu-id="ef18b-106">Entfernen Sie die Standardinstanz aus dem Klassenkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="ef18b-106">Remove the default instance from the class constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef18b-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef18b-107">See also</span></span>

- [<span data-ttu-id="ef18b-108">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="ef18b-108">Constructors</span></span>](../programming-guide/concepts/object-oriented-programming.md#constructors)
