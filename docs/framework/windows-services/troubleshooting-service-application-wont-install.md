---
title: "Troubleshooting: Service Application Won&#39;t Install | Microsoft Docs"
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
  - "troubleshooting service applications"
  - "services, troubleshooting"
  - "services, debugging"
  - "Windows NT services, troubleshooting"
  - "troubleshooting NT services"
  - "Windows Service applications, troubleshooting"
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 8
---
# Troubleshooting: Service Application Won&#39;t Install
Wenn die Dienstanwendung nicht korrekt installiert werden kann, überprüfen Sie die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>\-Eigenschaft. Stellen Sie sicher, dass ihr Wert für die Dienstklasse mit dem übereinstimmt, der im Installer für diesen Dienst angezeigt wird.  Der Wert in beiden Instanzen muss übereinstimmen, damit der Dienst richtig installiert wird.  
  
> [!NOTE]
>  Feedback zum Installationsvorgang erhalten Sie auch, indem Sie die Installationsprotokolle überprüfen.  
  
 Außerdem muss überprüft werden, ob bereits ein weiterer Dienst mit dem gleichen Namen installiert wurde.  Die Namen von Diensten müssen eindeutig sein, damit sie installiert werden können.  
  
## Siehe auch  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)