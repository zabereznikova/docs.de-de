---
title: Sichern von Clients
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: clients [WCF], security considerations
ms.assetid: 44c8578c-9a5b-4acd-8168-1c30a027c4c5
caps.latest.revision: "22"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: d41d2f8419644d5ddcb15f49bbe895b0a3f1f2d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="securing-clients"></a>Sichern von Clients
In [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] schreibt der Dienst die Sicherheitsanforderungen für Clients vor, d. h. der Dienst legt fest, welcher Sicherheitsmodus verwendet wird und ob der Client Anmeldeinformationen angeben muss oder nicht. Der Sicherungsvorgang an einem Client ist also unkompliziert: Man verwendet einfach die vom Dienst erhaltenen Metadaten (sofern diese veröffentlicht wurden) und erstellt einen Client. Die Metadaten geben an, wie der Client konfiguriert wird. Wenn der Dienst erfordert, dass der Client Anmeldeinformationen angibt, müssen Sie Anmeldeinformationen erhalten, die die Anforderung erfüllen. Dieses Thema beschreibt den Vorgang ausführlicher. [!INCLUDE[crabout](../../../includes/crabout-md.md)]Erstellen eines sicheren Diensts finden Sie unter [Sichern von Services](../../../docs/framework/wcf/securing-services.md).  
  
## <a name="the-service-specifies-security"></a>Der Dienst legt die Sicherheit fest  
 Standardmäßig weisen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Bindungen aktivierte Sicherheitsfunktionen auf. (Die Ausnahme ist <xref:System.ServiceModel.BasicHttpBinding>.) Wenn der Dienst also über [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] erstellt wird, ist die Wahrscheinlichkeit größer, dass er Sicherheitsmaßnahmen umsetzt, um Authentifizierung, Vertraulichkeit und Integrität zu gewährleisten. In diesem Fall geben die vom Dienst bereitgestellten Metadaten an, was für den Aufbau eines sicheren Kommunikationskanals erforderlich ist. Wenn die Dienstmetadaten keine Sicherheitsanforderungen enthalten, gibt es keine Möglichkeit, einem Dienst ein Sicherheitsschema wie Secure Sockets Layer (SSL) über HTTP aufzuerlegen. Wenn jedoch der Dienst erfordert, dass der Client Anmeldeinformationen liefert, muss der Entwickler, Bereitsteller oder Administrator des Clients genau diejenigen Anmeldeinformationen liefern, die der Client zur Authentifizierung gegenüber dem Dienst nutzen wird.  
  
## <a name="obtaining-metadata"></a>Erlangen von Metadaten  
 Beim Erstellen eines Clients besteht der erste Schritt darin, die Metadaten für den Dienst zu erlangen, die der Client für die Kommunikation nutzen wird. Dazu gibt es zwei Möglichkeiten. Zuerst, wenn der Dienst einen Metadatenaustausch (MEX)-Endpunkt veröffentlicht oder seine Metadaten über HTTP oder HTTPS verfügbar macht, Sie können die Metadaten mit den [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), wodurch generiert sowohl die Codedateien für einen Client als auch eine Konfigurationsdatei. ([!INCLUDE[crabout](../../../includes/crabout-md.md)] mithilfe des Tools finden Sie [beim Zugriff auf Dienste, die mithilfe eines WCF-Clients](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md).) Wenn der Dienst keinen MEX-Endpunkt veröffentlicht und keine Metadaten über HTTP oder HTTPS zur Verfügung stellt, müssen Sie den Dienstersteller um Dokumentation bitten, die die Sicherheitsanforderungen und die Metadaten beschreibt.  
  
> [!IMPORTANT]
>  Sie sollten darauf achten, dass die Metadaten von einer vertrauenswürdigen Quelle stammen und dass sie nicht manipuliert wurden. Über das HTTP-Protokoll abgerufene Metadaten werden im Klartext gesendet und können manipuliert werden. Wenn der Dienst die Eigenschaften <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> und <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> verwendet, verwenden Sie den URL, den der Dienstersteller geliefert hat, um die Daten über das HTTPS-Protokoll herunterzuladen.  
  
## <a name="validating-security"></a>Überprüfen von Sicherheit  
 Metadatenquellen können in zwei grundlegende Kategorien aufgeteilt werden: vertrauenswürdige Quellen und nicht vertrauenswürdige Quellen. Wenn Sie einer Quelle vertrauen und den Clientcode und andere Metadaten vom sicheren MEX-Endpunkt der Quelle heruntergeladen haben, können Sie den Client erstellen, ihm die korrekten Anmeldeinformationen zuweisen und ihn ohne Bedenken ausführen.  
  
 Wenn Sie sich jedoch für ein Herunterladen eines Clients und von Metadaten von einer Quelle entscheiden, über die Sie nur wenig wissen, sollten Sie die vom Code verwendetenSicherheitsmaßnahmen überprüfen. Sie dürfen beispielsweise nicht einfach einen Client erstellen, der Ihre persönlichen oder finanziellen Daten an einen Dienst sendet, sofern der Dienst nicht zumindesten Vertraulichkeit und Integrität erfordert. Sie sollten dem Besitzer des Diensts soweit vertrauen, dass Sie bereit sind, Daten dieser Art an ihn weiterzugeben, da er auf sie zugreifen kann.  
  
 Als Regel sollten Sie daher, wenn Sie Code und Metadaten von einer nicht vertrauenswürdigen Quelle verwenden, den Code und die Metadaten überprüfen, um sicherzustellen, dass sie das von Ihnen benötigte Sicherheitsniveau erfüllen.  
  
## <a name="setting-a-client-credential"></a>Festlegen von Clientanmeldeinformationen  
 Das Festlegen von Clientanmeldeinformationen auf einem Client erfolgt in zwei Schritten:  
  
1.  Bestimmen der *Clientanmeldeinformationstyp* den Dienst erforderlich sind. Dies wird durch eine der folgenden beiden Methoden erreicht. Erstens: Wenn Sie Dokumentation vom Dienstersteller besitzen, sollte diese den Typ der Clientanmeldeinformation (sofern vorhanden) angeben, der vom Dienst gefordert wird. Zweitens: Wenn Sie nur eine vom Svcutil.exe-Tool erstellte Konfigurationsdatei besitzen, können Sie die einzelnen Bindungen untersuchen, um herauszufinden, welcher Typ von Anmeldeinformationen benötigt wird.  
  
2.  Geben Sie tatsächliche Clientanmeldeinformationen an. Die tatsächlichen Clientanmeldeinformationen heißt ein *clientanmeldeinformationswert* zur Unterscheidung von den Typ. Wenn der Typ der Clientanmeldeinformationen beispielsweise ein Zertifikat angibt, müssen Sie ein X.509-Zertifikat bereitstellen, das von einer Zertifizierungsstelle ausgestellt wurde, der der Dienst vertraut.  
  
### <a name="determining-the-client-credential-type"></a>Bestimmen des Typs der Clientanmeldeinformationen  
 Wenn Sie die Konfiguration, sehen Sie das Tool Svcutil.exe generierten Datei haben die [ \<Bindungen >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) Abschnitt aus, um zu bestimmen, welcher Typ von Anmeldeinformationen erforderlich ist. Innerhalb des Abschnitts befinden sich Bindungselemente, die die Sicherheitsanforderungen angeben. Untersuchen Sie besonders die \<Sicherheit >-Element jeder Bindung. Zu diesem Element gehört das Attribut `mode`, das Sie auf einen von drei möglichen Werten festlegen können (`Message`, `Transport` oder `TransportWithMessageCredential`). Der Wert des Attributs bestimmt den Modus, und der Modus legt fest, welches der untergeordneten Elemente von Bedeutung ist.  
  
 Die `<security>` Element kann entweder enthalten eine `<transport>` oder `<message>` -Element oder beides. Das bedeutende Element ist dasjenige, das dem Sicherheitsmodus entspricht. Der folgende Code gibt beispielsweise an, dass der Sicherheitsmodus `"Message"` und der Typ der Clientanmeldeinformationen für das Element `<message>` `"Certificate"` ist. In diesem Fall kann das Element `<transport>` ignoriert werden. Das Element `<message>` legt jedoch fest, dass ein X.509-Zertifikat angegeben werden muss.  
  
```xml  
<wsHttpBinding>  
    <binding name="WSHttpBinding_ICalculator">  
       <security mode="Message">  
           <transport clientCredentialType="Windows"   
                      realm="" />  
           <message clientCredentialType="Certificate"   
                    negotiateServiceCredential="true"  
                    algorithmSuite="Default"   
                    establishSecurityContext="true" />  
       </security>  
    </binding>  
</wsHttpBinding>  
```  
  
 Wenn das Attribut `clientCredentialType` auf `"Windows"` festgelegt ist (siehe folgendes Beispiel), müssen Sie keinen tatsächlichen Wert der Anmeldeinformationen liefern. Dies liegt daran, dass die in Windows integrierte Sicherheit die tatsächlichen Anmeldeinformationen (ein Kerberos-Token) der Person liefert, die den Client ausführt.  
  
```xml  
<security mode="Message">  
    <transport clientCredentialType="Windows "   
        realm="" />  
</security>  
```  
  
### <a name="setting-the-client-credential-value"></a>Festlegen des Werts der Clientanmeldeinformationen  
 Wenn bestimmt wird, dass der Client Anmeldeinformationen liefern muss, müssen Sie die richtige Methode zum Konfigurieren des Clients verwenden. Wenden Sie z. B. zum Festlegen eines Clientzertifikats die Methode <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> an.  
  
 Eine gebräuchliche Form von Anmeldeinformationen ist das X.509-Zertifikat. Sie können die Anmeldeinformationen auf zwei Arten bereitstellen:  
  
-   Durch Programmieren in Ihren Clientcode (über die Methode `SetCertificate`).  
  
 Durch Hinzufügen einer [ \<Verhalten >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Abschnitt der Konfigurationsdatei für den Client und Verwenden der `clientCredentials` Element (siehe unten).  
  
#### <a name="setting-a-clientcredentials-value-in-code"></a>Festlegen einer \<ClientCredentials > Werts in Code  
 Festlegen einer [ \<ClientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) Wert in Code können Sie Zugriff auf die <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> Eigenschaft des der <xref:System.ServiceModel.ClientBase%601> Klasse. Die Eigenschaft gibt ein <xref:System.ServiceModel.Description.ClientCredentials>-Objekt zurück, das Zugriff auf verschiedene Typen von Anmeldeinformationen zulässt (siehe Tabelle unten).  
  
|ClientCredential-Eigenschaft|Beschreibung|Hinweise|  
|-------------------------------|-----------------|-----------|  
|<xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>|Gibt <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> zurück.|Stellt ein X.509-Zertifikat dar, das vom Client geliefert wird, um sich selbst am Dienst zu authentifizieren.|  
|<xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>|Gibt <xref:System.ServiceModel.Security.HttpDigestClientCredential> zurück.|Stellt HTTP-Digest-Anmeldeinformationen dar. Die Anmeldeinformationen sind ein Hash des Benutzernamens und des Kennworts.|  
|<xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>|Gibt <xref:System.ServiceModel.Security.IssuedTokenClientCredential> zurück.|Stellt ein benutzerdefiniertes Sicherheitstoken dar, das von einem Sicherheitstokendienst ausgegeben wird und normalerweise in Verbundszenarien verwendet wird.|  
|<xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>|Gibt <xref:System.ServiceModel.Security.PeerCredential> zurück.|Stellt auf einer Windows-Domäne Peeranmeldeinformationen für die Teilnahme in einem Peernetz dar.|  
|<xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>|Gibt <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential> zurück.|Stellt ein X.509-Zertifikat dar, das vom Dienst in einer Out-of-Band-Aushandlung geliefert wurde.|  
|<xref:System.ServiceModel.Description.ClientCredentials.UserName%2A>|Gibt <xref:System.ServiceModel.Security.UserNamePasswordClientCredential> zurück.|Stellt eine Kombination aus Benutzername und Kennwort dar.|  
|<xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>|Gibt <xref:System.ServiceModel.Security.WindowsClientCredential> zurück.|Stellt Windows-Clientanmeldeinformationen (Kerberos-Anmeldeinformationen) dar. Die Eigenschaften der Klasse sind schreibgeschützt.|  
  
#### <a name="setting-a-clientcredentials-value-in-configuration"></a>Festlegen einer \<ClientCredentials > Wert in der Konfiguration  
 Anmeldeinformationswerte gemäß unter Verwendung eines Endpunktverhaltens als untergeordnete Elemente von der [ \<ClientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) Element. Das verwendete Element hängt vom Typ der Clientanmeldeinformationen ab. Das folgende Beispiel zeigt z. B. die Konfiguration festzulegende ein x. 509-Zertifikat mit dem <[\<ClientCertificate >](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="myEndpointBehavior">  
          <clientCredentials>  
            <clientCertificate findvalue="myMachineName"   
            storeLocation="Current" X509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>              
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 Um die Clientanmeldeinformationen in der Konfiguration festzulegen, fügen eine [ \<EndpointBehaviors >](../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) Element der Konfigurationsdatei. Darüber hinaus muss die hinzugefügte verhaltenselement verknüpft werden, an den Dienst-Endpunkt mithilfe der `behaviorConfiguration` Attribut des der [ \<Endpunkt >](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) Element, wie im folgenden Beispiel gezeigt. Der Wert des `behaviorConfiguration`-Attributs muss dem Wert des Verhaltensattributs `name` entsprechen.  
  
 `<configuration>`  
  
 `<system.serviceModel>`  
  
 `<client>`  
  
 `<endpoint address="http://localhost/servicemodelsamples/service.svc"`  
  
 `binding="wsHttpBinding"`  
  
 `bindingConfiguration="Binding1"`  
  
 `behaviorConfiguration="myEndpointBehavior"`  
  
 `contract="Microsoft.ServiceModel.Samples.ICalculator" />`  
  
 `</client>`  
  
 `</system.serviceModel>`  
  
 `</configuration>`  
  
> [!NOTE]
>  Einige der Werte der Clientanmeldeinformationen können nicht über Anwendungskonfigurationsdateien festgelegt werden, u. a. der Benutzername und das Kennwort oder die Werte für den Windows-Benutzer und das Windows-Kennwort. Solche Werte für die Anmeldeinformationen können nur im Code angegeben werden.  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]die Clientanmeldeinformationen finden Sie unter [Vorgehensweise: Angeben der Clientanmeldeinformationswerte](../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
> [!NOTE]
>  `ClientCredentialType` wird ignoriert, wenn `SecurityMode` auf `"TransportWithMessageCredential",` festgelegt wird (siehe Beispielkonfiguration unten).  
  
```xml  
<wsHttpBinding>  
    <binding name="PingBinding">  
        <security mode="TransportWithMessageCredential"  >  
           <message  clientCredentialType="UserName"   
               establishSecurityContext="false"    
               negotiateServiceCredential="false" />  
           <transport clientCredentialType="Certificate"  />  
         </security>  
    </binding>  
</wsHttpBinding>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>  
 <xref:System.ServiceModel.ClientBase%601>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>  
 [\<Bindungen >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)  
 [Configuration Editor-Tool (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [Sichern von Diensten](../../../docs/framework/wcf/securing-services.md)  
 [Zugreifen auf Dienste mithilfe eines WCF-Clients](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md)  
 [Vorgehensweise: Angeben der Clientanmeldeinformationswerte](../../../docs/framework/wcf/how-to-specify-client-credential-values.md)  
 [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [Vorgehensweise: Angeben des Typs von Clientanmeldeinformationen](../../../docs/framework/wcf/how-to-specify-the-client-credential-type.md)
