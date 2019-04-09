---
title: <httpsTransport>
ms.date: 03/30/2017
ms.assetid: f6ed4bc0-7e38-4348-9259-30bf61eb9435
ms.openlocfilehash: c7e4dc540458bbfb69318d2f14cfa9776f444c55
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172821"
---
# <a name="httpstransport"></a>\<httpsTransport>
Gibt einen HTTP-Transport zur Übertragung von SOAP-Nachrichten für eine benutzerdefinierte Bindung an.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<httpsTransport>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<httpsTransport allowCookies="Boolean"
                authenticationScheme="Digest/Negotiate/Ntlm/Basic/Anonymous"
                bypassProxyOnLocal="Boolean"
                hostnameComparisonMode="StrongWildcard/Exact/WeakWildcard"
                manualAddressing="Boolean"
                maxBufferPoolSize="Integer"
                maxBufferSize="Integer"
                maxReceivedMessageSize="Integer"
                proxyAddress="Uri"
                proxyAuthenticationScheme="None/Digest/Negotiate/Ntlm/Basic/Anonymous"
                realm="String"
                requireClientCertificate="Boolean"
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
|hostnameComparisonMode|Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren. Folgende Werte sind gültig:<br /><br /> -StrongWildcard: ("+") entspricht allen möglichen Hostnamen im Kontext der angegebenen Schemas, Anschlusses und relativen URI.<br />-Genauer: keine Platzhalter<br />-WeakWildcard: ("\*") entspricht allen möglichen Hostnamen im Kontext des angegebenen Schemas, Anschlusses und URIS, die nicht explizit zugeordnet wurde oder durch den StrongWildcard-Mechanismus.<br /><br /> Die Standardeinstellung ist StrongWildcard. Dieses Attribut ist vom Typ `System.ServiceModel.HostnameComparison`.|  
|manualAddressing|Ein boolescher Wert , der es dem Benutzer ermöglicht, die Kontrolle über die Nachrichtenadressierung zu übernehmen. Diese Eigenschaft wird i.&amp;#160;d.&amp;#160;R. in Routerumgebungen verwendet, wenn das Ziel der Nachricht von der Anwendung bestimmt wird.<br /><br /> Wenn diese Eigenschaft auf `true` festgelegt ist, wird vom Kanal angenommen, dass die Nachricht bereits adressiert wurde, und es werden ihr keine weiteren Informationen hinzugefügt. Der Benutzer kann dann jede Nachricht einzeln adressieren.<br /><br /> Wenn als Wert `false` festgelegt wurde, erstellt der Standard-Windows Communication Foundation (WCF)-Adressiermechanismus automatisch Adressen für alle Nachrichten.<br /><br /> Die Standardeinstellung ist `false`.|  
|maxBufferPoolSize|Eine positive ganze Zahl, die die maximale Pufferpoolgröße angibt. Der Standard ist 524288.<br /><br /> Viele Bereiche von WCF verwenden Puffer. Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer. Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen. So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.|  
|maxBufferSize|Eine positive ganze Zahl, die die maximale Puffergröße angibt. Der Standardwert ist 524288.|  
|maxReceivedMessageSize|Eine positive ganze Zahl, die die maximal zulässige Nachrichtengröße, die empfangen werden kann, angibt. Der Standard ist 65536.|  
|proxyAddress|Ein URI, der die Adresse des HTTP-Proxys angibt. Wenn `useSystemWebProxy``true` ist, muss diese Einstellung `null` lauten. Die Standardeinstellung ist `null`.|  
|proxyAuthenticationScheme|Gibt das Protokoll an, mit dem Clientanforderungen authentifiziert werden, die von einem HTTP-Proxy verarbeitet werden. Folgende Werte sind gültig:<br /><br /> – None: Es wird keine Authentifizierung ausgeführt.<br />-Digest: Gibt die Digestauthentifizierung an.<br />– Negotiate: Mit dem Client das Authentifizierungsschema handelt. Wenn sowohl Client als auch Server Kerberos unterstützen, wird dieses Schema verwendet. Andernfalls wird NTLM verwendet.<br />-Ntlm: Gibt die NTLM-Authentifizierung an.<br />-   Basic: Gibt die Standardauthentifizierung an.<br />– Anonymous: Gibt die anonyme Authentifizierung an.<br /><br /> Die Standardeinstellung ist Anonymous. Dieses Attribut ist vom Typ <xref:System.Net.AuthenticationSchemes>. Beachten Sie, dass <xref:System.Net.AuthenticationSchemes.IntegratedWindowsAuthentication?displayProperty=nameWithType> wird nicht unterstützt.|  
|realm|Eine Zeichenfolge, die den auf dem Proxy/Server zu verwendenden Bereich angibt. Der Standardwert ist eine leere Zeichenfolge.<br /><br /> Server verwenden Bereiche, um geschützte Ressourcen zu partitionieren. Jede Partition kann ihr eigenes Authentifizierungsschema und/oder ihre eigene Autorisierungsdatenbank aufweisen. Bereiche werden nur für die Standard- und Hashwertauthentifizierung verwendet. Nach der erfolgreichen Authentifizierung eines Clients ist die Authentifizierung für alle Ressourcen in einem bestimmten Bereich gültig. Eine ausführliche Beschreibung der Bereiche finden Sie unter RFC 2617 unter der [IETF-Website](https://www.ietf.org).|  
|requireClientCertificate|Ein boolescher Wert, der angibt, ob der Server erfordert, dass der Client ein Clientzertifikat als Teil des HTTPS-Handshakes bereitstellt. Die Standardeinstellung ist `false`.|  
|transferMode|Gibt an, ob Nachrichten bei einer Anforderung oder Antwort gepuffert oder per Stream übertragen werden. Folgende Werte sind gültig:<br /><br /> -Buffered: Die Anforderungs- und Antwortnachrichten werden gepuffert.<br />-Streaming: Die Anforderungs- und Antwortnachrichten werden per Stream übertragen.<br />-StreamedRequest: Die Anforderungsnachricht wird per Stream übertragen, und die Antwortnachricht wird gepuffert.<br />-StreamedResponse: Die Anforderungsnachricht wird gepuffert, und die Antwortnachricht wird per Stream übertragen.<br /><br /> Der Standardwert ist Buffered. Dieses Attribut ist vom Typ <xref:System.ServiceModel.TransferMode>.|  
|unsafeConnectionNtlmAuthentication|Ein boolescher Wert, der angibt, ob die Freigabe nicht sicherer Verbindungen auf dem Server aktiviert ist. Die Standardeinstellung ist `false`. Wenn aktiviert, wird NTLM-Authentifizierung einmal auf jeder TCP-Verbindung ausgeführt.|  
|useDefaultWebProxy|Ein boolescher Wert, der angibt, ob die Proxyeinstellungen auf dem Computer anstatt der benutzerspezifischen Einstellungen verwendet werden sollen. Die Standardeinstellung ist `true`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## <a name="remarks"></a>Hinweise  
 Das `httpsTransport`-Element stellt den Startpunkt für das Erstellen einer benutzerdefinierten Bindung dar, die das HTTPS-Übertragungsprotokoll implementiert. HTTPS stellt die primäre Übertragungsweise für einen sicheren Datenaustausch dar. HTTPS wird von der Windows Communication Foundation (WCF) um sicherzustellen, dass Interoperabilität mit anderen Web-Dienste unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.HttpsTransportElement>
- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Transportprotokolle](../../../../../docs/framework/wcf/feature-details/transports.md)
- [Wählen eines Transports](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [Bindungen](../../../../../docs/framework/wcf/bindings.md)
- [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
