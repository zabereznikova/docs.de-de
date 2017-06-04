---
title: "3552 - MaxPendingMessagesPerChannelExceeded | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 3552 - MaxPendingMessagesPerChannelExceeded
## Eigenschaften  
  
|||  
|-|-|  
|ID|3552|  
|Schlüsselwörter|Kontingent, WFServices|  
|Ebene|Warnung|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Gibt an, dass die Drosselungsgrenze 'MaxPendingMessagesPerChannel' erreicht wurde.  
  
## Meldung  
 Die Drosselungsgrenze 'MaxPendingMessagesPerChannel' von '%1' wurde erreicht.  Passen Sie die MaxPendingMessagesPerChannel\-Eigenschaft von BufferedReceiveServiceBehavior an, um diese Grenze zu erhöhen.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|Limit|xs:string|Die Drosselungsgrenze 'MaxPendingMessagesPerChannel'.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|