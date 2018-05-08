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
---
# <a name="myresponse-object"></a>My.Response-Objekt
Ruft die <xref:System.Web.HttpResponse> zugeordnete Objekt der <xref:System.Web.UI.Page>. Mit diesem Objekt können Sie HTTP-Antwortdaten an einen Client senden. Es enthält außerdem Informationen über diese Antwort.  
  
## <a name="remarks"></a>Hinweise  
 Die `My.Response` Objekt enthält die aktuelle <xref:System.Web.HttpResponse> Objekt, das mit der Seite zugeordnet.  
  
 Die `My.Response` -Objekts ist nur verfügbar für [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] Anwendungen.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel ruft die headerauflistung aus der `My.Request` -Objekt und verwendet die `My.Response` Objekt, das in der ASP.NET-Seite zu schreiben.  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Web.HttpResponse>  
 [My.Request-Objekt](../../../visual-basic/language-reference/objects/my-request-object.md)
