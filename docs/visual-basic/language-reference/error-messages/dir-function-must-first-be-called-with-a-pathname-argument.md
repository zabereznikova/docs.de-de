---
title: Die 'Dir'-Funktion muss zuerst mit einem 'PathName'-Argument aufgerufen werden.
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 7f8191b0ef5452fcf6f3a20c3e0f28ca84ef9c4a
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163427"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a><span data-ttu-id="16101-102">Die 'Dir'-Funktion muss zuerst mit einem 'PathName'-Argument aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="16101-102">'Dir' function must first be called with a 'PathName' argument</span></span>

<span data-ttu-id="16101-103">Ein anfänglicher-Rückruf für die- `Dir` Funktion schließt das-Argument nicht ein `PathName` .</span><span class="sxs-lookup"><span data-stu-id="16101-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="16101-104">Der erste Aufruf von `Dir` muss einen enthalten `PathName` , aber nachfolgende Aufrufe von `Dir` müssen keine Parameter enthalten, um das nächste Element abzurufen.</span><span class="sxs-lookup"><span data-stu-id="16101-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="16101-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="16101-105">To correct this error</span></span>

- <span data-ttu-id="16101-106">Geben Sie `PathName` im Funktions aufrufein Argument an.</span><span class="sxs-lookup"><span data-stu-id="16101-106">Supply a `PathName` argument in the function call.</span></span>

## <a name="see-also"></a><span data-ttu-id="16101-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16101-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
