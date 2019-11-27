---
title: My.Response-Objekt
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 522814ad48fb7548032b8a37779bb3ff6ca62413
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350654"
---
# <a name="myresponse-object"></a>My.Response-Objekt
Ruft das <xref:System.Web.HttpResponse>-Objekt ab, das der <xref:System.Web.UI.Page>zugeordnet ist. Mit diesem Objekt können Sie HTTP-Antwortdaten an einen Client senden. Es enthält außerdem Informationen über diese Antwort.  
  
## <a name="remarks"></a>Hinweise  
 Das `My.Response`-Objekt enthält das aktuelle <xref:System.Web.HttpResponse>-Objekt, das der Seite zugeordnet ist.  
  
 Das `My.Response`-Objekt ist nur für ASP.NET-Anwendungen verfügbar.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Header Auflistung aus dem `My.Request` Objekt abgerufen und das `My.Response`-Objekt verwendet, um Sie auf die ASP.NET-Seite zu schreiben.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Web.HttpResponse>
- [My.Request-Objekt](../../../visual-basic/language-reference/objects/my-request-object.md)
