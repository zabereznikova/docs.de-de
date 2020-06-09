---
title: 'Vorgehensweise: Konfigurieren eines WCF-Clients für die Zusammenarbeit mit WSE3.0-Diensten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3dadd7f1-d207-4ea5-a73b-3e8aa44407f8
ms.openlocfilehash: 7dd50fcc07c6c090042cf87acb4aa5d2b5321a68
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579578"
---
# <a name="how-to-configure-a-wcf-client-to-interoperate-with-wse30-services"></a>Vorgehensweise: Konfigurieren eines WCF-Clients für die Zusammenarbeit mit WSE3.0-Diensten
Windows Communication Foundation (WCF)-Clients sind auf Wire-Ebene mit den Webdienst Erweiterungen 3,0 für Microsoft .net (WSE)-Dienste kompatibel, wenn WCF-Clients für die Verwendung der WS-Adressierungs Spezifikation vom August 2004 konfiguriert sind.  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a>So konfigurieren Sie einen WCF-Client für die Zusammenarbeit mit einem WSE3.0-Webdienst  
  
1. Führen Sie das [Service Model Metadata Utility-Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) aus, um einen WCF-Client für den WSE 3,0-Webdienst zu erstellen.  
  
     Für einen WSE-Webdienst wird eine WCF-Client Klasse erstellt.  
  
     Ausführliche Informationen zum Erstellen eines WCF-Clients finden Sie unter Gewusst [wie: Erstellen eines Clients](../how-to-create-a-wcf-client.md).  
  
2. Erstellen Sie eine Klasse, die eine Bindung darstellt, die mit WSE 3.0-Webdiensten kommunizieren kann.  
  
     Die folgende Klasse ist Teil der [Interoperation mit WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29) -Beispiel.  
  
    1. Erstellen Sie eine von der <xref:System.ServiceModel.Channels.Binding>-Klasse abgeleitete Klasse.  
  
         Der folgende Code erstellt eine Klasse mit dem Namen `WseHttpBinding`, die von der <xref:System.ServiceModel.Channels.Binding>-Klasse abgeleitet wird.  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2. Fügen Sie der Klasse Eigenschaften hinzu, die die sofort verwendbare WSE-Assertion festlegen. Hierzu gehört, ob abgeleitete Schlüssel erforderlich sind, ob Sicherheitssitzungen zum Einsatz kommen, ob Signaturbestätigungen erforderlich sind sowie die Einstellungen für den Nachrichtenschutz.  
  
         Im folgenden Codebeispiel werden die `SecurityAssertion` `RequireDerivedKeys` Eigenschaften,, `EstablishSecurityContext` und definiert `MessageProtectionOrder` . Sie geben die sofort verwendbare WSE-Assertion an, unabhängig davon, ob abgeleitete Schlüssel erforderlich sind, ob sichere Sitzungen verwendet werden, ob Signatur Bestätigungen erforderlich sind und welche Einstellungen für den Nachrichten Schutz erforderlich sind.  
  
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
 Das folgende Codebeispiel definiert eine benutzerdefinierte Bindung, die Eigenschaften offenlegt, die mit den Eigenschaften der sofort verwendbaren WSE 3.0-Sicherheitsassertion übereinstimmen. Die benutzerdefinierte Bindung mit dem Namen `WseHttpBinding` wird dann verwendet, um die Bindungseigenschaften für einen WCF-Client anzugeben.  

[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Channels.Binding>
- [Interoperieren mit WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29)
