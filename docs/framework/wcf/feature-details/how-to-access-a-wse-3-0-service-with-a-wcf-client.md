---
title: "Vorgehensweise: Zugriff auf einen WSE3.0-Dienst über einen WCF-Client"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1f9bcd9b-8f8f-47fa-8f1e-0d47236eb800
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cd6ad4ed735cb94321adad8fd2e4cf396e2221fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-a-wse-30-service-with-a-wcf-client"></a>Vorgehensweise: Zugriff auf einen WSE3.0-Dienst über einen WCF-Client
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Clients sind auf niedriger Ebene mit Diensten von Web Services Enhancements (WSE) 3.0 für Microsoft .NET-Dienste kompatibel, wenn [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients für die Verwendung der Version der WS-Adressierungsspezifikation vom August 2004 konfiguriert sind. WSE 3.0-Dienste nicht unterstützen jedoch die Metadaten-Exchange (MEX)-Protokoll daher bei Verwendung der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) zum Erstellen einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Clientklasse, die Sicherheitseinstellungen gelten nicht für die generierte [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Client. Daher müssen Sie die Sicherheitseinstellungen, die der WSE 3.0-Dienst erfordert, festlegen, nachdem der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client erzeugt wurde.  
  
 Sie können diese Sicherheitseinstellungen anwenden, indem Sie eine benutzerdefinierte Bindung verwenden, um die Anforderungen des WSE 3.0-Diensts und die Interoperabilitätsanforderungen zwischen einem WSE 3.0-Dienst und einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client zu berücksichtigen. Diese Interoperabilitätsanforderungen umfassen die zuvor genannte Verwendung der WS-Adressierungsspezifikation vom August 2004 und den WSE 3.0-Standardnachrichtenschutz von <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>. Der Standardnachrichtenschutz für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ist <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>. Diese Thema enthält Details zum Erstellen einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Bindung, die mit einem WSE 3.0-Dienst zusammenarbeitet. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] enthält ebenfalls ein Beispiel, das diese Bindung enthält. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Dieses Beispiel finden Sie unter [Zusammenwirken mit ASMX-Webdiensten](../../../../docs/framework/wcf/samples/interoperating-with-asmx-web-services.md).  
  
### <a name="to-access-a-wse-30-web-service-with-a-wcf-client"></a>So greifen Sie mit einem WCF-Client auf einen WSE 3.0-Webdienst zu  
  
1.  Führen Sie die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) zum Erstellen einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Client für den WSE 3.0-Webdienst.  
  
     Für einen WSE 3.0-Webdienst wird ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client erstellt. Da WSE 3.0 das MEX-Protokoll nicht unterstützt, können Sie das Tool nicht nutzen, um die Sicherheitsanforderungen für den Webdienst aufzurufen. Der Anwendungsentwickler muss die Sicherheitseinstellungen für den Client hinzufügen.  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Erstellen einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Client finden Sie unter der [Vorgehensweise: Erstellen eines Clients](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
2.  Erstellen Sie eine Klasse, die eine Bindung darstellt, die mit WSE 3.0-Webdiensten kommunizieren kann.  
  
     Die folgende Klasse ist Teil der [Zusammenarbeit mit WSE](http://msdn.microsoft.com/en-us/f6816861-96a0-45f9-8736-8e4e82cd3a41) Beispiel:  
  
    1.  Erstellen Sie eine von der <xref:System.ServiceModel.Channels.Binding>-Klasse abgeleitete Klasse.  
  
         Der folgende Code erstellt eine Klasse mit dem Namen `WseHttpBinding`, die von der <xref:System.ServiceModel.Channels.Binding>-Klasse abgeleitet wird.  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  Fügen Sie Eigenschaften zur Klasse hinzu, die die sofort verwendbare WSE-Assertion festlegen, die vom WSE-Dienst verwendet wird. Hierzu gehört, ob abgeleitete Schlüssel erforderlich sind, ob Sicherheitssitzungen zum Einsatz kommen, ob Signaturbestätigungen erforderlich sind sowie die Einstellungen für den Nachrichtenschutz. In WSE 3.0 legt eine sofort verwendbare Assertion die Sicherheitsanforderungen für einen Client oder einen Webdienst fest – ähnlich dem Authentifizierungsmodus einer Bindung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
         Das folgende Codebeispiel definiert die `SecurityAssertion`, `RequireDerivedKeys` `EstablishSecurityContext` und die `MessageProtectionOrder`-Eigenschaften, die die sofort verwendbare WSE-Assertion festlegen. Hierzu gehört, ob abgeleitete Schlüssel erforderlich sind, ob Sicherheitssitzungen zum Einsatz kommen, ob Signaturbestätigungen erforderlich sind sowie die Einstellungen für den Nachrichtenschutz.  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  Überschreiben Sie die <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A>-Methode, um die Bindungseigenschaften einzurichten.  
  
         Das folgende Codebeispiel legt die Einstellungen für Transport, Nachrichtencodierung und Nachrichtenschutz fest, indem die Werte für `SecurityAssertion` und die `MessageProtectionOrder`-Eigenschaften abgerufen werden.  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3.  Fügen Sie im Clientanwendungscode Code hinzu, um die Bindungseigenschaften festzulegen.  
  
     Das folgende Codebeispiel legt fest, dass der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client Nachrichtenschutz und -authentifizierung, wie von der sofort verwendbaren WSE 3.0-`AnonymousForCertificate`-Sicherheitsassertion definiert, verwenden muss. Darüber hinaus sind Sicherheitssitzungen und abgeleitete Schlüssel erforderlich.  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert eine benutzerdefinierte Bindung, die Eigenschaften offenlegt, die mit den Eigenschaften der sofort verwendbaren WSE 3.0-Sicherheitsassertion übereinstimmen. Die benutzerdefinierte Bindung mit dem Namen `WseHttpBinding` wird dann für die Festlegung der Bindungseigenschaften für einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client verwendet, der mit dem WSSecurityAnonymous WSE 3.0 QuickStart kommuniziert.  
  
  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.Binding>  
 [Zusammenarbeit mit WSE](http://msdn.microsoft.com/en-us/f6816861-96a0-45f9-8736-8e4e82cd3a41)
