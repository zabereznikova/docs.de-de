---
title: Vertrag
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 0df39bbd0b273f1e898ccbe585be288cc245b7f5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274139"
---
# <a name="contract"></a><span data-ttu-id="e2efc-102">Vertrag</span><span class="sxs-lookup"><span data-stu-id="e2efc-102">Contract</span></span>

<span data-ttu-id="e2efc-103">Vertrag</span><span class="sxs-lookup"><span data-stu-id="e2efc-103">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2efc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2efc-104">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="e2efc-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e2efc-105">Methods</span></span>  

 <span data-ttu-id="e2efc-106">Die Contract-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="e2efc-106">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e2efc-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e2efc-107">Properties</span></span>  

 <span data-ttu-id="e2efc-108">Die Contract-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="e2efc-108">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="e2efc-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="e2efc-109">AppDomainId</span></span>  

 <span data-ttu-id="e2efc-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="e2efc-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="e2efc-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2efc-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2efc-112">Die Anwendungsdomänen-ID der Anwendungsdomäne, die den Vertrag hostet.</span><span class="sxs-lookup"><span data-stu-id="e2efc-112">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="e2efc-113">Verhalten</span><span class="sxs-lookup"><span data-stu-id="e2efc-113">Behaviors</span></span>  

 <span data-ttu-id="e2efc-114">Datentyp: Behavior-Array</span><span class="sxs-lookup"><span data-stu-id="e2efc-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="e2efc-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2efc-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2efc-116">Die mit diesem Vertrag verknüpften Verhalten.</span><span class="sxs-lookup"><span data-stu-id="e2efc-116">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="e2efc-117">Name</span><span class="sxs-lookup"><span data-stu-id="e2efc-117">Name</span></span>  

 <span data-ttu-id="e2efc-118">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="e2efc-118">Data type: string</span></span>  
  
 <span data-ttu-id="e2efc-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2efc-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2efc-120">Der Name des Vertrags in WSDL.</span><span class="sxs-lookup"><span data-stu-id="e2efc-120">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="e2efc-121">Namespace</span><span class="sxs-lookup"><span data-stu-id="e2efc-121">Namespace</span></span>  

 <span data-ttu-id="e2efc-122">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="e2efc-122">Data type: string</span></span>  
  
 <span data-ttu-id="e2efc-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2efc-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2efc-124">Der Namespace des `portType`-Elements in WSDL.</span><span class="sxs-lookup"><span data-stu-id="e2efc-124">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="e2efc-125">Operations</span><span class="sxs-lookup"><span data-stu-id="e2efc-125">Operations</span></span>  

 <span data-ttu-id="e2efc-126">Datentyp: Operation-Array</span><span class="sxs-lookup"><span data-stu-id="e2efc-126">Data type: Operation array</span></span>  
  
 <span data-ttu-id="e2efc-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2efc-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2efc-128">Der Vorgang dieses Vertrags.</span><span class="sxs-lookup"><span data-stu-id="e2efc-128">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="e2efc-129">ProcessId</span><span class="sxs-lookup"><span data-stu-id="e2efc-129">ProcessId</span></span>  

 <span data-ttu-id="e2efc-130">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="e2efc-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="e2efc-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2efc-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2efc-132">Die Porzess-ID des Prozesses, der den Vertrag hostet.</span><span class="sxs-lookup"><span data-stu-id="e2efc-132">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="e2efc-133">ref</span><span class="sxs-lookup"><span data-stu-id="e2efc-133">ref</span></span>  

 <span data-ttu-id="e2efc-134">Datentyp: Contract</span><span class="sxs-lookup"><span data-stu-id="e2efc-134">Data type: Contract</span></span>  
  
 <span data-ttu-id="e2efc-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2efc-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2efc-136">Der Typ des Rückrufs, wenn es sich beim Vertrag um einen Duplexvertrag handelt.</span><span class="sxs-lookup"><span data-stu-id="e2efc-136">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="e2efc-137">SessionMode</span><span class="sxs-lookup"><span data-stu-id="e2efc-137">SessionMode</span></span>  

 <span data-ttu-id="e2efc-138">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="e2efc-138">Data type: string</span></span>  
  
 <span data-ttu-id="e2efc-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2efc-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2efc-140">Gibt an, ob der Vertrag die ihm zugeordnete Bindung für die Verwendung der Kanalsitzung benötigt.</span><span class="sxs-lookup"><span data-stu-id="e2efc-140">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="e2efc-141">type</span><span class="sxs-lookup"><span data-stu-id="e2efc-141">Type</span></span>  

 <span data-ttu-id="e2efc-142">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="e2efc-142">Data type: string</span></span>  
  
 <span data-ttu-id="e2efc-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2efc-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2efc-144">Der Typ des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="e2efc-144">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2efc-145">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e2efc-145">Requirements</span></span>  
  
|<span data-ttu-id="e2efc-146">MOF</span><span class="sxs-lookup"><span data-stu-id="e2efc-146">MOF</span></span>|<span data-ttu-id="e2efc-147">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e2efc-147">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e2efc-148">Namespace</span><span class="sxs-lookup"><span data-stu-id="e2efc-148">Namespace</span></span>|<span data-ttu-id="e2efc-149">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e2efc-149">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2efc-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e2efc-150">See also</span></span>

- <xref:System.ServiceModel.Description.ContractDescription>
