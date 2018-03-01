---
title: My.Response-Objekt
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76d0e701107add0d5bd468ba7a829759739e0cd9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="myresponse-object"></a><span data-ttu-id="2278e-102">My.Response-Objekt</span><span class="sxs-lookup"><span data-stu-id="2278e-102">My.Response Object</span></span>
<span data-ttu-id="2278e-103">Ruft die <xref:System.Web.HttpResponse> zugeordnete Objekt der <xref:System.Web.UI.Page>.</span><span class="sxs-lookup"><span data-stu-id="2278e-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="2278e-104">Mit diesem Objekt können Sie HTTP-Antwortdaten an einen Client senden. Es enthält außerdem Informationen über diese Antwort.</span><span class="sxs-lookup"><span data-stu-id="2278e-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2278e-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2278e-105">Remarks</span></span>  
 <span data-ttu-id="2278e-106">Die `My.Response` Objekt enthält die aktuelle <xref:System.Web.HttpResponse> Objekt, das mit der Seite zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="2278e-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="2278e-107">Die `My.Response` -Objekts ist nur verfügbar für [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="2278e-107">The `My.Response` object is only available for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2278e-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2278e-108">Example</span></span>  
 <span data-ttu-id="2278e-109">Im folgende Beispiel ruft die headerauflistung aus der `My.Request` -Objekt und verwendet die `My.Response` Objekt, das in der ASP.NET-Seite zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="2278e-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## <a name="see-also"></a><span data-ttu-id="2278e-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2278e-110">See Also</span></span>  
 <xref:System.Web.HttpResponse>  
 [<span data-ttu-id="2278e-111">My.Request-Objekt</span><span class="sxs-lookup"><span data-stu-id="2278e-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
