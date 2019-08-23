---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: c62f29c53d807cab397ff09c6163d924a71ea319
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926600"
---
# <a name="allowaccounts"></a>\<allowAccounts>
Enthält eine Auflistung von Konfigurationselementen, die Benutzerkonten für Prozesse angeben, die Windows Communication Foundation (WCF)-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.  
  
 \<system.serviceModel.activation>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|[\<add>](add-of-allowaccounts.md)|Fügt ein Benutzerkonto für Prozesse hinzu, die WCF-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|["net. Pipe" > oder "net. TCP" > \<](net-pipe.md) [ \<](net-tcp.md)|Gibt die Konfigurationseinstellungen für den Freigabedienst Net Pipe oder TCP an.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
