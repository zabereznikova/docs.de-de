---
title: My.Response-Objekt
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 0a907d74112586e7b88c5a0a6f40080455454d7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597522"
---
# <a name="myresponse-object"></a><span data-ttu-id="de330-102">My.Response-Objekt</span><span class="sxs-lookup"><span data-stu-id="de330-102">My.Response Object</span></span>
<span data-ttu-id="de330-103">Ruft die <xref:System.Web.HttpResponse> zugeordnete Objekt der <xref:System.Web.UI.Page>.</span><span class="sxs-lookup"><span data-stu-id="de330-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="de330-104">Mit diesem Objekt können Sie HTTP-Antwortdaten an einen Client senden. Es enthält außerdem Informationen über diese Antwort.</span><span class="sxs-lookup"><span data-stu-id="de330-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de330-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="de330-105">Remarks</span></span>  
 <span data-ttu-id="de330-106">Die `My.Response` Objekt enthält die aktuelle <xref:System.Web.HttpResponse> Objekt, das mit der Seite zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="de330-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="de330-107">Die `My.Response` -Objekts ist nur verfügbar für [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="de330-107">The `My.Response` object is only available for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de330-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="de330-108">Example</span></span>  
 <span data-ttu-id="de330-109">Im folgende Beispiel ruft die headerauflistung aus der `My.Request` -Objekt und verwendet die `My.Response` Objekt, das in der ASP.NET-Seite zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="de330-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## <a name="see-also"></a><span data-ttu-id="de330-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de330-110">See Also</span></span>  
 <xref:System.Web.HttpResponse>  
 [<span data-ttu-id="de330-111">My.Request-Objekt</span><span class="sxs-lookup"><span data-stu-id="de330-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
