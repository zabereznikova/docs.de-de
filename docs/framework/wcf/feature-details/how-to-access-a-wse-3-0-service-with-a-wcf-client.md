---
title: "Vorgehensweise: Zugriff auf einen WSE3.0-Dienst &#252;ber einen WCF-Client | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1f9bcd9b-8f8f-47fa-8f1e-0d47236eb800
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Vorgehensweise: Zugriff auf einen WSE3.0-Dienst &#252;ber einen WCF-Client
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Clients sind auf niedriger Ebene mit Diensten von Web Services Enhancements (WSE) 3.0 für Microsoft .NET-Dienste kompatibel, wenn [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients für die Verwendung der Version der WS-Adressierungsspezifikation vom August 2004 konfiguriert sind. WSE 3.0-Dienste unterstützen jedoch nicht das metadatenaustauschprotokoll (MEX), sodass bei Verwendung der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) erstellen eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Client-Klasse, die Sicherheitseinstellungen sind nicht auf die generierten angewendet [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Client. Daher müssen Sie die Sicherheitseinstellungen, die der WSE 3.0-Dienst erfordert, festlegen, nachdem der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client erzeugt wurde.  
  
 Sie können diese Sicherheitseinstellungen anwenden, indem Sie eine benutzerdefinierte Bindung verwenden, um die Anforderungen des WSE 3.0-Diensts und die Interoperabilitätsanforderungen zwischen einem WSE 3.0-Dienst und einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client zu berücksichtigen. Diese interoperabilitätsanforderungen umfassen die zuvor genannte Verwendung der vom August 2004 WS-Addressing-Spezifikation und den WSE 3.0-standardnachrichtenschutz den Nachrichtenschutz des <xref:System.ServiceModel.Security.MessageProtectionOrder>. Der standardnachrichtenschutz für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ist <xref:System.ServiceModel.Security.MessageProtectionOrder>. Diese Thema enthält Details zum Erstellen einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Bindung, die mit einem WSE 3.0-Dienst zusammenarbeitet. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] enthält ebenfalls ein Beispiel, das diese Bindung enthält. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]In diesem Beispiel finden Sie unter [Zusammenwirken mit ASMX-Webdiensten](../../../../docs/framework/wcf/samples/interoperating-with-asmx-web-services.md).  
  
### <a name="to-access-a-wse-30-web-service-with-a-wcf-client"></a>So greifen Sie mit einem WCF-Client auf einen WSE 3.0-Webdienst zu  
  
1.  Führen Sie die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) zum Erstellen einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Client für den WSE 3.0-Webdienst.  
  
     Für einen WSE 3.0-Webdienst wird ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client erstellt. Da WSE 3.0 das MEX-Protokoll nicht unterstützt, können Sie das Tool nicht nutzen, um die Sicherheitsanforderungen für den Webdienst aufzurufen. Der Anwendungsentwickler muss die Sicherheitseinstellungen für den Client hinzufügen.  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Erstellen einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Client finden Sie unter der [Gewusst wie: Erstellen Sie einen Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
2.  Erstellen Sie eine Klasse, die eine Bindung darstellt, die mit WSE 3.0-Webdiensten kommunizieren kann.  
  
     Die folgende Klasse ist Teil der [interoperieren mit WSE](http://msdn.microsoft.com/de-de/f6816861-96a0-45f9-8736-8e4e82cd3a41) Beispiel:  
  
    1.  Erstellen Sie eine Klasse, die von abgeleitet ist die <xref:System.ServiceModel.Channels.Binding> Klasse.  
  
         Das folgende Codebeispiel erstellt eine Klasse namens `WseHttpBinding` abgeleitet, die die <xref:System.ServiceModel.Channels.Binding> Klasse.  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  Fügen Sie Eigenschaften zur Klasse hinzu, die die sofort verwendbare WSE-Assertion festlegen, die vom WSE-Dienst verwendet wird. Hierzu gehört, ob abgeleitete Schlüssel erforderlich sind, ob Sicherheitssitzungen zum Einsatz kommen, ob Signaturbestätigungen erforderlich sind sowie die Einstellungen für den Nachrichtenschutz. In WSE 3.0 legt eine sofort verwendbare Assertion die Sicherheitsanforderungen für einen Client oder einen Webdienst fest – ähnlich dem Authentifizierungsmodus einer Bindung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
         Das folgende Codebeispiel definiert die `SecurityAssertion`, `RequireDerivedKeys` `EstablishSecurityContext` und die `MessageProtectionOrder`-Eigenschaften, die die sofort verwendbare WSE-Assertion festlegen. Hierzu gehört, ob abgeleitete Schlüssel erforderlich sind, ob Sicherheitssitzungen zum Einsatz kommen, ob Signaturbestätigungen erforderlich sind sowie die Einstellungen für den Nachrichtenschutz.  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  Überschreiben Sie die <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> Methode, um die Bindungseigenschaften festzulegen.  
  
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
 [Interoperieren mit WSE](http://msdn.microsoft.com/de-de/f6816861-96a0-45f9-8736-8e4e82cd3a41)