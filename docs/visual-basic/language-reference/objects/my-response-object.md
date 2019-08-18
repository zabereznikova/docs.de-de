---
title: My. Response-Objekt (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: a50701998011c25c600c2a3763459c1aba3cc59a
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567453"
---
# <a name="myresponse-object"></a><span data-ttu-id="2413d-102">My.Response-Objekt</span><span class="sxs-lookup"><span data-stu-id="2413d-102">My.Response Object</span></span>
<span data-ttu-id="2413d-103">Ruft das <xref:System.Web.HttpResponse> -Objekt ab, <xref:System.Web.UI.Page>das zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="2413d-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="2413d-104">Mit diesem Objekt können Sie HTTP-Antwortdaten an einen Client senden. Es enthält außerdem Informationen über diese Antwort.</span><span class="sxs-lookup"><span data-stu-id="2413d-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2413d-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2413d-105">Remarks</span></span>  
 <span data-ttu-id="2413d-106">Das `My.Response` -Objekt enthält das <xref:System.Web.HttpResponse> aktuelle-Objekt, das der Seite zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="2413d-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="2413d-107">Das `My.Response` -Objekt ist nur für ASP.NET-Anwendungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2413d-107">The `My.Response` object is only available for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2413d-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2413d-108">Example</span></span>  
 <span data-ttu-id="2413d-109">Im folgenden Beispiel wird die Header Auflistung aus dem `My.Request` -Objekt abgerufen, `My.Response` und das-Objekt wird verwendet, um Sie auf die ASP.NET-Seite zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="2413d-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2413d-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2413d-110">See also</span></span>

- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="2413d-111">My.Request-Objekt</span><span class="sxs-lookup"><span data-stu-id="2413d-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
