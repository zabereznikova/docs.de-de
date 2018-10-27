---
title: Contract1
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 12e9cbf5232ebbad33ccc4fdca33233997d27357
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194669"
---
# <a name="contract"></a><span data-ttu-id="e2fbf-102">Vertrag</span><span class="sxs-lookup"><span data-stu-id="e2fbf-102">Contract</span></span>
<span data-ttu-id="e2fbf-103">Vertrag</span><span class="sxs-lookup"><span data-stu-id="e2fbf-103">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2fbf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2fbf-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="e2fbf-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e2fbf-105">Methods</span></span>  
 <span data-ttu-id="e2fbf-106">Die Contract-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="e2fbf-106">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e2fbf-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e2fbf-107">Properties</span></span>  
 <span data-ttu-id="e2fbf-108">Die Contract-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="e2fbf-108">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="e2fbf-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="e2fbf-109">AppDomainId</span></span>  
 <span data-ttu-id="e2fbf-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="e2fbf-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="e2fbf-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2fbf-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2fbf-112">Die Anwendungsdomänen-ID der Anwendungsdomäne, die den Vertrag hostet.</span><span class="sxs-lookup"><span data-stu-id="e2fbf-112">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="e2fbf-113">Verhalten</span><span class="sxs-lookup"><span data-stu-id="e2fbf-113">Behaviors</span></span>  
 <span data-ttu-id="e2fbf-114">Datentyp: Behavior-Array</span><span class="sxs-lookup"><span data-stu-id="e2fbf-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="e2fbf-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2fbf-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2fbf-116">Die mit diesem Vertrag verknüpften Verhalten.</span><span class="sxs-lookup"><span data-stu-id="e2fbf-116">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="e2fbf-117">name</span><span class="sxs-lookup"><span data-stu-id="e2fbf-117">Name</span></span>  
 <span data-ttu-id="e2fbf-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e2fbf-118">Data type: string</span></span>  
  
 <span data-ttu-id="e2fbf-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2fbf-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2fbf-120">Der Name des Vertrags in WSDL.</span><span class="sxs-lookup"><span data-stu-id="e2fbf-120">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="e2fbf-121">Namespace</span><span class="sxs-lookup"><span data-stu-id="e2fbf-121">Namespace</span></span>  
 <span data-ttu-id="e2fbf-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e2fbf-122">Data type: string</span></span>  
  
 <span data-ttu-id="e2fbf-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2fbf-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2fbf-124">Der Namespace des `portType`-Elements in WSDL.</span><span class="sxs-lookup"><span data-stu-id="e2fbf-124">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="e2fbf-125">Vorgänge</span><span class="sxs-lookup"><span data-stu-id="e2fbf-125">Operations</span></span>  
 <span data-ttu-id="e2fbf-126">Datentyp: Operation-Array</span><span class="sxs-lookup"><span data-stu-id="e2fbf-126">Data type: Operation array</span></span>  
  
 <span data-ttu-id="e2fbf-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2fbf-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2fbf-128">Der Vorgang dieses Vertrags.</span><span class="sxs-lookup"><span data-stu-id="e2fbf-128">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="e2fbf-129">ProcessId</span><span class="sxs-lookup"><span data-stu-id="e2fbf-129">ProcessId</span></span>  
 <span data-ttu-id="e2fbf-130">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="e2fbf-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="e2fbf-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2fbf-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2fbf-132">Die Porzess-ID des Prozesses, der den Vertrag hostet.</span><span class="sxs-lookup"><span data-stu-id="e2fbf-132">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="e2fbf-133">ref</span><span class="sxs-lookup"><span data-stu-id="e2fbf-133">ref</span></span>  
 <span data-ttu-id="e2fbf-134">Datentyp: Contract</span><span class="sxs-lookup"><span data-stu-id="e2fbf-134">Data type: Contract</span></span>  
  
 <span data-ttu-id="e2fbf-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2fbf-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2fbf-136">Der Typ des Rückrufs, wenn es sich beim Vertrag um einen Duplexvertrag handelt.</span><span class="sxs-lookup"><span data-stu-id="e2fbf-136">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="e2fbf-137">SessionMode</span><span class="sxs-lookup"><span data-stu-id="e2fbf-137">SessionMode</span></span>  
 <span data-ttu-id="e2fbf-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e2fbf-138">Data type: string</span></span>  
  
 <span data-ttu-id="e2fbf-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2fbf-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2fbf-140">Gibt an, ob der Vertrag die ihm zugeordnete Bindung für die Verwendung der Kanalsitzung benötigt.</span><span class="sxs-lookup"><span data-stu-id="e2fbf-140">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="e2fbf-141">Typ</span><span class="sxs-lookup"><span data-stu-id="e2fbf-141">Type</span></span>  
 <span data-ttu-id="e2fbf-142">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e2fbf-142">Data type: string</span></span>  
  
 <span data-ttu-id="e2fbf-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2fbf-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2fbf-144">Der Typ des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="e2fbf-144">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2fbf-145">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e2fbf-145">Requirements</span></span>  
  
|<span data-ttu-id="e2fbf-146">MOF</span><span class="sxs-lookup"><span data-stu-id="e2fbf-146">MOF</span></span>|<span data-ttu-id="e2fbf-147">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e2fbf-147">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e2fbf-148">Namespace</span><span class="sxs-lookup"><span data-stu-id="e2fbf-148">Namespace</span></span>|<span data-ttu-id="e2fbf-149">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e2fbf-149">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2fbf-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2fbf-150">See Also</span></span>  
 <xref:System.ServiceModel.Description.ContractDescription>
