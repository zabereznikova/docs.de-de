---
title: Endpunkt
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 03c401358839671d750985b95b1aada599931aad
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795908"
---
# <a name="endpoint"></a><span data-ttu-id="cb0f2-102">Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cb0f2-102">Endpoint</span></span>
<span data-ttu-id="cb0f2-103">Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cb0f2-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb0f2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb0f2-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="cb0f2-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="cb0f2-105">Methods</span></span>  
 <span data-ttu-id="cb0f2-106">Von der Endpoint-Klasse wird die folgende Methode definiert:</span><span class="sxs-lookup"><span data-stu-id="cb0f2-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="cb0f2-107">Methode</span><span class="sxs-lookup"><span data-stu-id="cb0f2-107">Method</span></span>|<span data-ttu-id="cb0f2-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb0f2-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cb0f2-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="cb0f2-109">GetOperationCounterInstanceName</span></span>](getoperationcounterinstancename.md)|<span data-ttu-id="cb0f2-110">Ruft den Instanznamen des Vorgangsleistungsindikators ab.</span><span class="sxs-lookup"><span data-stu-id="cb0f2-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="cb0f2-111">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cb0f2-111">Properties</span></span>  
 <span data-ttu-id="cb0f2-112">Die Endpoint-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="cb0f2-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="cb0f2-113">Adresse</span><span class="sxs-lookup"><span data-stu-id="cb0f2-113">Address</span></span>  
 <span data-ttu-id="cb0f2-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="cb0f2-114">Data type: string</span></span>  
  
 <span data-ttu-id="cb0f2-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="cb0f2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cb0f2-116">Ein URI, der die Adresse des Endpunkts enthält.</span><span class="sxs-lookup"><span data-stu-id="cb0f2-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="cb0f2-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="cb0f2-117">AddressHeaders</span></span>  
 <span data-ttu-id="cb0f2-118">Datentyp: Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="cb0f2-118">Data type: string array</span></span>  
  
 <span data-ttu-id="cb0f2-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="cb0f2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cb0f2-120">Die Auflistung von Adressheadern, die diesem Endpunkt angefügt sind.</span><span class="sxs-lookup"><span data-stu-id="cb0f2-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="cb0f2-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="cb0f2-121">AddressIdentity</span></span>  
 <span data-ttu-id="cb0f2-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="cb0f2-122">Data type: string</span></span>  
  
 <span data-ttu-id="cb0f2-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="cb0f2-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cb0f2-124">Die Identität des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="cb0f2-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="cb0f2-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="cb0f2-125">AppDomainId</span></span>  
 <span data-ttu-id="cb0f2-126">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="cb0f2-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="cb0f2-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="cb0f2-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cb0f2-128">Die Anwendungsdomänen-ID der Anwendungsdomäne, von der der Endpunkt gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="cb0f2-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="cb0f2-129">Verhalten</span><span class="sxs-lookup"><span data-stu-id="cb0f2-129">Behaviors</span></span>  
 <span data-ttu-id="cb0f2-130">Datentyp: Behavior-Array</span><span class="sxs-lookup"><span data-stu-id="cb0f2-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="cb0f2-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="cb0f2-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cb0f2-132">Die Auflistung der von diesem Endpunkt implementierten Verhaltensweisen.</span><span class="sxs-lookup"><span data-stu-id="cb0f2-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="cb0f2-133">Bindung</span><span class="sxs-lookup"><span data-stu-id="cb0f2-133">Binding</span></span>  
 <span data-ttu-id="cb0f2-134">Datentyp: Bindung</span><span class="sxs-lookup"><span data-stu-id="cb0f2-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="cb0f2-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="cb0f2-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cb0f2-136">Die von diesem Endpunkt verwendete Bindung.</span><span class="sxs-lookup"><span data-stu-id="cb0f2-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="cb0f2-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="cb0f2-137">ContractName</span></span>  
 <span data-ttu-id="cb0f2-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="cb0f2-138">Data type: string</span></span>  
  
 <span data-ttu-id="cb0f2-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="cb0f2-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cb0f2-140">Eine Zeichenfolge, die angibt, welche Verträge von diesem Endpunkt verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="cb0f2-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="cb0f2-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="cb0f2-141">CounterInstanceName</span></span>  
 <span data-ttu-id="cb0f2-142">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="cb0f2-142">Data type: string</span></span>  
  
 <span data-ttu-id="cb0f2-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="cb0f2-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cb0f2-144">Der Instanzname der Leistungsindikatoren des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="cb0f2-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="cb0f2-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="cb0f2-145">ListenUri</span></span>  
 <span data-ttu-id="cb0f2-146">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="cb0f2-146">Data type: string</span></span>  
  
 <span data-ttu-id="cb0f2-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="cb0f2-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cb0f2-148">Der URI, der vom Endpunkt zum Abhören verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cb0f2-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="cb0f2-149">Name</span><span class="sxs-lookup"><span data-stu-id="cb0f2-149">Name</span></span>  
 <span data-ttu-id="cb0f2-150">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="cb0f2-150">Data type: string</span></span>  
  
 <span data-ttu-id="cb0f2-151">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="cb0f2-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cb0f2-152">Der eindeutige Name des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="cb0f2-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="cb0f2-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="cb0f2-153">ProcessId</span></span>  
 <span data-ttu-id="cb0f2-154">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="cb0f2-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="cb0f2-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="cb0f2-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cb0f2-156">Die Prozess-ID des Prozesses, von dem der Endpunkt gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="cb0f2-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="cb0f2-157">ref</span><span class="sxs-lookup"><span data-stu-id="cb0f2-157">ref</span></span>  
 <span data-ttu-id="cb0f2-158">Datentyp: Vertrag</span><span class="sxs-lookup"><span data-stu-id="cb0f2-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="cb0f2-159">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="cb0f2-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cb0f2-160">Der Vertrag, der von diesem Endpunkt verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="cb0f2-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb0f2-161">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cb0f2-161">Requirements</span></span>  
  
|<span data-ttu-id="cb0f2-162">MOF</span><span class="sxs-lookup"><span data-stu-id="cb0f2-162">MOF</span></span>|<span data-ttu-id="cb0f2-163">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="cb0f2-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="cb0f2-164">Namespace</span><span class="sxs-lookup"><span data-stu-id="cb0f2-164">Namespace</span></span>|<span data-ttu-id="cb0f2-165">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cb0f2-165">Defined in root\ServiceModel</span></span>|
