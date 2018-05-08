---
title: Migrieren von WSE 3.0-Webdiensten zu WCF
ms.date: 03/30/2017
ms.assetid: 7bc5fff7-a2b2-4dbc-86cc-ecf73653dcdc
ms.openlocfilehash: fea56d5737b47dabd5632477b7daed23fcfaf249
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="migrating-wse-30-web-services-to-wcf"></a>Migrieren von WSE 3.0-Webdiensten zu WCF
Migrieren von WSE 3.0-Webdiensten, Windows Communication Foundation (WCF) Vorteile verbesserte Leistung und die Unterstützung zusätzlicher Transporte, zusätzlicher Sicherheitsszenarien und WS-* Spezifikationen. Ein Webdienst, der von WSE 3.0 zu WCF migriert wird, kann bis zu 200 % bis 400 % verbessert die Leistung auftreten. Weitere Informationen zu den von WCF unterstützten Transporte, finden Sie unter [Wählen eines Transports](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md). Eine Liste der von WCF unterstützten Szenarien finden Sie [häufige Sicherheitsszenarien](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md). Eine Liste der Spezifikationen, die von WCF unterstützt werden, finden Sie unter [Handbuch Interoperabilität von Webdienstprotokollen](../../../../docs/framework/wcf/feature-details/web-services-protocols-interoperability-guide.md).  
  
 Die folgenden Abschnitte bieten eine Anleitung zum Migrieren von einer bestimmten Funktion eines WSE 3.0-Webdiensts zu WCF.  
  
## <a name="general"></a>Allgemein  
 WSE 3.0- und WCF-Anwendungen umfassen Interoperabilität auf niedriger Ebene und eine Standardmenge an Terminologie. WSE 3.0- und WCF-Anwendungen sind auf niedriger Ebene interoperabel basierend auf den Satz von WS-* Spezifikationen, die beide unterstützen. Wenn eine WSE 3.0- oder WCF-Anwendung entwickelt wird wird eine Standardmenge an Terminologie, wie die Namen der Sicherheitsassertionen in WSE und die Authentifizierungsmodi.  
  
 Obwohl viele ähnliche zwischen WCF und ASP.NET Aspekte oder WSE 3.0 Programmiermodelle, sind sie unterschiedlich. Weitere Informationen zu den WCF-Programmiermodell, finden Sie unter [grundlegende Programmierung Lebenszyklus](../../../../docs/framework/wcf/basic-programming-lifecycle.md).  
  
> [!NOTE]
>  WSE-Webdiensts zu WCF Migrieren der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Tool kann verwendet werden, um einen Client zu generieren. Der Client enthält jedoch Schnittstellen und Klassen, die auch als Startpunkt für einen WCF-Dienst verwendet werden können. Bei den generierten Schnittstellen wird das <xref:System.ServiceModel.OperationContractAttribute>-Attribut auf die Member des Vertrags angewendet, wobei die <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A>-Eigenschaft auf `*` festgelegt ist. Wenn ein WSE-Client einen Webdienst mit dieser Einstellung aufruft, wird die folgende Ausnahme ausgelöst: **Web.Services3.ResponseProcessingException: WSE910: bei der Verarbeitung einer Antwortnachricht ist ein Fehler aufgetreten, und den Fehler finden Sie in der inneren Ausnahme**. Um dies abzuschwächen, legen Sie für die <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A>-Eigenschaft des <xref:System.ServiceModel.OperationContractAttribute>-Attributs einen Nicht-`null`-Wert fest, wie z. B. `http://Microsoft.WCF.Documentation/ResponseToOCAMethod`.  
  
## <a name="security"></a>Sicherheit  
  
### <a name="wse-30-web-services-that-are-secured-using-a-policy-file"></a>WSE 3.0-Webdienste, die mit einer Richtliniendatei gesichert werden  
 WCF-Dienste können eine Konfigurationsdatei verwenden, um einen Dienst sichern, und dieser Mechanismus funktioniert ähnlich wie eine WSE 3.0-Richtliniendatei. Wenn Sie in WSE 3.0 einen Webdienst mit einer Richtliniendatei sichern, verwenden Sie entweder eine sofort verwendbare Sicherheitsassertion oder eine benutzerdefinierte Richtlinienassertion. Die Sicherheitsassertionen sind nahezu deckungsgleich mit den Authentifizierungsmodus eines Bindungselements einer WCF-Sicherheit. Nicht nur die WCF-Authentifizierungsmodi und WSE 3.0-Sicherheitsassertionen die denselben Namen, oder auf ähnliche Weise sichern sie die Nachrichten, die mit derselben Anmeldeinformationstypen. Für die Instanz, die `usernameForCertificate` -sicherheitsassertion in WSE 3.0 ordnet die `UsernameForCertificate` in WCF-Authentifizierungsmodus. Die folgenden Codebeispiele zeigen, wie eine minimale Richtlinie, die verwendet die `usernameForCertificate` -sicherheitsassertion in WSE 3.0 ordnet eine `UsernameForCertificate` Authentifizierungsmodus in WCF in einer benutzerdefinierten Bindung.  
  
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
  
 Um die Sicherheitseinstellungen eines WSE 3.0-Webdiensts zu migrieren, die in einer Richtliniendatei WCF angegeben sind, muss eine benutzerdefinierte Bindung in einer Konfigurationsdatei erstellt werden, und die sicherheitsassertion muss auf den entsprechenden Authentifizierungsmodus festgelegt werden. Darüber hinaus muss die benutzerdefinierte Bindung für die Verwendung der WS-Adressing-Spezifikation vom August 2004 konfiguriert werden, wenn WSE 3.0-Clients mit dem Dienst kommunizieren. Wenn der migrierte WCF-Dienst keine Kommunikation mit WSE 3.0-Clients erfordert und nur die sicherheitsparität verwalten muss, sollten Sie die vordefinierten WCF-Bindungen mit entsprechenden Sicherheitseinstellungen fest, statt eine benutzerdefinierte Bindung zu erstellen.  
  
 Die folgende Tabelle enthält die Zuordnung zwischen einer WSE 3.0-Richtliniendatei und der entsprechenden benutzerdefinierten Bindung in WCF.  
  
|Sofort verwendbare WSE 3.0 Sicherheitsassertion|Konfiguration einer benutzerdefinierten WCF-Bindung|  
|----------------------------------------|--------------------------------------|  
|\<UsernameOverTransportSecurity / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UserNameOverTransport" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate10Security / >|`<customBinding>   <binding name="MyBinding">     <security messageSecurityVersion="WSSecurity10WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10" authenticationMode="MutualCertificate" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<UsernameForCertificateSecurity / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UsernameForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<AnonymousForCertificateSecurity / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="AnonymousForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<KerberosSecurity / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="Kerberos"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate11Security / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="MutualCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
  
 Weitere Informationen zum Erstellen benutzerdefinierter Bindungen in WCF finden Sie unter [benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
### <a name="wse-30-web-services-that-are-secured-using-application-code"></a>WSE 3.0-Webdienste, die mit einem Anwendungscode gesichert werden  
 Ob WSE 3.0- oder WCF verwendet wird, können die sicherheitsanforderungen im Anwendungscode statt in der Konfiguration angegeben werden. Bei WSE 3.0 wird dies durch Erstellen einer Klasse, die sich von der `Policy`-Klasse ableitet, und dann durch Hinzufügen der Anforderungen durch Aufrufen der `Add`-Methode erreicht. Weitere Informationen zu die sicherheitsanforderungen im Code angeben, finden Sie unter [Vorgehensweise: Sichern einer Web-Dienst ohne Verwendung einer Richtliniendatei](http://go.microsoft.com/fwlink/?LinkId=73747). In WCF, um sicherheitsanforderungen im Code anzugeben, erstellen eine Instanz von der <xref:System.ServiceModel.Channels.BindingElementCollection> Klasse und fügen Sie eine Instanz von einer <xref:System.ServiceModel.Channels.SecurityBindingElement> auf die <xref:System.ServiceModel.Channels.BindingElementCollection>. Die Anforderungen an die Sicherheitsassertionen werden mit den statischen Hilfsmethoden des Authentifizierungsmodus der <xref:System.ServiceModel.Channels.SecurityBindingElement>-Klasse festgelegt. Ausführliche Informationen zur Angabe von sicherheitsanforderungen im Code mithilfe von WCF finden Sie unter [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md) und [Vorgehensweise: Erstellen eines SecurityBindingElement für eine angegebene Authentifizierungsmodus](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
### <a name="wse-30-custom-policy-assertion"></a>Benutzerdefinierte WSE 3.0-Richtlinienassertion  
 Bei WSE 3.0 gibt es zwei Typen von benutzerdefinierten Richtlinienassertionen: solche, die eine SOAP-Nachricht sichern, und solche, die keine SOAP-Nachricht sichern. Richtlinienassertionen, die SOAP-Nachrichten Sichern von WSE 3.0 ableiten `SecurityPolicyAssertion` Klasse und das konzeptuelle Äquivalent in WCF ist das <xref:System.ServiceModel.Channels.SecurityBindingElement> Klasse.  
  
 Ein wichtiger Punkt zu beachten ist, dass die WSE 3.0-Sicherheitsassertionen eine Teilmenge der WCF-Authentifizierungsmodi sind. Wenn Sie eine benutzerdefinierte Richtlinienassertion in WSE 3.0 erstellt haben, es gibt möglicherweise ein äquivalente WCF-Authentifizierungsmodus. WSE 3.0 stellt z. B. keine CertificateOverTransport-Sicherheitsassertion bereit, die der sofort anwendbaren `UsernameOverTransport`-Sicherheitsassertion entspricht, verwendet aber ein X.509-Zertifikat für Clientauthentifizierungszwecke. Wenn Sie eine eigene benutzerdefinierte Richtlinienassertion für dieses Szenario definiert haben, vereinfacht WCF die Migration. WCF definiert einen Authentifizierungsmodus für dieses Szenario, sodass Sie bei der Authentifizierung statische Hilfsmethoden zum Konfigurieren eines WCFS nutzen können<xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
 Wenn kein WCF-Authentifizierungsmodus, der eine benutzerdefinierte Richtlinienassertion entspricht, die SOAP-Nachrichten sichert, leiten Sie eine Klasse von <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> oder <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>WCF-Klassen, und geben Sie das entsprechende Bindungselement. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
 Um eine benutzerdefinierte Richtlinienassertion zu konvertieren, die keine SOAP-Nachricht gesichert wird, finden Sie unter [Filtering](../../../../docs/framework/wcf/feature-details/filtering.md) und im Beispiel [benutzerdefinierte Nachrichteninterceptor](../../../../docs/framework/wcf/samples/custom-message-interceptor.md).  
  
### <a name="wse-30-custom-security-token"></a>Benutzerdefiniertes WSE 3.0 Sicherheitstoken  
 Das WCF-Programmiermodell zum Erstellen eines benutzerdefinierten Tokens unterscheidet sich von WSE 3.0. Ausführliche Informationen zum Erstellen eines benutzerdefinierten Tokens in WSE finden Sie unter [benutzerdefiniertes Sicherheitstoken erstellen](http://go.microsoft.com/fwlink/?LinkID=73750). Ausführliche Informationen zum Erstellen eines benutzerdefinierten Tokens in WCF finden Sie unter [Vorgehensweise: Erstellen eines benutzerdefinierten Tokens](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
### <a name="wse-30-custom-token-manager"></a>Benutzerdefinierter WSE 3.0 Token-Manager  
 Das Programmiermodell zum Erstellen eines benutzerdefinierten Sicherheitstoken-Managers unterscheidet sich in WCF als WSE 3.0. Ausführliche Informationen zum Erstellen einer benutzerdefinierten Sicherheitstoken-Manager und die anderen Komponenten, die für ein benutzerdefiniertes Sicherheitstoken erforderlich sind, finden Sie unter [Vorgehensweise: Erstellen eines benutzerdefinierten Tokens](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
> [!NOTE]
>  Wenn Sie eine benutzerdefinierte erstellt haben `UsernameToken` sicherheitstokenmanager WCF bietet einen einfacheren Mechanismus zum Angeben der Authentifizierungslogik als Erstellen eines benutzerdefinierten Sicherheitstoken-Manager. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie einen benutzerdefinierten-Benutzernamen und Kennwort-Validierungssteuerelement](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md).  
  
### <a name="wse-30-web-services-that-use-mtom-encoded-soap-messages"></a>WSE 3.0-Webdienste, die MTOM-codierte SOAP-Nachrichten verwenden  
 Eine WCF-Anwendung kann die MTOM-nachrichtencodierung in der Konfiguration angeben, wie eine WSE 3-Anwendung. Fügen Sie zum Migrieren dieser Einstellung die [ \<MtomMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/mtommessageencoding.md) der Bindung für den Dienst. Im folgenden Codebeispiel wird veranschaulicht, wie MTOM-Codierung in WSE 3.0 für einen Dienst angegeben wird, die in WCF entspricht.  
  
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
 Wenn die WSE-Messaging-API verwendet wird, um direkten Zugriff auf die XML zu erhalten, die zwischen dem Client und dem Webdienst kommuniziert wird, kann die Anwendung so umgewandelt werden, dass sie "Plain Old XML" (POX) verwendet. Weitere Informationen zu POX, finden Sie unter [Interoperabilität mit POX-Anwendungen](../../../../docs/framework/wcf/feature-details/interoperability-with-pox-applications.md). Weitere Informationen über die WSE-Messaging-API finden Sie unter [senden und Empfangen von SOAP-Nachrichten mithilfe von WSE-Messaging-API](http://go.microsoft.com/fwlink/?LinkID=73755).  
  
## <a name="transports"></a>Transportprotokolle  
  
### <a name="tcp"></a>TCP  
 Standardmäßig zusammenarbeiten WSE 3.0-Clients und Webdienste, die SOAP-Nachrichten mittels TCP-Transport senden nicht mit WCF-Clients und Webdiensten. Diese Inkompatibilität beruht auf Unterschieden in dem im TCP-Protokoll verwendeten Rahmen und auf Leistungsgründen. Ein WCF-Beispiel wird jedoch erläutert, wie eine benutzerdefinierte TCP-Sitzung zu implementieren, die mit WSE 3.0 zusammenwirkt. Einzelheiten zu diesem Beispiel finden Sie unter [Transport: WSE 3.0-TCP-Interoperabilität](../../../../docs/framework/wcf/samples/transport-wse-3-0-tcp-interoperability.md).  
  
 Verwenden, um anzugeben, dass eine WCF-Anwendung über den TCP-Transport verwendet die [ \<NetTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).  
  
### <a name="custom-transport"></a>Benutzerdefinierter Transport  
 Die Entsprechung eines benutzerdefinierten WSE 3.0-Transports in WCF ist eine kanalerweiterung. Ausführliche Informationen zum Erstellen einer kanalerweiterung finden Sie unter [Erweitern der Kanalschicht](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlegender Programmierlebenszyklus](../../../../docs/framework/wcf/basic-programming-lifecycle.md)  
 [Benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
