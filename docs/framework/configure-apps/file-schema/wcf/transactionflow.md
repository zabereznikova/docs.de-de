---
title: '&lt;TransactionFlow-Protokolls&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3720294ac937c6aa7ce99ab687efa76b2e860abb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="lttransactionflowgt"></a><span data-ttu-id="4f42f-102">&lt;TransactionFlow-Protokolls&gt;</span><span class="sxs-lookup"><span data-stu-id="4f42f-102">&lt;transactionFlow&gt;</span></span>
<span data-ttu-id="4f42f-103">Gibt die Transaktionsflussunterstützung für die benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="4f42f-103">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="4f42f-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="4f42f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="4f42f-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="4f42f-105">\<bindings></span></span>  
<span data-ttu-id="4f42f-106">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="4f42f-106">\<customBinding></span></span>  
<span data-ttu-id="4f42f-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="4f42f-107">\<binding></span></span>  
<span data-ttu-id="4f42f-108">\<TransactionFlow ></span><span class="sxs-lookup"><span data-stu-id="4f42f-108">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f42f-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f42f-109">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f42f-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4f42f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4f42f-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4f42f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f42f-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="4f42f-112">Attributes</span></span>  
  
|<span data-ttu-id="4f42f-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="4f42f-113">Attribute</span></span>|<span data-ttu-id="4f42f-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f42f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4f42f-115">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="4f42f-115">transactionProtocol</span></span>|<span data-ttu-id="4f42f-116">Gibt das zu verwendende Transaktionsprotokoll an.</span><span class="sxs-lookup"><span data-stu-id="4f42f-116">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="4f42f-117">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="4f42f-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="4f42f-118">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="4f42f-118">-   OleTransactions</span></span><br /><span data-ttu-id="4f42f-119">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="4f42f-119">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="4f42f-120">Der Standardwert ist OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="4f42f-120">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="4f42f-121">Dieses Attribut ist vom Typ <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="4f42f-121">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f42f-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4f42f-122">Child Elements</span></span>  
 <span data-ttu-id="4f42f-123">Keine</span><span class="sxs-lookup"><span data-stu-id="4f42f-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4f42f-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4f42f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="4f42f-125">Element</span><span class="sxs-lookup"><span data-stu-id="4f42f-125">Element</span></span>|<span data-ttu-id="4f42f-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f42f-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f42f-127">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="4f42f-127">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="4f42f-128">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="4f42f-128">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f42f-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4f42f-129">Remarks</span></span>  
 <span data-ttu-id="4f42f-130">Mit diesem Element können Sie den eingehenden Transaktionsfluss in den Bindungseinstellungen eines Endpunkts aktivieren oder deaktivieren und das gewünschte Protokollformat für eingehende Transaktionen angeben.</span><span class="sxs-lookup"><span data-stu-id="4f42f-130">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="4f42f-131">Weitere Informationen zur Verwendung dieses Konfigurationselements finden Sie unter [ServiceModel-Transaktionskonfiguration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) und [Transaktionsfluss aktivieren](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="4f42f-131">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4f42f-132">Bei Verwendung des `OleTransactions`-Protokolls für den Transaktionsfluss von Endpunkt zu Endpunkt kann das Transaktionstimeout verloren gehen, wenn der Zielendpunkt mit einem anderen Protokoll als `OleTransactions` versucht, die Transaktion erneut weiterzugeben.</span><span class="sxs-lookup"><span data-stu-id="4f42f-132">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="4f42f-133">Dies kann dazu führen, dass alle Knoten auf den unteren Ebenen nach dem OleTransactions-Hop später als erwartet das Timeout erreichen.</span><span class="sxs-lookup"><span data-stu-id="4f42f-133">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f42f-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f42f-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransactionFlowElement>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="4f42f-135">ServiceModel-Transaktionskonfiguration</span><span class="sxs-lookup"><span data-stu-id="4f42f-135">ServiceModel Transaction Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)  
 [<span data-ttu-id="4f42f-136">Aktivieren des Transaktionsdatenflusses</span><span class="sxs-lookup"><span data-stu-id="4f42f-136">Enabling Transaction Flow</span></span>](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)  
 [<span data-ttu-id="4f42f-137">Bindungen</span><span class="sxs-lookup"><span data-stu-id="4f42f-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="4f42f-138">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="4f42f-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="4f42f-139">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="4f42f-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="4f42f-140">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="4f42f-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
