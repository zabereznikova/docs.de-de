---
title: <httpDigest>-Element
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 328411a429cd42927a190c6805a1f5e2b3555ea1
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448451"
---
# <a name="httpdigest-element"></a>\<httpdigest-> Element
Gibt Anmeldeinformationen vom Typ Digest an, die bei der Authentifizierung des Clients bei einem Dienst verwendet werden.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhalten**](behaviors.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**endpointverhaltensweisen**](endpointbehaviors.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**Verhalten >** ](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Clientanmelde**](clientcredentials.md) Informationen >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<httpdigest >**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<httpDigest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`impersonationLevel`|Legt die Identitätswechseleinstellungen fest, die der Client an den Server weitergibt. Der Identitätswechselmodus, den der Client auswählt, wird nicht auf dem Server durchgesetzt. Gültige Werte sind:<br /><br /> -Identifikation: der Server kann die Identität und die Berechtigungen des Clients erhalten, kann jedoch nicht die Identität des Clients annehmen.<br />-Identitätswechsel: der Server kann den Sicherheitskontext des Clients auf dem lokalen System imitieren.<br />-Delegierung: der Server kann den Sicherheitskontext des Clients auf Remote Systemen imitieren.<br />-Anonymous: der Server kann den Client nicht annehmen oder ihn identifizieren.<br />-None: Es wurde keine Identitätswechsel Ebene zugewiesen.<br /><br /> Die Standardeinstellung ist Identification. Dieses Attribut ist vom Typ <xref:System.Security.Principal.TokenImpersonationLevel>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Clientanmelde Informationen >](clientcredentials.md)|Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Digest ist ein Hash, der mit einem Algorithmus und einer Reihe von Eingaben ermittelt wird. Der Authentifizierer und der Authentifizierte verständigen sich über einen Algorithmus und tauschen die für die Eingabe verwendeten Daten aus. Der Client kann den Hash berechnen und an den Dienst senden. Der Dienst berechnet den Hash ebenfalls und vergleicht die Werte. Bei einer Übereinstimmung ist die Überprüfung des Clients erfolgreich.  
  
 Diese Funktion muss mit Active Directory unter Windows und unter IIS (Internet Information Services) aktiviert werden. Weitere Informationen finden Sie unter [Digest-Authentifizierung in IIS 6,0](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [Sicherheitsverhalten](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Sichern von Clients](../../../wcf/securing-clients.md)
- [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md)
- [Securing Services and Clients](../../../wcf/feature-details/securing-services-and-clients.md)
