---
title: Deklaration erwartet.
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: 2755f5afcb96ca7a6c4d140908649390dd66d571
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162699"
---
# <a name="bc30188-declaration-expected"></a><span data-ttu-id="8df07-102">BC30188: Deklaration erwartet</span><span class="sxs-lookup"><span data-stu-id="8df07-102">BC30188: Declaration expected</span></span>

<span data-ttu-id="8df07-103">Eine nicht deklarative Anweisung, z. b. eine Zuweisungs-oder Schleifen Anweisung, findet außerhalb der Prozeduren statt.</span><span class="sxs-lookup"><span data-stu-id="8df07-103">A nondeclarative statement, such as an assignment or loop statement, occurs outside any procedure.</span></span> <span data-ttu-id="8df07-104">Nur Deklarationen sind außerhalb der Prozeduren zulässig.</span><span class="sxs-lookup"><span data-stu-id="8df07-104">Only declarations are allowed outside procedures.</span></span>

 <span data-ttu-id="8df07-105">Alternativ wird ein Programmier Element ohne Deklarations Schlüsselwort, wie z `Dim` . b. oder, deklariert `Const` .</span><span class="sxs-lookup"><span data-stu-id="8df07-105">Alternatively, a programming element is declared without a declaration keyword such as `Dim` or `Const`.</span></span>

 <span data-ttu-id="8df07-106">**Fehler-ID:** BC30188</span><span class="sxs-lookup"><span data-stu-id="8df07-106">**Error ID:** BC30188</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="8df07-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="8df07-107">To correct this error</span></span>

- <span data-ttu-id="8df07-108">Verschieben Sie die nicht deklarative Anweisung in den Text einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="8df07-108">Move the nondeclarative statement to the body of a procedure.</span></span>

- <span data-ttu-id="8df07-109">Beginnen Sie die Deklaration mit einem entsprechenden Deklarations Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="8df07-109">Begin the declaration with an appropriate declaration keyword.</span></span>

- <span data-ttu-id="8df07-110">Stellen Sie sicher, dass ein Deklarations Schlüsselwort falsch geschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="8df07-110">Ensure that a declaration keyword is not misspelled.</span></span>

## <a name="see-also"></a><span data-ttu-id="8df07-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8df07-111">See also</span></span>

- [<span data-ttu-id="8df07-112">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="8df07-112">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="8df07-113">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8df07-113">Dim Statement</span></span>](../statements/dim-statement.md)
