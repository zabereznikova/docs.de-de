---
title: Dienst
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f7b631ede7bd011a92003dc5f6083c1c427d990e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="service"></a><span data-ttu-id="0430f-102">Dienst</span><span class="sxs-lookup"><span data-stu-id="0430f-102">Service</span></span>
<span data-ttu-id="0430f-103">Dienst</span><span class="sxs-lookup"><span data-stu-id="0430f-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0430f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0430f-104">Syntax</span></span>  
  
```  
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="0430f-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="0430f-105">Methods</span></span>  
 <span data-ttu-id="0430f-106">Die Dienstklasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="0430f-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0430f-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0430f-107">Properties</span></span>  
 <span data-ttu-id="0430f-108">Die Dienstklasse hat die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="0430f-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="0430f-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="0430f-109">BaseAddresses</span></span>  
 <span data-ttu-id="0430f-110">Datentyp: Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="0430f-110">Data type: string array</span></span>  
  
 <span data-ttu-id="0430f-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0430f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0430f-112">Die vom Dienst verwendeten Basisadressen.</span><span class="sxs-lookup"><span data-stu-id="0430f-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="0430f-113">Verhalten</span><span class="sxs-lookup"><span data-stu-id="0430f-113">Behaviors</span></span>  
 <span data-ttu-id="0430f-114">Datentyp: Behavior-Array</span><span class="sxs-lookup"><span data-stu-id="0430f-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="0430f-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0430f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0430f-116">Die diesem Dienst zugewiesenen Verhalten.</span><span class="sxs-lookup"><span data-stu-id="0430f-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="0430f-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="0430f-117">ConfigurationName</span></span>  
 <span data-ttu-id="0430f-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0430f-118">Data type: string</span></span>  
  
 <span data-ttu-id="0430f-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0430f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0430f-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="0430f-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="0430f-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="0430f-121">CounterInstanceName</span></span>  
 <span data-ttu-id="0430f-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0430f-122">Data type: string</span></span>  
  
 <span data-ttu-id="0430f-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0430f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0430f-124">Name der Instanz der Leistungsindikatoren des Dienstes.</span><span class="sxs-lookup"><span data-stu-id="0430f-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="0430f-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="0430f-125">DistinguishedName</span></span>  
 <span data-ttu-id="0430f-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0430f-126">Data type: string</span></span>  
  
 <span data-ttu-id="0430f-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0430f-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0430f-128">Der Dienstname an der Adresse.</span><span class="sxs-lookup"><span data-stu-id="0430f-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="0430f-129">Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="0430f-129">Extensions</span></span>  
 <span data-ttu-id="0430f-130">Datentyp: Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="0430f-130">Data type: string array</span></span>  
  
 <span data-ttu-id="0430f-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0430f-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0430f-132">Die Instanzkontexte für die Erweiterungen der Dienstinstanz.</span><span class="sxs-lookup"><span data-stu-id="0430f-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="0430f-133">Metadaten</span><span class="sxs-lookup"><span data-stu-id="0430f-133">Metadata</span></span>  
 <span data-ttu-id="0430f-134">Datentyp: Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="0430f-134">Data type: string array</span></span>  
  
 <span data-ttu-id="0430f-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0430f-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0430f-136">Die Dienstmetadateneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="0430f-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="0430f-137">name</span><span class="sxs-lookup"><span data-stu-id="0430f-137">Name</span></span>  
 <span data-ttu-id="0430f-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0430f-138">Data type: string</span></span>  
  
 <span data-ttu-id="0430f-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0430f-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0430f-140">Der eindeutige Name des Diensts.</span><span class="sxs-lookup"><span data-stu-id="0430f-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="0430f-141">Namespace</span><span class="sxs-lookup"><span data-stu-id="0430f-141">Namespace</span></span>  
 <span data-ttu-id="0430f-142">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0430f-142">Data type: string</span></span>  
  
 <span data-ttu-id="0430f-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0430f-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0430f-144">Der Namespace des Dienstes.</span><span class="sxs-lookup"><span data-stu-id="0430f-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="0430f-145">Opened</span><span class="sxs-lookup"><span data-stu-id="0430f-145">Opened</span></span>  
 <span data-ttu-id="0430f-146">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="0430f-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="0430f-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0430f-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0430f-148">Die Zeit, zu der der Dienst geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="0430f-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="0430f-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="0430f-149">OutgoingChannels</span></span>  
 <span data-ttu-id="0430f-150">Data type: Channel array (Kanal-Array)</span><span class="sxs-lookup"><span data-stu-id="0430f-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="0430f-151">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0430f-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0430f-152">Die Kanäle, die von der Dienstinstanz ausgehen.</span><span class="sxs-lookup"><span data-stu-id="0430f-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="0430f-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="0430f-153">ProcessId</span></span>  
 <span data-ttu-id="0430f-154">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="0430f-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="0430f-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0430f-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0430f-156">Die Prozess-ID des Vorgangs, von dem der Dienst gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="0430f-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0430f-157">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0430f-157">Requirements</span></span>  
  
|<span data-ttu-id="0430f-158">MOF</span><span class="sxs-lookup"><span data-stu-id="0430f-158">MOF</span></span>|<span data-ttu-id="0430f-159">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="0430f-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0430f-160">Namespace</span><span class="sxs-lookup"><span data-stu-id="0430f-160">Namespace</span></span>|<span data-ttu-id="0430f-161">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0430f-161">Defined in root\ServiceModel</span></span>|
