---
title: 'Vorgehensweise: Zugriff auf einen WSE3.0-Dienst über einen WCF-Client'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1f9bcd9b-8f8f-47fa-8f1e-0d47236eb800
ms.openlocfilehash: c955244c2e6821abda3a1fc5e25f00a73389ff1d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257768"
---
# <a name="how-to-access-a-wse-30-service-with-a-wcf-client"></a>Vorgehensweise: Zugriff auf einen WSE3.0-Dienst über einen WCF-Client

Windows Communication Foundation (WCF)-Clients sind auf Wire-Ebene kompatibel mit Web Services-Erweiterungen (WSE) 3,0 für Microsoft .NET Services, wenn WCF-Clients für die Verwendung der WS-Addressing Spezifikation vom August 2004 konfiguriert sind. WSE 3,0-Dienste unterstützen das Metadatenaustausch-Protokoll (MEX) nicht. Wenn Sie also das [Service Model Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) zum Erstellen einer WCF-Client Klasse verwenden, werden die Sicherheitseinstellungen nicht auf den generierten WCF-Client angewendet. Daher müssen Sie die Sicherheitseinstellungen angeben, die der WSE 3,0-Dienst benötigt, nachdem der WCF-Client generiert wurde.  
  
 Sie können diese Sicherheitseinstellungen anwenden, indem Sie eine benutzerdefinierte Bindung verwenden, um die Anforderungen des WSE 3,0-Diensts und die interoperablen Anforderungen zwischen einem WSE 3,0-Dienst und einem WCF-Client zu berücksichtigen. Diese Interoperabilitätsanforderungen umfassen die zuvor genannte Verwendung der WS-Adressierungsspezifikation vom August 2004 und den WSE 3.0-Standardnachrichtenschutz von <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>. Der Standard Nachrichten Schutz für WCF ist <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature> . In diesem Thema wird erläutert, wie eine WCF-Bindung erstellt wird, die mit einem WSE 3,0-Dienst interagiert. WCF stellt auch ein Beispiel bereit, das diese Bindung enthält. Weitere Informationen zu diesem Beispiel finden Sie unter Interoperabilität [mit ASMX-Webdiensten](../samples/interoperating-with-asmx-web-services.md).  
  
### <a name="to-access-a-wse-30-web-service-with-a-wcf-client"></a>So greifen Sie mit einem WCF-Client auf einen WSE 3.0-Webdienst zu  
  
1. Führen Sie das [Service Model Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) aus, um einen WCF-Client für den WSE 3,0-Webdienst zu erstellen.  
  
     Für einen WSE 3,0-Webdienst wird ein WCF-Client erstellt. Da WSE 3.0 das MEX-Protokoll nicht unterstützt, können Sie das Tool nicht nutzen, um die Sicherheitsanforderungen für den Webdienst aufzurufen. Der Anwendungsentwickler muss die Sicherheitseinstellungen für den Client hinzufügen.  
  
     Weitere Informationen zum Erstellen eines WCF-Clients finden Sie unter Gewusst [wie: Erstellen eines Clients](../how-to-create-a-wcf-client.md).  
  
2. Erstellen Sie eine Klasse, die eine Bindung darstellt, die mit WSE 3.0-Webdiensten kommunizieren kann.  
  
     Die folgende Klasse ist Teil des [Interoperating with WSE](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90)) -Beispiels:  
  
    1. Erstellen Sie eine von der <xref:System.ServiceModel.Channels.Binding>-Klasse abgeleitete Klasse.  
  
         Der folgende Code erstellt eine Klasse mit dem Namen `WseHttpBinding`, die von der <xref:System.ServiceModel.Channels.Binding>-Klasse abgeleitet wird.  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2. Fügen Sie Eigenschaften zur Klasse hinzu, die die sofort verwendbare WSE-Assertion festlegen, die vom WSE-Dienst verwendet wird. Hierzu gehört, ob abgeleitete Schlüssel erforderlich sind, ob Sicherheitssitzungen zum Einsatz kommen, ob Signaturbestätigungen erforderlich sind sowie die Einstellungen für den Nachrichtenschutz. In WSE 3,0 gibt eine sofort einsetzbare Aussage die Sicherheitsanforderungen für einen Client oder Webdienst an – ähnlich dem Authentifizierungsmodus einer Bindung in WCF.  
  
         Das folgende Codebeispiel definiert die `SecurityAssertion`, `RequireDerivedKeys``EstablishSecurityContext` und die `MessageProtectionOrder`-Eigenschaften, die die sofort verwendbare WSE-Assertion festlegen. Hierzu gehört, ob abgeleitete Schlüssel erforderlich sind, ob Sicherheitssitzungen zum Einsatz kommen, ob Signaturbestätigungen erforderlich sind sowie die Einstellungen für den Nachrichtenschutz.  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3. Überschreiben Sie die <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A>-Methode, um die Bindungseigenschaften einzurichten.  
  
         Das folgende Codebeispiel legt die Einstellungen für Transport, Nachrichtencodierung und Nachrichtenschutz fest, indem die Werte für `SecurityAssertion` und die `MessageProtectionOrder`-Eigenschaften abgerufen werden.  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3. Fügen Sie im Clientanwendungscode Code hinzu, um die Bindungseigenschaften festzulegen.  
  
     Im folgenden Codebeispiel wird angegeben, dass der WCF-Client den Nachrichten Schutz und die Authentifizierung verwenden muss, wie von der schlüsselfertigen WSE 3,0-Sicherheitserklärung definiert `AnonymousForCertificate` . Darüber hinaus sind Sicherheitssitzungen und abgeleitete Schlüssel erforderlich.  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a>Beispiel  

 Das folgende Codebeispiel definiert eine benutzerdefinierte Bindung, die Eigenschaften offenlegt, die mit den Eigenschaften der sofort verwendbaren WSE 3.0-Sicherheitsassertion übereinstimmen. Diese benutzerdefinierte Bindung mit dem Namen `WseHttpBinding` wird dann verwendet, um die Bindungseigenschaften für einen WCF-Client anzugeben, der mit dem WSSecurityAnonymous WSE 3,0-Schnellstart Beispiel kommuniziert.  

## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Channels.Binding>
- [Interoperieren mit WSE](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90))
