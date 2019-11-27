---
title: My.Request-Objekt
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: 22329bc501c9bb75b1336dd5384ab5b23a98ac21
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350679"
---
# <a name="myrequest-object"></a>My.Request-Objekt
Ruft das <xref:System.Web.HttpRequest>-Objekt für die angefragte Seite ab.  
  
## <a name="remarks"></a>Hinweise  
 Das `My.Request`-Objekt enthält Informationen zur aktuellen HTTP-Anforderung.  
  
 Das `My.Request`-Objekt ist nur für ASP.NET-Anwendungen verfügbar.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Header Auflistung aus dem `My.Request` Objekt abgerufen und das `My.Response`-Objekt verwendet, um Sie auf die ASP.NET-Seite zu schreiben.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Web.HttpRequest>
- [My.Response-Objekt](../../../visual-basic/language-reference/objects/my-response-object.md)
