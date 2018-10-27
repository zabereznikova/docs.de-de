---
title: Endpunkt
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 4562481e8b0b18c0ea0d9df0af3427ffe6419821
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452926"
---
# <a name="endpoint"></a><span data-ttu-id="1ea52-102">Endpunkt</span><span class="sxs-lookup"><span data-stu-id="1ea52-102">Endpoint</span></span>
<span data-ttu-id="1ea52-103">Endpunkt</span><span class="sxs-lookup"><span data-stu-id="1ea52-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ea52-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ea52-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="1ea52-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="1ea52-105">Methods</span></span>  
 <span data-ttu-id="1ea52-106">Von der Endpoint-Klasse wird die folgende Methode definiert:</span><span class="sxs-lookup"><span data-stu-id="1ea52-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="1ea52-107">Methode</span><span class="sxs-lookup"><span data-stu-id="1ea52-107">Method</span></span>|<span data-ttu-id="1ea52-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ea52-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1ea52-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="1ea52-109">GetOperationCounterInstanceName</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|<span data-ttu-id="1ea52-110">Ruft den Instanznamen des Vorgangsleistungsindikators ab.</span><span class="sxs-lookup"><span data-stu-id="1ea52-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="1ea52-111">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1ea52-111">Properties</span></span>  
 <span data-ttu-id="1ea52-112">Die Endpoint-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="1ea52-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="1ea52-113">Adresse</span><span class="sxs-lookup"><span data-stu-id="1ea52-113">Address</span></span>  
 <span data-ttu-id="1ea52-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="1ea52-114">Data type: string</span></span>  
  
 <span data-ttu-id="1ea52-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1ea52-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1ea52-116">Ein URI, der die Adresse des Endpunkts enthält.</span><span class="sxs-lookup"><span data-stu-id="1ea52-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="1ea52-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="1ea52-117">AddressHeaders</span></span>  
 <span data-ttu-id="1ea52-118">Datentyp: Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="1ea52-118">Data type: string array</span></span>  
  
 <span data-ttu-id="1ea52-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1ea52-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1ea52-120">Die Auflistung von Adressheadern, die diesem Endpunkt angefügt sind.</span><span class="sxs-lookup"><span data-stu-id="1ea52-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="1ea52-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="1ea52-121">AddressIdentity</span></span>  
 <span data-ttu-id="1ea52-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="1ea52-122">Data type: string</span></span>  
  
 <span data-ttu-id="1ea52-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1ea52-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1ea52-124">Die Identität des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="1ea52-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="1ea52-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="1ea52-125">AppDomainId</span></span>  
 <span data-ttu-id="1ea52-126">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="1ea52-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="1ea52-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1ea52-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1ea52-128">Die Anwendungsdomänen-ID der Anwendungsdomäne, von der der Endpunkt gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="1ea52-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="1ea52-129">Verhalten</span><span class="sxs-lookup"><span data-stu-id="1ea52-129">Behaviors</span></span>  
 <span data-ttu-id="1ea52-130">Datentyp: Behavior-Array</span><span class="sxs-lookup"><span data-stu-id="1ea52-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="1ea52-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1ea52-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1ea52-132">Die Auflistung der von diesem Endpunkt implementierten Verhaltensweisen.</span><span class="sxs-lookup"><span data-stu-id="1ea52-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="1ea52-133">Bindung</span><span class="sxs-lookup"><span data-stu-id="1ea52-133">Binding</span></span>  
 <span data-ttu-id="1ea52-134">Datentyp: Bindung</span><span class="sxs-lookup"><span data-stu-id="1ea52-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="1ea52-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1ea52-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1ea52-136">Die von diesem Endpunkt verwendete Bindung.</span><span class="sxs-lookup"><span data-stu-id="1ea52-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="1ea52-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="1ea52-137">ContractName</span></span>  
 <span data-ttu-id="1ea52-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="1ea52-138">Data type: string</span></span>  
  
 <span data-ttu-id="1ea52-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1ea52-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1ea52-140">Eine Zeichenfolge, die angibt, welche Verträge von diesem Endpunkt verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="1ea52-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="1ea52-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="1ea52-141">CounterInstanceName</span></span>  
 <span data-ttu-id="1ea52-142">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="1ea52-142">Data type: string</span></span>  
  
 <span data-ttu-id="1ea52-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1ea52-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1ea52-144">Der Instanzname der Leistungsindikatoren des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="1ea52-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="1ea52-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="1ea52-145">ListenUri</span></span>  
 <span data-ttu-id="1ea52-146">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="1ea52-146">Data type: string</span></span>  
  
 <span data-ttu-id="1ea52-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1ea52-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1ea52-148">Der URI, der vom Endpunkt zum Abhören verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1ea52-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="1ea52-149">Name</span><span class="sxs-lookup"><span data-stu-id="1ea52-149">Name</span></span>  
 <span data-ttu-id="1ea52-150">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="1ea52-150">Data type: string</span></span>  
  
 <span data-ttu-id="1ea52-151">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1ea52-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1ea52-152">Der eindeutige Name des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="1ea52-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="1ea52-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="1ea52-153">ProcessId</span></span>  
 <span data-ttu-id="1ea52-154">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="1ea52-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="1ea52-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1ea52-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1ea52-156">Die Prozess-ID des Prozesses, von dem der Endpunkt gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="1ea52-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="1ea52-157">ref</span><span class="sxs-lookup"><span data-stu-id="1ea52-157">ref</span></span>  
 <span data-ttu-id="1ea52-158">Datentyp: Contract</span><span class="sxs-lookup"><span data-stu-id="1ea52-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="1ea52-159">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1ea52-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1ea52-160">Der Vertrag, der von diesem Endpunkt verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="1ea52-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ea52-161">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1ea52-161">Requirements</span></span>  
  
|<span data-ttu-id="1ea52-162">MOF</span><span class="sxs-lookup"><span data-stu-id="1ea52-162">MOF</span></span>|<span data-ttu-id="1ea52-163">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1ea52-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1ea52-164">Namespace</span><span class="sxs-lookup"><span data-stu-id="1ea52-164">Namespace</span></span>|<span data-ttu-id="1ea52-165">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1ea52-165">Defined in root\ServiceModel</span></span>|
