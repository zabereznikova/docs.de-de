---
title: My.Request-Objekt
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: 38f510e2a3958761b902f37760069aa8d595ea8e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372426"
---
# <a name="myrequest-object"></a><span data-ttu-id="29f43-102">My.Request-Objekt</span><span class="sxs-lookup"><span data-stu-id="29f43-102">My.Request Object</span></span>
<span data-ttu-id="29f43-103">Ruft das <xref:System.Web.HttpRequest>-Objekt für die angefragte Seite ab.</span><span class="sxs-lookup"><span data-stu-id="29f43-103">Gets the <xref:System.Web.HttpRequest> object for the requested page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29f43-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="29f43-104">Remarks</span></span>  
 <span data-ttu-id="29f43-105">Das `My.Request`-Objekt enthält Informationen zur aktuellen HTTP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="29f43-105">The `My.Request` object contains information about the current HTTP request.</span></span>  
  
 <span data-ttu-id="29f43-106">Das `My.Request`-Objekt ist nur für ASP.NET-Anwendungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="29f43-106">The `My.Request` object is available only for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29f43-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="29f43-107">Example</span></span>  
 <span data-ttu-id="29f43-108">Im folgenden Beispiel wird die Header Auflistung aus dem `My.Request` -Objekt abgerufen, und das-Objekt wird verwendet `My.Response` , um Sie auf die ASP.NET-Seite zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="29f43-108">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="29f43-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="29f43-109">See also</span></span>

- <xref:System.Web.HttpRequest>
- [<span data-ttu-id="29f43-110">My.Response-Objekt</span><span class="sxs-lookup"><span data-stu-id="29f43-110">My.Response Object</span></span>](my-response-object.md)
