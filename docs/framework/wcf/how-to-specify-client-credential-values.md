---
title: "Gewusst wie: Angeben der Clientanmeldeinformationswerte | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
caps.latest.revision: 28
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 28
---
# Gewusst wie: Angeben der Clientanmeldeinformationswerte
Wenn Sie [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] verwenden, kann der Dienst angeben, wie ein Client für den Dienst authentifiziert wird.  Ein Dienst kann beispielsweise festlegen, dass der Client mit einem Zertifikat authentifiziert wird.  
  
### So bestimmen Sie den Typ der Clientanmeldeinformationen  
  
1.  Rufen Sie die Metadaten aus dem Metadatenendpunkt des Diensts ab.  Die Metadaten umfassen in der Regel zwei Dateien: den Clientcode in der Programmiersprache Ihrer Wahl \(die Standardeinstellung ist Visual C\#\) und eine XML\-Konfigurationsdatei.  Eine Möglichkeit zum Abrufen der Metadaten ist, das Tool "Svcutil.exe" zu verwenden, um den Clientcode und die Clientkonfiguration zurückzugeben.  Weitere Informationen finden Sie unter [Abrufen von Metadaten](../../../docs/framework/wcf/feature-details/retrieving-metadata.md) und [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
2.  Öffnen Sie die XML\-Konfigurationsdatei.  Wenn Sie das Tool "Svcutil.exe" verwenden, lautet der Standardname der Datei "Output.config".  
  
3.  Suchen Sie nach dem **\<security\>**\-Element mit dem **mode**\-Attribut \(**\<security mode \=** `MessageOrTransport`**\>**, wobei `MessageOrTransport` auf einen der Sicherheitsmodi festgelegt ist.  
  
4.  Suchen Sie nach dem untergeordneten Element, das dem Moduswert entspricht.  Wenn der Modus beispielsweise auf **Nachricht** festgelegt ist, suchen Sie nach dem **\<message\>**\-Element, das im **\<security\>**\-Element enthalten ist.  
  
5.  Beachten Sie den Wert, der dem **clientCredentialType**\-Attribut zugeordnet ist.  Der tatsächliche Wert hängt davon ab, welcher Modus verwendet wird: Transport oder Nachricht.  
  
 Der folgende XML\-Code veranschaulicht die Konfiguration für einen Client, der die Nachrichtensicherheit verwendet und ein Zertifikat zum Authentifizieren des Clients erfordert.  
  
```  
<security mode="Message">  
    <transport clientCredentialType="Windows" proxyCredentialType="None"  
        realm="" />  
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"  
    algorithmSuite="Default" establishSecurityContext="true" />  
</security>  
```  
  
## Beispiel: TCP\-Transportmodus mit einem Zertifikat als Clientanmeldeinformationen  
 In diesem Beispiel wird der Sicherheitsmodus auf "Transport" und der Clientanmeldeinformationswert auf ein X.509\-Zertifikat festgelegt.  Die folgenden Vorgänge zeigen, wie Sie den Clientanmeldeinformationswert für den Client im Code und in der Konfiguration festlegen können.  Dabei wird davon ausgegangen, dass Sie das [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) verwendet haben, um die Metadaten \(Code und Konfiguration\) vom Dienst zurückzugeben.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Vorgehensweise: Erstellen eines Clients](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
#### So legen Sie den Clientanmeldeinformationswert für den Client im Code fest  
  
1.  Verwenden Sie das [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), um Code und Konfiguration aus dem Dienst zu generieren.  
  
2.  Erstellen Sie mit dem generierten Code eine Instanz des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clients.  
  
3.  Legen Sie für die Clientklasse die <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>\-Eigenschaft der <xref:System.ServiceModel.ClientBase%601>\-Klasse auf einen geeigneten Wert fest.  In diesem Beispiel wird die Eigenschaft auf ein X.509\-Zertifikat mit der <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>\-Methode der <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>\-Klasse festgelegt.  
  
     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]  
  
     Sie können jede beliebige Enumeration der <xref:System.Security.Cryptography.X509Certificates.X509FindType>\-Klasse verwenden.  Der Betreffname wird hier verwendet, für den Fall, dass das Zertifikat \(aufgrund des Ablaufdatums\) geändert wird.  Anhand des Betreffnamens kann die Infrastruktur das Zertifikat wieder suchen.  
  
#### So legen Sie den Clientanmeldeinformationswert für den Client in der Konfiguration fest  
  
1.  Fügen Sie ein [\<Verhalten\>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)\-Element zum [\<Verhalten\>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)\-Element hinzu.  
  
2.  Fügen Sie ein [\<clientCredentials\>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)\-Element zum [\<Verhalten\>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)\-Element hinzu.  Achten Sie darauf, für das erforderliche `name`\-Attribut einen geeigneten Wert festzulegen.  
  
3.  Fügen Sie ein [\<clientCertificate\>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)\-Element zum [\<clientCredentials\>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)\-Element hinzu.  
  
4.  Legen Sie für die folgenden Attribute geeignete Werte fest: `storeLocation`, `storeName`, `x509FindType` und `findValue`, wie im folgenden Code dargestellt.  [!INCLUDE[crabout](../../../includes/crabout-md.md)] Zertifikaten finden Sie unter [Verwenden von Zertifikaten](../../../docs/framework/wcf/feature-details/working-with-certificates.md)￼.  
  
    ```  
    <behaviors>  
       <endpointBehaviors>  
          <behavior name="endpointCredentialBehavior">  
            <clientCredentials>  
              <clientCertificate findValue="Contoso.com"   
                                 storeLocation="LocalMachine"  
                                 storeName="TrustedPeople"  
                                 x509FindType="FindBySubjectName" />  
            </clientCredentials>  
          </behavior>  
       </endpointBehaviors>  
    </behaviors>  
    ```  
  
5.  Wenn Sie den Client konfigurieren, legen Sie das Verhalten fest, indem Sie das `behaviorConfiguration`\-Attribut des `<endpoint>`\-Elements festlegen, wie im folgenden Code dargestellt.  Das Endpunktelement ist dem [\<client\>](../../../docs/framework/configure-apps/file-schema/wcf/client.md)\-Element untergeordnet.  Geben Sie auch den Namen der Bindungskonfiguration an, indem Sie das `bindingConfiguration`\-Attribut auf die Bindung für den Client festlegen.  Wenn Sie eine generierte Konfigurationsdatei verwenden, wird der Name der Bindung automatisch erstellt.  In diesem Beispiel lautet der Name `"tcpBindingWithCredential"`.  
  
    ```  
    <client>  
      <endpoint name =""  
                address="net.tcp://contoso.com:8036/aloha"  
                binding="netTcpBinding"  
                bindingConfiguration="tcpBindingWithCredential"  
                behaviorConfiguration="endpointCredentialBehavior" />  
    </client>  
    ```  
  
## Siehe auch  
 <xref:System.ServiceModel.NetTcpBinding>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>   
 <xref:System.ServiceModel.ClientBase%601>   
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>   
 [Programmieren der WCF\-Sicherheit](../../../docs/framework/wcf/feature-details/programming-wcf-security.md)   
 [Wählen eines Typs von Anmeldeinformationen](../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)   
 [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [Verwenden von Zertifikaten](../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Vorgehensweise: Erstellen eines Clients](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)   
 [\<netTcpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)   
 [\<Sicherheit\>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)   
 [\<message\>](../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)   
 [\<Verhalten\>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)   
 [\<Verhalten\>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)   
 [\<clientCertificate\>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)   
 [\<clientCredentials\>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)