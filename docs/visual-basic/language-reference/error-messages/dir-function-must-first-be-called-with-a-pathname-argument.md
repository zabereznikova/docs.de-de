---
title: '&#39;Dir&#39; Funktion muss zuerst aufgerufen werden, mit einem &#39;Pfadnamen&#39; Argument'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: f7e9ef9cc6309f24ae9f8963e910b41180c029b7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518487"
---
# <a name="39dir39-function-must-first-be-called-with-a-39pathname39-argument"></a><span data-ttu-id="a8f70-102">&#39;Dir&#39; Funktion muss zuerst aufgerufen werden, mit einem &#39;Pfadnamen&#39; Argument</span><span class="sxs-lookup"><span data-stu-id="a8f70-102">&#39;Dir&#39; function must first be called with a &#39;PathName&#39; argument</span></span>
<span data-ttu-id="a8f70-103">Einen anfänglichen Aufruf der `Dir` Funktion schließt nicht die `PathName` Argument.</span><span class="sxs-lookup"><span data-stu-id="a8f70-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="a8f70-104">Der erste Aufruf `Dir` müssen eine `PathName`, aber nachfolgende Aufrufe von `Dir` müssen keine Parameter zum Abrufen des nächsten Elements enthalten.</span><span class="sxs-lookup"><span data-stu-id="a8f70-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a8f70-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a8f70-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="a8f70-106">Geben Sie einen `PathName` Argument im Funktionsaufruf.</span><span class="sxs-lookup"><span data-stu-id="a8f70-106">Supply a `PathName` argument in the function call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8f70-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8f70-107">See also</span></span>
- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
