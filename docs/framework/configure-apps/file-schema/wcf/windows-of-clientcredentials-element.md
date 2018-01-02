---
title: '&lt;windows&gt; des &lt;clientCredentials&gt;-Elements'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6687f93be26dedcb34f08770708c072742fdd4de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltwindowsgt-of-ltclientcredentialsgt-element"></a>&lt;windows&gt; des &lt;clientCredentials&gt;-Elements
Gibt die Einstellungen für Windows-Anmeldeinformationen an, die zum Darstellen des Clients verwendet werden.  
  
 \<System. ServiceModel >  
\<Verhalten >  
\<EndpointBehaviors >  
\<Verhalten >  
\<ClientCredentials >  
\<Windows >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<windows   
    allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"  
        allowNtlm="Boolean"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|Legt die Identitätswechseleinstellungen fest, die der Client an den Server weitergibt. Der Identitätswechselmodus, den der Client auswählt, wird nicht auf dem Server durchgesetzt. Folgende Werte sind gültig:<br /><br /> -ID: Der Server kann die Identitäts- und Berechtigungsinformationen des Clients abrufen, aber den Client nicht imitieren.<br />-Impersonation: Der Server kann der Clientsicherheitskontext auf dem lokalen System imitieren.<br />-Delegation: Der Server kann Sie in der Sicherheitskontext des Clients auf Remotesystemen imitieren.<br />– Anonymous: Der Server kann nicht imitieren oder identifizieren den Client.<br />-"None": Eine Ebene des Identitätswechsels ist nicht zugewiesen.<br /><br /> Die Standardeinstellung ist Identification. Dieses Attribut ist vom Typ <xref:System.Security.Principal.TokenImpersonationLevel>.|  
|`allowNtlm`|Durch das Festlegen dieser Eigenschaft auf `true` kann die Authentifizierung auf NTLM herabgestuft werden, wenn Kerberos nicht verfügbar ist.<br /><br /> Das Festlegen dieser Eigenschaft auf `false` führt dazu, dass [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] nach dem Best-Effort-Prinzip eine Ausnahme auslöst, wenn NTLM verwendet wird. Durch das Festlegen dieser Eigenschaft auf `false` wird unter Umständen nicht verhindert, dass NTLM-Anmeldeinformationen über die Verbindung gesendet werden.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ClientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.WindowsClientElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>  
 <xref:System.ServiceModel.Security.WindowsClientCredential>  
 [Sichern von Clients](../../../../../docs/framework/wcf/securing-clients.md)  
 [Arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
