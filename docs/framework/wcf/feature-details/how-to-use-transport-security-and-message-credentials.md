---
title: 'Vorgehensweise: Verwenden von Transportsicherheit und Nachrichtenanmeldeinformationen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TransportWithMessageCredentials
ms.assetid: 6cc35346-c37a-4859-b82b-946c0ba6e68f
ms.openlocfilehash: f9c90ac93a27f90479ee7225f62afb98a5000fe9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62047172"
---
# <a name="how-to-use-transport-security-and-message-credentials"></a>Vorgehensweise: Verwenden von Transportsicherheit und Nachrichtenanmeldeinformationen
Absichern eines Diensts mit sowohl Transport- und nachrichtenanmeldeinformationen vereint die Vorteile der Transport- und Sicherheitsmodi, in Windows Communication Foundation (WCF) auf. Während die Transport Layer Security (TLS) Integrität und Vertraulichkeit bietet, stellt die Message Layer Security (MLS) verschiedene Anmeldeinformationen bereit, die bei reinen Transportsicherheitsmechanismen nicht verfügbar sind. In diesem Thema werden die grundlegenden Schritte zur Implementierung des Transports mit Nachrichtenanmeldeinformationen mithilfe der Bindungen <xref:System.ServiceModel.WSHttpBinding> und <xref:System.ServiceModel.NetTcpBinding> veranschaulicht. Weitere Informationen zum Festlegen des Sicherheitsmodus finden Sie unter [Vorgehensweise: Festlegen des Sicherheitsmodus](../../../../docs/framework/wcf/how-to-set-the-security-mode.md).  
  
 Wenn Sie den Sicherheitsmodus auf `TransportWithMessageCredential` festlegen, wird der tatsächliche Mechanismus, der die Sicherheitseinstellungen auf Transportebene bereitstellt, vom Transport bestimmt. Der Secure Sockets Layer (SSL)-Mechanismus über HTTP (HTTPS) wird für HTTP verwendet, wohingegen SSL über TCP oder Windows für TCP verwendet wird.  
  
 Wenn der Transport HTTP ist (unter Verwendung der <xref:System.ServiceModel.WSHttpBinding>), dann wird die Sicherheit auf Transportebene von SSL über HTTP bereitgestellt. In diesem Fall müssen Sie den Computer, der als Host für den Dienst fungiert, mit einem SSL-Zertifikat konfigurieren, das an einen Anschluss gebunden ist. Dies wird im weiteren Verlauf des Themas noch näher erläutert.  
  
 Wenn der Transport TCP ist (unter Verwendung der <xref:System.ServiceModel.NetTcpBinding>), wird für die Sicherheit auf Transportebene standardmäßig die Windows-Sicherheit bereitgestellt oder SSL über TCP wird verwendet. Wenn Sie SSL über TCP verwenden, müssen Sie das Zertifikat mit der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>-Methode angeben. Dies wird im weiteren Verlauf des Themas noch näher erläutert.  
  
### <a name="to-use-the-wshttpbinding-with-a-certificate-for-transport-security-in-code"></a>So verwenden Sie die WSHttpBinding mit einem Zertifikat für die Transportsicherheit (im Code)  
  
1. Binden Sie ein SSL-Zertifikat mit dem Tool HttpCfg.exe an einen Anschluss auf dem Computer. Weitere Informationen finden Sie unter [Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).  
  
2. Erstellen Sie eine Instanz der <xref:System.ServiceModel.WSHttpBinding>-Klasse, und legen Sie die <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>-Eigenschaft auf <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential> fest.  
  
3. Legen Sie für die <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>-Eigenschaft einen geeigneten Wert fest. (Weitere Informationen finden Sie unter [Ausählen eines Anmeldeinformationentyps](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md).) Im folgenden Code wird der <xref:System.ServiceModel.MessageCredentialType.Certificate>-Wert verwendet.  
  
4. Erstellen Sie eine Instanz der <xref:System.Uri>-Klasse mit einer entsprechenden Basisadresse. Dabei muss das HTTPS-Schema verwendet werden, und die Adresse muss den tatsächlichen Namen des Computers sowie die Nummer des Anschlusses enthalten, an den das SSL-Zertifikat gebunden ist. (Sie können die Basisadresse auch in der Konfiguration festlegen.)  
  
5. Fügen Sie mit der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methode einen Dienstendpunkt hinzu.  
  
6. Erstellen Sie eine Instanz des <xref:System.ServiceModel.ServiceHost>, und rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode auf, wie im folgenden Code veranschaulicht.  
  
     [!code-csharp[c_SettingSecurityMode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#7)]
     [!code-vb[c_SettingSecurityMode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#7)]  
  
### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security-in-code"></a>So verwenden Sie die NetTcpBinding mit einem Zertifikat für die Transportsicherheit (im Code)  
  
1. Erstellen Sie eine Instanz der <xref:System.ServiceModel.NetTcpBinding>-Klasse, und legen Sie die <xref:System.ServiceModel.NetTcpSecurity.Mode%2A>-Eigenschaft auf <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential> fest.  
  
2. Legen Sie den <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> auf einen geeigneten Wert fest. Im folgenden Code wird der <xref:System.ServiceModel.MessageCredentialType.Certificate>-Wert verwendet.  
  
3. Erstellen Sie eine Instanz der <xref:System.Uri>-Klasse mit einer entsprechenden Basisadresse. Die Adresse muss das NET.TCP-Schema verwenden. (Sie können die Basisadresse auch in der Konfiguration festlegen.)  
  
4. Erstellen Sie die Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse.  
  
5. Legen Sie das X.509-Zertifikat für den Dienst mit der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>-Methode der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>-Klasse explizit fest.  
  
6. Fügen Sie mit der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methode einen Dienstendpunkt hinzu.  
  
7. Rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode auf, wie im folgenden Code dargestellt:  
  
     [!code-csharp[c_SettingSecurityMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#8)]
     [!code-vb[c_SettingSecurityMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#8)]  
  
### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security-in-code"></a>So verwenden Sie die NetTcpBinding mit Windows für die Transportsicherheit (im Code)  
  
1. Erstellen Sie eine Instanz der <xref:System.ServiceModel.NetTcpBinding>-Klasse, und legen Sie die <xref:System.ServiceModel.NetTcpSecurity.Mode%2A>-Eigenschaft auf <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential> fest.  
  
2. Legen Sie die Transportsicherheit auf Windows fest, indem Sie den <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> auf <xref:System.ServiceModel.TcpClientCredentialType.Windows> festlegen. (Dabei handelt es sich um die Standardeinstellung.)  
  
3. Legen Sie den <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> auf einen geeigneten Wert fest. Im folgenden Code wird der <xref:System.ServiceModel.MessageCredentialType.Certificate>-Wert verwendet.  
  
4. Erstellen Sie eine Instanz der <xref:System.Uri>-Klasse mit einer entsprechenden Basisadresse. Die Adresse muss das NET.TCP-Schema verwenden. (Sie können die Basisadresse auch in der Konfiguration festlegen.)  
  
5. Erstellen Sie die Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse.  
  
6. Legen Sie das X.509-Zertifikat für den Dienst mit der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>-Methode der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>-Klasse explizit fest.  
  
7. Fügen Sie mit der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methode einen Dienstendpunkt hinzu.  
  
8. Rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode auf, wie im folgenden Code dargestellt:  
  
     [!code-csharp[c_SettingSecurityMode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#9)]
     [!code-vb[c_SettingSecurityMode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#9)]  
  
## <a name="using-configuration"></a>Verwenden der Konfiguration  
  
#### <a name="to-use-the-wshttpbinding"></a>So verwenden Sie die WSHttpBinding  
  
1. Konfigurieren Sie den Computer mit einem SSL-Zertifikat, das an einen Anschluss gebunden ist. (Weitere Informationen finden Sie unter [Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)). Sie müssen nicht festlegen eine <`transport`>-Element den Wert mit dieser Konfiguration.  
  
2. Geben Sie den Typ der Anmeldeinformationen für den Client bezüglich der Sicherheit auf Nachrichtenebene an. Im folgenden Beispiel wird der `clientCredentialType` -Attribut der <`message`>-Element `UserName`.  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="WsHttpBinding_ICalculator">  
            <security mode="TransportWithMessageCredential" >  
               <message clientCredentialType="UserName" />  
            </security>  
    </binding>  
    </wsHttpBinding>  
    ```  
  
#### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security"></a>So verwenden Sie die NetTcpBinding mit einem Zertifikat für die Transportsicherheit  
  
1. Bei SSL über TCP müssen Sie das Zertifikat explizit im `<behaviors>`-Element angeben. Im folgenden Beispiel wird ein Zertifikat vom Aussteller am Standardspeicherort angegeben (lokaler Computer und persönlicher Speicher).  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
       <behavior name="mySvcBehavior">  
           <serviceCredentials>  
             <serviceCertificate findValue="contoso.com"  
                                 x509FindType="FindByIssuerName" />  
           </serviceCredentials>  
       </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
2. Hinzufügen einer [ \<NetTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) , im Abschnitt über Bindungen  
  
3. Fügen Sie ein Bindungselement hinzu, und legen Sie das `name`-Attribut auf einen geeigneten Wert fest.  
  
4. Hinzufügen einer <`security`>-Element, und legen die `mode` Attribut `TransportWithMessageCredential`.  
  
5. Hinzufügen einer <`message>` -Element, und legen die `clientCredentialType` -Attribut auf einen geeigneten Wert.  
  
    ```xml  
    <bindings>  
    <netTcpBinding>  
      <binding name="myTcpBinding">  
        <security mode="TransportWithMessageCredential" >  
           <message clientCredentialType="Windows" />  
        </security>  
      </binding>  
    </netTcpBinding>  
    </bindings>  
    ```  
  
#### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security"></a>So verwenden Sie die NetTcpBinding mit Windows für die Transportsicherheit  
  
1. Hinzufügen einer [ \<NetTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) Abschnitt Bindungen  
  
2. Hinzufügen einer <`binding`> Element, und legen die `name` -Attribut auf einen geeigneten Wert.  
  
3. Hinzufügen einer <`security`>-Element, und legen die `mode` Attribut `TransportWithMessageCredential`.  
  
4. Hinzufügen einer <`transport`> Element, und legen die `clientCredentialType` Attribut `Windows`.  
  
5. Hinzufügen einer <`message`> Element, und legen die `clientCredentialType` -Attribut auf einen geeigneten Wert. Im folgenden Code wird der Wert auf ein Zertifikat festgelegt.  
  
    ```xml  
    <bindings>  
    <netTcpBinding>  
      <binding name="myTcpBinding">  
        <security mode="TransportWithMessageCredential" >  
           <transport clientCredentialType="Windows" />  
           <message clientCredentialType="Certificate" />  
        </security>  
      </binding>  
    </netTcpBinding>  
    </bindings>  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Festlegen des Sicherheitsmodus](../../../../docs/framework/wcf/how-to-set-the-security-mode.md)
- [Sichern von Diensten](../../../../docs/framework/wcf/securing-services.md)
- [Sichern von Diensten und Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
