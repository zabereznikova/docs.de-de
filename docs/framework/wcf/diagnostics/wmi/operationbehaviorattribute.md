---
title: OperationBehaviorAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 63824ae2171053bee2af204e748a6fa811f2ba82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="f78ec-102">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="f78ec-102">OperationBehaviorAttribute</span></span>
<span data-ttu-id="f78ec-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="f78ec-103">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f78ec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f78ec-104">Syntax</span></span>  
  
```  
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f78ec-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f78ec-105">Methods</span></span>  
 <span data-ttu-id="f78ec-106">Die OperationBehaviorAttribute-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="f78ec-106">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f78ec-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f78ec-107">Properties</span></span>  
 <span data-ttu-id="f78ec-108">Die OperationBehaviorAttribute-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f78ec-108">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="f78ec-109">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="f78ec-109">AutoDisposeParameters</span></span>  
 <span data-ttu-id="f78ec-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="f78ec-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="f78ec-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f78ec-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f78ec-112">Der Zustand der Funktion für automatisches Verwerfen für Parameter.</span><span class="sxs-lookup"><span data-stu-id="f78ec-112">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="f78ec-113">Identitätswechsel</span><span class="sxs-lookup"><span data-stu-id="f78ec-113">Impersonation</span></span>  
 <span data-ttu-id="f78ec-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f78ec-114">Data type: string</span></span>  
  
 <span data-ttu-id="f78ec-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f78ec-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f78ec-116">Gibt die Ebene des Aufruferidentitätswechsels an, die von dem Vorgang unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="f78ec-116">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="f78ec-117">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="f78ec-117">ReleaseInstanceMode</span></span>  
 <span data-ttu-id="f78ec-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f78ec-118">Data type: string</span></span>  
  
 <span data-ttu-id="f78ec-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f78ec-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f78ec-120">Gibt an, wann das Objekt im Verlauf eines Vorgangsaufrufs wiederverwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f78ec-120">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="f78ec-121">TransactionAutoComplete</span><span class="sxs-lookup"><span data-stu-id="f78ec-121">TransactionAutoComplete</span></span>  
 <span data-ttu-id="f78ec-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="f78ec-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="f78ec-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f78ec-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f78ec-124">Gibt an, ob die aktuelle Transaktion automatisch übergeben werden soll, wenn keine unbehandelten Ausnahmen auftreten.</span><span class="sxs-lookup"><span data-stu-id="f78ec-124">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="f78ec-125">TransactionScopeRequired</span><span class="sxs-lookup"><span data-stu-id="f78ec-125">TransactionScopeRequired</span></span>  
 <span data-ttu-id="f78ec-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="f78ec-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="f78ec-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f78ec-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f78ec-128">Gibt an, ob der Vorgang eine Transaktion erfordert.</span><span class="sxs-lookup"><span data-stu-id="f78ec-128">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f78ec-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f78ec-129">Requirements</span></span>  
  
|<span data-ttu-id="f78ec-130">MOF</span><span class="sxs-lookup"><span data-stu-id="f78ec-130">MOF</span></span>|<span data-ttu-id="f78ec-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f78ec-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f78ec-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="f78ec-132">Namespace</span></span>|<span data-ttu-id="f78ec-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f78ec-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f78ec-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f78ec-134">See Also</span></span>  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
