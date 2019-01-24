---
title: '&lt;transactionFlow&gt;'
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: d8597a71a9b7afadba7565290085f491052e04d6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622119"
---
# <a name="lttransactionflowgt"></a><span data-ttu-id="f92fb-102">&lt;transactionFlow&gt;</span><span class="sxs-lookup"><span data-stu-id="f92fb-102">&lt;transactionFlow&gt;</span></span>
<span data-ttu-id="f92fb-103">Gibt die Transaktionsflussunterstützung für die benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="f92fb-103">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="f92fb-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f92fb-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f92fb-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="f92fb-105">\<bindings></span></span>  
<span data-ttu-id="f92fb-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f92fb-106">\<customBinding></span></span>  
<span data-ttu-id="f92fb-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="f92fb-107">\<binding></span></span>  
<span data-ttu-id="f92fb-108">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="f92fb-108">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f92fb-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="f92fb-109">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f92fb-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f92fb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f92fb-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f92fb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f92fb-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="f92fb-112">Attributes</span></span>  
  
|<span data-ttu-id="f92fb-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="f92fb-113">Attribute</span></span>|<span data-ttu-id="f92fb-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f92fb-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f92fb-115">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="f92fb-115">transactionProtocol</span></span>|<span data-ttu-id="f92fb-116">Gibt das zu verwendende Transaktionsprotokoll an.</span><span class="sxs-lookup"><span data-stu-id="f92fb-116">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="f92fb-117">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="f92fb-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f92fb-118">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="f92fb-118">-   OleTransactions</span></span><br /><span data-ttu-id="f92fb-119">-   WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="f92fb-119">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="f92fb-120">Der Standardwert ist OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="f92fb-120">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="f92fb-121">Dieses Attribut ist vom Typ <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="f92fb-121">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f92fb-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f92fb-122">Child Elements</span></span>  
 <span data-ttu-id="f92fb-123">Keine</span><span class="sxs-lookup"><span data-stu-id="f92fb-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f92fb-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f92fb-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f92fb-125">Element</span><span class="sxs-lookup"><span data-stu-id="f92fb-125">Element</span></span>|<span data-ttu-id="f92fb-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f92fb-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f92fb-127">\<binding></span><span class="sxs-lookup"><span data-stu-id="f92fb-127">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="f92fb-128">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="f92fb-128">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f92fb-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f92fb-129">Remarks</span></span>  
 <span data-ttu-id="f92fb-130">Mit diesem Element können Sie den eingehenden Transaktionsfluss in den Bindungseinstellungen eines Endpunkts aktivieren oder deaktivieren und das gewünschte Protokollformat für eingehende Transaktionen angeben.</span><span class="sxs-lookup"><span data-stu-id="f92fb-130">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="f92fb-131">Weitere Informationen zur Verwendung dieses Konfigurationselements finden Sie unter [ServiceModel-Transaktionskonfiguration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) und [Transaktionsfluss aktivieren](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="f92fb-131">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="f92fb-132">Bei Verwendung des `OleTransactions`-Protokolls für den Transaktionsfluss von Endpunkt zu Endpunkt kann das Transaktionstimeout verloren gehen, wenn der Zielendpunkt mit einem anderen Protokoll als `OleTransactions` versucht, die Transaktion erneut weiterzugeben.</span><span class="sxs-lookup"><span data-stu-id="f92fb-132">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="f92fb-133">Dies kann dazu führen, dass alle Knoten auf den unteren Ebenen nach dem OleTransactions-Hop später als erwartet das Timeout erreichen.</span><span class="sxs-lookup"><span data-stu-id="f92fb-133">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f92fb-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f92fb-134">See also</span></span>
- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f92fb-135">ServiceModel-Transaktionskonfiguration</span><span class="sxs-lookup"><span data-stu-id="f92fb-135">ServiceModel Transaction Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="f92fb-136">Aktivieren des Transaktionsdatenflusses</span><span class="sxs-lookup"><span data-stu-id="f92fb-136">Enabling Transaction Flow</span></span>](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="f92fb-137">Bindungen</span><span class="sxs-lookup"><span data-stu-id="f92fb-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="f92fb-138">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="f92fb-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f92fb-139">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="f92fb-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="f92fb-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f92fb-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
