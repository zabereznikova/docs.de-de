---
title: Programmieren der WCF-Sicherheit
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message security [WCF], programming overview
ms.assetid: 739ec222-4eda-4cc9-a470-67e64a7a3f10
ms.openlocfilehash: 2b3c96e91c0d6f01fa30b3b617449e7d4a148933
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596772"
---
# <a name="programming-wcf-security"></a>Programmieren der WCF-Sicherheit
In diesem Thema werden die grundlegenden Programmieraufgaben beschrieben, die zum Erstellen einer Secure Windows Communication Foundation (WCF)-Anwendung verwendet werden. In diesem Thema werden nur Authentifizierung, Vertraulichkeit und Integrität behandelt, die zusammen als *Übertragungssicherheit*bezeichnet werden. In diesem Thema wird die Autorisierung (Kontrolle des Zugriffs auf Ressourcen oder Dienste) nicht behandelt. Informationen zur Autorisierung finden Sie unter [Autorisierung](authorization-in-wcf.md).  
  
> [!NOTE]
> Eine wertvolle Einführung in Sicherheitskonzepte, insbesondere im Hinblick auf WCF, finden Sie in den Tutorials zu Mustern und Vorgehensweisen auf MSDN unter [Szenarien, Muster und Implementierungs Leit Faden für Web Services-Erweiterungen (WSE) 3,0](https://docs.microsoft.com/previous-versions/msp-n-p/ff648183(v=pandp.10)).  
  
 Das Programmieren der WCF-Sicherheit basiert auf drei Schritten, die Folgendes festlegen: der Sicherheitsmodus, ein Client Anmelde Informationstyp und die Anmelde Informationswerte. Sie können diese Schritte durch Code oder die Konfiguration durchführen.  
  
## <a name="setting-the-security-mode"></a>Festlegen des Sicherheitsmodus  
 Im folgenden werden die allgemeinen Schritte zum Programmieren mit dem Sicherheitsmodus in WCF erläutert:  
  
1. Wählen Sie eine der vordefinierten Bindungen, die den Anwendungsanforderungen entsprechen. Eine Liste der Bindungs Optionen finden Sie unter vom [System bereitgestellte Bindungen](../system-provided-bindings.md). Standardmäßig ist beinahe jede Bindung sicherheitsaktiviert. Die einzige Ausnahme ist die- <xref:System.ServiceModel.BasicHttpBinding> Klasse (mithilfe der-Konfiguration, der [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) ).  
  
     Durch die von Ihnen ausgewählte Bindung bestimmen Sie auch den Transport. <xref:System.ServiceModel.WSHttpBinding> verwendet beispielsweise HTTP als Transportmethode, <xref:System.ServiceModel.NetTcpBinding> verwendet TCP.  
  
2. Wählen Sie einen der Sicherheitsmodi für die Bindung aus. Beachten Sie, dass die von Ihnen ausgewählte Bindung auch die Verfügbarkeit der Modi beeinflusst. Die <xref:System.ServiceModel.WSDualHttpBinding> ermöglicht beispielsweise keine Transportsicherheit. (Sie steht nicht als Option zur Verfügung.) Auf ähnliche Weise ermöglichen weder <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> noch <xref:System.ServiceModel.NetNamedPipeBinding> die Nachrichtensicherheit.  
  
     Sie haben drei Möglichkeiten:  
  
    1. `Transport`  
  
         Die Transportsicherheit ist vom Mechanismus abhängig, den die ausgewählte Bindung verwendet. Wenn Sie beispielsweise `WSHttpBinding` verwenden, wird als Sicherheitsmechanismus Secure Sockets Layer (SSL) verwendet, was auch der Mechanismus für das HTTPS-Protokoll ist. Der Hauptvorteil der Transportsicherheit besteht im Allgemeinen darin, dass sie unabhängig von der Transportmethode einen guten Durchsatz ermöglicht. Es gibt jedoch zwei Einschränkungen: Der Transportmechanismus bestimmt den Anmeldeinformationstyp, der zum Authentifizieren eines Benutzers verwendet wird. Dies ist jedoch nur dann von Nachteil, wenn ein Dienst mit anderen Diensten zusammenarbeiten muss, für die unterschiedliche Anmeldeinformationstypen notwendig sind. Darüber hinaus wird die Sicherheit nicht auf Nachrichtenebene angewendet, vielmehr wird die Sicherheit per Hop-by-Hop-Methode anstelle einer End-to-End-Methode implementiert. Diese zweite Einschränkung ist nur dann ein Problem, wenn der Nachrichtenpfad zwischen Client und Dienst Vermittler umfasst. Weitere Informationen zum zu verwendenden Transport finden Sie unter [Auswählen eines Transports](choosing-a-transport.md). Weitere Informationen zum Verwenden der Transportsicherheit finden Sie unter Übersicht über die [Transportsicherheit](transport-security-overview.md).  
  
    2. `Message`  
  
         Nachrichtensicherheit bedeutet, dass jede Nachricht die notwendigen Header und Daten enthält, um die Nachricht zu sichern. Da die Struktur der Header unterschiedlich ist, können Sie beliebig viele Anmeldeinformationen umfassen. Dies spielt eine Rolle, wenn Sie mit anderen Diensten zusammenarbeiten, die einen bestimmten Anmeldeinformationstyp erfordern, den ein Transportmechanismus nicht bereitstellen kann, oder wenn die Nachricht mit mehr als einem Dienst verwendet werden muss, wobei jeder Dienst einen unterschiedlichen Anmeldeinformationstyp erfordert.  
  
         Weitere Informationen finden Sie unter [Nachrichten Sicherheit](message-security-in-wcf.md).  
  
    3. `TransportWithMessageCredential`  
  
         Diese Auswahl verwendet die Transportschicht, um die Nachrichtenübertragung zu sichern, während jede Nachricht die komplexen Anmeldeinformationen enthält, die andere Dienste benötigen. Dadurch wird der Leistungsvorteil der Transportsicherheit mit dem Vorteil komplexer Anmeldeinformationen der Nachrichtensicherheit kombiniert. Dies ist mit den folgenden Bindungen verfügbar: <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSFederationHttpBinding>, <xref:System.ServiceModel.NetPeerTcpBinding> und <xref:System.ServiceModel.WSHttpBinding>.  
  
3. Wenn Sie für HTTP eine Transportsicherheit verwenden möchten (d. h. HTTPS), müssen Sie auch den Host mit einem SSL-Zertifikat konfigurieren und SSL auf einem Port aktivieren. Weitere Informationen finden Sie unter [http-Transport Sicherheit](http-transport-security.md).  
  
4. Wenn Sie <xref:System.ServiceModel.WSHttpBinding> verwenden und keine sichere Sitzung einrichten müssen, legen Sie für die <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A>-Eigenschaft den Wert `false` fest.  
  
     Eine sichere Sitzung entsteht, wenn ein Client und ein Dienst einen Kanal mithilfe eines symmetrischen Schlüssels erstellen (sowohl Client als auch Server verwenden den gleichen Schlüssel für die Dauer einer Konversation und bis der Dialog geschlossen wird).  
  
## <a name="setting-the-client-credential-type"></a>Festlegen des Clientanmeldeinformationstyps  
 Wählen Sie wie erforderlich einen Clientanmeldeinformationstyp aus. Weitere Informationen finden Sie unter [Auswählen eines](selecting-a-credential-type.md)Anmelde Informations Typs. Die folgenden Clientanmeldeinformationstypen sind verfügbar:  
  
- `Windows`  
  
- `Certificate`  
  
- `Digest`  
  
- `Basic`  
  
- `UserName`  
  
- `NTLM`  
  
- `IssuedToken`  
  
 Die Art und Weise, wie Sie den Modus festlegen, bestimmt auch die Festlegung des Anmeldeinformationstyps. Wenn Sie beispielsweise `wsHttpBinding` ausgewählt haben und als Modus "Message" festgelegt haben, können Sie auch das `clientCredentialType`-Attribut des Nachrichtenelements auf einen der folgenden Werte festlegen: `None`, `Windows`, `UserName`, `Certificate` und `IssuedToken`, wie im folgenden Konfigurationsbeispiel gezeigt wird.  
  
```xml  
<system.serviceModel>  
<bindings>  
  <wsHttpBinding>  
    <binding name="myBinding">  
      <security mode="Message"/>  
      <message clientCredentialType="Windows"/>  
    </binding>
  </wsHttpBinding>
</bindings>  
</system.serviceModel>  
```  
  
 Oder in Code:  
  
 [!code-csharp[c_WsHttpService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#1)]
 [!code-vb[c_WsHttpService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#1)]  
  
## <a name="setting-service-credential-values"></a>Festlegen von Dienstanmeldeinformationswerten  
 Nachdem Sie einen Dienstanmeldeinformationstyp ausgewählt haben, müssen Sie die tatsächlichen Anmeldeinformationen für den zu verwendenden Dienst und Client festlegen. Für den Dienst werden die Anmeldeinformationen mit der <xref:System.ServiceModel.Description.ServiceCredentials>-Klasse festgelegt und von der <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>-Eigenschaft der <xref:System.ServiceModel.ServiceHostBase>-Klasse zurückgegeben. Die verwendete Bindung gibt den Dienstanmeldeinformationstyp, den ausgewählten Sicherheitsmodus und den Typ der Clientanmeldeinformationen an. Mit dem folgenden Code wird ein Zertifikat für die Dienstanmeldeinformationen festgelegt:  
  
 [!code-csharp[c_tcpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#3)]
 [!code-vb[c_tcpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#3)]  
  
## <a name="setting-client-credential-values"></a>Festlegen der Werte der Clientanmeldeinformationen  
 Für den Client werden die Clientanmeldeinformationswerte mit der <xref:System.ServiceModel.Description.ClientCredentials>-Klasse festgelegt und von der <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>-Eigenschaft der <xref:System.ServiceModel.ClientBase%601>-Klasse zurückgegeben. Mit dem folgenden Code wird ein Zertifikat als Anmeldeinformationen auf einem Client mit dem TCP-Protokoll festgelegt.  
  
 [!code-csharp[c_TcpClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpclient/cs/source.cs#1)]
 [!code-vb[c_TcpClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpclient/vb/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Einfache WCF-Programmierung](../basic-wcf-programming.md)
- [Häufige Sicherheitsszenarien](common-security-scenarios.md)
