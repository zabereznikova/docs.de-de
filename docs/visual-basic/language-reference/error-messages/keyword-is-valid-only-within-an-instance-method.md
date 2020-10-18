---
title: <keyword> ist nur innerhalb einer Instanzenmethode gültig.
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: ad39ade294b362b20f2dfb93455445bf41d056cd
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163323"
---
# <a name="bc30043-keyword-is-valid-only-within-an-instance-method"></a><span data-ttu-id="54690-102">BC30043: " \<keyword> " ist nur innerhalb einer Instanzmethode gültig</span><span class="sxs-lookup"><span data-stu-id="54690-102">BC30043: '\<keyword>' is valid only within an instance method</span></span>

<span data-ttu-id="54690-103">Die `Me` `MyClass` `MyBase` Schlüsselwörter, und verweisen auf bestimmte Klassen Instanzen.</span><span class="sxs-lookup"><span data-stu-id="54690-103">The `Me`, `MyClass`, and `MyBase` keywords refer to specific class instances.</span></span> <span data-ttu-id="54690-104">Sie können Sie nicht in einer freigegebenen- `Function` oder- `Sub` Prozedur verwenden.</span><span class="sxs-lookup"><span data-stu-id="54690-104">You cannot use them inside a shared `Function` or `Sub` procedure.</span></span>

<span data-ttu-id="54690-105">*Fehler-ID:*\* BC30043</span><span class="sxs-lookup"><span data-stu-id="54690-105">*Error ID:*\* BC30043</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="54690-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="54690-106">To correct this error</span></span>

- <span data-ttu-id="54690-107">Entfernen Sie das-Schlüsselwort aus der Prozedur, oder entfernen Sie das- `Shared` Schlüsselwort aus der Prozedur Deklaration.</span><span class="sxs-lookup"><span data-stu-id="54690-107">Remove the keyword from the procedure, or remove the `Shared` keyword from the procedure declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="54690-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54690-108">See also</span></span>

- [<span data-ttu-id="54690-109">Zuweisung von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="54690-109">Object Variable Assignment</span></span>](../../programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="54690-110">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="54690-110">Me, My, MyBase, and MyClass</span></span>](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="54690-111">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="54690-111">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
