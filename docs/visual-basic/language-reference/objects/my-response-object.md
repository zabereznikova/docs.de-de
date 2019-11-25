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
Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>. Mit diesem Objekt können Sie HTTP-Antwortdaten an einen Client senden. Es enthält außerdem Informationen über diese Antwort.  
  
## <a name="remarks"></a>Hinweise  
 The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.  
  
 The `My.Response` object is only available for ASP.NET applications.  
  
## <a name="example"></a>Beispiel  
 The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Web.HttpResponse>
- [My.Request-Objekt](../../../visual-basic/language-reference/objects/my-request-object.md)
