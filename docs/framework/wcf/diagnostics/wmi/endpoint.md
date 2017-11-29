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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ef4e27f6e7a45fe705aa09827702a64c960b6a16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint"></a><span data-ttu-id="2bafa-102">Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2bafa-102">Endpoint</span></span>
<span data-ttu-id="2bafa-103">Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2bafa-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bafa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2bafa-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="2bafa-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="2bafa-105">Methods</span></span>  
 <span data-ttu-id="2bafa-106">Von der Endpoint-Klasse wird die folgende Methode definiert:</span><span class="sxs-lookup"><span data-stu-id="2bafa-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="2bafa-107">Methode</span><span class="sxs-lookup"><span data-stu-id="2bafa-107">Method</span></span>|<span data-ttu-id="2bafa-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2bafa-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2bafa-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="2bafa-109">GetOperationCounterInstanceName</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|<span data-ttu-id="2bafa-110">Ruft den Instanznamen des Vorgangsleistungsindikators ab.</span><span class="sxs-lookup"><span data-stu-id="2bafa-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="2bafa-111">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2bafa-111">Properties</span></span>  
 <span data-ttu-id="2bafa-112">Die Endpoint-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="2bafa-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="2bafa-113">Adresse</span><span class="sxs-lookup"><span data-stu-id="2bafa-113">Address</span></span>  
 <span data-ttu-id="2bafa-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="2bafa-114">Data type: string</span></span>  
  
 <span data-ttu-id="2bafa-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2bafa-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2bafa-116">Ein URI, der die Adresse des Endpunkts enthält.</span><span class="sxs-lookup"><span data-stu-id="2bafa-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="2bafa-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="2bafa-117">AddressHeaders</span></span>  
 <span data-ttu-id="2bafa-118">Datentyp: Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="2bafa-118">Data type: string array</span></span>  
  
 <span data-ttu-id="2bafa-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2bafa-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2bafa-120">Die Auflistung von Adressheadern, die diesem Endpunkt angefügt sind.</span><span class="sxs-lookup"><span data-stu-id="2bafa-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="2bafa-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="2bafa-121">AddressIdentity</span></span>  
 <span data-ttu-id="2bafa-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="2bafa-122">Data type: string</span></span>  
  
 <span data-ttu-id="2bafa-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2bafa-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2bafa-124">Die Identität des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="2bafa-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="2bafa-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="2bafa-125">AppDomainId</span></span>  
 <span data-ttu-id="2bafa-126">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="2bafa-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="2bafa-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2bafa-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2bafa-128">Die Anwendungsdomänen-ID der Anwendungsdomäne, von der der Endpunkt gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="2bafa-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="2bafa-129">Verhalten</span><span class="sxs-lookup"><span data-stu-id="2bafa-129">Behaviors</span></span>  
 <span data-ttu-id="2bafa-130">Datentyp: Behavior-Array</span><span class="sxs-lookup"><span data-stu-id="2bafa-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="2bafa-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2bafa-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2bafa-132">Die Auflistung der von diesem Endpunkt implementierten Verhaltensweisen.</span><span class="sxs-lookup"><span data-stu-id="2bafa-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="2bafa-133">Bindung</span><span class="sxs-lookup"><span data-stu-id="2bafa-133">Binding</span></span>  
 <span data-ttu-id="2bafa-134">Datentyp: Bindung</span><span class="sxs-lookup"><span data-stu-id="2bafa-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="2bafa-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2bafa-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2bafa-136">Die von diesem Endpunkt verwendete Bindung.</span><span class="sxs-lookup"><span data-stu-id="2bafa-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="2bafa-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="2bafa-137">ContractName</span></span>  
 <span data-ttu-id="2bafa-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="2bafa-138">Data type: string</span></span>  
  
 <span data-ttu-id="2bafa-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2bafa-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2bafa-140">Eine Zeichenfolge, die angibt, welche Verträge von diesem Endpunkt verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="2bafa-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="2bafa-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="2bafa-141">CounterInstanceName</span></span>  
 <span data-ttu-id="2bafa-142">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="2bafa-142">Data type: string</span></span>  
  
 <span data-ttu-id="2bafa-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2bafa-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2bafa-144">Der Instanzname der Leistungsindikatoren des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="2bafa-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="2bafa-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="2bafa-145">ListenUri</span></span>  
 <span data-ttu-id="2bafa-146">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="2bafa-146">Data type: string</span></span>  
  
 <span data-ttu-id="2bafa-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2bafa-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2bafa-148">Der URI, der vom Endpunkt zum Abhören verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2bafa-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="2bafa-149">Name</span><span class="sxs-lookup"><span data-stu-id="2bafa-149">Name</span></span>  
 <span data-ttu-id="2bafa-150">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="2bafa-150">Data type: string</span></span>  
  
 <span data-ttu-id="2bafa-151">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2bafa-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2bafa-152">Der eindeutige Name des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="2bafa-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="2bafa-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="2bafa-153">ProcessId</span></span>  
 <span data-ttu-id="2bafa-154">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="2bafa-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="2bafa-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2bafa-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2bafa-156">Die Prozess-ID des Prozesses, von dem der Endpunkt gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="2bafa-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="2bafa-157">ref</span><span class="sxs-lookup"><span data-stu-id="2bafa-157">ref</span></span>  
 <span data-ttu-id="2bafa-158">Datentyp: Contract</span><span class="sxs-lookup"><span data-stu-id="2bafa-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="2bafa-159">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2bafa-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2bafa-160">Der Vertrag, der von diesem Endpunkt verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="2bafa-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bafa-161">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2bafa-161">Requirements</span></span>  
  
|<span data-ttu-id="2bafa-162">MOF</span><span class="sxs-lookup"><span data-stu-id="2bafa-162">MOF</span></span>|<span data-ttu-id="2bafa-163">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="2bafa-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2bafa-164">Namespace</span><span class="sxs-lookup"><span data-stu-id="2bafa-164">Namespace</span></span>|<span data-ttu-id="2bafa-165">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2bafa-165">Defined in root\ServiceModel</span></span>|
