---
title: '&lt;TransactionFlow-Protokolls&gt;'
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: c708098676e5634281e29c17639304a1a9cf5afe
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="lttransactionflowgt"></a><span data-ttu-id="68148-102">&lt;TransactionFlow-Protokolls&gt;</span><span class="sxs-lookup"><span data-stu-id="68148-102">&lt;transactionFlow&gt;</span></span>
<span data-ttu-id="68148-103">Gibt die Transaktionsflussunterstützung für die benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="68148-103">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="68148-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="68148-104">\<system.serviceModel></span></span>  
<span data-ttu-id="68148-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="68148-105">\<bindings></span></span>  
<span data-ttu-id="68148-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="68148-106">\<customBinding></span></span>  
<span data-ttu-id="68148-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="68148-107">\<binding></span></span>  
<span data-ttu-id="68148-108">\<TransactionFlow ></span><span class="sxs-lookup"><span data-stu-id="68148-108">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68148-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="68148-109">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68148-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="68148-110">Attributes and Elements</span></span>  
 <span data-ttu-id="68148-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="68148-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68148-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="68148-112">Attributes</span></span>  
  
|<span data-ttu-id="68148-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="68148-113">Attribute</span></span>|<span data-ttu-id="68148-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="68148-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="68148-115">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="68148-115">transactionProtocol</span></span>|<span data-ttu-id="68148-116">Gibt das zu verwendende Transaktionsprotokoll an.</span><span class="sxs-lookup"><span data-stu-id="68148-116">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="68148-117">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="68148-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="68148-118">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="68148-118">-   OleTransactions</span></span><br /><span data-ttu-id="68148-119">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="68148-119">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="68148-120">Der Standardwert ist OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="68148-120">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="68148-121">Dieses Attribut ist vom Typ <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="68148-121">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="68148-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="68148-122">Child Elements</span></span>  
 <span data-ttu-id="68148-123">Keine</span><span class="sxs-lookup"><span data-stu-id="68148-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="68148-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="68148-124">Parent Elements</span></span>  
  
|<span data-ttu-id="68148-125">Element</span><span class="sxs-lookup"><span data-stu-id="68148-125">Element</span></span>|<span data-ttu-id="68148-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="68148-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68148-127">\<binding></span><span class="sxs-lookup"><span data-stu-id="68148-127">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="68148-128">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="68148-128">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68148-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="68148-129">Remarks</span></span>  
 <span data-ttu-id="68148-130">Mit diesem Element können Sie den eingehenden Transaktionsfluss in den Bindungseinstellungen eines Endpunkts aktivieren oder deaktivieren und das gewünschte Protokollformat für eingehende Transaktionen angeben.</span><span class="sxs-lookup"><span data-stu-id="68148-130">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="68148-131">Weitere Informationen zur Verwendung dieses Konfigurationselements finden Sie unter [ServiceModel-Transaktionskonfiguration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) und [Transaktionsfluss aktivieren](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="68148-131">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="68148-132">Bei Verwendung des `OleTransactions`-Protokolls für den Transaktionsfluss von Endpunkt zu Endpunkt kann das Transaktionstimeout verloren gehen, wenn der Zielendpunkt mit einem anderen Protokoll als `OleTransactions` versucht, die Transaktion erneut weiterzugeben.</span><span class="sxs-lookup"><span data-stu-id="68148-132">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="68148-133">Dies kann dazu führen, dass alle Knoten auf den unteren Ebenen nach dem OleTransactions-Hop später als erwartet das Timeout erreichen.</span><span class="sxs-lookup"><span data-stu-id="68148-133">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68148-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68148-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransactionFlowElement>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="68148-135">ServiceModel-Transaktionskonfiguration</span><span class="sxs-lookup"><span data-stu-id="68148-135">ServiceModel Transaction Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)  
 [<span data-ttu-id="68148-136">Aktivieren des Transaktionsdatenflusses</span><span class="sxs-lookup"><span data-stu-id="68148-136">Enabling Transaction Flow</span></span>](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)  
 [<span data-ttu-id="68148-137">Bindungen</span><span class="sxs-lookup"><span data-stu-id="68148-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="68148-138">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="68148-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="68148-139">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="68148-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="68148-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="68148-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
