---
title: 'Vorgehensweise: Konfigurieren eines WCF-Clients für die Zusammenarbeit mit WSE3.0-Diensten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3dadd7f1-d207-4ea5-a73b-3e8aa44407f8
ms.openlocfilehash: e30403f9c97f31e93c22a9658ffb74d4d02a49ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490642"
---
# <a name="how-to-configure-a-wcf-client-to-interoperate-with-wse30-services"></a><span data-ttu-id="92886-102">Vorgehensweise: Konfigurieren eines WCF-Clients für die Zusammenarbeit mit WSE3.0-Diensten</span><span class="sxs-lookup"><span data-stu-id="92886-102">How to: Configure a WCF Client to interoperate with WSE3.0 Services</span></span>
<span data-ttu-id="92886-103">Windows Communication Foundation (WCF)-Clients sind auf Übertragungsebene kompatibel mit Web Services Enhancements 3.0 für Microsoft .NET (WSE)-Dienste aus, wenn WCF-Clients konfiguriert sind, verwenden Sie die Version vom August 2004 des WS-Addressing-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="92886-103">Windows Communication Foundation (WCF) clients are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) services when WCF clients are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a><span data-ttu-id="92886-104">So konfigurieren Sie einen WCF-Client für die Zusammenarbeit mit einem WSE3.0-Webdienst</span><span class="sxs-lookup"><span data-stu-id="92886-104">To configure a WCF client to interoperate with a WSE 3.0 Web service</span></span>  
  
1.  <span data-ttu-id="92886-105">Führen Sie die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) beim Erstellen eines WCF-Clients für den WSE 3.0-Webdienst.</span><span class="sxs-lookup"><span data-stu-id="92886-105">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a WCF client for the WSE 3.0 Web service.</span></span>  
  
     <span data-ttu-id="92886-106">Für einen WSE-Webdienst ist eine WCF-Clientklasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="92886-106">For a WSE Web service, a WCF client class is created.</span></span>  
  
     <span data-ttu-id="92886-107">Ausführliche Informationen zum Erstellen eines WCF-Clients finden Sie unter der [Vorgehensweise: Erstellen eines Clients](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="92886-107">For details about creating a WCF client, see the [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
2.  <span data-ttu-id="92886-108">Erstellen Sie eine Klasse, die eine Bindung darstellt, die mit WSE 3.0-Webdiensten kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="92886-108">Create a class that represents a binding that can communicate with WSE 3.0 Web services.</span></span>  
  
     <span data-ttu-id="92886-109">Die folgende Klasse ist Teil der [Zusammenarbeit mit WSE](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="92886-109">The following class is part of the [Interoperating with WSE](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41) sample.</span></span>  
  
    1.  <span data-ttu-id="92886-110">Erstellen Sie eine von der <xref:System.ServiceModel.Channels.Binding>-Klasse abgeleitete Klasse.</span><span class="sxs-lookup"><span data-stu-id="92886-110">Create a class that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         <span data-ttu-id="92886-111">Der folgende Code erstellt eine Klasse mit dem Namen `WseHttpBinding`, die von der <xref:System.ServiceModel.Channels.Binding>-Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="92886-111">The following code example creates a class named `WseHttpBinding` that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  <span data-ttu-id="92886-112">Fügen Sie der Klasse Eigenschaften hinzu, die die sofort verwendbare WSE-Assertion festlegen. Hierzu gehört, ob abgeleitete Schlüssel erforderlich sind, ob Sicherheitssitzungen zum Einsatz kommen, ob Signaturbestätigungen erforderlich sind sowie die Einstellungen für den Nachrichtenschutz.</span><span class="sxs-lookup"><span data-stu-id="92886-112">Add properties to the class that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings.</span></span>  
  
         <span data-ttu-id="92886-113">Das folgende Codebeispiel definiert `SecurityAssertion,``RequireDerivedKeys, EstablishSecurityContext, MessageProtectionOrder` Eigenschaften, die angeben, die sofort verwendbare WSE-Assertion, gibt an, ob abgeleitete Schlüssel erforderlich sind, gibt an, ob sicherheitssitzungen zum Einsatz kommen, ob signaturbestätigungen erforderlich sind und Einstellungen für den Nachrichtenschutz, bzw.</span><span class="sxs-lookup"><span data-stu-id="92886-113">The following code example defines `SecurityAssertion,``RequireDerivedKeys, EstablishSecurityContext, MessageProtectionOrder` properties that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings, respectively.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  <span data-ttu-id="92886-114">Überschreiben Sie die <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A>-Methode, um die Bindungseigenschaften einzurichten.</span><span class="sxs-lookup"><span data-stu-id="92886-114">Override the <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> method to set the binding properties.</span></span>  
  
         <span data-ttu-id="92886-115">Das folgende Codebeispiel legt die Einstellungen für Transport, Nachrichtencodierung und Nachrichtenschutz fest, indem die Werte für `SecurityAssertion` und die `MessageProtectionOrder`-Eigenschaften abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="92886-115">The following code example specifies the transport, message encoding, and message protection settings by getting the values of the `SecurityAssertion` and `MessageProtectionOrder` properties.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3.  <span data-ttu-id="92886-116">Fügen Sie im Clientanwendungscode Code hinzu, um die Bindungseigenschaften festzulegen.</span><span class="sxs-lookup"><span data-stu-id="92886-116">In the client application code, add code to set the binding properties.</span></span>  
  
     <span data-ttu-id="92886-117">Das folgende Codebeispiel gibt an, dass der WCF-Client Nachrichtenschutz und -Authentifizierung verwenden muss, gemäß der Definition von der WSE 3.0 `AnonymousForCertificate` sicherheitsassertion.</span><span class="sxs-lookup"><span data-stu-id="92886-117">The following code example specifies that the WCF client must use message protection and authentication as defined by the WSE 3.0 `AnonymousForCertificate` turnkey security assertion.</span></span> <span data-ttu-id="92886-118">Darüber hinaus sind Sicherheitssitzungen und abgeleitete Schlüssel erforderlich.</span><span class="sxs-lookup"><span data-stu-id="92886-118">Additionally, secure sessions and derived keys are required.</span></span>  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="92886-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="92886-119">Example</span></span>  
 <span data-ttu-id="92886-120">Das folgende Codebeispiel definiert eine benutzerdefinierte Bindung, die Eigenschaften offenlegt, die mit den Eigenschaften der sofort verwendbaren WSE 3.0-Sicherheitsassertion übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="92886-120">The following code example defines a custom binding that exposes properties that correspond to the properties of a WSE 3.0 turnkey security assertion.</span></span> <span data-ttu-id="92886-121">Die benutzerdefinierte Bindung mit dem Namen `WseHttpBinding`, klicken Sie dann an die Bindungseigenschaften für einen WCF-Client verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="92886-121">The custom binding, which is named `WseHttpBinding`, is then used to specify the binding properties for a WCF client.</span></span>  
  
  
[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="92886-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92886-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 [<span data-ttu-id="92886-123">Zusammenarbeit mit WSE</span><span class="sxs-lookup"><span data-stu-id="92886-123">Interoperating with WSE</span></span>](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41)
