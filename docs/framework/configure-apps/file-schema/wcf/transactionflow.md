---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: 206a684e1279871eee4aed95a087921123f8efb9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918660"
---
# <a name="transactionflow"></a><span data-ttu-id="2eb44-101">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="2eb44-101">\<transactionFlow></span></span>
<span data-ttu-id="2eb44-102">Gibt die Transaktionsflussunterstützung für die benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="2eb44-102">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="2eb44-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2eb44-103">\<system.serviceModel></span></span>  
<span data-ttu-id="2eb44-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="2eb44-104">\<bindings></span></span>  
<span data-ttu-id="2eb44-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="2eb44-105">\<customBinding></span></span>  
<span data-ttu-id="2eb44-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="2eb44-106">\<binding></span></span>  
<span data-ttu-id="2eb44-107">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="2eb44-107">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2eb44-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="2eb44-108">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2eb44-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2eb44-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2eb44-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2eb44-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2eb44-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="2eb44-111">Attributes</span></span>  
  
|<span data-ttu-id="2eb44-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="2eb44-112">Attribute</span></span>|<span data-ttu-id="2eb44-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2eb44-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2eb44-114">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="2eb44-114">transactionProtocol</span></span>|<span data-ttu-id="2eb44-115">Gibt das zu verwendende Transaktionsprotokoll an.</span><span class="sxs-lookup"><span data-stu-id="2eb44-115">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="2eb44-116">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="2eb44-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="2eb44-117">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="2eb44-117">-   OleTransactions</span></span><br /><span data-ttu-id="2eb44-118">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="2eb44-118">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="2eb44-119">Der Standardwert ist OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="2eb44-119">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="2eb44-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="2eb44-120">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2eb44-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2eb44-121">Child Elements</span></span>  
 <span data-ttu-id="2eb44-122">Keine</span><span class="sxs-lookup"><span data-stu-id="2eb44-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2eb44-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2eb44-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2eb44-124">Element</span><span class="sxs-lookup"><span data-stu-id="2eb44-124">Element</span></span>|<span data-ttu-id="2eb44-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2eb44-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2eb44-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="2eb44-126">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="2eb44-127">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="2eb44-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2eb44-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2eb44-128">Remarks</span></span>  
 <span data-ttu-id="2eb44-129">Mit diesem Element können Sie den eingehenden Transaktionsfluss in den Bindungseinstellungen eines Endpunkts aktivieren oder deaktivieren und das gewünschte Protokollformat für eingehende Transaktionen angeben.</span><span class="sxs-lookup"><span data-stu-id="2eb44-129">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="2eb44-130">Weitere Informationen zur Verwendung dieses Konfigurations Elements finden Sie unter [Service Model Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) und [Aktivieren des Transaktions Flusses](../../../wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="2eb44-130">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="2eb44-131">Bei Verwendung des `OleTransactions`-Protokolls für den Transaktionsfluss von Endpunkt zu Endpunkt kann das Transaktionstimeout verloren gehen, wenn der Zielendpunkt mit einem anderen Protokoll als `OleTransactions` versucht, die Transaktion erneut weiterzugeben.</span><span class="sxs-lookup"><span data-stu-id="2eb44-131">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="2eb44-132">Dies kann dazu führen, dass alle Knoten auf den unteren Ebenen nach dem OleTransactions-Hop später als erwartet das Timeout erreichen.</span><span class="sxs-lookup"><span data-stu-id="2eb44-132">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eb44-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2eb44-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="2eb44-134">ServiceModel-Transaktionskonfiguration</span><span class="sxs-lookup"><span data-stu-id="2eb44-134">ServiceModel Transaction Configuration</span></span>](../../../wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="2eb44-135">Aktivieren des Transaktionsdatenflusses</span><span class="sxs-lookup"><span data-stu-id="2eb44-135">Enabling Transaction Flow</span></span>](../../../wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="2eb44-136">Bindungen</span><span class="sxs-lookup"><span data-stu-id="2eb44-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2eb44-137">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="2eb44-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="2eb44-138">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="2eb44-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="2eb44-139">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="2eb44-139">\<customBinding></span></span>](custombinding.md)
