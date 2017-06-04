---
title: "Sichern von Clients | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Clients [WCF], Überlegungen zur Sicherheit"
ms.assetid: 44c8578c-9a5b-4acd-8168-1c30a027c4c5
caps.latest.revision: 22
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 22
---
# Sichern von Clients
In [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] schreibt der Dienst die Sicherheitsanforderungen für Clients vor,d. h. der Dienst legt fest, welcher Sicherheitsmodus verwendet wird und ob der Client Anmeldeinformationen angeben muss oder nicht.Der Sicherungsvorgang an einem Client ist also unkompliziert: Man verwendet einfach die vom Dienst erhaltenen Metadaten \(sofern diese veröffentlicht wurden\) und erstellt einen Client.Die Metadaten geben an, wie der Client konfiguriert wird.Wenn der Dienst erfordert, dass der Client Anmeldeinformationen angibt, müssen Sie Anmeldeinformationen erhalten, die die Anforderung erfüllen.Dieses Thema beschreibt den Vorgang im Detail.[!INCLUDE[crabout](../../../includes/crabout-md.md)] zum Erstellen eines sicheren Diensts erhalten Sie unter [Sichern von Diensten](../../../docs/framework/wcf/securing-services.md).  
  
## Der Dienst legt die Sicherheit fest  
 Standardmäßig weisen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Bindungen aktivierte Sicherheitsfunktionen auf.\(Die Ausnahme ist <xref:System.ServiceModel.BasicHttpBinding>.\) Wenn der Dienst also über [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] erstellt wird, ist die Wahrscheinlichkeit größer, dass er Sicherheitsmaßnahmen umsetzt, um Authentifizierung, Vertraulichkeit und Integrität zu gewährleisten.In diesem Fall geben die vom Dienst bereitgestellten Metadaten an, was für den Aufbau eines sicheren Kommunikationskanals erforderlich ist.Wenn die Dienstmetadaten keine Sicherheitsanforderungen enthalten, gibt es keine Möglichkeit, einem Dienst ein Sicherheitsschema wie Secure Sockets Layer \(SSL\) über HTTP aufzuerlegen.Wenn jedoch der Dienst erfordert, dass der Client Anmeldeinformationen liefert, muss der Entwickler, Bereitsteller oder Administrator des Clients genau diejenigen Anmeldeinformationen liefern, die der Client zur Authentifizierung gegenüber dem Dienst nutzen wird.  
  
## Erlangen von Metadaten  
 Beim Erstellen eines Clients besteht der erste Schritt darin, die Metadaten für den Dienst zu erlangen, die der Client für die Kommunikation nutzen wird.Dazu gibt es zwei Möglichkeiten.Erstens: Wenn der Dienst einen Metadatenaustauschendpunkt \(MEX\-Endpunkt\) veröffentlicht oder seine Metadaten über HTTP oder HTTPS zur Verfügung stellt, können Sie die Metadaten mit dem [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) herunterladen, das sowohl Codedateien für einen Client als auch eine Konfigurationsdatei erstellt.\([!INCLUDE[crabout](../../../includes/crabout-md.md)] zur Verwendung des Tools finden Sie unter [Zugreifen auf Dienste mithilfe eines WCF\-Clients](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md).\) Wenn der Dienst keinen MEX\-Endpunkt veröffentlicht und keine Metadaten über HTTP oder HTTPS zur Verfügung stellt, müssen Sie den Dienstersteller um Dokumentation bitten, die die Sicherheitsanforderungen und die Metadaten beschreibt.  
  
> [!IMPORTANT]
>  Sie sollten darauf achten, dass die Metadaten von einer vertrauenswürdigen Quelle stammen und dass sie nicht manipuliert wurden.Über das HTTP\-Protokoll abgerufene Metadaten werden im Klartext gesendet und können manipuliert werden.Wenn der Dienst die Eigenschaften <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> und <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> verwendet, verwenden Sie den URL, den der Dienstersteller geliefert hat, um die Daten über das HTTPS\-Protokoll herunterzuladen.  
  
## Überprüfen von Sicherheit  
 Metadatenquellen können in zwei grundlegende Kategorien aufgeteilt werden: vertrauenswürdige Quellen und nicht vertrauenswürdige Quellen.Wenn Sie einer Quelle vertrauen und den Clientcode und andere Metadaten vom sicheren MEX\-Endpunkt der Quelle heruntergeladen haben, können Sie den Client erstellen, ihm die korrekten Anmeldeinformationen zuweisen und ihn ohne Bedenken ausführen.  
  
 Wenn Sie sich jedoch für ein Herunterladen eines Clients und von Metadaten von einer Quelle entscheiden, über die Sie nur wenig wissen, sollten Sie die vom Code verwendetenSicherheitsmaßnahmen überprüfen.Sie dürfen beispielsweise nicht einfach einen Client erstellen, der Ihre persönlichen oder finanziellen Daten an einen Dienst sendet, sofern der Dienst nicht zumindesten Vertraulichkeit und Integrität erfordert.Sie sollten dem Besitzer des Diensts soweit vertrauen, dass Sie bereit sind, Daten dieser Art an ihn weiterzugeben, da er auf sie zugreifen kann.  
  
 Als Regel sollten Sie daher, wenn Sie Code und Metadaten von einer nicht vertrauenswürdigen Quelle verwenden, den Code und die Metadaten überprüfen, um sicherzustellen, dass sie das von Ihnen benötigte Sicherheitsniveau erfüllen.  
  
## Festlegen von Clientanmeldeinformationen  
 Das Festlegen von Clientanmeldeinformationen auf einem Client erfolgt in zwei Schritten:  
  
1.  Bestimmen Sie den *Typ der Clientanmeldeinformationen*, den der Dienst erfordert.Dies wird durch eine der folgenden beiden Methoden erreicht.Erstens: Wenn Sie Dokumentation vom Dienstersteller besitzen, sollte diese den Typ der Clientanmeldeinformation \(sofern vorhanden\) angeben, der vom Dienst gefordert wird.Zweitens: Wenn Sie nur eine vom Svcutil.exe\-Tool erstellte Konfigurationsdatei besitzen, können Sie die einzelnen Bindungen untersuchen, um herauszufinden, welcher Typ von Anmeldeinformationen benötigt wird.  
  
2.  Geben Sie tatsächliche Clientanmeldeinformationen an.Die tatsächlichen Clientanmeldeinformationen werden als *Wert der Clientanmeldeinformationen* bezeichnet, um sie vom Typ zu unterscheiden.Wenn der Typ der Clientanmeldeinformationen beispielsweise ein Zertifikat angibt, müssen Sie ein X.509\-Zertifikat bereitstellen, das von einer Zertifizierungsstelle ausgestellt wurde, der der Dienst vertraut.  
  
### Bestimmen des Typs der Clientanmeldeinformationen  
 Wenn Sie die vom Svcutil.exe\-Tool erstellte Konfigurationsdatei besitzen, können Sie den Abschnitt [\<Bindungen\>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) untersuchen, um festzustellen, welcher Typ von Clientanmeldeinformationen benötigt wird.Innerhalb des Abschnitts befinden sich Bindungselemente, die die Sicherheitsanforderungen angeben.Untersuchen Sie besonders das \<Sicherheitselement\> jeder Bindung.Zu diesem Element gehört das Attribut `mode`, das Sie auf einen von drei möglichen Werten festlegen können \(`Message`, `Transport` oder `TransportWithMessageCredential`\).Der Wert des Attributs bestimmt den Modus, und der Modus legt fest, welches der untergeordneten Elemente von Bedeutung ist.  
  
 Das Element  `<security>``<transport>` kann entweder ein `<message>` \- oder ein \-Element oder beides enthalten.Das bedeutende Element ist dasjenige, das dem Sicherheitsmodus entspricht.Der folgende Code gibt beispielsweise an, dass der Sicherheitsmodus `"Message"` und der Typ der Clientanmeldeinformationen für das Element `<message>``"Certificate"` ist.In diesem Fall kann das Element `<transport>` ignoriert werden.Das Element `<message>` legt jedoch fest, dass ein X.509\-Zertifikat angegeben werden muss.  
  
```  
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
  
 Wenn das Attribut `clientCredentialType` auf `"Windows"` festgelegt ist \(siehe folgendes Beispiel\), müssen Sie keinen tatsächlichen Wert der Anmeldeinformationen liefern.Dies liegt daran, dass die in Windows integrierte Sicherheit die tatsächlichen Anmeldeinformationen \(ein Kerberos\-Token\) der Person liefert, die den Client ausführt.  
  
```  
<security mode="Message">  
    <transport clientCredentialType="Windows "   
        realm="" />  
</security>  
```  
  
### Festlegen des Werts der Clientanmeldeinformationen  
 Wenn bestimmt wird, dass der Client Anmeldeinformationen liefern muss, müssen Sie die richtige Methode zum Konfigurieren des Clients verwenden.Wenden Sie z. B. zum Festlegen eines Clientzertifikats die Methode <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> an.  
  
 Eine gebräuchliche Form von Anmeldeinformationen ist das X.509\-Zertifikat.Sie können die Anmeldeinformationen auf zwei Arten bereitstellen:  
  
-   Durch Programmieren in Ihren Clientcode \(über die Methode `SetCertificate`\).  
  
 Durch Hinzufügen eines [\<Verhalten\>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)\-Abschnitts für den Client in der Konfiguration und Verwenden des `clientCredentials`\-Elements \(siehe unten\).  
  
#### Festlegen eines \<clientCredentials\-\>\-Werts im Code  
 Zum Festlegen eines [\<clientCredentials\>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)\-Werts im Code müssen Sie auf die Eigenschaft <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> der Klasse <xref:System.ServiceModel.ClientBase%601> zugreifen.Die Eigenschaft gibt ein <xref:System.ServiceModel.Description.ClientCredentials>\-Objekt zurück, das Zugriff auf verschiedene Typen von Anmeldeinformationen zulässt \(siehe Tabelle unten\).  
  
|ClientCredential\-Eigenschaft|Beschreibung|Hinweise|  
|-----------------------------------|------------------|--------------|  
|<xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>|Gibt <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> zurück.|Stellt ein X.509\-Zertifikat dar, das vom Client geliefert wird, um sich selbst am Dienst zu authentifizieren.|  
|<xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>|Gibt <xref:System.ServiceModel.Security.HttpDigestClientCredential> zurück.|Stellt HTTP\-Digest\-Anmeldeinformationen dar.Die Anmeldeinformationen sind ein Hash des Benutzernamens und des Kennworts.|  
|<xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>|Gibt <xref:System.ServiceModel.Security.IssuedTokenClientCredential> zurück.|Stellt ein benutzerdefiniertes Sicherheitstoken dar, das von einem Sicherheitstokendienst ausgegeben wird und normalerweise in Verbundszenarien verwendet wird.|  
|<xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>|Gibt <xref:System.ServiceModel.Security.PeerCredential> zurück.|Stellt auf einer Windows\-Domäne Peeranmeldeinformationen für die Teilnahme in einem Peernetz dar.|  
|<xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>|Gibt <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential> zurück.|Stellt ein X.509\-Zertifikat dar, das vom Dienst in einer Out\-of\-Band\-Aushandlung geliefert wurde.|  
|<xref:System.ServiceModel.Description.ClientCredentials.UserName%2A>|Gibt <xref:System.ServiceModel.Security.UserNamePasswordClientCredential> zurück.|Stellt eine Kombination aus Benutzername und Kennwort dar.|  
|<xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>|Gibt <xref:System.ServiceModel.Security.WindowsClientCredential> zurück.|Stellt Windows\-Clientanmeldeinformationen \(Kerberos\-Anmeldeinformationen\) dar.Die Eigenschaften der Klasse sind schreibgeschützt.|  
  
#### Festlegen eines \<clientCredentials\-\>\-Werts in der Konfiguration  
 Werte für die Anmeldeinformationen werden angegeben, indem man ein Endpunktverhalten als untergeordnetes Element des [\<clientCredentials\>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)\-Elements verwendet.Das verwendete Element hängt vom Typ der Clientanmeldeinformationen ab.Das folgende Beispiel zeigt beispielsweise die Konfiguration zur Festlegung eines X.509\-Zertifikats mit \<[\<clientCertificate\>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).  
  
```  
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
  
 Zum Festlegen der Clientanmeldeinformationen in der Konfiguration, fügen Sie der Konfigurationsdatei ein [\<endpointBehaviors\>](../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)\-Element hinzu.Zusätzlich muss das hinzugefügte Verhaltenselement über das `behaviorConfiguration`\-Attribut des [\<endpoint\>](http://msdn.microsoft.com/de-de/13aa23b7-2f08-4add-8dbf-a99f8127c017)\-Elements mit dem Endpunkt des Diensts verknüpft werden \(siehe Beispiel unten\).Der Wert des `behaviorConfiguration`\-Attributs muss dem Wert des Verhaltensattributs `name` entsprechen.  
  
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
>  Einige der Werte der Clientanmeldeinformationen können nicht über Anwendungskonfigurationsdateien festgelegt werden, u. a. der Benutzername und das Kennwort oder die Werte für den Windows\-Benutzer und das Windows\-Kennwort.Solche Werte für die Anmeldeinformationen können nur im Code angegeben werden.  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)] zum Festlegen der Clientanmeldeinformationen finden Sie unter [Gewusst wie: Angeben der Clientanmeldeinformationswerte](../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
> [!NOTE]
>  `ClientCredentialType` wird ignoriert, wenn `SecurityMode` auf `"TransportWithMessageCredential",` festgelegt wird \(siehe Beispielkonfiguration unten\).  
  
```  
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
  
## Siehe auch  
 <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>   
 <xref:System.ServiceModel.ClientBase%601>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>   
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>   
 [\<Bindungen\>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)   
 [Configuration Editor\-Tool \(SvcConfigEditor.exe\)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)   
 [Sichern von Diensten](../../../docs/framework/wcf/securing-services.md)   
 [Zugreifen auf Dienste mithilfe eines WCF\-Clients](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md)   
 [Gewusst wie: Angeben der Clientanmeldeinformationswerte](../../../docs/framework/wcf/how-to-specify-client-credential-values.md)   
 [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [Vorgehensweise: Angeben des Typs von Clientanmeldeinformationen](../../../docs/framework/wcf/how-to-specify-the-client-credential-type.md)