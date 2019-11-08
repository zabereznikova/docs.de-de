---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: f5bcd142fb2b032ea179bcbba68fee53b98d2d77
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736312"
---
# <a name="transactionflow"></a><span data-ttu-id="aff19-101">\<transaktionflow ></span><span class="sxs-lookup"><span data-stu-id="aff19-101">\<transactionFlow></span></span>
<span data-ttu-id="aff19-102">Gibt die Transaktionsflussunterstützung für die benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="aff19-102">Specifies transaction flow support for the custom binding.</span></span>  
  
<span data-ttu-id="aff19-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aff19-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="aff19-104">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="aff19-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="aff19-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="aff19-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="aff19-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="aff19-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="aff19-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="aff19-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="aff19-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<transaktionflow >**</span><span class="sxs-lookup"><span data-stu-id="aff19-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactionFlow>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aff19-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="aff19-109">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aff19-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="aff19-110">Attributes and Elements</span></span>  
 <span data-ttu-id="aff19-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="aff19-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aff19-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="aff19-112">Attributes</span></span>  
  
|<span data-ttu-id="aff19-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="aff19-113">Attribute</span></span>|<span data-ttu-id="aff19-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aff19-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aff19-115">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="aff19-115">transactionProtocol</span></span>|<span data-ttu-id="aff19-116">Gibt das zu verwendende Transaktionsprotokoll an.</span><span class="sxs-lookup"><span data-stu-id="aff19-116">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="aff19-117">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="aff19-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="aff19-118">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="aff19-118">-   OleTransactions</span></span><br /><span data-ttu-id="aff19-119">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="aff19-119">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="aff19-120">Der Standardwert ist OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="aff19-120">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="aff19-121">Dieses Attribut ist vom Typ <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="aff19-121">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aff19-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aff19-122">Child Elements</span></span>  
 <span data-ttu-id="aff19-123">Keine</span><span class="sxs-lookup"><span data-stu-id="aff19-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aff19-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aff19-124">Parent Elements</span></span>  
  
|<span data-ttu-id="aff19-125">Element</span><span class="sxs-lookup"><span data-stu-id="aff19-125">Element</span></span>|<span data-ttu-id="aff19-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aff19-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aff19-127">\<binding ></span><span class="sxs-lookup"><span data-stu-id="aff19-127">\<binding></span></span>](bindings.md)|<span data-ttu-id="aff19-128">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="aff19-128">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aff19-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aff19-129">Remarks</span></span>  
 <span data-ttu-id="aff19-130">Mit diesem Element können Sie den eingehenden Transaktionsfluss in den Bindungseinstellungen eines Endpunkts aktivieren oder deaktivieren und das gewünschte Protokollformat für eingehende Transaktionen angeben.</span><span class="sxs-lookup"><span data-stu-id="aff19-130">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="aff19-131">Weitere Informationen zur Verwendung dieses Konfigurations Elements finden Sie unter [Service Model Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) und [Aktivieren des Transaktions Flusses](../../../wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="aff19-131">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="aff19-132">Bei Verwendung des `OleTransactions`-Protokolls für den Transaktionsfluss von Endpunkt zu Endpunkt kann das Transaktionstimeout verloren gehen, wenn der Zielendpunkt mit einem anderen Protokoll als `OleTransactions` versucht, die Transaktion erneut weiterzugeben.</span><span class="sxs-lookup"><span data-stu-id="aff19-132">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="aff19-133">Dies kann dazu führen, dass alle Knoten auf den unteren Ebenen nach dem OleTransactions-Hop später als erwartet das Timeout erreichen.</span><span class="sxs-lookup"><span data-stu-id="aff19-133">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aff19-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aff19-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="aff19-135">ServiceModel-Transaktionskonfiguration</span><span class="sxs-lookup"><span data-stu-id="aff19-135">ServiceModel Transaction Configuration</span></span>](../../../wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="aff19-136">Aktivieren des Transaktionsdatenflusses</span><span class="sxs-lookup"><span data-stu-id="aff19-136">Enabling Transaction Flow</span></span>](../../../wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="aff19-137">Bindungen</span><span class="sxs-lookup"><span data-stu-id="aff19-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="aff19-138">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="aff19-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="aff19-139">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="aff19-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="aff19-140">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="aff19-140">\<customBinding></span></span>](custombinding.md)
