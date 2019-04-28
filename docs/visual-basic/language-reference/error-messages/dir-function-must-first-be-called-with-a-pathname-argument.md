---
title: Die 'Dir'-Funktion muss zuerst mit einem 'PathName'-Argument aufgerufen werden.
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: d255b8dddd098835764f72b8a166eaa08b0353df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803453"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a><span data-ttu-id="91318-102">Die 'Dir'-Funktion muss zuerst mit einem 'PathName'-Argument aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="91318-102">'Dir' function must first be called with a 'PathName' argument</span></span>
<span data-ttu-id="91318-103">Einen anfänglichen Aufruf der `Dir` Funktion schließt nicht die `PathName` Argument.</span><span class="sxs-lookup"><span data-stu-id="91318-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="91318-104">Der erste Aufruf `Dir` müssen eine `PathName`, aber nachfolgende Aufrufe von `Dir` müssen keine Parameter zum Abrufen des nächsten Elements enthalten.</span><span class="sxs-lookup"><span data-stu-id="91318-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="91318-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="91318-105">To correct this error</span></span>  
  
1. <span data-ttu-id="91318-106">Geben Sie einen `PathName` Argument im Funktionsaufruf.</span><span class="sxs-lookup"><span data-stu-id="91318-106">Supply a `PathName` argument in the function call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91318-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91318-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
