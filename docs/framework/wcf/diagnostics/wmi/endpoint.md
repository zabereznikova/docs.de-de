---
title: Endpunkt
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: ceb4e4b41502b00d7bb21f1ecbd8249fccf1ce3b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288813"
---
# <a name="endpoint"></a><span data-ttu-id="19331-102">Endpunkt</span><span class="sxs-lookup"><span data-stu-id="19331-102">Endpoint</span></span>

<span data-ttu-id="19331-103">Endpunkt</span><span class="sxs-lookup"><span data-stu-id="19331-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19331-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="19331-104">Syntax</span></span>  
  
```csharp
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="19331-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="19331-105">Methods</span></span>  

 <span data-ttu-id="19331-106">Von der Endpoint-Klasse wird die folgende Methode definiert:</span><span class="sxs-lookup"><span data-stu-id="19331-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="19331-107">Methode</span><span class="sxs-lookup"><span data-stu-id="19331-107">Method</span></span>|<span data-ttu-id="19331-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="19331-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="19331-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="19331-109">GetOperationCounterInstanceName</span></span>](getoperationcounterinstancename.md)|<span data-ttu-id="19331-110">Ruft den Instanznamen des Vorgangsleistungsindikators ab.</span><span class="sxs-lookup"><span data-stu-id="19331-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="19331-111">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="19331-111">Properties</span></span>  

 <span data-ttu-id="19331-112">Die Endpoint-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="19331-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="19331-113">Adresse</span><span class="sxs-lookup"><span data-stu-id="19331-113">Address</span></span>  

 <span data-ttu-id="19331-114">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="19331-114">Data type: string</span></span>  
  
 <span data-ttu-id="19331-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19331-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19331-116">Ein URI, der die Adresse des Endpunkts enthält.</span><span class="sxs-lookup"><span data-stu-id="19331-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="19331-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="19331-117">AddressHeaders</span></span>  

 <span data-ttu-id="19331-118">Datentyp: Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="19331-118">Data type: string array</span></span>  
  
 <span data-ttu-id="19331-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19331-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19331-120">Die Auflistung von Adressheadern, die diesem Endpunkt angefügt sind.</span><span class="sxs-lookup"><span data-stu-id="19331-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="19331-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="19331-121">AddressIdentity</span></span>  

 <span data-ttu-id="19331-122">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="19331-122">Data type: string</span></span>  
  
 <span data-ttu-id="19331-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19331-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19331-124">Die Identität des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="19331-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="19331-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="19331-125">AppDomainId</span></span>  

 <span data-ttu-id="19331-126">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="19331-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="19331-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19331-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19331-128">Die Anwendungsdomänen-ID der Anwendungsdomäne, von der der Endpunkt gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="19331-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="19331-129">Verhalten</span><span class="sxs-lookup"><span data-stu-id="19331-129">Behaviors</span></span>  

 <span data-ttu-id="19331-130">Datentyp: Behavior-Array</span><span class="sxs-lookup"><span data-stu-id="19331-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="19331-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19331-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19331-132">Die Auflistung der von diesem Endpunkt implementierten Verhaltensweisen.</span><span class="sxs-lookup"><span data-stu-id="19331-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="19331-133">Bindung</span><span class="sxs-lookup"><span data-stu-id="19331-133">Binding</span></span>  

 <span data-ttu-id="19331-134">Datentyp: Bindung</span><span class="sxs-lookup"><span data-stu-id="19331-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="19331-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19331-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19331-136">Die von diesem Endpunkt verwendete Bindung.</span><span class="sxs-lookup"><span data-stu-id="19331-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="19331-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="19331-137">ContractName</span></span>  

 <span data-ttu-id="19331-138">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="19331-138">Data type: string</span></span>  
  
 <span data-ttu-id="19331-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19331-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19331-140">Eine Zeichenfolge, die angibt, welche Verträge von diesem Endpunkt verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="19331-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="19331-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="19331-141">CounterInstanceName</span></span>  

 <span data-ttu-id="19331-142">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="19331-142">Data type: string</span></span>  
  
 <span data-ttu-id="19331-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19331-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19331-144">Der Instanzname der Leistungsindikatoren des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="19331-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="19331-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="19331-145">ListenUri</span></span>  

 <span data-ttu-id="19331-146">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="19331-146">Data type: string</span></span>  
  
 <span data-ttu-id="19331-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19331-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19331-148">Der URI, der vom Endpunkt zum Abhören verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="19331-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="19331-149">Name</span><span class="sxs-lookup"><span data-stu-id="19331-149">Name</span></span>  

 <span data-ttu-id="19331-150">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="19331-150">Data type: string</span></span>  
  
 <span data-ttu-id="19331-151">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19331-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19331-152">Der eindeutige Name des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="19331-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="19331-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="19331-153">ProcessId</span></span>  

 <span data-ttu-id="19331-154">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="19331-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="19331-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19331-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19331-156">Die Prozess-ID des Prozesses, von dem der Endpunkt gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="19331-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="19331-157">ref</span><span class="sxs-lookup"><span data-stu-id="19331-157">ref</span></span>  

 <span data-ttu-id="19331-158">Datentyp: Contract</span><span class="sxs-lookup"><span data-stu-id="19331-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="19331-159">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19331-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19331-160">Der Vertrag, der von diesem Endpunkt verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="19331-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19331-161">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="19331-161">Requirements</span></span>  
  
|<span data-ttu-id="19331-162">MOF</span><span class="sxs-lookup"><span data-stu-id="19331-162">MOF</span></span>|<span data-ttu-id="19331-163">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="19331-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="19331-164">Namespace</span><span class="sxs-lookup"><span data-stu-id="19331-164">Namespace</span></span>|<span data-ttu-id="19331-165">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="19331-165">Defined in root\ServiceModel</span></span>|
