---
title: Vergleichen von Transaktionen in COM+ und ServiceModel
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5229c872c4843df916cf538b7f2e88e451dc6b9d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a><span data-ttu-id="9fa30-102">Vergleichen von Transaktionen in COM+ und ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9fa30-102">Comparing Transactions in COM+ and ServiceModel</span></span>
<span data-ttu-id="9fa30-103">In diesem Thema wird das Simulieren des Verhaltens eines COM+-Transaktionsdienstes mithilfe der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Attribute, die der <xref:System.ServiceModel>-Namespace bereitstellt, beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9fa30-103">This topic discusses how to simulate the behavior of a transactional COM+ service using the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] attributes the <xref:System.ServiceModel> namespace provides.</span></span>  
  
## <a name="emulating-com-using-servicemodel-attributes"></a><span data-ttu-id="9fa30-104">Emulieren von COM+ mit ServiceModel-Attributen</span><span class="sxs-lookup"><span data-stu-id="9fa30-104">Emulating COM+ Using ServiceModel Attributes</span></span>  
 <span data-ttu-id="9fa30-105">In der folgenden Tabelle wird die <xref:System.EnterpriseServices.TransactionOption>-Enumeration, die zum Erstellen einer `EnterpriseServices`-Transaktion verwendet wird, und die Beziehung zu den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Attributen, die der <xref:System.ServiceModel>-Namespace bereitstellt, verglichen.</span><span class="sxs-lookup"><span data-stu-id="9fa30-105">The following table compares the <xref:System.EnterpriseServices.TransactionOption> enumeration used to create an `EnterpriseServices` transaction and how they correlate to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attributes the <xref:System.ServiceModel> namespace provides.</span></span>  
  
|<span data-ttu-id="9fa30-106">COM+-Attribut</span><span class="sxs-lookup"><span data-stu-id="9fa30-106">COM+ attribute</span></span>|[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9fa30-107">-Attribute</span><span class="sxs-lookup"><span data-stu-id="9fa30-107"> attributes</span></span>|  
|---------------------|------------------------------------------------------------------------|  
|<span data-ttu-id="9fa30-108">RequiresNew</span><span class="sxs-lookup"><span data-stu-id="9fa30-108">RequiresNew</span></span>|<span data-ttu-id="9fa30-109">Für <xref:System.ServiceModel.TransactionFlowAttribute> ist <xref:System.ServiceModel.TransactionFlowOption.NotAllowed> festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9fa30-109"><xref:System.ServiceModel.TransactionFlowAttribute> is set to <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.</span></span><br /><br /> <span data-ttu-id="9fa30-110"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> ist `true`.</span><span class="sxs-lookup"><span data-stu-id="9fa30-110"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> is `true`.</span></span><br /><br /> <span data-ttu-id="9fa30-111">Das `TransactionFlow`-Attribut im Bindungselement ist `false`.</span><span class="sxs-lookup"><span data-stu-id="9fa30-111">The `TransactionFlow` attribute in the binding element is `false`.</span></span>|  
|<span data-ttu-id="9fa30-112">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="9fa30-112">Required</span></span>|<span data-ttu-id="9fa30-113">Für <xref:System.ServiceModel.TransactionFlowAttribute> ist <xref:System.ServiceModel.TransactionFlowOption.Allowed> festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9fa30-113"><xref:System.ServiceModel.TransactionFlowAttribute> is set to <xref:System.ServiceModel.TransactionFlowOption.Allowed>.</span></span><br /><br /> <span data-ttu-id="9fa30-114"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> ist `true`.</span><span class="sxs-lookup"><span data-stu-id="9fa30-114"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> is `true`.</span></span><br /><br /> <span data-ttu-id="9fa30-115">Das `TransactionFlow`-Attribut im Bindungselement ist `true`.</span><span class="sxs-lookup"><span data-stu-id="9fa30-115">The `TransactionFlow` attribute in the binding element is `true`.</span></span>|  
|<span data-ttu-id="9fa30-116">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="9fa30-116">Supported</span></span>|<span data-ttu-id="9fa30-117">Es gibt keine direkte Entsprechung.</span><span class="sxs-lookup"><span data-stu-id="9fa30-117">There is no direct equivalent.</span></span> <span data-ttu-id="9fa30-118">Übernehmen Sie stattdessen im Allgemeinen das für `Required` angegebene Verhalten.</span><span class="sxs-lookup"><span data-stu-id="9fa30-118">In general, you should adopt the behavior specified for `Required` instead.</span></span>|  
|<span data-ttu-id="9fa30-119">NotSupported</span><span class="sxs-lookup"><span data-stu-id="9fa30-119">NotSupported</span></span>|<span data-ttu-id="9fa30-120"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> ist `false`.</span><span class="sxs-lookup"><span data-stu-id="9fa30-120"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> is `false`.</span></span><br /><br /> <span data-ttu-id="9fa30-121">Das `TransactionFlow`-Attribut im Bindungselement ist `false`.</span><span class="sxs-lookup"><span data-stu-id="9fa30-121">The `TransactionFlow` attribute in the binding element is `false`.</span></span>|  
|<span data-ttu-id="9fa30-122">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="9fa30-122">Disabled</span></span>|<span data-ttu-id="9fa30-123">Es gibt keine direkte Entsprechung.</span><span class="sxs-lookup"><span data-stu-id="9fa30-123">There is no direct equivalent.</span></span> <span data-ttu-id="9fa30-124">Übernehmen Sie stattdessen im Allgemeinen das für `NotSupported` angegebene Verhalten.</span><span class="sxs-lookup"><span data-stu-id="9fa30-124">In general, you should adopt the behavior specified for `NotSupported` instead.</span></span>|
