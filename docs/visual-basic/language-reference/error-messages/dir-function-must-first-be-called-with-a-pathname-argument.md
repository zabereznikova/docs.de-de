---
title: '&#39;Dir&#39; Funktion muss zuerst aufgerufen werden, mit einem &#39;PathName&#39; Argument'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 3a271d7c2c2f7b98bae8f3f6fa9b67b65e3548f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="39dir39-function-must-first-be-called-with-a-39pathname39-argument"></a><span data-ttu-id="f2e22-102">&#39;Dir&#39; Funktion muss zuerst aufgerufen werden, mit einem &#39;PathName&#39; Argument</span><span class="sxs-lookup"><span data-stu-id="f2e22-102">&#39;Dir&#39; function must first be called with a &#39;PathName&#39; argument</span></span>
<span data-ttu-id="f2e22-103">Einem ersten Aufruf der `Dir` Funktion schließt nicht die `PathName` Argument.</span><span class="sxs-lookup"><span data-stu-id="f2e22-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="f2e22-104">Der erste Aufruf von `Dir` umfasst eine `PathName`, aber nachfolgende Aufrufe `Dir` müssen nicht enthalten Parameter, um das nächste Element abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f2e22-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f2e22-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f2e22-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="f2e22-106">Geben Sie einen `PathName` Argument im Funktionsaufruf.</span><span class="sxs-lookup"><span data-stu-id="f2e22-106">Supply a `PathName` argument in the function call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2e22-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2e22-107">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
