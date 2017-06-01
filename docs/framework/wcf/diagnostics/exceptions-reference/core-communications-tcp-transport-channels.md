---
title: "Kernkommunikationen: TCP-Transportkan&#228;le | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d5cd057f-faec-4e21-ae0e-18bbc22bcfb1
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Kernkommunikationen: TCP-Transportkan&#228;le
In diesem Thema sind alle von den TCP\-Transportkanälen generierten Ausnahmen aufgeführt.  
  
## Ausnahmeliste  
  
|Ressourcencode|Ressourcenzeichenfolge|  
|--------------------|----------------------------|  
|SocketCloseReadTimeout|Der Remoteendpunkt des angegebenen Sockets hat auf eine Anforderung zum Schließen nicht innerhalb des zugewiesenen Zeitlimits geantwortet.  Möglicherweise ruft der Remoteendpunkt nach dem Empfang des EOF\-Signals \(NULL\) vom Receive\-Vorgang nicht Close auf.  Die für diesen Vorgang zugewiesene Zeit war möglicherweise ein Teil eines längeren Timeouts.|