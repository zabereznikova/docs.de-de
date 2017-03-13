---
title: "My.Response Object | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "My.MyWebExtension.Response"
  - "My.Response"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Response object"
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# My.Response Object
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Ruft das <xref:System.Web.HttpResponse>\-Objekt ab, das der <xref:System.Web.UI.Page> zugeordnet ist.  Dieses Objekt ermöglicht das Senden von HTTP\-Antwortdaten an einen Client und enthält Informationen über diese Antwort.  
  
## Hinweise  
 Das `My.Response`\-Objekt enthält das aktuelle <xref:System.Web.HttpResponse>\-Objekt, das der Seite zugeordnet ist.  
  
 Das `My.Response`\-Objekt ist nur für [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)]\-Anwendungen verfügbar.  
  
## Beispiel  
 Im folgenden Beispiel wird die Headerauflistung vom `My.Request`\-Objekt abgerufen, und das `My.Response`\-Objekt wird zum Schreiben der Auflistung in die ASP.NET\-Seite verwendet.  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## Siehe auch  
 <xref:System.Web.HttpResponse>   
 [My.Request Object](../../../visual-basic/language-reference/objects/my-request-object.md)