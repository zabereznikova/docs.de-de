---
title: Endpunkt
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3bcb02ae01d66830d9bfd486c5ae3941c45c2a19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="endpoint"></a><span data-ttu-id="317c7-102">Endpunkt</span><span class="sxs-lookup"><span data-stu-id="317c7-102">Endpoint</span></span>
<span data-ttu-id="317c7-103">Endpunkt</span><span class="sxs-lookup"><span data-stu-id="317c7-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="317c7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="317c7-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="317c7-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="317c7-105">Methods</span></span>  
 <span data-ttu-id="317c7-106">Von der Endpoint-Klasse wird die folgende Methode definiert:</span><span class="sxs-lookup"><span data-stu-id="317c7-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="317c7-107">Methode</span><span class="sxs-lookup"><span data-stu-id="317c7-107">Method</span></span>|<span data-ttu-id="317c7-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="317c7-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="317c7-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="317c7-109">GetOperationCounterInstanceName</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|<span data-ttu-id="317c7-110">Ruft den Instanznamen des Vorgangsleistungsindikators ab.</span><span class="sxs-lookup"><span data-stu-id="317c7-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="317c7-111">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="317c7-111">Properties</span></span>  
 <span data-ttu-id="317c7-112">Die Endpoint-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="317c7-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="317c7-113">Adresse</span><span class="sxs-lookup"><span data-stu-id="317c7-113">Address</span></span>  
 <span data-ttu-id="317c7-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="317c7-114">Data type: string</span></span>  
  
 <span data-ttu-id="317c7-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="317c7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="317c7-116">Ein URI, der die Adresse des Endpunkts enthält.</span><span class="sxs-lookup"><span data-stu-id="317c7-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="317c7-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="317c7-117">AddressHeaders</span></span>  
 <span data-ttu-id="317c7-118">Datentyp: Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="317c7-118">Data type: string array</span></span>  
  
 <span data-ttu-id="317c7-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="317c7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="317c7-120">Die Auflistung von Adressheadern, die diesem Endpunkt angefügt sind.</span><span class="sxs-lookup"><span data-stu-id="317c7-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="317c7-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="317c7-121">AddressIdentity</span></span>  
 <span data-ttu-id="317c7-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="317c7-122">Data type: string</span></span>  
  
 <span data-ttu-id="317c7-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="317c7-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="317c7-124">Die Identität des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="317c7-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="317c7-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="317c7-125">AppDomainId</span></span>  
 <span data-ttu-id="317c7-126">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="317c7-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="317c7-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="317c7-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="317c7-128">Die Anwendungsdomänen-ID der Anwendungsdomäne, von der der Endpunkt gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="317c7-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="317c7-129">Verhalten</span><span class="sxs-lookup"><span data-stu-id="317c7-129">Behaviors</span></span>  
 <span data-ttu-id="317c7-130">Datentyp: Behavior-Array</span><span class="sxs-lookup"><span data-stu-id="317c7-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="317c7-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="317c7-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="317c7-132">Die Auflistung der von diesem Endpunkt implementierten Verhaltensweisen.</span><span class="sxs-lookup"><span data-stu-id="317c7-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="317c7-133">Bindung</span><span class="sxs-lookup"><span data-stu-id="317c7-133">Binding</span></span>  
 <span data-ttu-id="317c7-134">Datentyp: Bindung</span><span class="sxs-lookup"><span data-stu-id="317c7-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="317c7-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="317c7-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="317c7-136">Die von diesem Endpunkt verwendete Bindung.</span><span class="sxs-lookup"><span data-stu-id="317c7-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="317c7-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="317c7-137">ContractName</span></span>  
 <span data-ttu-id="317c7-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="317c7-138">Data type: string</span></span>  
  
 <span data-ttu-id="317c7-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="317c7-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="317c7-140">Eine Zeichenfolge, die angibt, welche Verträge von diesem Endpunkt verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="317c7-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="317c7-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="317c7-141">CounterInstanceName</span></span>  
 <span data-ttu-id="317c7-142">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="317c7-142">Data type: string</span></span>  
  
 <span data-ttu-id="317c7-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="317c7-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="317c7-144">Der Instanzname der Leistungsindikatoren des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="317c7-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="317c7-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="317c7-145">ListenUri</span></span>  
 <span data-ttu-id="317c7-146">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="317c7-146">Data type: string</span></span>  
  
 <span data-ttu-id="317c7-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="317c7-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="317c7-148">Der URI, der vom Endpunkt zum Abhören verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="317c7-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="317c7-149">Name</span><span class="sxs-lookup"><span data-stu-id="317c7-149">Name</span></span>  
 <span data-ttu-id="317c7-150">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="317c7-150">Data type: string</span></span>  
  
 <span data-ttu-id="317c7-151">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="317c7-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="317c7-152">Der eindeutige Name des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="317c7-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="317c7-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="317c7-153">ProcessId</span></span>  
 <span data-ttu-id="317c7-154">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="317c7-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="317c7-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="317c7-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="317c7-156">Die Prozess-ID des Prozesses, von dem der Endpunkt gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="317c7-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="317c7-157">ref</span><span class="sxs-lookup"><span data-stu-id="317c7-157">ref</span></span>  
 <span data-ttu-id="317c7-158">Datentyp: Contract</span><span class="sxs-lookup"><span data-stu-id="317c7-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="317c7-159">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="317c7-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="317c7-160">Der Vertrag, der von diesem Endpunkt verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="317c7-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="317c7-161">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="317c7-161">Requirements</span></span>  
  
|<span data-ttu-id="317c7-162">MOF</span><span class="sxs-lookup"><span data-stu-id="317c7-162">MOF</span></span>|<span data-ttu-id="317c7-163">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="317c7-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="317c7-164">Namespace</span><span class="sxs-lookup"><span data-stu-id="317c7-164">Namespace</span></span>|<span data-ttu-id="317c7-165">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="317c7-165">Defined in root\ServiceModel</span></span>|
