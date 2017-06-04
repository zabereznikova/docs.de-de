---
title: "Troubleshooting: Debugging Windows Services | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "debugging Windows Service applications"
  - "debugging [Visual Studio], Windows services"
  - "troubleshooting service applications"
  - "services, troubleshooting"
  - "troubleshooting debugging, Windows Services"
  - "Windows Service applications, debugging"
  - "services, debugging"
  - "Windows Service applications, troubleshooting"
ms.assetid: cf859d4c-f04c-4cb7-81e3-bc7de8bea190
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 8
---
# Troubleshooting: Debugging Windows Services
Beim Debuggen einer Windows\-Dienstanwendung werden zwischen dem Dienst und dem **Dienst\-Manager** von Windows Daten ausgetauscht.  Der Dienst wird vom **Dienst\-Manager** gestartet, indem die <xref:System.ServiceProcess.ServiceBase.OnStart%2A>\-Methode aufgerufen wird. Danach wird 30 Sekunden lang gewartet, bis die <xref:System.ServiceProcess.ServiceBase.OnStart%2A>\-Methode antwortet.  Wenn von der Methode in dieser Zeit nicht zurückgekehrt wird, zeigt der Manager einen Fehler an, dass der Dienst nicht gestartet werden kann.  
  
 Beim Debuggen der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>\-Methode entsprechend der Beschreibung in [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md) müssen Sie den genannten Zeitraum von 30 Sekunden beachten.  Wenn in der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>\-Methode ein Haltepunkt gesetzt wird und sie nicht in 30 Sekunden durchlaufen wird, wird der Dienst vom Manager nicht gestartet.  
  
## Siehe auch  
 [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)   
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)