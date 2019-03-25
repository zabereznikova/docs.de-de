---
title: <httpTransport>
ms.date: 03/30/2017
ms.assetid: 8b30c065-b32a-4fa3-8eb4-5537a9c6b897
ms.openlocfilehash: f529cd5290c74999a010381fadfb94ea9a4d515e
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58408937"
---
# <a name="httptransport"></a>\<httpTransport>
Gibt einen HTTP-Transport zur Übertragung von SOAP-Nachrichten für eine benutzerdefinierte Bindung an.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<httpTransport>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<httpTransport allowCookies="Boolean"
               authenticationScheme="Digest/Negotiate/Ntlm/Basic/Anonymous"
               bypassProxyOnLocal="Boolean"
               hostnameComparisonMode="StrongWildcard/Exact/WeakWildcard"
               keepAliveEnabled="Boolean"
               maxBufferSize="Integer"
               proxyAddress="Uri"
               proxyAuthenticationScheme="None/Digest/Negotiate/Ntlm/Basic/Anonymous"
               realm="String"
               transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"
               unsafeConnectionNtlmAuthentication="Boolean"
               useDefaultWebProxy="Boolean" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|allowCookies|Ein boolescher Wert, der angibt, ob der Client Cookies akzeptiert und bei zukünftigen Anforderungen propagiert. Die Standardeinstellung ist `false`.<br /><br /> Sie können dieses Attribut verwenden, wenn Sie mit ASMX-Webdiensten interagieren, die Cookies verwenden. Auf diese Weise können Sie sicherstellen, dass die vom Server zurückgegebenen Cookies automatisch bei allen zukünftigen Clientanforderungen für diesen Dienst kopiert werden.|  
|authenticationScheme|Gibt das Protokoll an, mit dem Clientanforderungen authentifiziert werden, die von einem HTTP-Listener verarbeitet werden. Folgende Werte sind gültig:<br /><br /> -Digest: Gibt die Digestauthentifizierung an.<br />– Negotiate: Mit dem Client das Authentifizierungsschema handelt. Wenn sowohl Client als auch Server Kerberos unterstützen, wird dieses Schema verwendet. Andernfalls wird NTLM verwendet.<br />-Ntlm: Gibt die NTLM-Authentifizierung an.<br />-   Basic: Gibt die Standardauthentifizierung an.<br />– Anonymous: Gibt die anonyme Authentifizierung an.<br /><br /> Die Standardeinstellung ist Anonymous. Dieses Attribut ist vom Typ <xref:System.Net.AuthenticationSchemes>. Dieses Attribut kann nur einmal festgelegt werden.|  
|bypassProxyOnLocal|Ein boolescher Wert, der angibt, ob der Proxyserver bei lokalen Adressen umgangen werden soll. Die Standardeinstellung ist `false`.<br /><br /> Eine lokale Adresse ist eine, die sich im lokalen LAN oder Intranet befindet.<br /><br /> Windows Communication Foundation (WCF) ignoriert immer den Proxy, wenn die Dienstadresse mit beginnt `http://localhost`.<br /><br /> Sie sollten den Hostnamen anstatt localhost verwenden, wenn die Clients bei der Kommunikation mit Diensten auf demselben Computer einen Proxy nutzen sollen.|  
|hostnameComparisonMode|Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren. Folgende Werte sind gültig:<br /><br /> -StrongWildcard: ("+") entspricht allen möglichen Hostnamen im Kontext der angegebenen Schemas, Anschlusses und relativen URI.<br />-Genauer: keine Platzhalter<br />-WeakWildcard: ("\*") entspricht allen möglichen Hostnamen im Kontext des angegebenen Schemas, Anschlusses und URIS, die nicht explizit zugeordnet wurde oder durch den StrongWildcard-Mechanismus.<br /><br /> Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostNameComparisonMode>. Die Standardeinstellung ist <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>.|  
|keepAliveEnabled|Ein boolescher Wert, der angibt, ob eine permanente Verbindung mit der Internetressource hergestellt werden soll.|  
|maxBufferSize|Eine positive ganze Zahl, die die maximale Puffergröße angibt. Der Standardwert ist 524288.|  
|proxyAddress|Ein URI, der die Adresse des HTTP-Proxys angibt. Wenn `useSystemWebProxy``true` ist, muss diese Einstellung `null` lauten. Die Standardeinstellung ist `null`.|  
|proxyAuthenticationScheme|Gibt das Protokoll an, mit dem Clientanforderungen authentifiziert werden, die von einem HTTP-Proxy verarbeitet werden. Folgende Werte sind gültig:<br /><br /> – None: Es wird keine Authentifizierung ausgeführt.<br />-Digest: Gibt die Digestauthentifizierung an.<br />– Negotiate: Mit dem Client das Authentifizierungsschema handelt. Wenn sowohl Client als auch Server Kerberos unterstützen, wird dieses Schema verwendet. Andernfalls wird NTLM verwendet.<br />-Ntlm: Gibt die NTLM-Authentifizierung an.<br />-   Basic: Gibt die Standardauthentifizierung an.<br />– Anonymous: Gibt die anonyme Authentifizierung an.<br /><br /> Die Standardeinstellung ist Anonymous. Dieses Attribut ist vom Typ <xref:System.Net.AuthenticationSchemes>. Beachten Sie, dass <xref:System.Net.AuthenticationSchemes.IntegratedWindowsAuthentication?displayProperty=nameWithType> wird nicht unterstützt.|  
|realm|Eine Zeichenfolge, die den auf dem Proxy/Server zu verwendenden Bereich angibt. Der Standardwert ist eine leere Zeichenfolge.<br /><br /> Server verwenden Bereiche, um geschützte Ressourcen zu partitionieren. Jede Partition kann ihr eigenes Authentifizierungsschema und/oder ihre eigene Autorisierungsdatenbank aufweisen. Bereiche werden nur für die Standard- und Hashwertauthentifizierung verwendet. Nach der erfolgreichen Authentifizierung eines Clients ist die Authentifizierung für alle Ressourcen in einem bestimmten Bereich gültig. Eine ausführliche Beschreibung der Bereiche finden Sie unter RFC 2617 unter der [IETF-Website](https://www.ietf.org).|  
|transferMode|Gibt an, ob Nachrichten bei einer Anforderung oder Antwort gepuffert oder per Stream übertragen werden. Folgende Werte sind gültig:<br /><br /> -Buffered: Die Anforderungs- und Antwortnachrichten werden gepuffert.<br />-Streaming: Die Anforderungs- und Antwortnachrichten werden per Stream übertragen.<br />-StreamedRequest: Die Anforderungsnachricht wird per Stream übertragen, und die Antwortnachricht wird gepuffert.<br />-StreamedResponse: Die Anforderungsnachricht wird gepuffert, und die Antwortnachricht wird per Stream übertragen.<br /><br /> Der Standardwert ist Buffered. Dieses Attribut ist vom Typ <xref:System.ServiceModel.TransferMode>.|  
|unsafeConnectionNtlmAuthentication|Ein boolescher Wert, der angibt, ob die Freigabe nicht sicherer Verbindungen auf dem Server aktiviert ist. Die Standardeinstellung ist `false`. Wenn aktiviert, wird NTLM-Authentifizierung einmal auf jeder TCP-Verbindung ausgeführt.|  
|useDefaultWebProxy|Ein boolescher Wert, der angibt, ob die Proxyeinstellungen auf dem Computer anstatt der benutzerspezifischen Einstellungen verwendet werden sollen. Die Standardeinstellung ist `true`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## <a name="remarks"></a>Hinweise  
 Das `httpTransport`-Element stellt den Startpunkt für das Erstellen einer benutzerdefinierten Bindung dar, die das HTTP-Transportprotokoll implementiert. HTTP stellt die primäre Übertragungsweise für den Datenaustausch dar. Dieser Transport wird von der Windows Communication Foundation (WCF) um sicherzustellen, dass Interoperabilität mit anderen nicht - WCF-Dienste unterstützt.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ServiceModel.Configuration.HttpTransportElement>
- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Transportprotokolle](../../../../../docs/framework/wcf/feature-details/transports.md)
- [Auswählen eines Transports](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [Bindungen](../../../../../docs/framework/wcf/bindings.md)
- [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
