---
title: "System.ServiceModel.MessageClosedAgain | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.MessageClosedAgain
System.ServiceModel.MessageClosedAgain  
  
## Beschreibung  
 Eine Nachricht wurde wieder geschlossen.  
  
 Eine Nachricht sollte nur einmal geschlossen werden.Wird diese Ablaufverfolgung in Benutzererweiterungscode ausgegeben, weist dies darauf hin, dass der Benutzererweiterungscode im Begriff ist, eine Nachricht zu schließen, die bereits geschlossen wurde.Wird diese Ablaufverfolgung in Produktcode ausgegeben, weist dies darauf hin, dass der Benutzererweiterungscode eine Nachricht möglicherweise zu früh schließt.  
  
## Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)