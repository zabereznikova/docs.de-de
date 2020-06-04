---
title: My.Response-Objekt
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 962108264563c5e0b2894c5c856a5f23a3c1a8b4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372458"
---
# <a name="myresponse-object"></a><span data-ttu-id="c87b5-102">My.Response-Objekt</span><span class="sxs-lookup"><span data-stu-id="c87b5-102">My.Response Object</span></span>
<span data-ttu-id="c87b5-103">Ruft das-Objekt ab, das <xref:System.Web.HttpResponse> zugeordnet ist <xref:System.Web.UI.Page> .</span><span class="sxs-lookup"><span data-stu-id="c87b5-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="c87b5-104">Mit diesem Objekt können Sie HTTP-Antwortdaten an einen Client senden. Es enthält außerdem Informationen über diese Antwort.</span><span class="sxs-lookup"><span data-stu-id="c87b5-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c87b5-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c87b5-105">Remarks</span></span>  
 <span data-ttu-id="c87b5-106">Das- `My.Response` Objekt enthält das aktuelle- <xref:System.Web.HttpResponse> Objekt, das der Seite zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c87b5-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="c87b5-107">Das- `My.Response` Objekt ist nur für ASP.NET-Anwendungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c87b5-107">The `My.Response` object is only available for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c87b5-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c87b5-108">Example</span></span>  
 <span data-ttu-id="c87b5-109">Im folgenden Beispiel wird die Header Auflistung aus dem `My.Request` -Objekt abgerufen, und das-Objekt wird verwendet `My.Response` , um Sie auf die ASP.NET-Seite zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="c87b5-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c87b5-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c87b5-110">See also</span></span>

- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="c87b5-111">My.Request-Objekt</span><span class="sxs-lookup"><span data-stu-id="c87b5-111">My.Request Object</span></span>](my-request-object.md)
