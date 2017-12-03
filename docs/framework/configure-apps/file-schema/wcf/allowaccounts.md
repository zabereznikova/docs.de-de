---
title: '&lt;allowAccounts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 20d411fbe052940fd8fc752e74d012f28ffa441b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltallowaccountsgt"></a>&lt;allowAccounts&gt;
Enthält eine Auflistung von Konfigurationselementen, die Benutzerkonten für Prozesse angeben, die [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Dienste hosten und Verbindungszugriff auf den Freigabedienst haben.  
  
 \<system.serviceModel.activation >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|Fügt ein Benutzerkonto für Prozesse hinzu, die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Dienste hosten und Verbindungszugriff auf den Freigabedienst haben.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<NET.Pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) oder [ \<net.tcp >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)|Gibt die Konfigurationseinstellungen für den Freigabedienst Net Pipe oder TCP an.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
