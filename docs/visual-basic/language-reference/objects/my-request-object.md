---
title: My. Request-Objekt (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: da17872acb839cdcdfa7f80c3f58f26dc25d0ab5
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567460"
---
# <a name="myrequest-object"></a>My.Request-Objekt
Ruft das <xref:System.Web.HttpRequest>-Objekt für die angefragte Seite ab.  
  
## <a name="remarks"></a>Hinweise  
 Das `My.Request`-Objekt enthält Informationen zur aktuellen HTTP-Anforderung.  
  
 Das `My.Request`-Objekt ist nur für ASP.NET-Anwendungen verfügbar.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Header Auflistung aus dem `My.Request` -Objekt abgerufen, `My.Response` und das-Objekt wird verwendet, um Sie auf die ASP.NET-Seite zu schreiben.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Web.HttpRequest>
- [My.Response-Objekt](../../../visual-basic/language-reference/objects/my-response-object.md)
