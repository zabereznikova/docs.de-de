---
title: "WS-MetadataExchange-Bindungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# WS-MetadataExchange-Bindungen
In diesem Thema wird beschrieben, wie die Standardmetadatenaustausch\-Bindungen für verschiedene Transporte erstellt werden.  
  
## Die Standardbindungen  
  
|Standardbindungsname|Wie die Bindung erstellt wird|  
|--------------------------|-----------------------------------|  
|MexHttpBinding|Eine <xref:System.ServiceModel.WSHttpBinding> mit deaktivierter Sicherheit auf Transportebene.|  
|MexHttpsBinding|Eine <xref:System.ServiceModel.WSHttpBinding>, die Sicherheit auf Transportebene unterstützt.|  
|MexNamedPipeBinding|Eine <xref:System.ServiceModel.Channels.CustomBinding> mit einem <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>, das die Standardwerte verwendet.|  
|MexTcpBinding|Eine <xref:System.ServiceModel.Channels.CustomBinding> mit einem <xref:System.ServiceModel.Channels.TcpTransportBindingElement>, das die Standardwerte verwendet.|