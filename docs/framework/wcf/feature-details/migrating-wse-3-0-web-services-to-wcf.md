---
title: Migrieren von WSE 3.0-Webdiensten zu WCF
ms.date: 03/30/2017
ms.assetid: 7bc5fff7-a2b2-4dbc-86cc-ecf73653dcdc
ms.openlocfilehash: 84d227a46c4d17291ccf35a759018ffbe6f48b82
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248161"
---
# <a name="migrating-wse-30-web-services-to-wcf"></a>Migrieren von WSE 3.0-Webdiensten zu WCF

Zu den Vorteilen der Migration von WSE 3,0-Webdiensten zu Windows Communication Foundation (WCF) zählen die verbesserte Leistung und die Unterstützung zusätzlicher Transporte, zusätzliche Sicherheitsszenarien und WS-*-Spezifikationen. Ein Webdienst, der von WSE 3,0 zu WCF migriert wird, kann eine Leistungsverbesserung von bis zu 200% bis 400% haben. Weitere Informationen zu den von WCF unterstützten Transporten finden Sie unter [Auswählen eines Transports](choosing-a-transport.md). Eine Liste der Szenarien, die von WCF unterstützt werden, finden Sie unter [Allgemeine Sicherheitsszenarien](common-security-scenarios.md). Eine Liste der Spezifikationen, die von WCF unterstützt werden, finden Sie im [Handbuch zur Interoperabilität von Webdienst Protokollen](web-services-protocols-interoperability-guide.md).  
  
 Die folgenden Abschnitte bieten Anleitungen zum Migrieren einer bestimmten Funktion eines WSE 3,0-Webdiensts zu WCF.  
  
## <a name="general"></a>Allgemein  

 WSE 3,0-und WCF-Anwendungen umfassen Interoperabilität auf Wire-Ebene und einen allgemeinen Satz von Terminologie. WSE 3,0-und WCF-Anwendungen sind auf der Grundlage des Satzes von WS-*-Spezifikationen, die beide unterstützen, interoperabel. Wenn eine WSE 3,0-oder WCF-Anwendung entwickelt wird, gibt es einen allgemeinen Satz von Terminologie, wie z. b. die Namen der sofort einsetzbaren Sicherheits Assertionen in WSE und die Authentifizierungs Modi.  
  
 Obwohl es viele ähnliche Aspekte zwischen den Programmier Modellen WCF und ASP.net oder WSE 3,0 gibt, unterscheiden Sie sich. Ausführliche Informationen zum WCF-Programmiermodell finden Sie unter [grundlegender Programmier Lebenszyklus](../basic-programming-lifecycle.md).  
  
> [!NOTE]
> Zum Migrieren eines WSE-Webdiensts zu WCF kann das [Service Model Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) verwendet werden, um einen Client zu generieren. Der Client enthält jedoch Schnittstellen und Klassen, die auch als Startpunkt für einen WCF-Dienst verwendet werden können. Bei den generierten Schnittstellen wird das <xref:System.ServiceModel.OperationContractAttribute>-Attribut auf die Member des Vertrags angewendet, wobei die <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A>-Eigenschaft auf `*` festgelegt ist. Wenn ein WSE-Client mit dieser Einstellung einen Webdienst aufruft, wird die folgende Ausnahme ausgelöst: **Web. Services3. Response processingexception: WSE910: während der Verarbeitung einer Antwortnachricht ist ein Fehler aufgetreten, und Sie können den Fehler in der inneren Ausnahme finden**. Um dies abzuschwächen, legen Sie für die <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A>-Eigenschaft des <xref:System.ServiceModel.OperationContractAttribute>-Attributs einen Nicht-`null`-Wert fest, wie z. B. `http://Microsoft.WCF.Documentation/ResponseToOCAMethod`.  
  
## <a name="security"></a>Sicherheit  
  
### <a name="wse-30-web-services-that-are-secured-using-a-policy-file"></a>WSE 3.0-Webdienste, die mit einer Richtliniendatei gesichert werden  

 WCF-Dienste können eine Konfigurationsdatei verwenden, um einen Dienst zu sichern. dieser Mechanismus ähnelt einer WSE 3,0-Richtlinien Datei. Wenn Sie in WSE 3.0 einen Webdienst mit einer Richtliniendatei sichern, verwenden Sie entweder eine sofort verwendbare Sicherheitsassertion oder eine benutzerdefinierte Richtlinienassertion. Die sofort einsetzbaren Sicherheits Assertionen werden dem Authentifizierungsmodus eines WCF-sicherheitsbindungs Elements genau zugeordnet. Nicht nur die WCF-Authentifizierungs Modi und die sofort verwendbaren WSE 3,0-Sicherheits Assertionen werden gleich oder ähnlich benannt, Sie sichern die Nachrichten mit denselben Anmelde Informationstypen. Beispielsweise wird die sofort einsetzbare `usernameForCertificate` Sicherheitserklärung in WSE 3,0 dem `UsernameForCertificate` Authentifizierungsmodus in WCF zugeordnet. Die folgenden Codebeispiele veranschaulichen, wie eine minimale Richtlinie, die die sofort einsetzbare `usernameForCertificate` Sicherheitserklärung in WSE 3,0 verwendet, einem `UsernameForCertificate` Authentifizierungsmodus in WCF in einer benutzerdefinierten Bindung zugeordnet wird.  
  
 **WSE 3.0**  
  
```xml  
<policies>  
  <policy name="MyPolicy">  
    <usernameForCertificate messageProtectionOrder="SignBeforeEncrypt"  
                            requireDeriveKeys="true"/>  
  </policy>  
</policies>  
```  
  
 **WCF**  
  
```xml  
<customBinding>  
  <binding name="MyBinding">  
    <security authenticationMode="UserNameForCertificate"
              messageProtectionOrder="SignBeforeEncrypt"  
              requireDerivedKeys="true"/>  
  </binding>  
</customBinding>  
```  
  
 Um die Sicherheitseinstellungen eines WSE 3,0-Webdiensts, die in einer Richtlinien Datei angegeben sind, zu WCF zu migrieren, muss eine benutzerdefinierte Bindung in einer Konfigurationsdatei erstellt werden, und die sofort einsetzbare Sicherheitserklärung muss auf den entsprechenden Authentifizierungsmodus festgelegt werden. Darüber hinaus muss die benutzerdefinierte Bindung für die Verwendung der WS-Adressing-Spezifikation vom August 2004 konfiguriert werden, wenn WSE 3.0-Clients mit dem Dienst kommunizieren. Wenn der migrierte WCF-Dienst keine Kommunikation mit WSE 3,0-Clients erfordert und nur die Sicherheits Parität beibehalten muss, sollten Sie die System definierten WCF-Bindungen mit entsprechenden Sicherheitseinstellungen verwenden, anstatt eine benutzerdefinierte Bindung zu erstellen.  
  
 In der folgenden Tabelle ist die Zuordnung zwischen einer WSE 3,0-Richtlinien Datei und der entsprechenden benutzerdefinierten Bindung in WCF aufgeführt.  
  
|Sofort verwendbare WSE 3.0 Sicherheitsassertion|Konfiguration einer benutzerdefinierten WCF-Bindung|  
|----------------------------------------|--------------------------------------|  
|\<usernameOverTransportSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UserNameOverTransport" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate10Security />|`<customBinding>   <binding name="MyBinding">     <security messageSecurityVersion="WSSecurity10WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10" authenticationMode="MutualCertificate" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<usernameForCertificateSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UsernameForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<anonymousForCertificateSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="AnonymousForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<kerberosSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="Kerberos"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate11Security />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="MutualCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
  
 Weitere Informationen zum Erstellen von benutzerdefinierten Bindungen in WCF finden Sie unter [benutzerdefinierte Bindungen](../extending/custom-bindings.md).  
  
### <a name="wse-30-web-services-that-are-secured-using-application-code"></a>WSE 3.0-Webdienste, die mit einem Anwendungscode gesichert werden  

 Unabhängig davon, ob WSE 3,0 oder WCF verwendet wird, können die Sicherheitsanforderungen im Anwendungscode anstelle der Konfiguration angegeben werden. Bei WSE 3.0 wird dies durch Erstellen einer Klasse, die sich von der `Policy`-Klasse ableitet, und dann durch Hinzufügen der Anforderungen durch Aufrufen der `Add`-Methode erreicht. Weitere Informationen zum Angeben der Sicherheitsanforderungen im Code finden Sie unter Gewusst [wie: Sichern eines Webdiensts ohne Verwendung einer Richtlinien Datei](/previous-versions/dotnet/netframework-2.0/aa528763(v=msdn.10)). Wenn Sie in WCF Sicherheitsanforderungen im Code angeben möchten, erstellen Sie eine Instanz der <xref:System.ServiceModel.Channels.BindingElementCollection> -Klasse, und fügen Sie dem eine Instanz von hinzu <xref:System.ServiceModel.Channels.SecurityBindingElement> <xref:System.ServiceModel.Channels.BindingElementCollection> . Die Anforderungen an die Sicherheitsassertionen werden mit den statischen Hilfsmethoden des Authentifizierungsmodus der <xref:System.ServiceModel.Channels.SecurityBindingElement>-Klasse festgelegt. Weitere Informationen zum Angeben von Sicherheitsanforderungen im Code mithilfe von WCF finden Sie unter Gewusst [wie: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md) und Gewusst [wie: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
### <a name="wse-30-custom-policy-assertion"></a>Benutzerdefinierte WSE 3.0-Richtlinienassertion  

 Bei WSE 3.0 gibt es zwei Typen von benutzerdefinierten Richtlinienassertionen: solche, die eine SOAP-Nachricht sichern, und solche, die keine SOAP-Nachricht sichern. Richtlinien Assertionen, die SOAP-Nachrichten schützen, werden von der WSE 3,0 `SecurityPolicyAssertion` -Klasse und der konzeptionellen Entsprechung in WCF abgeleitet <xref:System.ServiceModel.Channels.SecurityBindingElement> .  
  
 Ein wichtiger Punkt ist, dass die schlüsselfertigen WSE 3,0-Sicherheits Assertionen eine Teilmenge der WCF-Authentifizierungs Modi sind. Wenn Sie eine benutzerdefinierte Richtlinien Assertionen in WSE 3,0 erstellt haben, ist möglicherweise ein entsprechender WCF-Authentifizierungsmodus vorhanden. WSE 3.0 stellt z. B. keine CertificateOverTransport-Sicherheitsassertion bereit, die der sofort anwendbaren `UsernameOverTransport`-Sicherheitsassertion entspricht, verwendet aber ein X.509-Zertifikat für Clientauthentifizierungszwecke. Wenn Sie Ihre eigene benutzerdefinierte Richtlinien Assertionen für dieses Szenario definiert haben, macht WCF die Migration unkompliziert. WCF definiert einen Authentifizierungsmodus für dieses Szenario, sodass Sie die statischen Hilfsmethoden des Authentifizierungsmodus nutzen können, um WCF zu konfigurieren <xref:System.ServiceModel.Channels.SecurityBindingElement> .  
  
 Wenn kein WCF-Authentifizierungsmodus vorhanden ist, der einer benutzerdefinierten Richtlinien Assertion entspricht, die SOAP-Nachrichten sichert, leiten Sie eine Klasse von der <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> -oder WCF-Klasse ab, <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> und geben Sie das entsprechende Bindungs Element an. Weitere Informationen finden Sie unter Gewusst [wie: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
 Informationen zum Konvertieren einer benutzerdefinierten Richtlinien Assertion, die eine SOAP-Nachricht nicht sichert, finden Sie unter [Filterung](filtering.md) und das Beispiel für einen [benutzerdefinierten Nachrichteninterceptor](../samples/custom-message-interceptor.md).  
  
### <a name="wse-30-custom-security-token"></a>Benutzerdefiniertes WSE 3.0 Sicherheitstoken  

 Das WCF-Programmiermodell zum Erstellen eines benutzerdefinierten Tokens unterscheidet sich von WSE 3,0. Ausführliche Informationen zum Erstellen eines benutzerdefinierten Tokens in WSE finden Sie unter [Erstellen benutzerdefinierter Sicherheits Token](/previous-versions/dotnet/netframework-2.0/aa529304(v=msdn.10)). Ausführliche Informationen zum Erstellen eines benutzerdefinierten Tokens in WCF finden [Sie unter Gewusst wie: Erstellen eines benutzerdefinierten](../extending/how-to-create-a-custom-token.md)Tokens.  
  
### <a name="wse-30-custom-token-manager"></a>Benutzerdefinierter WSE 3.0 Token-Manager  

 Das Programmiermodell zum Erstellen eines benutzerdefinierten Token-Managers ist in WCF anders als WSE 3,0. Ausführliche Informationen zum Erstellen eines benutzerdefinierten Token-Managers und der anderen Komponenten, die für ein benutzerdefiniertes Sicherheits Token erforderlich sind, finden Sie unter Gewusst [wie: Erstellen eines benutzerdefinierten](../extending/how-to-create-a-custom-token.md)Tokens.  
  
> [!NOTE]
> Wenn Sie einen benutzerdefinierten `UsernameToken` Sicherheits Token-Manager erstellt haben, bietet WCF einen einfacheren Mechanismus, um die Authentifizierungs Logik anzugeben, als einen benutzerdefinierten Sicherheits Token-Manager zu erstellen. Weitere Informationen finden Sie unter Gewusst [wie: Verwenden eines benutzerdefinierten Benutzernamens und eines Kennwort-Validierungs](how-to-use-a-custom-user-name-and-password-validator.md)Steuer Elements.  
  
### <a name="wse-30-web-services-that-use-mtom-encoded-soap-messages"></a>WSE 3.0-Webdienste, die MTOM-codierte SOAP-Nachrichten verwenden  

 Wie eine WSE 3-Anwendung kann eine WCF-Anwendung die MTOM-Nachrichten Codierung in der Konfiguration angeben. Um diese Einstellung zu migrieren, fügen Sie der [\<mtomMessageEncoding>](../../configure-apps/file-schema/wcf/mtommessageencoding.md) Bindung für den Dienst hinzu. Im folgenden Codebeispiel wird veranschaulicht, wie die MTOM-Codierung in WSE 3,0 für einen Dienst angegeben wird, der in WCF Äquivalent ist.  
  
 **WSE 3.0**  
  
```xml  
<messaging>  
    <mtom clientMode="On"/>  
</messaging>  
```  
  
 **WCF**  
  
```xml  
<customBinding>  
  <binding name="MyBinding">  
    <mtomMessageEncoding/>  
  </binding>  
</customBinding>  
```  
  
## <a name="messaging"></a>Messaging  
  
### <a name="wse-30-applications-that-use-the-wse-messaging-api"></a>WSE 3.0-Anwendungen, die die WSE-Messaging-API verwenden  

 Wenn die WSE-Messaging-API verwendet wird, um direkten Zugriff auf die XML zu erhalten, die zwischen dem Client und dem Webdienst kommuniziert wird, kann die Anwendung so umgewandelt werden, dass sie "Plain Old XML" (POX) verwendet. Weitere Informationen zu POX finden Sie unter [Interoperabilität mit POX-Anwendungen](interoperability-with-pox-applications.md). Weitere Informationen zur WSE-Messaging-API finden [Sie unter Senden und empfangen von SOAP-Nachrichten mithilfe der WSE-Messaging-API](/previous-versions/dotnet/netframework-2.0/aa529293(v=msdn.10)).  
  
## <a name="transports"></a>Transportprotokolle  
  
### <a name="tcp"></a>TCP  

 Standardmäßig interagieren WSE 3,0-Clients und-Webdienste, die SOAP-Nachrichten über den TCP-Transport senden, nicht mit WCF-Clients und-Webdiensten. Diese Inkompatibilität beruht auf Unterschieden in dem im TCP-Protokoll verwendeten Rahmen und auf Leistungsgründen. In einem WCF-Beispiel wird jedoch ausführlich erläutert, wie eine benutzerdefinierte TCP-Sitzung implementiert wird, die mit WSE 3,0 interagiert. Ausführliche Informationen zu diesem Beispiel finden Sie unter [Transport: WSE 3,0 TCP-Interoperabilität](../samples/transport-wse-3-0-tcp-interoperability.md).  
  
 Um anzugeben, dass eine WCF-Anwendung den TCP-Transport verwendet, verwenden Sie die [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) .  
  
### <a name="custom-transport"></a>Benutzerdefinierter Transport  

 Die Entsprechung eines benutzerdefinierten WSE 3,0-Transports in WCF ist eine Kanalerweiterung. Ausführliche Informationen zum Erstellen einer Kanalerweiterung finden Sie unter [Erweitern der Kanal Ebene](../extending/extending-the-channel-layer.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Grundlegender Programmierlebenszyklus](../basic-programming-lifecycle.md)
- [Benutzerdefinierte Bindungen](../extending/custom-bindings.md)
- [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
