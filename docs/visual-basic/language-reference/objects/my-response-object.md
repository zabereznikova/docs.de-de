---
title: My.Response-Objekt (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 0e49a3b5732ee1a3626666ce06e366c4940eca05
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881965"
---
# <a name="myresponse-object"></a><span data-ttu-id="b96dd-102">My.Response-Objekt</span><span class="sxs-lookup"><span data-stu-id="b96dd-102">My.Response Object</span></span>
<span data-ttu-id="b96dd-103">Ruft die <xref:System.Web.HttpResponse> zugeordnete Objekt der <xref:System.Web.UI.Page>.</span><span class="sxs-lookup"><span data-stu-id="b96dd-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="b96dd-104">Mit diesem Objekt können Sie HTTP-Antwortdaten an einen Client senden. Es enthält außerdem Informationen über diese Antwort.</span><span class="sxs-lookup"><span data-stu-id="b96dd-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b96dd-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b96dd-105">Remarks</span></span>  
 <span data-ttu-id="b96dd-106">Die `My.Response` Objekt enthält die aktuelle <xref:System.Web.HttpResponse> Objekt, mit der Seite verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="b96dd-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="b96dd-107">Die `My.Response` -Objekts ist nur für ASP.NET-Anwendungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b96dd-107">The `My.Response` object is only available for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b96dd-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b96dd-108">Example</span></span>  
 <span data-ttu-id="b96dd-109">Im folgenden Beispiel wird die headerauflistung aus der `My.Request` -Objekt und verwendet die `My.Response` es in die ASP.NET-Seite zu schreibende Objekt.</span><span class="sxs-lookup"><span data-stu-id="b96dd-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b96dd-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b96dd-110">See also</span></span>

- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="b96dd-111">My.Request-Objekt</span><span class="sxs-lookup"><span data-stu-id="b96dd-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
