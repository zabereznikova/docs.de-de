---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: c4e5cbac24e2c72791c2f5c0faed0703363c99e1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201420"
---
# \<transactionFlow>

<span data-ttu-id="5476e-101">Gibt die Transaktionsflussunterstützung für die benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="5476e-101">Specifies transaction flow support for the custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactionFlow>**  
  
## <a name="syntax"></a><span data-ttu-id="5476e-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="5476e-102">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5476e-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5476e-103">Attributes and Elements</span></span>  

 <span data-ttu-id="5476e-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5476e-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5476e-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="5476e-105">Attributes</span></span>  
  
|<span data-ttu-id="5476e-106">attribute</span><span class="sxs-lookup"><span data-stu-id="5476e-106">Attribute</span></span>|<span data-ttu-id="5476e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5476e-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5476e-108">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="5476e-108">transactionProtocol</span></span>|<span data-ttu-id="5476e-109">Gibt das zu verwendende Transaktionsprotokoll an.</span><span class="sxs-lookup"><span data-stu-id="5476e-109">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="5476e-110">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="5476e-110">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5476e-111">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="5476e-111">-   OleTransactions</span></span><br /><span data-ttu-id="5476e-112">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="5476e-112">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="5476e-113">Der Standardwert ist OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="5476e-113">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="5476e-114">Dieses Attribut ist vom Typ <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="5476e-114">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5476e-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5476e-115">Child Elements</span></span>  

 <span data-ttu-id="5476e-116">Keine</span><span class="sxs-lookup"><span data-stu-id="5476e-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5476e-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5476e-117">Parent Elements</span></span>  
  
|<span data-ttu-id="5476e-118">Element</span><span class="sxs-lookup"><span data-stu-id="5476e-118">Element</span></span>|<span data-ttu-id="5476e-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5476e-119">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="5476e-120">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="5476e-120">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5476e-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5476e-121">Remarks</span></span>  

 <span data-ttu-id="5476e-122">Mit diesem Element können Sie den eingehenden Transaktionsfluss in den Bindungseinstellungen eines Endpunkts aktivieren oder deaktivieren und das gewünschte Protokollformat für eingehende Transaktionen angeben.</span><span class="sxs-lookup"><span data-stu-id="5476e-122">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="5476e-123">Weitere Informationen zur Verwendung dieses Konfigurations Elements finden Sie unter [Service Model Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) und [Aktivieren des Transaktions Flusses](../../../wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="5476e-123">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="5476e-124">Bei Verwendung des `OleTransactions`-Protokolls für den Transaktionsfluss von Endpunkt zu Endpunkt kann das Transaktionstimeout verloren gehen, wenn der Zielendpunkt mit einem anderen Protokoll als `OleTransactions` versucht, die Transaktion erneut weiterzugeben.</span><span class="sxs-lookup"><span data-stu-id="5476e-124">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="5476e-125">Dies kann dazu führen, dass alle Knoten auf den unteren Ebenen nach dem OleTransactions-Hop später als erwartet das Timeout erreichen.</span><span class="sxs-lookup"><span data-stu-id="5476e-125">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5476e-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5476e-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="5476e-127">ServiceModel-Transaktionskonfiguration</span><span class="sxs-lookup"><span data-stu-id="5476e-127">ServiceModel Transaction Configuration</span></span>](../../../wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="5476e-128">Aktivieren des Transaktionsflusses</span><span class="sxs-lookup"><span data-stu-id="5476e-128">Enabling Transaction Flow</span></span>](../../../wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="5476e-129">Bindungen</span><span class="sxs-lookup"><span data-stu-id="5476e-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5476e-130">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="5476e-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5476e-131">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="5476e-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
