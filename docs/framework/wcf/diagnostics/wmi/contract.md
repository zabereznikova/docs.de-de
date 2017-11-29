---
title: Contract1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2e92c5d804fca3c04506e951a5c341c89eed1c54
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="contract"></a><span data-ttu-id="137f2-102">Vertrag</span><span class="sxs-lookup"><span data-stu-id="137f2-102">Contract</span></span>
<span data-ttu-id="137f2-103">Vertrag</span><span class="sxs-lookup"><span data-stu-id="137f2-103">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="137f2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="137f2-104">Syntax</span></span>  
  
```  
class Contract  
{  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  string Name;  
  string Namespace;  
  Operation Operations[];  
  sint32 ProcessId;  
  Contract ref;  
  string SessionMode;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="137f2-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="137f2-105">Methods</span></span>  
 <span data-ttu-id="137f2-106">Die Contract-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="137f2-106">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="137f2-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="137f2-107">Properties</span></span>  
 <span data-ttu-id="137f2-108">Die Contract-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="137f2-108">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="137f2-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="137f2-109">AppDomainId</span></span>  
 <span data-ttu-id="137f2-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="137f2-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="137f2-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="137f2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="137f2-112">Die Anwendungsdomänen-ID der Anwendungsdomäne, die den Vertrag hostet.</span><span class="sxs-lookup"><span data-stu-id="137f2-112">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="137f2-113">Verhalten</span><span class="sxs-lookup"><span data-stu-id="137f2-113">Behaviors</span></span>  
 <span data-ttu-id="137f2-114">Datentyp: Behavior-Array</span><span class="sxs-lookup"><span data-stu-id="137f2-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="137f2-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="137f2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="137f2-116">Die mit diesem Vertrag verknüpften Verhalten.</span><span class="sxs-lookup"><span data-stu-id="137f2-116">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="137f2-117">Name</span><span class="sxs-lookup"><span data-stu-id="137f2-117">Name</span></span>  
 <span data-ttu-id="137f2-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="137f2-118">Data type: string</span></span>  
  
 <span data-ttu-id="137f2-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="137f2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="137f2-120">Der Name des Vertrags in WSDL.</span><span class="sxs-lookup"><span data-stu-id="137f2-120">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="137f2-121">Namespace</span><span class="sxs-lookup"><span data-stu-id="137f2-121">Namespace</span></span>  
 <span data-ttu-id="137f2-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="137f2-122">Data type: string</span></span>  
  
 <span data-ttu-id="137f2-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="137f2-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="137f2-124">Der Namespace des `portType`-Elements in WSDL.</span><span class="sxs-lookup"><span data-stu-id="137f2-124">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="137f2-125">Vorgänge</span><span class="sxs-lookup"><span data-stu-id="137f2-125">Operations</span></span>  
 <span data-ttu-id="137f2-126">Datentyp: Operation-Array</span><span class="sxs-lookup"><span data-stu-id="137f2-126">Data type: Operation array</span></span>  
  
 <span data-ttu-id="137f2-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="137f2-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="137f2-128">Der Vorgang dieses Vertrags.</span><span class="sxs-lookup"><span data-stu-id="137f2-128">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="137f2-129">ProcessId</span><span class="sxs-lookup"><span data-stu-id="137f2-129">ProcessId</span></span>  
 <span data-ttu-id="137f2-130">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="137f2-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="137f2-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="137f2-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="137f2-132">Die Porzess-ID des Prozesses, der den Vertrag hostet.</span><span class="sxs-lookup"><span data-stu-id="137f2-132">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="137f2-133">ref</span><span class="sxs-lookup"><span data-stu-id="137f2-133">ref</span></span>  
 <span data-ttu-id="137f2-134">Datentyp: Contract</span><span class="sxs-lookup"><span data-stu-id="137f2-134">Data type: Contract</span></span>  
  
 <span data-ttu-id="137f2-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="137f2-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="137f2-136">Der Typ des Rückrufs, wenn es sich beim Vertrag um einen Duplexvertrag handelt.</span><span class="sxs-lookup"><span data-stu-id="137f2-136">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="137f2-137">SessionMode</span><span class="sxs-lookup"><span data-stu-id="137f2-137">SessionMode</span></span>  
 <span data-ttu-id="137f2-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="137f2-138">Data type: string</span></span>  
  
 <span data-ttu-id="137f2-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="137f2-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="137f2-140">Gibt an, ob der Vertrag die ihm zugeordnete Bindung für die Verwendung der Kanalsitzung benötigt.</span><span class="sxs-lookup"><span data-stu-id="137f2-140">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="137f2-141">Typ</span><span class="sxs-lookup"><span data-stu-id="137f2-141">Type</span></span>  
 <span data-ttu-id="137f2-142">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="137f2-142">Data type: string</span></span>  
  
 <span data-ttu-id="137f2-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="137f2-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="137f2-144">Der Typ des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="137f2-144">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="137f2-145">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="137f2-145">Requirements</span></span>  
  
|<span data-ttu-id="137f2-146">MOF</span><span class="sxs-lookup"><span data-stu-id="137f2-146">MOF</span></span>|<span data-ttu-id="137f2-147">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="137f2-147">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="137f2-148">Namespace</span><span class="sxs-lookup"><span data-stu-id="137f2-148">Namespace</span></span>|<span data-ttu-id="137f2-149">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="137f2-149">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="137f2-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="137f2-150">See Also</span></span>  
 <xref:System.ServiceModel.Description.ContractDescription>
