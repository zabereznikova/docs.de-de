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
# <a name="myresponse-object"></a>My.Response-Objekt
Ruft das-Objekt ab, das <xref:System.Web.HttpResponse> zugeordnet ist <xref:System.Web.UI.Page> . Mit diesem Objekt können Sie HTTP-Antwortdaten an einen Client senden. Es enthält außerdem Informationen über diese Antwort.  
  
## <a name="remarks"></a>Bemerkungen  
 Das- `My.Response` Objekt enthält das aktuelle- <xref:System.Web.HttpResponse> Objekt, das der Seite zugeordnet ist.  
  
 Das- `My.Response` Objekt ist nur für ASP.NET-Anwendungen verfügbar.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Header Auflistung aus dem `My.Request` -Objekt abgerufen, und das-Objekt wird verwendet `My.Response` , um Sie auf die ASP.NET-Seite zu schreiben.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Web.HttpResponse>
- [My.Request-Objekt](my-request-object.md)
