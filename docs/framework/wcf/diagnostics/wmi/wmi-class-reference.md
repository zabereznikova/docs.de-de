---
title: WMI-Klassenreferenz
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b95a51f5-8251-4619-ae05-7de88cb90f9a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0e221c8197b9713dd5f4e35114ada3c63f4978ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="wmi-class-reference"></a><span data-ttu-id="3815b-102">WMI-Klassenreferenz</span><span class="sxs-lookup"><span data-stu-id="3815b-102">WMI Class Reference</span></span>
<span data-ttu-id="3815b-103">In diesem Abschnitt sind alle WMI-Klassen aufgeführt, die vom WMI-Anbieter von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] offengelegt werden.</span><span class="sxs-lookup"><span data-stu-id="3815b-103">This section lists all the WMI classes exposed by the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] WMI provider.</span></span>  
  
## <a name="accessing-wmi-instances"></a><span data-ttu-id="3815b-104">Zugreifen auf WMI-Instanzen</span><span class="sxs-lookup"><span data-stu-id="3815b-104">Accessing WMI Instances</span></span>  
 <span data-ttu-id="3815b-105">Alle in der WMI-Objektreferenz aufgeführten Klassen können nicht direkt instanziiert werden, mit Ausnahme von Service, AppDomain, Contract, ServiceAppDomain, ServiceToEndpointAssociation und Endpoint.</span><span class="sxs-lookup"><span data-stu-id="3815b-105">All the classes listed in the WMI Object Reference cannot be directly instantiated, except for Service, AppDomain, Contract, ServiceAppDomain, ServiceToEndpointAssociation and Endpoint.</span></span> <span data-ttu-id="3815b-106">Um auf die anderen Instanzen zuzugreifen, können Sie auf die Eigenschaften der vorher erwähnten Klassen der obersten Ebene zugreifen.</span><span class="sxs-lookup"><span data-stu-id="3815b-106">To access other instances, you can access the properties of the previously mentioned top level classes.</span></span> <span data-ttu-id="3815b-107">Zum Beispiel können Sie auf die "TransportBindingElement"Instanz über "Endpoint-Instanz -> Binding -> BindingElements" zugreifen.</span><span class="sxs-lookup"><span data-stu-id="3815b-107">For example, you can access the TransportBindingElement instance from the Endpoint instance -> Binding -> BindingElements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3815b-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3815b-108">In This Section</span></span>  
 [<span data-ttu-id="3815b-109">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="3815b-109">ActivityTransfer</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/activitytransfer.md)  
  
 [<span data-ttu-id="3815b-110">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="3815b-110">AppDomainInfo</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/appdomaininfo.md)  
  
 [<span data-ttu-id="3815b-111">AspNetCompatibilityRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="3815b-111">AspNetCompatibilityRequirementsAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/aspnetcompatibilityrequirementsattribute.md)  
  
 [<span data-ttu-id="3815b-112">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-112">AsymmetricSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/asymmetricsecuritybindingelement.md)  
  
 <span data-ttu-id="3815b-113">"Behavior-Klasse"</span><span class="sxs-lookup"><span data-stu-id="3815b-113">"Behavior class"</span></span>  
  
 [<span data-ttu-id="3815b-114">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-114">BinaryMessageEncodingBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/binarymessageencodingbindingelement.md)  
  
 [<span data-ttu-id="3815b-115">Bindung</span><span class="sxs-lookup"><span data-stu-id="3815b-115">Binding</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/binding.md)  
  
 [<span data-ttu-id="3815b-116">BindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-116">BindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/bindingelement.md)  
  
 [<span data-ttu-id="3815b-117">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="3815b-117">CallbackBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/callbackbehavior.md)  
  
 [<span data-ttu-id="3815b-118">Channel-Klasse</span><span class="sxs-lookup"><span data-stu-id="3815b-118">Channel class</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/channel-class.md)  
  
 [<span data-ttu-id="3815b-119">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="3815b-119">ChannelPoolSettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/channelpoolsettings.md)  
  
 [<span data-ttu-id="3815b-120">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="3815b-120">ClientCredentials</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/clientcredentials.md)  
  
 [<span data-ttu-id="3815b-121">ClientViaBehavior</span><span class="sxs-lookup"><span data-stu-id="3815b-121">ClientViaBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md)  
  
 [<span data-ttu-id="3815b-122">CompositeDuplexBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-122">CompositeDuplexBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/compositeduplexbindingelement.md)  
  
 [<span data-ttu-id="3815b-123">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-123">ConnectionOrientedTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/connectionorientedtransportbindingelement.md)  
  
 [<span data-ttu-id="3815b-124">Vertrag</span><span class="sxs-lookup"><span data-stu-id="3815b-124">Contract</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/contract.md)  
  
 [<span data-ttu-id="3815b-125">CustomBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-125">CustomBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/custombindingelement.md)  
  
 [<span data-ttu-id="3815b-126">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="3815b-126">DeliveryRequirementsAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/deliveryrequirementsattribute.md)  
  
 [<span data-ttu-id="3815b-127">Endpunkt</span><span class="sxs-lookup"><span data-stu-id="3815b-127">Endpoint</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md)  
  
 [<span data-ttu-id="3815b-128">HttpsTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-128">HttpsTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/httpstransportbindingelement.md)  
  
 [<span data-ttu-id="3815b-129">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-129">HttpTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/httptransportbindingelement.md)  
  
 [<span data-ttu-id="3815b-130">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="3815b-130">LocalServiceSecuritySettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/localservicesecuritysettings.md)  
  
 [<span data-ttu-id="3815b-131">MatchAllEndpointBehavior</span><span class="sxs-lookup"><span data-stu-id="3815b-131">MatchAllEndpointBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/matchallendpointbehavior.md)  
  
 [<span data-ttu-id="3815b-132">MessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-132">MessageEncodingBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/messageencodingbindingelement.md)  
  
 [<span data-ttu-id="3815b-133">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="3815b-133">MsmqBindingElementBase</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/msmqbindingelementbase.md)  
  
 [<span data-ttu-id="3815b-134">MsmqIntegrationBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-134">MsmqIntegrationBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/msmqintegrationbindingelement.md)  
  
 [<span data-ttu-id="3815b-135">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-135">MsmqTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/msmqtransportbindingelement.md)  
  
 [<span data-ttu-id="3815b-136">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-136">MtomMessageEncodingBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/mtommessageencodingbindingelement.md)  
  
 [<span data-ttu-id="3815b-137">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="3815b-137">MustUnderstandBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/mustunderstandbehavior.md)  
  
 [<span data-ttu-id="3815b-138">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="3815b-138">NamedPipeConnectionPoolSettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/namedpipeconnectionpoolsettings.md)  
  
 [<span data-ttu-id="3815b-139">NamedPipeTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-139">NamedPipeTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/namedpipetransportbindingelement.md)  
  
 [<span data-ttu-id="3815b-140">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-140">OneWayBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/onewaybindingelement.md)  
  
 <span data-ttu-id="3815b-141">"Vorgang Class"</span><span class="sxs-lookup"><span data-stu-id="3815b-141">"Operation class"</span></span>  
  
 [<span data-ttu-id="3815b-142">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="3815b-142">OperationBehaviorAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/operationbehaviorattribute.md)  
  
 [<span data-ttu-id="3815b-143">PeerCustomResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-143">PeerCustomResolverBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peercustomresolverbindingelement.md)  
  
 [<span data-ttu-id="3815b-144">PeerResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-144">PeerResolverBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peerresolverbindingelement.md)  
  
 [<span data-ttu-id="3815b-145">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="3815b-145">PeerSecuritySettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peersecuritysettings.md)  
  
 [<span data-ttu-id="3815b-146">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-146">PeerTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peertransportbindingelement.md)  
  
 [<span data-ttu-id="3815b-147">PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="3815b-147">PeerTransportSecuritySettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peertransportsecuritysettings.md)  
  
 [<span data-ttu-id="3815b-148">PnrpPeerResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-148">PnrpPeerResolverBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/pnrppeerresolverbindingelement.md)  
  
 [<span data-ttu-id="3815b-149">PrivacyNoticeBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-149">PrivacyNoticeBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/privacynoticebindingelement.md)  
  
 [<span data-ttu-id="3815b-150">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-150">ReliableSessionBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/reliablesessionbindingelement.md)  
  
 [<span data-ttu-id="3815b-151">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-151">SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/securitybindingelement.md)  
  
 [<span data-ttu-id="3815b-152">Dienst</span><span class="sxs-lookup"><span data-stu-id="3815b-152">Service</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/service.md)  
  
 [<span data-ttu-id="3815b-153">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="3815b-153">ServiceAppDomain</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/serviceappdomain.md)  
  
 [<span data-ttu-id="3815b-154">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="3815b-154">ServiceAuthorizationBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/serviceauthorizationbehavior.md)  
  
 [<span data-ttu-id="3815b-155">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="3815b-155">ServiceBehaviorAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicebehaviorattribute.md)  
  
 [<span data-ttu-id="3815b-156">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="3815b-156">ServiceCredentials</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicecredentials.md)  
  
 [<span data-ttu-id="3815b-157">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="3815b-157">ServiceDebugBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicedebugbehavior.md)  
  
 [<span data-ttu-id="3815b-158">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="3815b-158">ServiceMetadataBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicemetadatabehavior.md)  
  
 [<span data-ttu-id="3815b-159">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="3815b-159">ServiceSecurityAuditBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicesecurityauditbehavior.md)  
  
 [<span data-ttu-id="3815b-160">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="3815b-160">ServiceThrottlingBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicethrottlingbehavior.md)  
  
 [<span data-ttu-id="3815b-161">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="3815b-161">ServiceTimeoutsBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicetimeoutsbehavior.md)  
  
 [<span data-ttu-id="3815b-162">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="3815b-162">ServiceToEndpointAssociation</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicetoendpointassociation.md)  
  
 [<span data-ttu-id="3815b-163">SslStreamSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-163">SslStreamSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/sslstreamsecuritybindingelement.md)  
  
 [<span data-ttu-id="3815b-164">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-164">SymmetricSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/symmetricsecuritybindingelement.md)  
  
 [<span data-ttu-id="3815b-165">SynchronousReceiveBehavior</span><span class="sxs-lookup"><span data-stu-id="3815b-165">SynchronousReceiveBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/synchronousreceivebehavior.md)  
  
 [<span data-ttu-id="3815b-166">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="3815b-166">TcpConnectionPoolSettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/tcpconnectionpoolsettings.md)  
  
 [<span data-ttu-id="3815b-167">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-167">TcpTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/tcptransportbindingelement.md)  
  
 [<span data-ttu-id="3815b-168">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-168">TextMessageEncodingBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/textmessageencodingbindingelement.md)  
  
 [<span data-ttu-id="3815b-169">TraceListener</span><span class="sxs-lookup"><span data-stu-id="3815b-169">TraceListener</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/tracelistener.md)  
  
 [<span data-ttu-id="3815b-170">TraceListenerArgument</span><span class="sxs-lookup"><span data-stu-id="3815b-170">TraceListenerArgument</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/tracelistenerargument.md)  
  
 [<span data-ttu-id="3815b-171">TransactedBatchingBehavior</span><span class="sxs-lookup"><span data-stu-id="3815b-171">TransactedBatchingBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transactedbatchingbehavior.md)  
  
 [<span data-ttu-id="3815b-172">TransactionFlowAttribute</span><span class="sxs-lookup"><span data-stu-id="3815b-172">TransactionFlowAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transactionflowattribute.md)  
  
 [<span data-ttu-id="3815b-173">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-173">TransactionFlowBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transactionflowbindingelement.md)  
  
 [<span data-ttu-id="3815b-174">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-174">TransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transportbindingelement.md)  
  
 [<span data-ttu-id="3815b-175">TransportSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-175">TransportSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transportsecuritybindingelement.md)  
  
 [<span data-ttu-id="3815b-176">UseManagedPresentationBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-176">UseManagedPresentationBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/usemanagedpresentationbindingelement.md)  
  
 [<span data-ttu-id="3815b-177">WindowsStreamSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="3815b-177">WindowsStreamSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/windowsstreamsecuritybindingelement.md)  
  
 [<span data-ttu-id="3815b-178">WSAT_TraceEvent</span><span class="sxs-lookup"><span data-stu-id="3815b-178">WSAT_TraceEvent</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/wsat-traceevent.md)  
  
 [<span data-ttu-id="3815b-179">WSAT_TraceProvider</span><span class="sxs-lookup"><span data-stu-id="3815b-179">WSAT_TraceProvider</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/wsat-traceprovider.md)  
  
 [<span data-ttu-id="3815b-180">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="3815b-180">WSAT_TraceRecord</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/wsat-tracerecord.md)  
  
 [<span data-ttu-id="3815b-181">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="3815b-181">XmlDictionaryReaderQuotas</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/xmldictionaryreaderquotas.md)  
  
 [<span data-ttu-id="3815b-182">XmlSerializerOperationBehavior</span><span class="sxs-lookup"><span data-stu-id="3815b-182">XmlSerializerOperationBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/xmlserializeroperationbehavior.md)
