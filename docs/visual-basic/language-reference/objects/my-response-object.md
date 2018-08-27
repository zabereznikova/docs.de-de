---
title: My.Response-Objekt (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: d5f49529a2593093a234babc22f64b591ea3cc61
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42929550"
---
# <a name="myresponse-object"></a><span data-ttu-id="aef85-102">My.Response-Objekt</span><span class="sxs-lookup"><span data-stu-id="aef85-102">My.Response Object</span></span>
<span data-ttu-id="aef85-103">Ruft die <xref:System.Web.HttpResponse> zugeordnete Objekt der <xref:System.Web.UI.Page>.</span><span class="sxs-lookup"><span data-stu-id="aef85-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="aef85-104">Mit diesem Objekt können Sie HTTP-Antwortdaten an einen Client senden. Es enthält außerdem Informationen über diese Antwort.</span><span class="sxs-lookup"><span data-stu-id="aef85-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aef85-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aef85-105">Remarks</span></span>  
 <span data-ttu-id="aef85-106">Die `My.Response` Objekt enthält die aktuelle <xref:System.Web.HttpResponse> Objekt, mit der Seite verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="aef85-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="aef85-107">Die `My.Response` -Objekts ist nur verfügbar für [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="aef85-107">The `My.Response` object is only available for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aef85-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aef85-108">Example</span></span>  
 <span data-ttu-id="aef85-109">Im folgenden Beispiel wird die headerauflistung aus der `My.Request` -Objekt und verwendet die `My.Response` es in die ASP.NET-Seite zu schreibende Objekt.</span><span class="sxs-lookup"><span data-stu-id="aef85-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## <a name="see-also"></a><span data-ttu-id="aef85-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aef85-110">See Also</span></span>  
 <xref:System.Web.HttpResponse>  
 [<span data-ttu-id="aef85-111">My.Request-Objekt</span><span class="sxs-lookup"><span data-stu-id="aef85-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
