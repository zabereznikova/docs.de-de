---
title: My.Request-Objekt (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: 08212dc5fe563ce84be02ab706b56195a0636894
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58836622"
---
# <a name="myrequest-object"></a><span data-ttu-id="48ef7-102">My.Request-Objekt</span><span class="sxs-lookup"><span data-stu-id="48ef7-102">My.Request Object</span></span>
<span data-ttu-id="48ef7-103">Ruft das <xref:System.Web.HttpRequest>-Objekt für die angefragte Seite ab.</span><span class="sxs-lookup"><span data-stu-id="48ef7-103">Gets the <xref:System.Web.HttpRequest> object for the requested page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48ef7-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="48ef7-104">Remarks</span></span>  
 <span data-ttu-id="48ef7-105">Das `My.Request`-Objekt enthält Informationen zur aktuellen HTTP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="48ef7-105">The `My.Request` object contains information about the current HTTP request.</span></span>  
  
 <span data-ttu-id="48ef7-106">Das `My.Request`-Objekt ist nur für ASP.NET-Anwendungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="48ef7-106">The `My.Request` object is available only for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48ef7-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="48ef7-107">Example</span></span>  
 <span data-ttu-id="48ef7-108">Im folgenden Beispiel wird die headerauflistung aus der `My.Request` -Objekt und verwendet die `My.Response` es in die ASP.NET-Seite zu schreibende Objekt.</span><span class="sxs-lookup"><span data-stu-id="48ef7-108">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="48ef7-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48ef7-109">See also</span></span>

- <xref:System.Web.HttpRequest>
- [<span data-ttu-id="48ef7-110">My.Response-Objekt</span><span class="sxs-lookup"><span data-stu-id="48ef7-110">My.Response Object</span></span>](../../../visual-basic/language-reference/objects/my-response-object.md)
