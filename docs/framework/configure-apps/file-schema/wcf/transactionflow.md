---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: 626ae03d622221ab3e956bd03898b6cc30482c98
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758027"
---
# <a name="transactionflow"></a><span data-ttu-id="618f5-101">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="618f5-101">\<transactionFlow></span></span>
<span data-ttu-id="618f5-102">Gibt die Transaktionsflussunterstützung für die benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="618f5-102">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="618f5-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="618f5-103">\<system.serviceModel></span></span>  
<span data-ttu-id="618f5-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="618f5-104">\<bindings></span></span>  
<span data-ttu-id="618f5-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="618f5-105">\<customBinding></span></span>  
<span data-ttu-id="618f5-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="618f5-106">\<binding></span></span>  
<span data-ttu-id="618f5-107">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="618f5-107">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="618f5-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="618f5-108">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="618f5-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="618f5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="618f5-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="618f5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="618f5-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="618f5-111">Attributes</span></span>  
  
|<span data-ttu-id="618f5-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="618f5-112">Attribute</span></span>|<span data-ttu-id="618f5-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="618f5-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="618f5-114">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="618f5-114">transactionProtocol</span></span>|<span data-ttu-id="618f5-115">Gibt das zu verwendende Transaktionsprotokoll an.</span><span class="sxs-lookup"><span data-stu-id="618f5-115">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="618f5-116">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="618f5-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="618f5-117">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="618f5-117">-   OleTransactions</span></span><br /><span data-ttu-id="618f5-118">-   WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="618f5-118">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="618f5-119">Der Standardwert ist OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="618f5-119">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="618f5-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="618f5-120">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="618f5-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="618f5-121">Child Elements</span></span>  
 <span data-ttu-id="618f5-122">Keine</span><span class="sxs-lookup"><span data-stu-id="618f5-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="618f5-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="618f5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="618f5-124">Element</span><span class="sxs-lookup"><span data-stu-id="618f5-124">Element</span></span>|<span data-ttu-id="618f5-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="618f5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="618f5-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="618f5-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="618f5-127">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="618f5-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="618f5-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="618f5-128">Remarks</span></span>  
 <span data-ttu-id="618f5-129">Mit diesem Element können Sie den eingehenden Transaktionsfluss in den Bindungseinstellungen eines Endpunkts aktivieren oder deaktivieren und das gewünschte Protokollformat für eingehende Transaktionen angeben.</span><span class="sxs-lookup"><span data-stu-id="618f5-129">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="618f5-130">Weitere Informationen zur Verwendung dieses Konfigurationselements finden Sie unter [ServiceModel-Transaktionskonfiguration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) und [Transaktionsfluss aktivieren](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="618f5-130">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="618f5-131">Bei Verwendung des `OleTransactions`-Protokolls für den Transaktionsfluss von Endpunkt zu Endpunkt kann das Transaktionstimeout verloren gehen, wenn der Zielendpunkt mit einem anderen Protokoll als `OleTransactions` versucht, die Transaktion erneut weiterzugeben.</span><span class="sxs-lookup"><span data-stu-id="618f5-131">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="618f5-132">Dies kann dazu führen, dass alle Knoten auf den unteren Ebenen nach dem OleTransactions-Hop später als erwartet das Timeout erreichen.</span><span class="sxs-lookup"><span data-stu-id="618f5-132">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="618f5-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="618f5-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="618f5-134">ServiceModel-Transaktionskonfiguration</span><span class="sxs-lookup"><span data-stu-id="618f5-134">ServiceModel Transaction Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="618f5-135">Aktivieren des Transaktionsdatenflusses</span><span class="sxs-lookup"><span data-stu-id="618f5-135">Enabling Transaction Flow</span></span>](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="618f5-136">Bindungen</span><span class="sxs-lookup"><span data-stu-id="618f5-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="618f5-137">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="618f5-137">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="618f5-138">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="618f5-138">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="618f5-139">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="618f5-139">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
