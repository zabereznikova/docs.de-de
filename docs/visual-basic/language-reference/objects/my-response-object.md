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
# <a name="myresponse-object"></a>My.Response-Objekt
Ruft das <xref:System.Web.HttpResponse> -Objekt ab, <xref:System.Web.UI.Page>das zugeordnet ist. Mit diesem Objekt können Sie HTTP-Antwortdaten an einen Client senden. Es enthält außerdem Informationen über diese Antwort.  
  
## <a name="remarks"></a>Hinweise  
 Das `My.Response` -Objekt enthält das <xref:System.Web.HttpResponse> aktuelle-Objekt, das der Seite zugeordnet ist.  
  
 Das `My.Response` -Objekt ist nur für ASP.NET-Anwendungen verfügbar.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Header Auflistung aus dem `My.Request` -Objekt abgerufen, `My.Response` und das-Objekt wird verwendet, um Sie auf die ASP.NET-Seite zu schreiben.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Web.HttpResponse>
- [My.Request-Objekt](../../../visual-basic/language-reference/objects/my-request-object.md)
