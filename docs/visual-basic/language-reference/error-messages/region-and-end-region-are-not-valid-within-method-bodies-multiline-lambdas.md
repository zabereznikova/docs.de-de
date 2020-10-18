---
title: 'Region- und #End Region-Anweisungen sind im Methodentext/in mehrzeiligen Lambda-Ausdrücken ungültig.'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: c792fa1a42bde22959ae21439cb2a0a1e4be343f
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162283"
---
# <a name="bc32025-region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="29d12-102">BC32025: die Anweisungen "#Region" und "#End Region" sind innerhalb von Methoden Texten/mehrzeiligen Lambdas ungültig.</span><span class="sxs-lookup"><span data-stu-id="29d12-102">BC32025: '#Region' and '#End Region' statements are not valid within method bodies/multiline lambdas</span></span>

<span data-ttu-id="29d12-103">Der- `#Region` Block muss auf Klassen-, Modul-oder Namespace Ebene deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="29d12-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="29d12-104">Ein reduzierbarer Bereich kann eine oder mehrere Prozeduren enthalten, aber er kann nicht innerhalb einer Prozedur beginnen oder enden.</span><span class="sxs-lookup"><span data-stu-id="29d12-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>

 <span data-ttu-id="29d12-105">**Fehler-ID:** BC32025</span><span class="sxs-lookup"><span data-stu-id="29d12-105">**Error ID:** BC32025</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="29d12-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="29d12-106">To correct this error</span></span>

1. <span data-ttu-id="29d12-107">Stellen Sie sicher, dass die vorherige Prozedur mit einer-oder-Anweisung ordnungsgemäß beendet wird `End Function` `End Sub` .</span><span class="sxs-lookup"><span data-stu-id="29d12-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>

2. <span data-ttu-id="29d12-108">Stellen Sie sicher, dass `#Region` sich die-und- `#End Region` Direktiven im gleichen Codeblock befinden.</span><span class="sxs-lookup"><span data-stu-id="29d12-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>

## <a name="see-also"></a><span data-ttu-id="29d12-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29d12-109">See also</span></span>

- [<span data-ttu-id="29d12-110">#Region-Direktive</span><span class="sxs-lookup"><span data-stu-id="29d12-110">#Region Directive</span></span>](../directives/region-directive.md)
