---
title: „WSTrustChannelFactory“ und „WSTrustChannel“
ms.date: 03/30/2017
ms.assetid: 96cec467-e963-4132-b18b-7d0b3a2e979f
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 3fabd7e3cad76e17061751d0fe0bb4ae06bf6fb6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33410454"
---
# <a name="wstrustchannelfactory-and-wstrustchannel"></a>„WSTrustChannelFactory“ und „WSTrustChannel“
Wenn Sie mit Windows Communication Foundation (WCF) bereits vertraut sind, wissen Sie, dass ein WCF-Client bereits verbundfähig ist. Wird ein WCF-Client mit <xref:System.ServiceModel.WSFederationHttpBinding> oder einer ähnlichen benutzerdefinierten Bindung konfiguriert, können Sie die Verbundauthentifizierung für einen Dienst aktivieren.  
  
 WCF erhält das vom Sicherheitstokendienst (STS) im Hintergrund ausgegebene Token, und es wird dazu verwendet den Dienst zu authentifizieren. Die Haupteinschränkung bei dieser Vorgehensweise besteht darin, dass keine Sichtbarkeit in die Kommunikation des Clients mit dem Server besteht. WCF generiert das Anforderungssicherheitstoken (RST) zum Sicherheitstokendienst auf Grundlage des Parameters des ausgestellten Tokens für die Bindung automatisch. Das bedeutet, dass der Client die RST-Parameter pro Anforderung nicht unterscheiden kann, die Antwort des Anforderungssicherheitstokens (RSTR) nicht untersuchen kann, um Informationen wie etwa Anzeigenansprüche abzurufen, oder das Token nicht für die zukünftige Verwendung zwischenspeichern kann.  
  
 Derzeit ist der WCF-Client für grundlegende Verbundszenarien geeignet. Allerdings erfordert eine der wichtigsten Szenarien, die von Windows Foundation (WIF) unterstützt wird, Kontrolle über das Anforderungssicherheitstoken auf einer Ebene, die WCF nicht problemlos zulässt. Daher werden bei WIF Funktionen hinzugefügt, mit denen Sie die Kommunikation mit dem Sicherheitstokendienst besser steuern können.  
  
 WIF unterstützt die folgenden Verbundszenarien:  
  
-   Verwenden eines WCF-Clients ohne WIF-Abhängigkeiten zu einem Verbunddienst zu authentifizieren  
  
-   Aktivieren von WIF auf einem WCF-Client, um ein ActAs- oder ein OnBehalfOf-Element in das Anforderungssicherheitstoken im Sicherheitstokendienst einzufügen  
  
-   Verwenden nur von WIF, um ein Token vom Sicherheitstokendienst abzurufen und es dann einem WCF-Client zu ermöglichen, sich mit diesem Token zu authentifizieren. Weitere Informationen finden Sie unter dem Beispiel [ClaimsAwareWebService](http://go.microsoft.com/fwlink/?LinkID=248406).  
  
 Das erste Szenario ist selbsterklärend: Vorhandene WCF-Clients funktionieren weiterhin mit WIF-Seiten und Sicherheitstokendiensten. In diesem Thema werden die verbleibenden beiden Szenarien besprochen.  
  
## <a name="enhancing-an-existing-wcf-client-with-actas--onbehalfof"></a>Optimieren eines vorhandenen WCF-Clients mit ActAs/OnBehalfOf  
 In einem typischen Identitätsdelegierungsszenario ruft ein Client einen Dienst der mittleren Ebene auf, der dann einen Back-End-Dienst aufruft. Der Dienst der mittleren Ebene dient als oder im Namen vom Client.  
  
> [!TIP]
>  Worin besteht der Unterschied zwischen "ActAs" und "OnBehalfOf"?  
>   
>  Vom WS-Trust-Procotol-Standpunkt aus betrachtet:  
>   
>  1.  Ein ActAs-RST-Element gibt an, dass der Anforderer ein Token wünscht, das Ansprüche zu zwei verschiedenen Entitäten enthält: den Anforderer und eine externe Entität, die vom Token im ActAs-Element dargestellt wird.  
> 2.  Ein OnBehalfOf-RST-Element gibt an, dass der Anforderer ein Token wünscht, das nur Ansprüche zu einer Entität enthält: die externe Entität, die vom Token im OnBehalfOf-Element dargestellt wird.  
>   
>  Die ActAs-Funktion wird üblicherweise in Szenarien verwendet, die zusammengesetzte Delegierung erfordern, wobei der Endempfänger des ausgestellten Tokens die gesamte Delegierungskette überprüfen und nicht nur den Client, sondern alle Zwischenstufen, finden kann. Dadurch kann die Zugriffssteuerung, Überwachung und andere verwandte Aktivitäten auf Grundlage der gesamten Identitätsdelegierungskette ausgeführt werden. Die ActAs-Funktion wird üblicherweise in Systemen mit mehreren Ebenen verwendet, um Informationen über Identitäten zu authentifizieren und zwischen den Ebenen zu übergeben, ohne diese Informationen an die Anwendung/Geschäftslogikebene übergeben zu müssen.  
>   
>  Die OnBehalfOf-Funktion wird in Szenarien verwendet, in denen nur die Identität des ursprünglichen Clients wichtig ist und effektiv der Identitätsidentitätswechselfunktion gleicht, die in Windows verfügbar ist. Wenn OnBehalfOf verwendet wird, kann der Endempfänger des ausgestellten Tokens nur Ansprüche zum ursprünglichen Client sehen, und die Informationen zu Zwischenstufen werden nicht beibehalten. Ein gängiges Muster, bei dem die OnBehalfOf-Funktion verwendet wird, ist das Proxymuster, in dem vom Client nicht direkt auf den Sicherheitstokendienst zugegriffen werden kann, sondern stattdessen durch ein Proxygateway kommuniziert wird. Das Proxygateway authentifiziert den Aufrufer und gibt Informationen zum Aufrufen an das OnBehalfOf-Element der RST-Meldung weiter, die dann zur Verarbeitung an den tatsächlichen Sicherheitstokendienst gesendet wird. Das daraus resultierende Token enthält nur Ansprüche zum Client des Proxys. Dadurch wird das Proxy für den Empfänger des ausgestellten Tokens vollständig transparent. Beachten Sie, dass WIF \<wsse:SecurityTokenReference> oder \<wsa:EndpointReferences> als untergeordnetes Element von \<wst:OnBehalfOf> nicht unterstützt. Die WS-Trust-Spezifikation ermöglicht drei Methoden zur Identifizierung des ursprünglichen Anforderers (im Namen dessen der Proxy agiert). Diese lauten wie folgt:  
>   
>  -   Sicherheitstokenverweis Ein Verweis auf einen Token, entweder in der Meldung oder möglicherweise außerhalb des Bereichs abgerufen.  
> -   Endpunktverweis Wird als Schlüssel verwendet, um Daten zu suchen, wieder außerhalb des Bereichs.  
> -   Sicherheitstoken Identifiziert den ursprünglichen Anforderer direkt.  
>   
>  Von WIF werden nur Sicherheitstoken, entweder verschlüsselt oder unverschlüsselt, als direktes untergeordnetes Element von \<wst:OnBehalfOf> unterstützt.  
  
 Diese Informationen werden in einem WS-Trust-Aussteller mithilfe der ActAs- und OnBehalfOf-Tokenelemente im Anforderungssicherheitstoken übergeben.  
  
 WCF macht einen Erweiterungspunkt für die Bindung verfügbar, die das Hinzufügen von beliebigen XML-Elementen zum Anforderungssicherheitstoken ermöglicht. Da der Erweiterungspunkt allerdings an die Bindung gebunden ist, muss der Client in Szenarien, in denen die RST-Inhalte pro Aufruf variieren müssen, neu erstellt werden. Das verringert die Leistung. WIF verwendet bei der `ChannelFactory`-Klasse Erweiterungsmethoden, damit Entwickler jedes Token anfügen können, das außerhalb des Bereichs an das Anforderungssicherheitstoken abgerufen wird. Im folgenden Codebeispiel wird verdeutlicht, wie ein Token, das den Client darstellt (z. B. ein X.509, Benutzername oder ein SAML-Token), akzeptiert und an das Anforderungssicherheitstoken, der zum Aussteller gesendet wird, angefügt wird.  
  
```  
IHelloService serviceChannel = channelFactory.CreateChannelActingAs<IHelloService>( clientSamlToken );  
serviceChannel.Hello("Hi!");  
```  
  
 WIF bietet folgende Vorteile:  
  
-   Das Anforderungssicherheitstoken kann pro Kanal geändert werden. Daher muss die Kanalfactory von den Diensten der mittleren Ebene nicht für jeden Client neu erstellt werden. Das verbessert die Leistung.  
  
-   Das funktioniert mit vorhandenen WCF-Clients, was einen einfachen Upgradepfad für vorhandene WCF-Dienste der mittleren Ebene ermöglicht, mit denen Identitätsdelegierungssemantik aktiviert werden soll.  
  
 Es gibt allerdings noch keine Sichtbarkeit in die Kommunikation des Clients mit dem Sicherheitstokendienst. Das wird im dritten Szenario überprüft.  
  
## <a name="communicating-directly-with-an-issuer-and-using-the-issued-token-to-authenticate"></a>Direktes Kommunizieren mit einem Aussteller und Verwenden des ausgestellten Tokens zum Authentifizieren  
 Für einige erweiterte Szenarien reicht das Erweitern eines WCF-Client nicht aus. Entwickler, die nur WCF verwenden, nutzen in der Regel Message In/Message Out-Verträge und behandeln clientseitige Analyse der Ausstellerantwort manuell.  
  
 Bei WIF werden die Klassen <xref:System.ServiceModel.Security.WSTrustChannelFactory> und <xref:System.ServiceModel.Security.WSTrustChannel> eingeführt, um eine direkte Kommunikation zwischen Client und einem WS-Trust-Aussteller zu ermöglichen. Die Klassen <xref:System.ServiceModel.Security.WSTrustChannelFactory> und <xref:System.ServiceModel.Security.WSTrustChannel> ermöglichen den Ablauf stark typisierter RST- und RSTR-Objekte zwischen Client und Aussteller, wie im folgenden Codebeispiel verdeutlicht.  
  
```  
WSTrustChannelFactory trustChannelFactory = new WSTrustChannelFactory( stsBinding, stsAddress );  
WSTrustChannel channel = (WSTrustChannel) trustChannelFactory.CreateChannel();  
RequestSecurityToken rst = new RequestSecurityToken(RequestTypes.Issue);  
rst.AppliesTo = new EndpointAddress(serviceAddress);  
RequestSecurityTokenResponse rstr = null;  
SecurityToken token = channel.Issue(rst, out rstr);  
```  
  
 Beachten Sie, dass der `out`-Parameter auf der <xref:System.ServiceModel.Security.WSTrustChannel.Issue%2A>-Methode den Zugriff auf die Antwort des Anforderungssicherheitstokens für clientseitige Überprüfung zulässt.  
  
 Bisher wurde nur verdeutlicht, wie ein Token erhalten wird. Das Token, das vom <xref:System.ServiceModel.Security.WSTrustChannel>-Objekt zurückgegeben wird, ist ein `GenericXmlSecurityToken`-Element, in dem alle Informationen enthalten sind, die für die Authentifizierung bei einer Seite erforderlich ist. Im folgenden Codebeispiel wird die Verwendung dieses Tokens veranschaulicht.  
  
```  
IHelloService serviceChannel = channelFactory.CreateChannelWithIssuedToken<IHelloService>( token ); serviceChannel.Hello("Hi!");  
```  
  
 Die <xref:System.ServiceModel.ChannelFactory%601.CreateChannelWithIssuedToken%2A>-Erweiterungsmethode auf dem `ChannelFactory`-Objekt gibt bei WIF an, dass Sie ein Token außerhalb des Bereichs abgerufen wurde, und dass der normale WCF-Aufruf zum Aussteller beendet und stattdessen das Token verwendet werden sollte, das zum Authentifizieren der vertrauenden Seite abgerufen wurde. Dies hat folgende Vorteile:  
  
-   Sie erhalten die vollständige Kontrolle über den Tokenausstellungsprozess.  
  
-   Es werden ActAs/OnBehalfOf-Szenarien unterstützt, indem diese Eigenschaften für das ausgehende Anforderungssicherheitstoken direkt festgelegt werden.  
  
-   Dynamische clientseitige Entscheidungen über die Vertrauenswürdigkeit werden basierend auf dem Inhalt der Antwort des Anforderungssicherheitstokens ermöglicht.  
  
-   Das von der <xref:System.ServiceModel.Security.WSTrustChannel.Issue%2A>-Methode zurückgegebene Token kann zwischengespeichert und wiederverwendet werden.  
  
-   <xref:System.ServiceModel.Security.WSTrustChannelFactory> und <xref:System.ServiceModel.Security.WSTrustChannel> ermöglichen die Steuerung von Kanalzwischenspeicherung, Fehlern und Wiederherstellungssemantiken entsprechend WCF-Best Practices.  
  
## <a name="see-also"></a>Siehe auch  
 [WIF-Features](../../../docs/framework/security/wif-features.md)
