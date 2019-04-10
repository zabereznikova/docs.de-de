---
title: 'Vorgehensweise: Zugriff auf einen WSE 3.0-Dienst mit einem WCF-Client'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1f9bcd9b-8f8f-47fa-8f1e-0d47236eb800
ms.openlocfilehash: 83507a95dbc4bc7499b94a516f569703f21a2726
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59341061"
---
# <a name="how-to-access-a-wse-30-service-with-a-wcf-client"></a>Vorgehensweise: Zugriff auf einen WSE 3.0-Dienst mit einem WCF-Client
Windows Communication Foundation (WCF)-Clients sind auf niedriger Ebene kompatibel mit Web Services Enhancements (WSE) 3.0 für Microsoft .NET Services aus, wenn WCF-Clients konfiguriert werden, um die Version vom August 2004 von WS-Addressing-Spezifikation. WSE 3.0-Dienste unterstützen jedoch nicht des metadatenaustauschprotokolls (MEX), also bei Verwendung der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) um einen WCF-Clientklasse zu erstellen, die Sicherheitseinstellungen gelten nicht auf die generierte WCF-Client. Aus diesem Grund müssen Sie die Sicherheitseinstellungen angeben, dass der WSE 3.0-Dienst erforderlich ist, nachdem der WCF-Client generiert wurde.  
  
 Sie können diese Sicherheitseinstellungen anwenden, indem Sie mit einer benutzerdefinierten Bindung Anforderungen des WSE 3.0-Diensts und die interoperabilitätsanforderungen zwischen einem WSE 3.0-Dienst und einen WCF-Client in Betracht zu ziehen. Diese Interoperabilitätsanforderungen umfassen die zuvor genannte Verwendung der WS-Adressierungsspezifikation vom August 2004 und den WSE 3.0-Standardnachrichtenschutz von <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>. Der standardnachrichtenschutz für WCF ist <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>. In diesem Thema wird erläutert, wie eine WCF-Bindung, die Interoperabilität mit einem WSE 3.0-Dienst erstellen. WCF bietet außerdem ein Beispiel, das diese Bindung enthält. Weitere Informationen zu diesem Beispiel finden Sie unter [Zusammenwirken mit ASMX-Webdiensten](../../../../docs/framework/wcf/samples/interoperating-with-asmx-web-services.md).  
  
### <a name="to-access-a-wse-30-web-service-with-a-wcf-client"></a>So greifen Sie mit einem WCF-Client auf einen WSE 3.0-Webdienst zu  
  
1. Führen Sie die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) beim Erstellen eines WCF-Clients für den WSE 3.0-Webdienst.  
  
     Für einen WSE 3.0-Webdienst wird ein WCF-Client erstellt. Da WSE 3.0 das MEX-Protokoll nicht unterstützt, können Sie das Tool nicht nutzen, um die Sicherheitsanforderungen für den Webdienst aufzurufen. Der Anwendungsentwickler muss die Sicherheitseinstellungen für den Client hinzufügen.  
  
     Weitere Informationen zum Erstellen eines WCF-Clients finden Sie unter den [Vorgehensweise: Erstellen Sie einen Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
2. Erstellen Sie eine Klasse, die eine Bindung darstellt, die mit WSE 3.0-Webdiensten kommunizieren kann.  
  
     Die folgende Klasse ist Teil der [interoperieren mit WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29) Beispiel:  
  
    1.  Erstellen Sie eine von der <xref:System.ServiceModel.Channels.Binding>-Klasse abgeleitete Klasse.  
  
         Der folgende Code erstellt eine Klasse mit dem Namen `WseHttpBinding`, die von der <xref:System.ServiceModel.Channels.Binding>-Klasse abgeleitet wird.  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  Fügen Sie Eigenschaften zur Klasse hinzu, die die sofort verwendbare WSE-Assertion festlegen, die vom WSE-Dienst verwendet wird. Hierzu gehört, ob abgeleitete Schlüssel erforderlich sind, ob Sicherheitssitzungen zum Einsatz kommen, ob Signaturbestätigungen erforderlich sind sowie die Einstellungen für den Nachrichtenschutz. Bei WSE 3.0 gibt eine sofort verwendbare Assertion die sicherheitsanforderungen für einen Client oder den Webdienst, ähnlich dem Authentifizierungsmodus einer Bindung in WCF.  
  
         Das folgende Codebeispiel definiert die `SecurityAssertion`, `RequireDerivedKeys``EstablishSecurityContext` und die `MessageProtectionOrder`-Eigenschaften, die die sofort verwendbare WSE-Assertion festlegen. Hierzu gehört, ob abgeleitete Schlüssel erforderlich sind, ob Sicherheitssitzungen zum Einsatz kommen, ob Signaturbestätigungen erforderlich sind sowie die Einstellungen für den Nachrichtenschutz.  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  Überschreiben Sie die <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A>-Methode, um die Bindungseigenschaften einzurichten.  
  
         Das folgende Codebeispiel legt die Einstellungen für Transport, Nachrichtencodierung und Nachrichtenschutz fest, indem die Werte für `SecurityAssertion` und die `MessageProtectionOrder`-Eigenschaften abgerufen werden.  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3. Fügen Sie im Clientanwendungscode Code hinzu, um die Bindungseigenschaften festzulegen.  
  
     Das folgende Codebeispiel gibt an, dass der WCF-Client Nachrichtenschutz und -Authentifizierung verwenden muss, gemäß der WSE 3.0 `AnonymousForCertificate` sicherheitsassertion. Darüber hinaus sind Sicherheitssitzungen und abgeleitete Schlüssel erforderlich.  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert eine benutzerdefinierte Bindung, die Eigenschaften offenlegt, die mit den Eigenschaften der sofort verwendbaren WSE 3.0-Sicherheitsassertion übereinstimmen. Die benutzerdefinierte Bindung mit dem Namen `WseHttpBinding`, klicken Sie dann an die Bindungseigenschaften für einen WCF-Client, die für die Kommunikation mit dem WSSecurityAnonymous WSE 3.0-Schnellstart-Beispiel verwendet wird.  

## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Channels.Binding>
- [Interoperieren mit WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29)
