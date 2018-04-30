---
title: 'Vorgehensweise: Anpassen einer vom System bereitgestellten Bindung'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: f8b97862-e8bb-470d-8b96-07733c21fe26
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1d70a4c4234047e7410ae4f631e48595a0859f37
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-customize-a-system-provided-binding"></a><span data-ttu-id="a4ebf-102">Vorgehensweise: Anpassen einer vom System bereitgestellten Bindung</span><span class="sxs-lookup"><span data-stu-id="a4ebf-102">How to: Customize a System-Provided Binding</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="a4ebf-103"> umfasst mehrere systemseitig bereitgestellte Bindungen, bei denen Sie einige der Eigenschaften von zugrundeliegenden Bindungselementen konfigurieren können. Es lassen sich jedoch nicht alle Eigenschaften konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a4ebf-103"> includes several system-provided bindings that allow you to configure some of the properties of the underlying binding elements, but not all of the properties.</span></span> <span data-ttu-id="a4ebf-104">In diesem Thema wird veranschaulicht, wie Sie Eigenschaften für die Bindungselemente festlegen, um eine benutzerdefinierte Bindung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a4ebf-104">This topic demonstrates how to set properties on the binding elements to create a custom binding.</span></span>  
  
 <span data-ttu-id="a4ebf-105">Weitere Informationen dazu, wie direkt erstellen und Konfigurieren von Bindungen ohne Verwendung der vom System bereitgestellte Bindungen finden Sie unter [benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="a4ebf-105">For more information about how to directly create and configure binding elements without using the system-provided bindings, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
 <span data-ttu-id="a4ebf-106">Weitere Informationen zum Erstellen und Erweitern von benutzerdefinierten Bindungen finden Sie unter [Erweitern von Bindungen](../../../../docs/framework/wcf/extending/extending-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="a4ebf-106">For more information about creating and extending custom bindings, see [Extending Bindings](../../../../docs/framework/wcf/extending/extending-bindings.md).</span></span>  
  
 <span data-ttu-id="a4ebf-107">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Alle Bindungen bestehen aus *Bindungselementen*.</span><span class="sxs-lookup"><span data-stu-id="a4ebf-107">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] all bindings are made up of *binding elements*.</span></span> <span data-ttu-id="a4ebf-108">Jedes Bindungselement wird von der <xref:System.ServiceModel.Channels.BindingElement>-Klasse abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="a4ebf-108">Each binding element derives from the <xref:System.ServiceModel.Channels.BindingElement> class.</span></span> <span data-ttu-id="a4ebf-109">Systemseitig bereitgestellte Bindungen wie <xref:System.ServiceModel.BasicHttpBinding> erstellen und konfigurieren ihre eigenen Bindungselemente.</span><span class="sxs-lookup"><span data-stu-id="a4ebf-109">System-provided bindings such as <xref:System.ServiceModel.BasicHttpBinding> create and configure their own binding elements.</span></span> <span data-ttu-id="a4ebf-110">In diesem Thema wird gezeigt, wie Sie auf die Eigenschaften dieser Bindungselemente zugreifen und sie ändern können. Die Elemente sind nicht direkt über die Bindung verfügbar. Dies trifft insbesondere auf die <xref:System.ServiceModel.BasicHttpBinding>-Klasse zu.</span><span class="sxs-lookup"><span data-stu-id="a4ebf-110">This topic shows you how to access and change the properties of these binding elements, which are not directly exposed on the binding; specifically, the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="a4ebf-111">Die einzelnen Bindungselemente sind in einer Auflistung, die von der <xref:System.ServiceModel.Channels.BindingElementCollection>-Klasse dargestellt wird, enthalten, und werden in dieser Reihenfolge hinzugefügt: Transaktionsfluss, zuverlässige Sitzung, Sicherheit, Composite Duplex, Eindirektional, Streamsicherheit, Nachrichtencodierung und Transport.</span><span class="sxs-lookup"><span data-stu-id="a4ebf-111">The individual binding elements are contained in a collection represented by the <xref:System.ServiceModel.Channels.BindingElementCollection> class and are added in this order: Transaction Flow, Reliable Session, Security, Composite Duplex, One-way, Stream Security, Message Encoding, and Transport.</span></span> <span data-ttu-id="a4ebf-112">Beachten Sie, dass nicht alle aufgelisteten Bindungselemente in jeder Bindung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a4ebf-112">Note that not all the binding elements listed are required in every binding.</span></span> <span data-ttu-id="a4ebf-113">Auch benutzerdefinierte Bindungselemente können in dieser Auflistung enthalten sein und müssen in der gerade beschriebenen Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a4ebf-113">User-defined binding elements can also appear in this binding element collection and must appear in the same order as previously described.</span></span> <span data-ttu-id="a4ebf-114">Zum Beispiel muss ein benutzerdefinierter Transport das letzte Element der Bindungselementeauflistung sein.</span><span class="sxs-lookup"><span data-stu-id="a4ebf-114">For example, a user-defined transport must be the last element of the binding element collection.</span></span>  
  
 <span data-ttu-id="a4ebf-115">Die <xref:System.ServiceModel.BasicHttpBinding>-Klasse enthält drei Bindungselemente:</span><span class="sxs-lookup"><span data-stu-id="a4ebf-115">The <xref:System.ServiceModel.BasicHttpBinding> class contains three binding elements:</span></span>  
  
1.  <span data-ttu-id="a4ebf-116">Ein optionales Sicherheitsbindungselement, entweder die beim HTTP-Transport verwendete <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>-Klasse (Sicherheit auf Nachrichtenebene) oder die <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>-Klasse, die verwendet wird, wenn die Transportschicht für die Sicherheit sorgt. In diesem Fall wird der HTTPS-Transport verwendet.</span><span class="sxs-lookup"><span data-stu-id="a4ebf-116">An optional security binding element, either the <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> class used with the HTTP transport (message level security) or the <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> class, which is used when the transport layer provides security, in which case the HTTPS transport is used.</span></span>  
  
2.  <span data-ttu-id="a4ebf-117">Ein erforderliches Bindungselement zur Nachrichtencodierung, entweder <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> oder <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="a4ebf-117">A required message encoder binding element, either <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> or <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>.</span></span>  
  
3.  <span data-ttu-id="a4ebf-118">Ein erforderliches Transportbindungselement, entweder <xref:System.ServiceModel.Channels.HttpTransportBindingElement> oder <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="a4ebf-118">A required transport binding element, either <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, or <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.</span></span>  
  
 <span data-ttu-id="a4ebf-119">Wir in diesem Beispiel erstellen Sie eine Instanz der Bindung, generieren eine *benutzerdefinierte Bindung* aus, die Bindungselemente der benutzerdefinierten Bindung untersucht und wenn das HTTP-Bindungselement gefunden wird, legen wir die `KeepAliveEnabled` Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="a4ebf-119">In this example we create an instance of the binding, generate a *custom binding* from it, examine the binding elements in the custom binding, and when we find the HTTP binding element, we set its `KeepAliveEnabled` property to `false`.</span></span> <span data-ttu-id="a4ebf-120">Die `KeepAliveEnabled`-Eigenschaft steht nicht direkt über die `BasicHttpBinding` zur Verfügung, sodass eine benutzerdefinierte Bindung erstellt werden muss, um zum Bindungselement zu navigieren und dessen Eigenschaft festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a4ebf-120">The `KeepAliveEnabled` property is not exposed directly on the `BasicHttpBinding`, so we must create a custom binding to navigate down to the binding element and set this property.</span></span>  
  
### <a name="to-modify-a-system-provided-binding"></a><span data-ttu-id="a4ebf-121">So ändern Sie eine vom System bereitgestellte Bindung</span><span class="sxs-lookup"><span data-stu-id="a4ebf-121">To modify a system-provided binding</span></span>  
  
1.  <span data-ttu-id="a4ebf-122">Erstellen Sie eine Instanz der <xref:System.ServiceModel.BasicHttpBinding>-Klasse und legen Sie ihren Sicherheitsmodus auf die Nachrichtenebene fest.</span><span class="sxs-lookup"><span data-stu-id="a4ebf-122">Create an instance of the <xref:System.ServiceModel.BasicHttpBinding> class and set its security mode to message-level.</span></span>  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#1)]
     [!code-vb[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#1)]  
  
2.  <span data-ttu-id="a4ebf-123">Erstellen Sie eine benutzerdefinierte Bindung aus dieser Bindung, und erstellen Sie eine <xref:System.ServiceModel.Channels.BindingElementCollection>-Klasse aus einer der Eigenschaften der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="a4ebf-123">Create a custom binding from the binding and create a <xref:System.ServiceModel.Channels.BindingElementCollection> class from one of the custom binding's properties.</span></span>  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#2)]
     [!code-vb[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#2)]  
  
3.  <span data-ttu-id="a4ebf-124">Durchlaufen Sie die <xref:System.ServiceModel.Channels.BindingElementCollection>-Klasse, und wenn Sie die <xref:System.ServiceModel.Channels.HttpTransportBindingElement>-Klasse gefunden haben, legen Sie deren <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A>-Eigenschaft auf `false` fest.</span><span class="sxs-lookup"><span data-stu-id="a4ebf-124">Loop through the <xref:System.ServiceModel.Channels.BindingElementCollection> class, and when you find the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> class, set its <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> property to `false`.</span></span>  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#3)]
     [!code-vb[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="a4ebf-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4ebf-125">See Also</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="a4ebf-126">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="a4ebf-126">Custom Bindings</span></span>](../../../../docs/framework/wcf/extending/custom-bindings.md)
