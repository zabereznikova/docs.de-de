---
title: WMI-Klassenreferenz
ms.date: 03/30/2017
ms.assetid: b95a51f5-8251-4619-ae05-7de88cb90f9a
ms.openlocfilehash: 226e4dedecd152f3a3d4143280529c7823339932
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795873"
---
# <a name="wmi-class-reference"></a><span data-ttu-id="5f4aa-102">WMI-Klassenreferenz</span><span class="sxs-lookup"><span data-stu-id="5f4aa-102">WMI Class Reference</span></span>
<span data-ttu-id="5f4aa-103">In diesem Abschnitt werden alle WMI-Klassen aufgelistet, die vom WMI-Anbieter für Windows Communication Foundation (WCF) verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="5f4aa-103">This section lists all the WMI classes exposed by the Windows Communication Foundation (WCF) WMI provider.</span></span>  
  
## <a name="accessing-wmi-instances"></a><span data-ttu-id="5f4aa-104">Zugreifen auf WMI-Instanzen</span><span class="sxs-lookup"><span data-stu-id="5f4aa-104">Accessing WMI Instances</span></span>  
 <span data-ttu-id="5f4aa-105">Alle in der WMI-Objektreferenz aufgeführten Klassen können nicht direkt instanziiert werden, mit Ausnahme von Service, AppDomain, Contract, ServiceAppDomain, ServiceToEndpointAssociation und Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5f4aa-105">All the classes listed in the WMI Object Reference cannot be directly instantiated, except for Service, AppDomain, Contract, ServiceAppDomain, ServiceToEndpointAssociation and Endpoint.</span></span> <span data-ttu-id="5f4aa-106">Um auf die anderen Instanzen zuzugreifen, können Sie auf die Eigenschaften der vorher erwähnten Klassen der obersten Ebene zugreifen.</span><span class="sxs-lookup"><span data-stu-id="5f4aa-106">To access other instances, you can access the properties of the previously mentioned top level classes.</span></span> <span data-ttu-id="5f4aa-107">Beispielsweise können Sie von der Endpunkt Instanz > Bindungs > BindingElements auf die TransportBindingElement-Instanz zugreifen.</span><span class="sxs-lookup"><span data-stu-id="5f4aa-107">For example, you can access the TransportBindingElement instance from the Endpoint instance -> Binding -> BindingElements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5f4aa-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5f4aa-108">In This Section</span></span>  
 [<span data-ttu-id="5f4aa-109">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="5f4aa-109">ActivityTransfer</span></span>](activitytransfer.md)  
  
 [<span data-ttu-id="5f4aa-110">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="5f4aa-110">AppDomainInfo</span></span>](appdomaininfo.md)  
  
 [<span data-ttu-id="5f4aa-111">AspNetCompatibilityRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="5f4aa-111">AspNetCompatibilityRequirementsAttribute</span></span>](aspnetcompatibilityrequirementsattribute.md)  
  
 [<span data-ttu-id="5f4aa-112">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-112">AsymmetricSecurityBindingElement</span></span>](asymmetricsecuritybindingelement.md)  
  
 <span data-ttu-id="5f4aa-113">"Behavior Class"</span><span class="sxs-lookup"><span data-stu-id="5f4aa-113">"Behavior class"</span></span>  
  
 [<span data-ttu-id="5f4aa-114">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-114">BinaryMessageEncodingBindingElement</span></span>](binarymessageencodingbindingelement.md)  
  
 [<span data-ttu-id="5f4aa-115">Bindung</span><span class="sxs-lookup"><span data-stu-id="5f4aa-115">Binding</span></span>](binding.md)  
  
 [<span data-ttu-id="5f4aa-116">BindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-116">BindingElement</span></span>](bindingelement.md)  
  
 [<span data-ttu-id="5f4aa-117">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="5f4aa-117">CallbackBehavior</span></span>](callbackbehavior.md)  
  
 [<span data-ttu-id="5f4aa-118">Channel-Klasse</span><span class="sxs-lookup"><span data-stu-id="5f4aa-118">Channel class</span></span>](channel-class.md)  
  
 [<span data-ttu-id="5f4aa-119">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="5f4aa-119">ChannelPoolSettings</span></span>](channelpoolsettings.md)  
  
 [<span data-ttu-id="5f4aa-120">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="5f4aa-120">ClientCredentials</span></span>](clientcredentials.md)  
  
 [<span data-ttu-id="5f4aa-121">ClientViaBehavior</span><span class="sxs-lookup"><span data-stu-id="5f4aa-121">ClientViaBehavior</span></span>](clientviabehavior.md)  
  
 [<span data-ttu-id="5f4aa-122">CompositeDuplexBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-122">CompositeDuplexBindingElement</span></span>](compositeduplexbindingelement.md)  
  
 [<span data-ttu-id="5f4aa-123">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-123">ConnectionOrientedTransportBindingElement</span></span>](connectionorientedtransportbindingelement.md)  
  
 [<span data-ttu-id="5f4aa-124">Vertrag</span><span class="sxs-lookup"><span data-stu-id="5f4aa-124">Contract</span></span>](contract.md)  
  
 [<span data-ttu-id="5f4aa-125">CustomBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-125">CustomBindingElement</span></span>](custombindingelement.md)  
  
 [<span data-ttu-id="5f4aa-126">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="5f4aa-126">DeliveryRequirementsAttribute</span></span>](deliveryrequirementsattribute.md)  
  
 [<span data-ttu-id="5f4aa-127">Endpunkt</span><span class="sxs-lookup"><span data-stu-id="5f4aa-127">Endpoint</span></span>](endpoint.md)  
  
 [<span data-ttu-id="5f4aa-128">HttpsTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-128">HttpsTransportBindingElement</span></span>](httpstransportbindingelement.md)  
  
 [<span data-ttu-id="5f4aa-129">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-129">HttpTransportBindingElement</span></span>](httptransportbindingelement.md)  
  
 [<span data-ttu-id="5f4aa-130">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="5f4aa-130">LocalServiceSecuritySettings</span></span>](localservicesecuritysettings.md)  
  
 [<span data-ttu-id="5f4aa-131">MatchAllEndpointBehavior</span><span class="sxs-lookup"><span data-stu-id="5f4aa-131">MatchAllEndpointBehavior</span></span>](matchallendpointbehavior.md)  
  
 [<span data-ttu-id="5f4aa-132">MessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-132">MessageEncodingBindingElement</span></span>](messageencodingbindingelement.md)  
  
 [<span data-ttu-id="5f4aa-133">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="5f4aa-133">MsmqBindingElementBase</span></span>](msmqbindingelementbase.md)  
  
 [<span data-ttu-id="5f4aa-134">MsmqIntegrationBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-134">MsmqIntegrationBindingElement</span></span>](msmqintegrationbindingelement.md)  
  
 [<span data-ttu-id="5f4aa-135">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-135">MsmqTransportBindingElement</span></span>](msmqtransportbindingelement.md)  
  
 [<span data-ttu-id="5f4aa-136">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-136">MtomMessageEncodingBindingElement</span></span>](mtommessageencodingbindingelement.md)  
  
 [<span data-ttu-id="5f4aa-137">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="5f4aa-137">MustUnderstandBehavior</span></span>](mustunderstandbehavior.md)  
  
 [<span data-ttu-id="5f4aa-138">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="5f4aa-138">NamedPipeConnectionPoolSettings</span></span>](namedpipeconnectionpoolsettings.md)  
  
 [<span data-ttu-id="5f4aa-139">NamedPipeTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-139">NamedPipeTransportBindingElement</span></span>](namedpipetransportbindingelement.md)  
  
 [<span data-ttu-id="5f4aa-140">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-140">OneWayBindingElement</span></span>](onewaybindingelement.md)  
  
 <span data-ttu-id="5f4aa-141">"Operation Class"</span><span class="sxs-lookup"><span data-stu-id="5f4aa-141">"Operation class"</span></span>  
  
 [<span data-ttu-id="5f4aa-142">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="5f4aa-142">OperationBehaviorAttribute</span></span>](operationbehaviorattribute.md)  
  
 [<span data-ttu-id="5f4aa-143">PeerCustomResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-143">PeerCustomResolverBindingElement</span></span>](peercustomresolverbindingelement.md)  
  
 [<span data-ttu-id="5f4aa-144">PeerResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-144">PeerResolverBindingElement</span></span>](peerresolverbindingelement.md)  
  
 [<span data-ttu-id="5f4aa-145">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="5f4aa-145">PeerSecuritySettings</span></span>](peersecuritysettings.md)  
  
 [<span data-ttu-id="5f4aa-146">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-146">PeerTransportBindingElement</span></span>](peertransportbindingelement.md)  
  
 [<span data-ttu-id="5f4aa-147">PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="5f4aa-147">PeerTransportSecuritySettings</span></span>](peertransportsecuritysettings.md)  
  
 [<span data-ttu-id="5f4aa-148">PnrpPeerResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-148">PnrpPeerResolverBindingElement</span></span>](pnrppeerresolverbindingelement.md)  
  
 [<span data-ttu-id="5f4aa-149">PrivacyNoticeBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-149">PrivacyNoticeBindingElement</span></span>](privacynoticebindingelement.md)  
  
 [<span data-ttu-id="5f4aa-150">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-150">ReliableSessionBindingElement</span></span>](reliablesessionbindingelement.md)  
  
 [<span data-ttu-id="5f4aa-151">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-151">SecurityBindingElement</span></span>](securitybindingelement.md)  
  
 [<span data-ttu-id="5f4aa-152">Dienst</span><span class="sxs-lookup"><span data-stu-id="5f4aa-152">Service</span></span>](service.md)  
  
 [<span data-ttu-id="5f4aa-153">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="5f4aa-153">ServiceAppDomain</span></span>](serviceappdomain.md)  
  
 [<span data-ttu-id="5f4aa-154">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="5f4aa-154">ServiceAuthorizationBehavior</span></span>](serviceauthorizationbehavior.md)  
  
 [<span data-ttu-id="5f4aa-155">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="5f4aa-155">ServiceBehaviorAttribute</span></span>](servicebehaviorattribute.md)  
  
 [<span data-ttu-id="5f4aa-156">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="5f4aa-156">ServiceCredentials</span></span>](servicecredentials.md)  
  
 [<span data-ttu-id="5f4aa-157">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="5f4aa-157">ServiceDebugBehavior</span></span>](servicedebugbehavior.md)  
  
 [<span data-ttu-id="5f4aa-158">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="5f4aa-158">ServiceMetadataBehavior</span></span>](servicemetadatabehavior.md)  
  
 [<span data-ttu-id="5f4aa-159">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="5f4aa-159">ServiceSecurityAuditBehavior</span></span>](servicesecurityauditbehavior.md)  
  
 [<span data-ttu-id="5f4aa-160">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="5f4aa-160">ServiceThrottlingBehavior</span></span>](servicethrottlingbehavior.md)  
  
 [<span data-ttu-id="5f4aa-161">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="5f4aa-161">ServiceTimeoutsBehavior</span></span>](servicetimeoutsbehavior.md)  
  
 [<span data-ttu-id="5f4aa-162">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="5f4aa-162">ServiceToEndpointAssociation</span></span>](servicetoendpointassociation.md)  
  
 [<span data-ttu-id="5f4aa-163">SslStreamSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-163">SslStreamSecurityBindingElement</span></span>](sslstreamsecuritybindingelement.md)  
  
 [<span data-ttu-id="5f4aa-164">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-164">SymmetricSecurityBindingElement</span></span>](symmetricsecuritybindingelement.md)  
  
 [<span data-ttu-id="5f4aa-165">SynchronousReceiveBehavior</span><span class="sxs-lookup"><span data-stu-id="5f4aa-165">SynchronousReceiveBehavior</span></span>](synchronousreceivebehavior.md)  
  
 [<span data-ttu-id="5f4aa-166">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="5f4aa-166">TcpConnectionPoolSettings</span></span>](tcpconnectionpoolsettings.md)  
  
 [<span data-ttu-id="5f4aa-167">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-167">TcpTransportBindingElement</span></span>](tcptransportbindingelement.md)  
  
 [<span data-ttu-id="5f4aa-168">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-168">TextMessageEncodingBindingElement</span></span>](textmessageencodingbindingelement.md)  
  
 [<span data-ttu-id="5f4aa-169">TraceListener</span><span class="sxs-lookup"><span data-stu-id="5f4aa-169">TraceListener</span></span>](tracelistener.md)  
  
 [<span data-ttu-id="5f4aa-170">TraceListenerArgument</span><span class="sxs-lookup"><span data-stu-id="5f4aa-170">TraceListenerArgument</span></span>](tracelistenerargument.md)  
  
 [<span data-ttu-id="5f4aa-171">TransactedBatchingBehavior</span><span class="sxs-lookup"><span data-stu-id="5f4aa-171">TransactedBatchingBehavior</span></span>](transactedbatchingbehavior.md)  
  
 [<span data-ttu-id="5f4aa-172">TransactionFlowAttribute</span><span class="sxs-lookup"><span data-stu-id="5f4aa-172">TransactionFlowAttribute</span></span>](transactionflowattribute.md)  
  
 [<span data-ttu-id="5f4aa-173">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-173">TransactionFlowBindingElement</span></span>](transactionflowbindingelement.md)  
  
 [<span data-ttu-id="5f4aa-174">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-174">TransportBindingElement</span></span>](transportbindingelement.md)  
  
 [<span data-ttu-id="5f4aa-175">TransportSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-175">TransportSecurityBindingElement</span></span>](transportsecuritybindingelement.md)  
  
 [<span data-ttu-id="5f4aa-176">UseManagedPresentationBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-176">UseManagedPresentationBindingElement</span></span>](usemanagedpresentationbindingelement.md)  
  
 [<span data-ttu-id="5f4aa-177">WindowsStreamSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="5f4aa-177">WindowsStreamSecurityBindingElement</span></span>](windowsstreamsecuritybindingelement.md)  
  
 [<span data-ttu-id="5f4aa-178">WSAT_TraceEvent</span><span class="sxs-lookup"><span data-stu-id="5f4aa-178">WSAT_TraceEvent</span></span>](wsat-traceevent.md)  
  
 [<span data-ttu-id="5f4aa-179">WSAT_TraceProvider</span><span class="sxs-lookup"><span data-stu-id="5f4aa-179">WSAT_TraceProvider</span></span>](wsat-traceprovider.md)  
  
 [<span data-ttu-id="5f4aa-180">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="5f4aa-180">WSAT_TraceRecord</span></span>](wsat-tracerecord.md)  
  
 [<span data-ttu-id="5f4aa-181">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="5f4aa-181">XmlDictionaryReaderQuotas</span></span>](xmldictionaryreaderquotas.md)  
  
 [<span data-ttu-id="5f4aa-182">XmlSerializerOperationBehavior</span><span class="sxs-lookup"><span data-stu-id="5f4aa-182">XmlSerializerOperationBehavior</span></span>](xmlserializeroperationbehavior.md)
