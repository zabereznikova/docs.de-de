---
title: My. Request-Objekt (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: da17872acb839cdcdfa7f80c3f58f26dc25d0ab5
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567460"
---
# <a name="myrequest-object"></a><span data-ttu-id="32c8e-102">My.Request-Objekt</span><span class="sxs-lookup"><span data-stu-id="32c8e-102">My.Request Object</span></span>
<span data-ttu-id="32c8e-103">Ruft das <xref:System.Web.HttpRequest>-Objekt für die angefragte Seite ab.</span><span class="sxs-lookup"><span data-stu-id="32c8e-103">Gets the <xref:System.Web.HttpRequest> object for the requested page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32c8e-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="32c8e-104">Remarks</span></span>  
 <span data-ttu-id="32c8e-105">Das `My.Request`-Objekt enthält Informationen zur aktuellen HTTP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="32c8e-105">The `My.Request` object contains information about the current HTTP request.</span></span>  
  
 <span data-ttu-id="32c8e-106">Das `My.Request`-Objekt ist nur für ASP.NET-Anwendungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="32c8e-106">The `My.Request` object is available only for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32c8e-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="32c8e-107">Example</span></span>  
 <span data-ttu-id="32c8e-108">Im folgenden Beispiel wird die Header Auflistung aus dem `My.Request` -Objekt abgerufen, `My.Response` und das-Objekt wird verwendet, um Sie auf die ASP.NET-Seite zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="32c8e-108">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="32c8e-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32c8e-109">See also</span></span>

- <xref:System.Web.HttpRequest>
- [<span data-ttu-id="32c8e-110">My.Response-Objekt</span><span class="sxs-lookup"><span data-stu-id="32c8e-110">My.Response Object</span></span>](../../../visual-basic/language-reference/objects/my-response-object.md)
