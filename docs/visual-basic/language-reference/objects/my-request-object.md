---
title: My.Request-Objekt
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: d0459506994fb69ebfaa4186ba137044b6fe9464
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870083"
---
# <a name="myrequest-object"></a>My.Request-Objekt

Ruft das <xref:System.Web.HttpRequest>-Objekt für die angefragte Seite ab.  
  
## <a name="remarks"></a>Bemerkungen  

 Das `My.Request`-Objekt enthält Informationen zur aktuellen HTTP-Anforderung.  
  
 Das `My.Request`-Objekt ist nur für ASP.NET-Anwendungen verfügbar.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird die Header Auflistung aus dem `My.Request` -Objekt abgerufen, und das-Objekt wird verwendet `My.Response` , um Sie auf die ASP.NET-Seite zu schreiben.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Web.HttpRequest>
- [My.Response-Objekt](my-response-object.md)
