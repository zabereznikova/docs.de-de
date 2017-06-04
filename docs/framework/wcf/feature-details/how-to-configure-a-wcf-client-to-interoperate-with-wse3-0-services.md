---
title: "Vorgehensweise: Konfigurieren eines WCF-Clients f&#252;r die Zusammenarbeit mit WSE3.0-Diensten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3dadd7f1-d207-4ea5-a73b-3e8aa44407f8
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Vorgehensweise: Konfigurieren eines WCF-Clients f&#252;r die Zusammenarbeit mit WSE3.0-Diensten
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Clients sind auf niedriger Ebene mit Diensten von Web Services Enhancements 3.0 für Microsoft .NET (WSE) kompatibel, wenn [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients für die Verwendung der Version der WS-Addressing-Spezifikation vom August 2004 konfiguriert sind.  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a>So konfigurieren Sie einen WCF-Client für die Zusammenarbeit mit einem WSE3.0-Webdienst  
  
1.  Führen Sie die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) zum Erstellen einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Client für den WSE 3.0-Webdienst.  
  
     Für einen WSE-Webdienst wird eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clientklasse erstellt.  
  
     Ausführliche Informationen zum Erstellen einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Client finden Sie unter der [Gewusst wie: Erstellen Sie einen Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
2.  Erstellen Sie eine Klasse, die eine Bindung darstellt, die mit WSE 3.0-Webdiensten kommunizieren kann.  
  
     Die folgende Klasse ist Teil der [interoperieren mit WSE](http://msdn.microsoft.com/de-de/f6816861-96a0-45f9-8736-8e4e82cd3a41) Beispiel.  
  
    1.  Erstellen Sie eine Klasse, die von abgeleitet ist die <xref:System.ServiceModel.Channels.Binding> Klasse.  
  
         Das folgende Codebeispiel erstellt eine Klasse namens `WseHttpBinding` abgeleitet, die die <xref:System.ServiceModel.Channels.Binding> Klasse.  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  Fügen Sie der Klasse Eigenschaften hinzu, die die sofort verwendbare WSE-Assertion festlegen. Hierzu gehört, ob abgeleitete Schlüssel erforderlich sind, ob Sicherheitssitzungen zum Einsatz kommen, ob Signaturbestätigungen erforderlich sind sowie die Einstellungen für den Nachrichtenschutz.  
  
         Das folgende Codebeispiel definiert `SecurityAssertion,``RequireDerivedKeys, EstablishSecurityContext, MessageProtectionOrder` Eigenschaften, die die sofort verwendbare WSE-Assertion, gibt an, ob abgeleitete Schlüssel erforderlich sind, ob sichere Sitzungen verwendet werden, gibt an, ob signaturbestätigungen erforderlich sind und Einstellungen für den Schutz, bzw. angeben.  
  
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
 Das folgende Codebeispiel definiert eine benutzerdefinierte Bindung, die Eigenschaften offenlegt, die mit den Eigenschaften der sofort verwendbaren WSE 3.0-Sicherheitsassertion übereinstimmen. Die benutzerdefinierte Bindung mit dem Namen `WseHttpBinding` wird dann verwendet, um die Bindungseigenschaften für einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client festzulegen.  
  
  
[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.Binding>   
 [Interoperieren mit WSE](http://msdn.microsoft.com/de-de/f6816861-96a0-45f9-8736-8e4e82cd3a41)