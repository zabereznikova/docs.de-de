---
title: '&lt;httpDigest&gt;-Element'
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 2211c593090d697ae07350fcf7ac491b9d23e2d0
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150140"
---
# <a name="lthttpdigestgt-element"></a>&lt;httpDigest&gt;-Element
Gibt Anmeldeinformationen vom Typ Hashwert an, die bei der Authentifizierung des Clients bei einem Dienst verwendet werden.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<Verhalten >  
\<clientCredentials>  
\<HttpDigest >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`impersonationLevel`|Legt die Identitätswechseleinstellungen fest, die der Client an den Server weitergibt. Der Identitätswechselmodus, den der Client auswählt, wird nicht auf dem Server durchgesetzt. Folgende Werte sind gültig:<br /><br /> -ID: Der Server kann die Identitäts- und Berechtigungsinformationen des Clients abrufen, aber den Client nicht imitieren.<br />-Identitätswechsel: Der Server kann der Clientsicherheitskontext auf dem lokalen System imitieren.<br />-Delegierung: Der Server kann der Clientsicherheitskontext auf Remotesystemen imitieren.<br />– Anonymous: Der Server kann nicht imitieren oder identifizieren den Client.<br />– None: Ebene des Identitätswechsels wird nicht zugewiesen.<br /><br /> Die Standardeinstellung ist Identification. Dieses Attribut ist vom Typ <xref:System.Security.Principal.TokenImpersonationLevel>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Hashwert ist ein Hash, der mit einem Algorithmus und einer Reihe von Eingaben ermittelt wird. Der Authentifizierer und der Authentifizierte verständigen sich über einen Algorithmus und tauschen die für die Eingabe verwendeten Daten aus. Der Client kann den Hash berechnen und an den Dienst senden. Der Dienst berechnet den Hash ebenfalls und vergleicht die Werte. Bei einer Übereinstimmung ist die Überprüfung des Clients erfolgreich.  
  
 Diese Funktion muss mit Active Directory unter Windows und unter IIS (Internet Information Services) aktiviert werden. Weitere Informationen finden Sie unter [Digestauthentifizierung in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>  
 <xref:System.ServiceModel.Configuration.HttpDigestClientElement>  
 <xref:System.ServiceModel.Security.HttpDigestClientCredential>  
 [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Sichern von Clients](../../../../../docs/framework/wcf/securing-clients.md)  
 [Arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
