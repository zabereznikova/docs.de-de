---
title: Es ist ein Verweis auf die Assembly "<assemblyname>" erforderlich, die die Basisklasse "<classname>" enthält.
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: d2fb3498219dfe3318ec418ede250de818874ba9
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162335"
---
# <a name="bc30007-reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a><span data-ttu-id="b8d08-102">BC30007: Es ist ein Verweis auf die Assembly "" erforderlich, \<assemblyname> die die Basisklasse " \<classname> " enthält</span><span class="sxs-lookup"><span data-stu-id="b8d08-102">BC30007: Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'</span></span>

<span data-ttu-id="b8d08-103">Es ist ein Verweis auf die Assembly "" erforderlich, \<assemblyname> die die Basisklasse "" enthält \<classname> .</span><span class="sxs-lookup"><span data-stu-id="b8d08-103">Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'.</span></span> <span data-ttu-id="b8d08-104">Fügen Sie dem Projekt einen Verweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="b8d08-104">Add one to your project.</span></span>

 <span data-ttu-id="b8d08-105">Die Klasse ist in einer Dynamic Link Library (DLL) oder Assembly definiert, auf die in Ihrem Projekt nicht direkt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b8d08-105">The class is defined in a dynamic-link library (DLL) or assembly that is not directly referenced in your project.</span></span> <span data-ttu-id="b8d08-106">Der Visual Basic-Compiler benötigt einen Verweis, um Mehrdeutigkeiten zu vermeiden, falls die Klasse in mehr als einer DLL oder Assembly definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b8d08-106">The Visual Basic compiler requires a reference to avoid ambiguity in case the class is defined in more than one DLL or assembly.</span></span>

 <span data-ttu-id="b8d08-107">**Fehler-ID:** BC30007</span><span class="sxs-lookup"><span data-stu-id="b8d08-107">**Error ID:** BC30007</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="b8d08-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="b8d08-108">To correct this error</span></span>

- <span data-ttu-id="b8d08-109">Nehmen Sie den Namen der nicht referenzierten DLL oder Assembly in Ihre Projektverweise auf.</span><span class="sxs-lookup"><span data-stu-id="b8d08-109">Include the name of the unreferenced DLL or assembly in your project references.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8d08-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8d08-110">See also</span></span>

- [<span data-ttu-id="b8d08-111">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="b8d08-111">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="b8d08-112">Problembehandlung bei fehlerhaften Verweisen</span><span class="sxs-lookup"><span data-stu-id="b8d08-112">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
