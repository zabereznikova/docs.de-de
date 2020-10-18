---
title: Der Bezeichner ist zu lang.
ms.date: 07/20/2015
f1_keywords:
- bc30033
- vbc30033
helpviewer_keywords:
- BC30033
ms.assetid: 3d07f6d0-9a2f-49ca-94e8-1e354932e855
ms.openlocfilehash: eafcb2fdf706e12fa606a442ad577c88ed5a7427
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162855"
---
# <a name="bc30033-identifier-is-too-long"></a><span data-ttu-id="2c5a0-102">BC30033: der Bezeichner ist zu lang.</span><span class="sxs-lookup"><span data-stu-id="2c5a0-102">BC30033: Identifier is too long</span></span>

<span data-ttu-id="2c5a0-103">Der Name oder Bezeichner jedes Programmier Elements ist auf 1023 Zeichen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="2c5a0-103">The name, or identifier, of every programming element is limited to 1023 characters.</span></span> <span data-ttu-id="2c5a0-104">Außerdem darf ein voll qualifizierter Name nicht länger als 1023 Zeichen sein.</span><span class="sxs-lookup"><span data-stu-id="2c5a0-104">In addition, a fully qualified name cannot exceed 1023 characters.</span></span> <span data-ttu-id="2c5a0-105">Dies bedeutet, dass die gesamte `<namespace>.<...>.<namespace>.<class>.<element>` Bezeichnerzeichenfolge () nicht mehr als 1023 Zeichen lang sein darf, einschließlich der Member-Access Operator ( `.` )-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="2c5a0-105">This means that the entire identifier string (`<namespace>.<...>.<namespace>.<class>.<element>`) cannot be more than 1023 characters long, including the member-access operator (`.`) characters.</span></span>

 <span data-ttu-id="2c5a0-106">**Fehler-ID:** BC30033</span><span class="sxs-lookup"><span data-stu-id="2c5a0-106">**Error ID:** BC30033</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="2c5a0-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="2c5a0-107">To correct this error</span></span>

- <span data-ttu-id="2c5a0-108">Reduzieren Sie die Länge des Bezeichners.</span><span class="sxs-lookup"><span data-stu-id="2c5a0-108">Reduce the length of the identifier.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c5a0-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c5a0-109">See also</span></span>

- [<span data-ttu-id="2c5a0-110">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="2c5a0-110">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
