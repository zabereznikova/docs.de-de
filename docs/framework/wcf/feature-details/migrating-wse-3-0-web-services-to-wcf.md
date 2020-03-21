---
title: Migrieren von WSE 3.0-Webdiensten zu WCF
ms.date: 03/30/2017
ms.assetid: 7bc5fff7-a2b2-4dbc-86cc-ecf73653dcdc
ms.openlocfilehash: 8f79674350109d111fe263704dee6c40c1a12451
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184568"
---
# <a name="migrating-wse-30-web-services-to-wcf"></a>Migrieren von WSE 3.0-Webdiensten zu WCF
Zu den Vorteilen der Migration von WSE 3.0-Webdiensten zur Windows Communication Foundation (WCF) gehören eine verbesserte Leistung und die Unterstützung zusätzlicher Transporte, zusätzlicher Sicherheitsszenarien und WS-*-Spezifikationen. Ein Webdienst, der von WSE 3.0 zu WCF migriert wird, kann eine Leistungsverbesserung von bis zu 200 % bis 400 % aufweisen. Weitere Informationen zu den von WCF unterstützten Transporten finden Sie unter [Auswählen eines Transports](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md). Eine Liste der von WCF unterstützten Szenarien finden Sie unter [Allgemeine Sicherheitsszenarien](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md). Eine Liste der Spezifikationen, die von WCF unterstützt werden, finden Sie unter [Web Services Protocols Interoperability Guide](../../../../docs/framework/wcf/feature-details/web-services-protocols-interoperability-guide.md).  
  
 Die folgenden Abschnitte enthalten Anleitungen zum Migrieren eines bestimmten Features eines WSE 3.0-Webdiensts zu WCF.  
  
## <a name="general"></a>Allgemein  
 WSE 3.0- und WCF-Anwendungen umfassen Interoperabilität auf Drahtebene und einen gemeinsamen Satz von Terminologie. WSE 3.0- und WCF-Anwendungen sind interoperabel auf Drahtebene, basierend auf den WS-*-Spezifikationen, die beide unterstützen. Wenn eine WSE 3.0- oder WCF-Anwendung entwickelt wird, gibt es einen gemeinsamen Satz von Terminologie, z. B. die Namen der schlüsselfertigen Sicherheitsassertionen in WSE und die Authentifizierungsmodi.  
  
 Obwohl es viele ähnliche Aspekte zwischen den WCF- und ASP.NET- oder WSE 3.0-Programmiermodellen gibt, unterscheiden sie sich jedoch. Weitere Informationen zum WCF-Programmiermodell finden Sie unter [Basic Programming Lifecycle](../../../../docs/framework/wcf/basic-programming-lifecycle.md).  
  
> [!NOTE]
> Um einen WSE-Webdienst zu WCF zu migrieren, kann das [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) zum Generieren eines Clients verwendet werden. Der Client enthält jedoch Schnittstellen und Klassen, die auch als Startpunkt für einen WCF-Dienst verwendet werden können. Bei den generierten Schnittstellen wird das <xref:System.ServiceModel.OperationContractAttribute>-Attribut auf die Member des Vertrags angewendet, wobei die <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A>-Eigenschaft auf `*` festgelegt ist. Wenn ein WSE-Client einen Webdienst mit dieser Einstellung aufruft, wird die folgende Ausnahme ausgelöst: **Web.Services3.ResponseProcessingException: WSE910: Bei der Verarbeitung einer Antwortnachricht ist ein Fehler aufgetreten, und Sie können den Fehler in der inneren Ausnahme finden.** Um dies abzuschwächen, legen Sie für die <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A>-Eigenschaft des <xref:System.ServiceModel.OperationContractAttribute>-Attributs einen Nicht-`null`-Wert fest, wie z. B. `http://Microsoft.WCF.Documentation/ResponseToOCAMethod`.  
  
## <a name="security"></a>Sicherheit  
  
### <a name="wse-30-web-services-that-are-secured-using-a-policy-file"></a>WSE 3.0-Webdienste, die mit einer Richtliniendatei gesichert werden  
 WCF-Dienste können eine Konfigurationsdatei verwenden, um einen Dienst zu sichern, und dieser Mechanismus ähnelt einer WSE 3.0-Richtliniendatei. Wenn Sie in WSE 3.0 einen Webdienst mit einer Richtliniendatei sichern, verwenden Sie entweder eine sofort verwendbare Sicherheitsassertion oder eine benutzerdefinierte Richtlinienassertion. Die schlüsselfertigen Sicherheitsassertionen werden eng dem Authentifizierungsmodus eines WCF-Sicherheitsbindungselements zugeordnet. Die WCF-Authentifizierungsmodi und die schlüsselfertigen WSE 3.0-Sicherheitsassertionen werden nicht nur als identisch oder ähnlich bezeichnet, sie sichern die Nachrichten mit denselben Anmeldeinformationstypen. Beispielsweise wird `usernameForCertificate` die schlüsselfertige Sicherheitsbehauptung in WSE `UsernameForCertificate` 3.0 dem Authentifizierungsmodus in WCF zugeordnet. Die folgenden Codebeispiele veranschaulichen, wie `usernameForCertificate` eine minimale Richtlinie, die die schlüsselfertige Sicherheitsassertion in WSE 3.0 verwendet, einem `UsernameForCertificate` Authentifizierungsmodus in WCF in einer benutzerdefinierten Bindung zugeordnet wird.  
  
 **WSE 3.0**  
  
```xml  
<policies>  
  <policy name="MyPolicy">  
    <usernameForCertificate messageProtectionOrder="SignBeforeEncrypt"  
                            requireDeriveKeys="true"/>  
  </policy>  
</policies>  
```  
  
 **Wcf**  
  
```xml  
<customBinding>  
  <binding name="MyBinding">  
    <security authenticationMode="UserNameForCertificate"
              messageProtectionOrder="SignBeforeEncrypt"  
              requireDerivedKeys="true"/>  
  </binding>  
</customBinding>  
```  
  
 Um die Sicherheitseinstellungen eines WSE 3.0-Webdienstes zu migrieren, die in einer Richtliniendatei in WCF angegeben sind, muss eine benutzerdefinierte Bindung in einer Konfigurationsdatei erstellt werden, und die schlüsselfertige Sicherheitsbehauptung muss auf den entsprechenden Authentifizierungsmodus festgelegt werden. Darüber hinaus muss die benutzerdefinierte Bindung für die Verwendung der WS-Adressing-Spezifikation vom August 2004 konfiguriert werden, wenn WSE 3.0-Clients mit dem Dienst kommunizieren. Wenn der migrierte WCF-Dienst keine Kommunikation mit WSE 3.0-Clients erfordert und nur die Sicherheitsparität beibehalten muss, sollten Sie die vom WCF-System definierten Bindungen mit entsprechenden Sicherheitseinstellungen verwenden, anstatt eine benutzerdefinierte Bindung zu erstellen.  
  
 In der folgenden Tabelle ist die Zuordnung zwischen einer WSE 3.0-Richtliniendatei und der entsprechenden benutzerdefinierten Bindung in WCF aufgeführt.  
  
|Sofort verwendbare WSE 3.0 Sicherheitsassertion|Konfiguration einer benutzerdefinierten WCF-Bindung|  
|----------------------------------------|--------------------------------------|  
|\<BenutzernameOverTransportSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UserNameOverTransport" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate10Security />|`<customBinding>   <binding name="MyBinding">     <security messageSecurityVersion="WSSecurity10WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10" authenticationMode="MutualCertificate" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<benutzernameForCertificateSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UsernameForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<anonymForCertificateSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="AnonymousForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<kerberosSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="Kerberos"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<gegenseitigesZertifikat11Security />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="MutualCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
  
 Weitere Informationen zum Erstellen benutzerdefinierter Bindungen in WCF finden Sie unter [Benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
### <a name="wse-30-web-services-that-are-secured-using-application-code"></a>WSE 3.0-Webdienste, die mit einem Anwendungscode gesichert werden  
 Unabhängig davon, ob WSE 3.0 oder WCF verwendet wird, können die Sicherheitsanforderungen im Anwendungscode anstelle der Konfiguration angegeben werden. Bei WSE 3.0 wird dies durch Erstellen einer Klasse, die sich von der `Policy`-Klasse ableitet, und dann durch Hinzufügen der Anforderungen durch Aufrufen der `Add`-Methode erreicht. Weitere Informationen zum Angeben der Sicherheitsanforderungen im Code finden Sie unter [Gewusst wie: Sichern eines Webdienstes ohne Verwendung einer Richtliniendatei](https://docs.microsoft.com/previous-versions/dotnet/netframework-2.0/aa528763(v=msdn.10)). Um in WCF Sicherheitsanforderungen im Code anzugeben, <xref:System.ServiceModel.Channels.BindingElementCollection> erstellen Sie eine <xref:System.ServiceModel.Channels.SecurityBindingElement> Instanz <xref:System.ServiceModel.Channels.BindingElementCollection>der Klasse, und fügen Sie dem eine Instanz von a hinzu. Die Anforderungen an die Sicherheitsassertionen werden mit den statischen Hilfsmethoden des Authentifizierungsmodus der <xref:System.ServiceModel.Channels.SecurityBindingElement>-Klasse festgelegt. Weitere Informationen zum Angeben von Sicherheitsanforderungen im Code mithilfe von WCF finden Sie unter [Gewusst wie: Erstellen einer benutzerdefinierten Bindung mithilfe des SecurityBindingElements](how-to-create-a-custom-binding-using-the-securitybindingelement.md) und [How to: Create a SecurityBindingElement for a Specified Authentication Mode](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
### <a name="wse-30-custom-policy-assertion"></a>Benutzerdefinierte WSE 3.0-Richtlinienassertion  
 Bei WSE 3.0 gibt es zwei Typen von benutzerdefinierten Richtlinienassertionen: solche, die eine SOAP-Nachricht sichern, und solche, die keine SOAP-Nachricht sichern. Richtlinienassertionen, die sichere SOAP-Nachrichten von `SecurityPolicyAssertion` der WSE 3.0-Klasse <xref:System.ServiceModel.Channels.SecurityBindingElement> ableiten, und das konzeptionelle Äquivalent in WCF ist die Klasse.  
  
 Ein wichtiger Punkt ist, dass die schlüsselfertigen WSE 3.0-Sicherheitsassertionen eine Teilmenge der WCF-Authentifizierungsmodi sind. Wenn Sie eine benutzerdefinierte Richtlinienassertion in WSE 3.0 erstellt haben, kann es zu einem entsprechenden WCF-Authentifizierungsmodus führen. WSE 3.0 stellt z. B. keine CertificateOverTransport-Sicherheitsassertion bereit, die der sofort anwendbaren `UsernameOverTransport`-Sicherheitsassertion entspricht, verwendet aber ein X.509-Zertifikat für Clientauthentifizierungszwecke. Wenn Sie eine eigene benutzerdefinierte Richtlinienassertion für dieses Szenario definiert haben, vereinfacht WCF die Migration. WCF definiert einen Authentifizierungsmodus für dieses Szenario, sodass Sie die statischen<xref:System.ServiceModel.Channels.SecurityBindingElement>Authentifizierungsmodus-Hilfsmethoden zum Konfigurieren eines WCF verwenden können.  
  
 Wenn kein WCF-Authentifizierungsmodus vorhanden ist, der einer benutzerdefinierten Richtlinienassertion entspricht, <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>die SOAP-Nachrichten sichert, leiten Sie eine Klasse von <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>oder WCF-Klassen ab, und geben Sie das entsprechende Bindungselement an. Weitere Informationen finden Sie unter [Gewusst wie: Erstellen einer benutzerdefinierten Bindung mithilfe des SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
 Informationen zum Konvertieren einer benutzerdefinierten Richtlinienassertion, die keine SOAP-Nachricht sichert, finden Sie unter [Filtern](../../../../docs/framework/wcf/feature-details/filtering.md) und Beispiel [für benutzerdefinierte Nachrichtenabfangjäger](../../../../docs/framework/wcf/samples/custom-message-interceptor.md).  
  
### <a name="wse-30-custom-security-token"></a>Benutzerdefiniertes WSE 3.0 Sicherheitstoken  
 Das WCF-Programmiermodell zum Erstellen eines benutzerdefinierten Tokens unterscheidet sich von WSE 3.0. Weitere Informationen zum Erstellen eines benutzerdefinierten Tokens in WSE finden Sie unter [Erstellen benutzerdefinierter Sicherheitstoken](https://docs.microsoft.com/previous-versions/dotnet/netframework-2.0/aa529304(v=msdn.10)). Weitere Informationen zum Erstellen eines benutzerdefinierten Tokens in WCF finden Sie unter [Gewusst wie: Erstellen eines benutzerdefinierten Tokens](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
### <a name="wse-30-custom-token-manager"></a>Benutzerdefinierter WSE 3.0 Token-Manager  
 Das Programmiermodell zum Erstellen eines benutzerdefinierten Token-Managers unterscheidet sich in WCF von WSE 3.0. Weitere Informationen zum Erstellen eines benutzerdefinierten Token-Managers und der anderen Komponenten, die für ein benutzerdefiniertes Sicherheitstoken erforderlich sind, finden Sie unter [Gewusst wie: Erstellen eines benutzerdefinierten Tokens](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
> [!NOTE]
> Wenn Sie einen `UsernameToken` benutzerdefinierten Sicherheitstoken-Manager erstellt haben, bietet WCF einen einfacheren Mechanismus zum Angeben der Authentifizierungslogik als das Erstellen eines benutzerdefinierten Sicherheitstoken-Managers. Weitere Informationen finden Sie unter [Gewusst wie: Verwenden eines benutzerdefinierten Benutzernamens und Kennwortvalidators](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md).  
  
### <a name="wse-30-web-services-that-use-mtom-encoded-soap-messages"></a>WSE 3.0-Webdienste, die MTOM-codierte SOAP-Nachrichten verwenden  
 Wie eine WSE 3-Anwendung kann eine WCF-Anwendung die MTOM-Nachrichtencodierung in der Konfiguration angeben. Um diese Einstellung zu migrieren, fügen Sie der Bindung für den Dienst die [ \<mtomMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/mtommessageencoding.md) hinzu. Das folgende Codebeispiel veranschaulicht, wie die MTOM-Codierung in WSE 3.0 für einen Dienst angegeben wird, der in WCF äquivalent ist.  
  
 **WSE 3.0**  
  
```xml  
<messaging>  
    <mtom clientMode="On"/>  
</messaging>  
```  
  
 **Wcf**  
  
```xml  
<customBinding>  
  <binding name="MyBinding">  
    <mtomMessageEncoding/>  
  </binding>  
</customBinding>  
```  
  
## <a name="messaging"></a>Nachrichten  
  
### <a name="wse-30-applications-that-use-the-wse-messaging-api"></a>WSE 3.0-Anwendungen, die die WSE-Messaging-API verwenden  

 Wenn die WSE-Messaging-API verwendet wird, um direkten Zugriff auf die XML zu erhalten, die zwischen dem Client und dem Webdienst kommuniziert wird, kann die Anwendung so umgewandelt werden, dass sie "Plain Old XML" (POX) verwendet. Weitere Informationen zu POX finden Sie unter [Interoperabilität mit POX-Anwendungen](interoperability-with-pox-applications.md). Weitere Informationen zur WSE-Messaging-API finden Sie unter [Senden und Empfangen von SOAP-Nachrichten mithilfe der WSE-Messaging-API](https://docs.microsoft.com/previous-versions/dotnet/netframework-2.0/aa529293(v=msdn.10)).  
  
## <a name="transports"></a>Transportprotokolle  
  
### <a name="tcp"></a>TCP  
 Standardmäßig arbeiten WSE 3.0-Clients und Webdienste, die SOAP-Nachrichten mithilfe des TCP-Transports senden, nicht mit WCF-Clients und Webdiensten zusammen. Diese Inkompatibilität beruht auf Unterschieden in dem im TCP-Protokoll verwendeten Rahmen und auf Leistungsgründen. In einem WCF-Beispiel wird jedoch erläutert, wie eine benutzerdefinierte TCP-Sitzung implementiert wird, die mit WSE 3.0 zusammenarbeitet. Weitere Informationen zu diesem Beispiel finden Sie unter [Transport: WSE 3.0 TCP Interoperability](../../../../docs/framework/wcf/samples/transport-wse-3-0-tcp-interoperability.md).  
  
 Um anzugeben, dass eine WCF-Anwendung den TCP-Transport verwendet, verwenden Sie die [ \<netTcpBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).  
  
### <a name="custom-transport"></a>Benutzerdefinierter Transport  
 Das Äquivalent eines benutzerdefinierten WSE 3.0-Transports in WCF ist eine Kanalerweiterung. Weitere Informationen zum Erstellen einer Kanalerweiterung finden Sie unter [Erweitern der Kanalschicht](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Grundlegender Programmierlebenszyklus](../../../../docs/framework/wcf/basic-programming-lifecycle.md)
- [Benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md)
- [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
