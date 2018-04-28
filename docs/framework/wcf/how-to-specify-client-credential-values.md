---
title: 'Gewusst wie: Angeben der Clientanmeldeinformationswerte'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 35244032a36af8d3d23fd9d88006ea032a99b44b
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-specify-client-credential-values"></a>Gewusst wie: Angeben der Clientanmeldeinformationswerte
Wenn Sie [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] verwenden, kann der Dienst angeben, wie ein Client für den Dienst authentifiziert wird. Ein Dienst kann beispielsweise festlegen, dass der Client mit einem Zertifikat authentifiziert wird.  
  
### <a name="to-determine-the-client-credential-type"></a>So bestimmen Sie den Typ der Clientanmeldeinformationen  
  
1.  Rufen Sie die Metadaten aus dem Metadatenendpunkt des Diensts ab. Die Metadaten umfassen in der Regel zwei Dateien: den Clientcode in der Programmiersprache Ihrer Wahl (die Standardeinstellung ist Visual C#) und eine XML-Konfigurationsdatei. Eine Möglichkeit zum Abrufen der Metadaten ist, das Tool "Svcutil.exe" zu verwenden, um den Clientcode und die Clientkonfiguration zurückzugeben. Weitere Informationen finden Sie unter [Abrufen von Metadaten](../../../docs/framework/wcf/feature-details/retrieving-metadata.md) und [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
2.  Öffnen Sie die XML-Konfigurationsdatei. Wenn Sie das Tool "Svcutil.exe" verwenden, lautet der Standardname der Datei "Output.config".  
  
3.  Suchen der  **\<Sicherheit >** Element mit dem **Modus** Attribut (**< Sicherheitsmodus =** `MessageOrTransport` **>** , in dem `MessageOrTransport` auf einen der Sicherheitsmodi festgelegt ist.  
  
4.  Suchen Sie nach dem untergeordneten Element, das dem Moduswert entspricht. Wenn der Modus festgelegt ist z. B. **Nachricht**, suchen die  **\<Nachricht >** in enthaltenen Elementen der  **\<Sicherheit >** Element.  
  
5.  Beachten Sie den zugewiesenen Wert der **ClientCredentialType** Attribut. Der tatsächliche Wert hängt davon ab, welcher Modus verwendet wird: Transport oder Nachricht.  
  
 Der folgende XML-Code veranschaulicht die Konfiguration für einen Client, der die Nachrichtensicherheit verwendet und ein Zertifikat zum Authentifizieren des Clients erfordert.  
  
```xml  
<security mode="Message">  
    <transport clientCredentialType="Windows" proxyCredentialType="None"  
        realm="" />  
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"  
    algorithmSuite="Default" establishSecurityContext="true" />  
</security>  
```  
  
## <a name="example-tcp-transport-mode-with-certificate-as-client-credential"></a>Beispiel: TCP-Transportmodus mit einem Zertifikat als Clientanmeldeinformationen  
 In diesem Beispiel wird der Sicherheitsmodus auf "Transport" und der Clientanmeldeinformationswert auf ein X.509-Zertifikat festgelegt. Die folgenden Vorgänge zeigen, wie Sie den Clientanmeldeinformationswert für den Client im Code und in der Konfiguration festlegen können. Dabei wird vorausgesetzt, dass Sie verwendet haben, die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) die Metadaten (Code und Konfiguration) vom Dienst zurückgegeben. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines Clients](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-code"></a>So legen Sie den Clientanmeldeinformationswert für den Client im Code fest  
  
1.  Verwenden der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) zum Generieren von Code und die Konfiguration des Diensts.  
  
2.  Erstellen Sie mit dem generierten Code eine Instanz des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clients.  
  
3.  Legen Sie für die Clientklasse die <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>-Eigenschaft der <xref:System.ServiceModel.ClientBase%601>-Klasse auf einen geeigneten Wert fest. In diesem Beispiel wird die Eigenschaft auf ein X.509-Zertifikat mit der <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>-Methode der <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>-Klasse festgelegt.  
  
     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]  
  
     Sie können jede beliebige Enumeration der <xref:System.Security.Cryptography.X509Certificates.X509FindType>-Klasse verwenden. Der Betreffname wird hier verwendet, für den Fall, dass das Zertifikat (aufgrund des Ablaufdatums) geändert wird. Anhand des Betreffnamens kann die Infrastruktur das Zertifikat wieder suchen.  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-configuration"></a>So legen Sie den Clientanmeldeinformationswert für den Client in der Konfiguration fest  
  
1.  Hinzufügen einer [ \<Verhalten >](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) Element an der [ \<Verhalten >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Element.  
  
2.  Hinzufügen einer [ \<ClientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) Element an der [ \<Verhalten >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Element. Achten Sie darauf, für das erforderliche `name`-Attribut einen geeigneten Wert festzulegen.  
  
3.  Hinzufügen einer [ \<ClientCertificate >](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) Element an der [ \<ClientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) Element.  
  
4.  Legen Sie für die folgenden Attribute geeignete Werte fest: `storeLocation`, `storeName`, `x509FindType` und `findValue`, wie im folgenden Code dargestellt. [!INCLUDE[crabout](../../../includes/crabout-md.md)] Zertifikate, finden Sie unter [arbeiten mit Zertifikaten](../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
    ```xml  
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
  
5.  Wenn Sie den Client konfigurieren, legen Sie das Verhalten fest, indem Sie das `behaviorConfiguration`-Attribut des `<endpoint>`-Elements festlegen, wie im folgenden Code dargestellt. Das Element ist ein untergeordnetes Element von der [ \<Client >](../../../docs/framework/configure-apps/file-schema/wcf/client.md) Element. Geben Sie auch den Namen der Bindungskonfiguration an, indem Sie das `bindingConfiguration`-Attribut auf die Bindung für den Client festlegen. Wenn Sie eine generierte Konfigurationsdatei verwenden, wird der Name der Bindung automatisch erstellt. In diesem Beispiel lautet der Name `"tcpBindingWithCredential"`.  
  
    ```xml  
    <client>  
      <endpoint name =""  
                address="net.tcp://contoso.com:8036/aloha"  
                binding="netTcpBinding"  
                bindingConfiguration="tcpBindingWithCredential"  
                behaviorConfiguration="endpointCredentialBehavior" />  
    </client>  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.NetTcpBinding>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>  
 <xref:System.ServiceModel.ClientBase%601>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>  
 [Programmieren der WCF-Sicherheit](../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 [Ausählen eines Anmeldeinformationentyps](../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [Arbeiten mit Zertifikaten](../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Vorgehensweise: Erstellen eines Clients](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [\<netTcpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)  
 [\<security>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)  
 [\<message>](../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)  
 [\<behavior>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)  
 [\<behaviors>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)  
 [\<ClientCertificate >](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)  
 [\<clientCredentials>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)
