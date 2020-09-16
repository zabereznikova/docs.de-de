---
title: Übersicht über die Transportsicherheit
description: Erfahren Sie mehr über die wichtigsten Transport Sicherheitsmechanismen in den vom System bereitgestellten WCF-Bindungen. Diese Sicherheitsmechanismen sind abhängig von der verwendeten Bindung und dem verwendeten Transport.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 00959326-aa9d-44d0-af61-54933d4adc7f
ms.openlocfilehash: 8780b9c0fc06a49ddaf42166c292a41e9124f6e1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556797"
---
# <a name="transport-security-overview"></a>Übersicht über die Transportsicherheit
Transport Sicherheitsmechanismen in Windows Communication Foundation (WCF) richten sich nach der verwendeten Bindung und dem verwendeten Transport. Wenn Sie z. B. die <xref:System.ServiceModel.WSHttpBinding>-Klasse verwenden, lautet der Transportmechanismus HTTP, und der primäre Mechanismus zum Sichern des Transports ist Secure Sockets Layer (SSL) über HTTP, allgemein als HTTPS bezeichnet. In diesem Thema werden die wichtigsten Transport Sicherheitsmechanismen erläutert, die in den vom WCF-System bereitgestellten Bindungen verwendet werden.  
  
> [!NOTE]
> Wenn SSL-Sicherheit mit .NET Framework 3,5 und höher verwendet wird, verwendet ein WCF-Client sowohl die zwischen Zertifikate im Zertifikat Speicher als auch die zwischen Zertifikate, die während der SSL-Aushandlung empfangen werden, um die Überprüfung der Zertifikat Kette für das Dienst Zertifikat durchzuführen. Bei .NET Framework 3.0 werden nur die im lokalen Zertifikatspeicher installierten Zwischenzertifikate verwendet.  
  
> [!WARNING]
> Wenn die Transportsicherheit verwendet wird, kann die <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType>-Eigenschaft überschrieben werden. Um dies zu verhindern, legen <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A?displayProperty=nameWithType> Sie auf fest <xref:System.ServiceModel.Description.PrincipalPermissionMode.None?displayProperty=nameWithType> . <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> ist ein Dienstverhalten, das für die Dienstbeschreibung festgelegt werden kann.  
  
## <a name="basichttpbinding"></a>BasicHttpBinding  
 Die <xref:System.ServiceModel.BasicHttpBinding>-Klasse bietet standardmäßig keine Sicherheit. Diese Bindung ist für die Interoperabilität mit Webdienstanbietern ausgelegt, die keine Sicherheit implementieren. Sie können jedoch die Sicherheit aktivieren, indem Sie die <xref:System.ServiceModel.BasicHttpSecurity.Mode%2A>-Eigenschaft auf einen beliebigen Wert außer <xref:System.ServiceModel.BasicHttpSecurityMode.None> festlegen. Wenn Sie die Transportsicherheit aktivieren möchten, legen Sie die Eigenschaft auf <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> fest.  
  
### <a name="interoperation-with-iis"></a>Interoperieren mit IIS  
 Die <xref:System.ServiceModel.BasicHttpBinding>-Klasse wird hauptsächlich für die Interoperation mit bereits vorhandenen Webdiensten verwendet. Viele dieser Dienste werden von Internetinformationsdienste (IIS) gehostet. Deshalb ist die Transportsicherheit für diese Bindung auf die nahtlose Interoperation mit IIS-Websites ausgerichtet. Dies geschieht durch Festlegen des Sicherheitsmodus auf <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> und anschließendes Festlegen des Client-Anmeldeinformationstyps. Die Werte für die Anmeldeinformationstypen entsprechen den IIS-Verzeichnissicherheitsmechanismen. Der folgende Code zeigt den festgelegten Modus und einen Anmeldeinformationstyp, der auf Windows festgelegt ist. Sie können diese Konfiguration verwenden, wenn sich Client und Server in derselben Windows-Domäne befinden.  
  
 [!code-csharp[c_ProgrammingSecurity#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#10)]
 [!code-vb[c_ProgrammingSecurity#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#10)]  
  
 Oder in der Konfiguration:  
  
```xml  
<bindings>  
  <basicHttpBinding>  
    <binding name="SecurityByTransport">  
      <security mode="Transport">  
        <transport clientCredentialType="Windows" />  
       </security>  
     </binding>  
  </basicHttpBinding>  
</bindings>  
```  
  
 In den folgenden Abschnitten werden andere Client-Anmeldeinformationstypen erläutert.  
  
#### <a name="basic"></a>Standard  
 Dies entspricht der Authentifizierungsmethode Standard in IIS. Wenn Sie diesen Modus verwenden, muss der IIS-Server mit Windows-Benutzerkonten und den entsprechenden NTFS-Dateisystemberechtigungen konfiguriert sein. Weitere Informationen zu IIS 6,0 finden Sie unter [Aktivieren der Standard Authentifizierung und Konfigurieren des Bereichs namens](/previous-versions/windows/it-pro/windows-server-2003/cc785293(v=ws.10)). Weitere Informationen zu IIS 7,0 finden Sie unter [Konfigurieren der Standard Authentifizierung (IIS 7)](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772009(v=ws.10)).  
  
#### <a name="certificate"></a>Zertifikat  
 IIS verfügt über eine Option, mit der sich die Clients mit einem Zertifikat anmelden müssen. Mit dieser Funktion können die Internetinformationsdienste auch einem Windows-Konto ein Clientzertifikat zuordnen. Weitere Informationen zu IIS 6,0 finden Sie unter [Aktivieren von Client Zertifikaten in IIS 6,0](/previous-versions/windows/it-pro/windows-server-2003/cc727994(v=ws.10)). Weitere Informationen zu IIS 7,0 finden Sie unter [Konfigurieren von Server Zertifikaten in IIS 7](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732230(v=ws.10)).  
  
#### <a name="digest"></a>Digest  
 Die Hashwertauthentifizierung ähnelt der Standardauthentifizierung, bietet jedoch den Vorteil, die Anmeldeinformationen als Hash zu senden und nicht als Klartext. Weitere Informationen zu IIS 6,0 finden Sie unter [Digest-Authentifizierung in IIS 6,0](/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)). Weitere Informationen zu IIS 7,0 finden Sie unter [Konfigurieren der Digest-Authentifizierung (IIS 7)](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc754104(v=ws.10)).  
  
#### <a name="windows"></a>Windows  
 Dies entspricht der integrierten Windows-Authentifizierungsmethode in IIS. Bei dieser Methode muss sich auch der Server in einer Windows-Domäne befinden, die das Kerberos-Protokoll als Domänencontroller verwendet. Falls sich der Server nicht in einer Kerberos-Domäne befindet oder falls das Kerberos-System fehlschlägt, können Sie den im nächsten Abschnitt beschriebenen NTLM-Wert verwenden. Weitere Informationen zu IIS 6,0 finden Sie unter [integrierte Windows-Authentifizierung in IIS 6,0](/previous-versions/windows/it-pro/windows-server-2003/cc738016(v=ws.10)). Weitere Informationen zu IIS 7,0 finden Sie unter [Konfigurieren von Server Zertifikaten in IIS 7](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732230(v=ws.10)).
  
#### <a name="ntlm"></a>NTLM  
 Dadurch kann der Server NTLM für die Authentifizierung verwenden, falls das Kerberos-Protokoll fehlschlägt. Weitere Informationen zum Konfigurieren von IIS in IIS 6,0 finden Sie unter [erzwingen der NTLM-Authentifizierung](/previous-versions/windows/it-pro/windows-server-2003/cc786486(v=ws.10)). Für IIS 7,0 enthält die Windows-Authentifizierung die NTLM-Authentifizierung. Weitere Informationen finden Sie unter [Konfigurieren von Serverzertifikaten in IIS 7.0](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732230(v=ws.10)).
  
## <a name="wshttpbinding"></a>WsHttpBinding  
 Die <xref:System.ServiceModel.WSHttpBinding>-Klasse ist für die Zusammenarbeit mit Diensten vorgesehen, die WS-*-Spezifikationen implementieren. Die Transportsicherheit für diese Bindung ist SSL (Secure Sockets Layer) über HTTP oder HTTPS. Zum Erstellen einer WCF-Anwendung, die SSL verwendet, verwenden Sie IIS zum Hosten der Anwendung. Wenn Sie eine selbst gehostete Anwendung erstellen, können Sie mit dem Tool HttpCfg.exe ein X.509-Zertifikat an einen bestimmten Anschluss eines Computers binden. Die Portnummer wird als Teil der WCF-Anwendung als Endpunkt Adresse angegeben. Bei Verwendung des Transportmodus muss die Endpunktadresse das HTTPS-Protokoll enthalten. Andernfalls wird zur Laufzeit eine Ausnahme ausgelöst. Weitere Informationen finden Sie unter [http-Transport Sicherheit](http-transport-security.md).  
  
 Legen Sie zur Clientauthentifizierung die <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>-Eigenschaft der <xref:System.ServiceModel.HttpTransportSecurity>-Klasse auf einen der <xref:System.ServiceModel.HttpClientCredentialType>-Enumerationswerte fest. Die Enumerationswerte sind identisch mit den Client-Anmeldeinformationstypen für <xref:System.ServiceModel.BasicHttpBinding> und sind darauf ausgerichtet, mit IIS-Diensten gehostet zu werden.  
  
 Das folgende Beispiel zeigt die mit einem Client-Anmeldeinformationstyp von Windows verwendete Bindung.  
  
 [!code-csharp[c_ProgrammingSecurity#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#11)]
 [!code-vb[c_ProgrammingSecurity#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#11)]  
  
## <a name="wsdualhttpbinding"></a>WSDualHttpBinding  
 Diese Bindung bietet lediglich Sicherheit auf Nachrichtenebene, nicht Sicherheit auf Transportebene.  
  
## <a name="nettcpbinding"></a>NetTcpBinding  
 Die <xref:System.ServiceModel.NetTcpBinding>-Klasse verwendet TCP für den Nachrichtentransport. Die Sicherheit für den Transportmodus wird über die Implementierung von TLS über TCP bereitgestellt. Die TLS-Implementierung wird vom Betriebssystem bereitgestellt.  
  
 Sie können auch den Client-Anmeldeinformationstyp angeben, indem Sie die <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A>-Eigenschaft der <xref:System.ServiceModel.TcpTransportSecurity>-Klasse auf einen der <xref:System.ServiceModel.TcpClientCredentialType>-Werte festlegen, wie im folgenden Code dargestellt.  
  
 [!code-csharp[c_ProgrammingSecurity#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#12)]
 [!code-vb[c_ProgrammingSecurity#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#12)]  
  
#### <a name="client"></a>Client  
 Auf dem Client müssen Sie mit der <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>-Methode der <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>-Klasse ein Zertifikat angeben.  
  
> [!NOTE]
> Wenn Sie die Windows-Sicherheit verwenden, ist kein Zertifikat erforderlich.  
  
 Der folgende Code verwendet den Fingerabdruck des Zertifikats, der es eindeutig identifiziert. Weitere Informationen zu Zertifikaten finden Sie unter [Arbeiten mit Zertifikaten](working-with-certificates.md).  
  
 [!code-csharp[c_ProgrammingSecurity#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#13)]
 [!code-vb[c_ProgrammingSecurity#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#13)]  
  
 Alternativ können Sie das Zertifikat in der Konfiguration des Clients mit einem- [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md) Element im Verhaltens Abschnitt angeben.  
  
```xml  
<behaviors>  
  <behavior>  
   <clientCredentials>  
     <clientCertificate findValue= "101010101010101010101010101010000000000"
      storeLocation="LocalMachine" storeName="My"
      X509FindType="FindByThumbPrint">  
     </clientCertificate>  
   </clientCredentials>  
 </behavior>  
</behaviors>
```  
  
## <a name="netnamedpipebinding"></a>NetNamedPipeBinding  
 Die <xref:System.ServiceModel.NetNamedPipeBinding>-Klasse ist für eine effiziente Kommunikation zwischen verschiedenen Computern ausgerichtet, d. h. für Prozesse, die auf demselben Computer ausgeführt werden, obwohl zwischen zwei Computern im selben Netzwerk Named Pipe-Kanäle erstellt werden können. Diese Bindung bietet lediglich Sicherheit auf Transportebene. Wenn Sie mit dieser Bindung Anwendungen erstellen, müssen die Endpunktadressen „net.pipe“ als Protokoll der Endpunktadresse enthalten.  
  
## <a name="wsfederationhttpbinding"></a>WSFederationHttpBinding  
 Wenn Sie Transportsicherheit verwenden, erfolgt diese Bindung mit SSL über HTTP (als HTTPS bezeichnet) und einem ausgestellten Token (<xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential>). Weitere Informationen zu Verbund Anwendungen finden Sie unter Verbund [-und ausgestellte Token](federation-and-issued-tokens.md).  
  
## <a name="netpeertcpbinding"></a>NetPeerTcpBinding  
 Die <xref:System.ServiceModel.NetPeerTcpBinding>-Klasse stellt einen sicheren Transportmechanismus dar, ausgerichtet auf eine effektive Kommunikation, die die Peer-to-Peer-Netzwerkfunktion verwendet. Wie anhand des Namens der Klasse und der Bindung angegeben, ist TCP das Protokoll. Wenn der Sicherheitsmodus auf Transport festgelegt ist, implementiert die Bindung TLS über TCP. Weitere Informationen zur Peer-zu-Peer-Funktion finden Sie unter [Peer-to-Peer-Netzwerke](peer-to-peer-networking.md).  
  
## <a name="msmqintegrationbinding-and-netmsmqbinding"></a>MsmqIntegrationBinding und NetMsmqBinding  
 Eine umfassende Erläuterung der Transportsicherheit mit Message Queuing (zuvor als MSMQ bezeichnet) finden [Sie unter Sichern von Nachrichten mit Transportsicherheit](securing-messages-using-transport-security.md).  
  
## <a name="see-also"></a>Siehe auch

- [Programmieren der WCF-Sicherheit](programming-wcf-security.md)
