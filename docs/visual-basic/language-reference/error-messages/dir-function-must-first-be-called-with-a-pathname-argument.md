---
title: Die 'Dir'-Funktion muss zuerst mit einem 'PathName'-Argument aufgerufen werden.
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 828c715d9aaceef17d030113e7eda302f025ca9d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55282589"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a><span data-ttu-id="4a2ae-102">Die 'Dir'-Funktion muss zuerst mit einem 'PathName'-Argument aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4a2ae-102">'Dir' function must first be called with a 'PathName' argument</span></span>
<span data-ttu-id="4a2ae-103">Einen anfänglichen Aufruf der `Dir` Funktion schließt nicht die `PathName` Argument.</span><span class="sxs-lookup"><span data-stu-id="4a2ae-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="4a2ae-104">Der erste Aufruf `Dir` müssen eine `PathName`, aber nachfolgende Aufrufe von `Dir` müssen keine Parameter zum Abrufen des nächsten Elements enthalten.</span><span class="sxs-lookup"><span data-stu-id="4a2ae-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4a2ae-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4a2ae-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="4a2ae-106">Geben Sie einen `PathName` Argument im Funktionsaufruf.</span><span class="sxs-lookup"><span data-stu-id="4a2ae-106">Supply a `PathName` argument in the function call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a2ae-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a2ae-107">See also</span></span>
- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
