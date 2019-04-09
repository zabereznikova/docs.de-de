---
title: Contract1
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 10789f9a2940c239ae20c8fd1e9d48bca0e820ed
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201090"
---
# <a name="contract"></a><span data-ttu-id="05de5-102">Vertrag</span><span class="sxs-lookup"><span data-stu-id="05de5-102">Contract</span></span>
<span data-ttu-id="05de5-103">Vertrag</span><span class="sxs-lookup"><span data-stu-id="05de5-103">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05de5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="05de5-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="05de5-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="05de5-105">Methods</span></span>  
 <span data-ttu-id="05de5-106">Die Contract-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="05de5-106">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="05de5-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="05de5-107">Properties</span></span>  
 <span data-ttu-id="05de5-108">Die Contract-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="05de5-108">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="05de5-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="05de5-109">AppDomainId</span></span>  
 <span data-ttu-id="05de5-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="05de5-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="05de5-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="05de5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="05de5-112">Die Anwendungsdomänen-ID der Anwendungsdomäne, die den Vertrag hostet.</span><span class="sxs-lookup"><span data-stu-id="05de5-112">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="05de5-113">Verhalten</span><span class="sxs-lookup"><span data-stu-id="05de5-113">Behaviors</span></span>  
 <span data-ttu-id="05de5-114">Datentyp: Behavior-array</span><span class="sxs-lookup"><span data-stu-id="05de5-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="05de5-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="05de5-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="05de5-116">Die mit diesem Vertrag verknüpften Verhalten.</span><span class="sxs-lookup"><span data-stu-id="05de5-116">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="05de5-117">Name</span><span class="sxs-lookup"><span data-stu-id="05de5-117">Name</span></span>  
 <span data-ttu-id="05de5-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="05de5-118">Data type: string</span></span>  
  
 <span data-ttu-id="05de5-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="05de5-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="05de5-120">Der Name des Vertrags in WSDL.</span><span class="sxs-lookup"><span data-stu-id="05de5-120">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="05de5-121">Namespace</span><span class="sxs-lookup"><span data-stu-id="05de5-121">Namespace</span></span>  
 <span data-ttu-id="05de5-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="05de5-122">Data type: string</span></span>  
  
 <span data-ttu-id="05de5-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="05de5-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="05de5-124">Der Namespace des `portType`-Elements in WSDL.</span><span class="sxs-lookup"><span data-stu-id="05de5-124">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="05de5-125">Vorgänge</span><span class="sxs-lookup"><span data-stu-id="05de5-125">Operations</span></span>  
 <span data-ttu-id="05de5-126">Datentyp: Operation-array</span><span class="sxs-lookup"><span data-stu-id="05de5-126">Data type: Operation array</span></span>  
  
 <span data-ttu-id="05de5-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="05de5-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="05de5-128">Der Vorgang dieses Vertrags.</span><span class="sxs-lookup"><span data-stu-id="05de5-128">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="05de5-129">ProcessId</span><span class="sxs-lookup"><span data-stu-id="05de5-129">ProcessId</span></span>  
 <span data-ttu-id="05de5-130">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="05de5-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="05de5-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="05de5-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="05de5-132">Die Porzess-ID des Prozesses, der den Vertrag hostet.</span><span class="sxs-lookup"><span data-stu-id="05de5-132">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="05de5-133">ref</span><span class="sxs-lookup"><span data-stu-id="05de5-133">ref</span></span>  
 <span data-ttu-id="05de5-134">Datentyp: Vertrag</span><span class="sxs-lookup"><span data-stu-id="05de5-134">Data type: Contract</span></span>  
  
 <span data-ttu-id="05de5-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="05de5-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="05de5-136">Der Typ des Rückrufs, wenn es sich beim Vertrag um einen Duplexvertrag handelt.</span><span class="sxs-lookup"><span data-stu-id="05de5-136">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="05de5-137">SessionMode</span><span class="sxs-lookup"><span data-stu-id="05de5-137">SessionMode</span></span>  
 <span data-ttu-id="05de5-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="05de5-138">Data type: string</span></span>  
  
 <span data-ttu-id="05de5-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="05de5-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="05de5-140">Gibt an, ob der Vertrag die ihm zugeordnete Bindung für die Verwendung der Kanalsitzung benötigt.</span><span class="sxs-lookup"><span data-stu-id="05de5-140">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="05de5-141">Typ</span><span class="sxs-lookup"><span data-stu-id="05de5-141">Type</span></span>  
 <span data-ttu-id="05de5-142">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="05de5-142">Data type: string</span></span>  
  
 <span data-ttu-id="05de5-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="05de5-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="05de5-144">Der Typ des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="05de5-144">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05de5-145">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="05de5-145">Requirements</span></span>  
  
|<span data-ttu-id="05de5-146">MOF</span><span class="sxs-lookup"><span data-stu-id="05de5-146">MOF</span></span>|<span data-ttu-id="05de5-147">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="05de5-147">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="05de5-148">Namespace</span><span class="sxs-lookup"><span data-stu-id="05de5-148">Namespace</span></span>|<span data-ttu-id="05de5-149">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="05de5-149">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05de5-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05de5-150">See also</span></span>

- <xref:System.ServiceModel.Description.ContractDescription>
