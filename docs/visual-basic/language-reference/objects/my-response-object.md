---
title: My.Response-Objekt | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MyWebExtension.Response
- My.Response
dev_langs:
- VB
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b9b34c9df31536f6d553cda2e26677a2645768c2
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="myresponse-object"></a><span data-ttu-id="26661-102">My.Response-Objekt</span><span class="sxs-lookup"><span data-stu-id="26661-102">My.Response Object</span></span>
<span data-ttu-id="26661-103">Ruft <xref:System.Web.HttpResponse>den <xref:System.Web.UI.Page>.</xref:System.Web.UI.Page> zugeordnete Objekt</xref:System.Web.HttpResponse></span><span class="sxs-lookup"><span data-stu-id="26661-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="26661-104">Dieses Objekt ermöglicht es Ihnen, HTTP-Antwortdaten an einen Client gesendet und enthält Informationen über diese Antwort.</span><span class="sxs-lookup"><span data-stu-id="26661-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26661-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="26661-105">Remarks</span></span>  
 <span data-ttu-id="26661-106">Die `My.Response` -Objekt enthält das aktuelle <xref:System.Web.HttpResponse>Objekt, das der Seite zugeordnet.</xref:System.Web.HttpResponse></span><span class="sxs-lookup"><span data-stu-id="26661-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="26661-107">Die `My.Response` -Objekts ist nur verfügbar für [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] Applications.</span><span class="sxs-lookup"><span data-stu-id="26661-107">The `My.Response` object is only available for [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26661-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="26661-108">Example</span></span>  
 <span data-ttu-id="26661-109">Im folgenden Beispiel wird die Auflistung aus der `My.Request` -Objekt und verwendet die `My.Response` -Objekt, das in der ASP.NET-Seite schreiben.</span><span class="sxs-lookup"><span data-stu-id="26661-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 <span data-ttu-id="26661-110">[!code-vb[VbVbalrMyWeb&#1;](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]</span><span class="sxs-lookup"><span data-stu-id="26661-110">[!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26661-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26661-111">See Also</span></span>  
 <span data-ttu-id="26661-112"><xref:System.Web.HttpResponse></xref:System.Web.HttpResponse></span><span class="sxs-lookup"><span data-stu-id="26661-112"><xref:System.Web.HttpResponse></span></span>   
<span data-ttu-id="26661-113"> [My.Request-Objekt](../../../visual-basic/language-reference/objects/my-request-object.md)</span><span class="sxs-lookup"><span data-stu-id="26661-113"> [My.Request Object](../../../visual-basic/language-reference/objects/my-request-object.md)</span></span>
