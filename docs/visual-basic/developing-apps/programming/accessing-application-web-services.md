---
title: "Accessing Application Web Services (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Web services, My.WebServices object"
  - "My.WebServices object"
  - "applications [Visual Basic], Web services"
ms.assetid: 8ad5405b-e771-42b1-82d3-ce97af2cea9e
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Accessing Application Web Services (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Das `My.WebServices`\-Objekt stellt eine Instanz von jedem Webdienst bereit, auf den im aktuellen Projekt verwiesen wird.  Jede Instanz wird bei Bedarf instanziiert.  Sie können auf diese Webdienste über die Eigenschaften des `My.WebServices`\-Objekts zugreifen.  Der Name der Eigenschaft ist identisch mit dem Namen des Webdienstes, auf den die Eigenschaft zugreift.  Jede Klasse, die von <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> erbt, ist ein Webdienst.  
  
## Aufgaben  
 In der folgenden Tabelle werden Möglichkeiten für den Zugriff auf Webdienste aufgelistet, auf auf die aus einer Anwendung verwiesen wird.  
  
|||  
|-|-|  
|To|Siehe|  
|Aufrufen eines Webdienstes|[My.WebServices Object](../../../visual-basic/language-reference/objects/my-webservices-object.md)|  
|Asynchrones Aufrufen eines Webdienstes und Behandeln eines Ereignisses nach dessen Abschluss|[How to: Call a Web Service Asynchronously](../../../visual-basic/developing-apps/programming/how-to-call-a-web-service-asynchronously.md)|  
  
## Siehe auch  
 [My.WebServices Object](../../../visual-basic/language-reference/objects/my-webservices-object.md)