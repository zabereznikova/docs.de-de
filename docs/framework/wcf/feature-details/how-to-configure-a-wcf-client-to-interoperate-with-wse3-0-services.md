---
title: "Vorgehensweise: Konfigurieren eines WCF-Clients für die Zusammenarbeit mit WSE3.0-Diensten"
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
ms.assetid: 3dadd7f1-d207-4ea5-a73b-3e8aa44407f8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 901b75e1683a830d32428685a33afb63ace29a8f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-configure-a-wcf-client-to-interoperate-with-wse30-services"></a><span data-ttu-id="22d09-102">Vorgehensweise: Konfigurieren eines WCF-Clients für die Zusammenarbeit mit WSE3.0-Diensten</span><span class="sxs-lookup"><span data-stu-id="22d09-102">How to: Configure a WCF Client to interoperate with WSE3.0 Services</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="22d09-103">-Clients sind auf niedriger Ebene mit Diensten von Web Services Enhancements 3.0 für Microsoft .NET (WSE) kompatibel, wenn [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients für die Verwendung der Version der WS-Addressing-Spezifikation vom August 2004 konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="22d09-103"> clients are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) services when [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a><span data-ttu-id="22d09-104">So konfigurieren Sie einen WCF-Client für die Zusammenarbeit mit einem WSE3.0-Webdienst</span><span class="sxs-lookup"><span data-stu-id="22d09-104">To configure a WCF client to interoperate with a WSE 3.0 Web service</span></span>  
  
1.  <span data-ttu-id="22d09-105">Führen Sie die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) zum Erstellen einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Client für den WSE 3.0-Webdienst.</span><span class="sxs-lookup"><span data-stu-id="22d09-105">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client for the WSE 3.0 Web service.</span></span>  
  
     <span data-ttu-id="22d09-106">Für einen WSE-Webdienst wird eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clientklasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="22d09-106">For a WSE Web service, a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client class is created.</span></span>  
  
     <span data-ttu-id="22d09-107">Ausführliche Informationen zum Erstellen einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Client finden Sie unter der [Vorgehensweise: Erstellen eines Clients](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="22d09-107">For details about creating a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client, see the [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
2.  <span data-ttu-id="22d09-108">Erstellen Sie eine Klasse, die eine Bindung darstellt, die mit WSE 3.0-Webdiensten kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="22d09-108">Create a class that represents a binding that can communicate with WSE 3.0 Web services.</span></span>  
  
     <span data-ttu-id="22d09-109">Die folgende Klasse ist Teil der [Zusammenarbeit mit WSE](http://msdn.microsoft.com/en-us/f6816861-96a0-45f9-8736-8e4e82cd3a41) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="22d09-109">The following class is part of the [Interoperating with WSE](http://msdn.microsoft.com/en-us/f6816861-96a0-45f9-8736-8e4e82cd3a41) sample.</span></span>  
  
    1.  <span data-ttu-id="22d09-110">Erstellen Sie eine von der <xref:System.ServiceModel.Channels.Binding>-Klasse abgeleitete Klasse.</span><span class="sxs-lookup"><span data-stu-id="22d09-110">Create a class that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         <span data-ttu-id="22d09-111">Der folgende Code erstellt eine Klasse mit dem Namen `WseHttpBinding`, die von der <xref:System.ServiceModel.Channels.Binding>-Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="22d09-111">The following code example creates a class named `WseHttpBinding` that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  <span data-ttu-id="22d09-112">Fügen Sie der Klasse Eigenschaften hinzu, die die sofort verwendbare WSE-Assertion festlegen. Hierzu gehört, ob abgeleitete Schlüssel erforderlich sind, ob Sicherheitssitzungen zum Einsatz kommen, ob Signaturbestätigungen erforderlich sind sowie die Einstellungen für den Nachrichtenschutz.</span><span class="sxs-lookup"><span data-stu-id="22d09-112">Add properties to the class that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings.</span></span>  
  
         <span data-ttu-id="22d09-113">Das folgende Codebeispiel definiert `SecurityAssertion,``RequireDerivedKeys, EstablishSecurityContext, MessageProtectionOrder` Eigenschaften, die angeben, die sofort verwendbare WSE-Assertion, gibt an, ob abgeleitete Schlüssel erforderlich sind, gibt an, ob sicherheitssitzungen zum Einsatz kommen, ob signaturbestätigungen erforderlich sind und Einstellungen für den Nachrichtenschutz, bzw.</span><span class="sxs-lookup"><span data-stu-id="22d09-113">The following code example defines `SecurityAssertion,``RequireDerivedKeys, EstablishSecurityContext, MessageProtectionOrder` properties that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings, respectively.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  <span data-ttu-id="22d09-114">Überschreiben Sie die <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A>-Methode, um die Bindungseigenschaften einzurichten.</span><span class="sxs-lookup"><span data-stu-id="22d09-114">Override the <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> method to set the binding properties.</span></span>  
  
         <span data-ttu-id="22d09-115">Das folgende Codebeispiel legt die Einstellungen für Transport, Nachrichtencodierung und Nachrichtenschutz fest, indem die Werte für `SecurityAssertion` und die `MessageProtectionOrder`-Eigenschaften abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="22d09-115">The following code example specifies the transport, message encoding, and message protection settings by getting the values of the `SecurityAssertion` and `MessageProtectionOrder` properties.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3.  <span data-ttu-id="22d09-116">Fügen Sie im Clientanwendungscode Code hinzu, um die Bindungseigenschaften festzulegen.</span><span class="sxs-lookup"><span data-stu-id="22d09-116">In the client application code, add code to set the binding properties.</span></span>  
  
     <span data-ttu-id="22d09-117">Das folgende Codebeispiel legt fest, dass der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client Nachrichtenschutz und -authentifizierung, wie von der sofort verwendbaren WSE 3.0-`AnonymousForCertificate`-Sicherheitsassertion definiert, verwenden muss.</span><span class="sxs-lookup"><span data-stu-id="22d09-117">The following code example specifies that the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client must use message protection and authentication as defined by the WSE 3.0 `AnonymousForCertificate` turnkey security assertion.</span></span> <span data-ttu-id="22d09-118">Darüber hinaus sind Sicherheitssitzungen und abgeleitete Schlüssel erforderlich.</span><span class="sxs-lookup"><span data-stu-id="22d09-118">Additionally, secure sessions and derived keys are required.</span></span>  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="22d09-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="22d09-119">Example</span></span>  
 <span data-ttu-id="22d09-120">Das folgende Codebeispiel definiert eine benutzerdefinierte Bindung, die Eigenschaften offenlegt, die mit den Eigenschaften der sofort verwendbaren WSE 3.0-Sicherheitsassertion übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="22d09-120">The following code example defines a custom binding that exposes properties that correspond to the properties of a WSE 3.0 turnkey security assertion.</span></span> <span data-ttu-id="22d09-121">Die benutzerdefinierte Bindung mit dem Namen `WseHttpBinding` wird dann verwendet, um die Bindungseigenschaften für einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client festzulegen.</span><span class="sxs-lookup"><span data-stu-id="22d09-121">The custom binding, which is named `WseHttpBinding`, is then used to specify the binding properties for a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client.</span></span>  
  
  
[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="22d09-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22d09-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 [<span data-ttu-id="22d09-123">Zusammenarbeit mit WSE</span><span class="sxs-lookup"><span data-stu-id="22d09-123">Interoperating with WSE</span></span>](http://msdn.microsoft.com/en-us/f6816861-96a0-45f9-8736-8e4e82cd3a41)
