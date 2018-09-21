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
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46526544"
---
# <a name="myresponse-object"></a>My.Response-Objekt
Ruft die <xref:System.Web.HttpResponse> zugeordnete Objekt der <xref:System.Web.UI.Page>. Mit diesem Objekt können Sie HTTP-Antwortdaten an einen Client senden. Es enthält außerdem Informationen über diese Antwort.  
  
## <a name="remarks"></a>Hinweise  
 Die `My.Response` Objekt enthält die aktuelle <xref:System.Web.HttpResponse> Objekt, mit der Seite verknüpft ist.  
  
 Die `My.Response` -Objekts ist nur verfügbar für [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] Anwendungen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die headerauflistung aus der `My.Request` -Objekt und verwendet die `My.Response` es in die ASP.NET-Seite zu schreibende Objekt.  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Web.HttpResponse>  
 [My.Request-Objekt](../../../visual-basic/language-reference/objects/my-request-object.md)
