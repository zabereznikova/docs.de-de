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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bd784b470810e16b86ba7537b1f45681ac3e1ed1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="service"></a><span data-ttu-id="9d67d-102">Dienst</span><span class="sxs-lookup"><span data-stu-id="9d67d-102">Service</span></span>
<span data-ttu-id="9d67d-103">Dienst</span><span class="sxs-lookup"><span data-stu-id="9d67d-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d67d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d67d-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="9d67d-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="9d67d-105">Methods</span></span>  
 <span data-ttu-id="9d67d-106">Die Dienstklasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="9d67d-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9d67d-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9d67d-107">Properties</span></span>  
 <span data-ttu-id="9d67d-108">Die Dienstklasse hat die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="9d67d-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="9d67d-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="9d67d-109">BaseAddresses</span></span>  
 <span data-ttu-id="9d67d-110">Datentyp: Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="9d67d-110">Data type: string array</span></span>  
  
 <span data-ttu-id="9d67d-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d67d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d67d-112">Die vom Dienst verwendeten Basisadressen.</span><span class="sxs-lookup"><span data-stu-id="9d67d-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="9d67d-113">Verhalten</span><span class="sxs-lookup"><span data-stu-id="9d67d-113">Behaviors</span></span>  
 <span data-ttu-id="9d67d-114">Datentyp: Behavior-Array</span><span class="sxs-lookup"><span data-stu-id="9d67d-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="9d67d-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d67d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d67d-116">Die diesem Dienst zugewiesenen Verhalten.</span><span class="sxs-lookup"><span data-stu-id="9d67d-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="9d67d-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="9d67d-117">ConfigurationName</span></span>  
 <span data-ttu-id="9d67d-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="9d67d-118">Data type: string</span></span>  
  
 <span data-ttu-id="9d67d-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d67d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d67d-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="9d67d-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="9d67d-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="9d67d-121">CounterInstanceName</span></span>  
 <span data-ttu-id="9d67d-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="9d67d-122">Data type: string</span></span>  
  
 <span data-ttu-id="9d67d-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d67d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d67d-124">Name der Instanz der Leistungsindikatoren des Dienstes.</span><span class="sxs-lookup"><span data-stu-id="9d67d-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="9d67d-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="9d67d-125">DistinguishedName</span></span>  
 <span data-ttu-id="9d67d-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="9d67d-126">Data type: string</span></span>  
  
 <span data-ttu-id="9d67d-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d67d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d67d-128">Der Dienstname an der Adresse.</span><span class="sxs-lookup"><span data-stu-id="9d67d-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="9d67d-129">Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="9d67d-129">Extensions</span></span>  
 <span data-ttu-id="9d67d-130">Datentyp: Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="9d67d-130">Data type: string array</span></span>  
  
 <span data-ttu-id="9d67d-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d67d-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d67d-132">Die Instanzkontexte für die Erweiterungen der Dienstinstanz.</span><span class="sxs-lookup"><span data-stu-id="9d67d-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="9d67d-133">Metadaten</span><span class="sxs-lookup"><span data-stu-id="9d67d-133">Metadata</span></span>  
 <span data-ttu-id="9d67d-134">Datentyp: Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="9d67d-134">Data type: string array</span></span>  
  
 <span data-ttu-id="9d67d-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d67d-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d67d-136">Die Dienstmetadateneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="9d67d-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="9d67d-137">Name</span><span class="sxs-lookup"><span data-stu-id="9d67d-137">Name</span></span>  
 <span data-ttu-id="9d67d-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="9d67d-138">Data type: string</span></span>  
  
 <span data-ttu-id="9d67d-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d67d-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d67d-140">Der eindeutige Name des Diensts.</span><span class="sxs-lookup"><span data-stu-id="9d67d-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="9d67d-141">Namespace</span><span class="sxs-lookup"><span data-stu-id="9d67d-141">Namespace</span></span>  
 <span data-ttu-id="9d67d-142">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="9d67d-142">Data type: string</span></span>  
  
 <span data-ttu-id="9d67d-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d67d-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d67d-144">Der Namespace des Dienstes.</span><span class="sxs-lookup"><span data-stu-id="9d67d-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="9d67d-145">Opened</span><span class="sxs-lookup"><span data-stu-id="9d67d-145">Opened</span></span>  
 <span data-ttu-id="9d67d-146">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="9d67d-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="9d67d-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d67d-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d67d-148">Die Zeit, zu der der Dienst geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="9d67d-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="9d67d-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="9d67d-149">OutgoingChannels</span></span>  
 <span data-ttu-id="9d67d-150">Data type: Channel array (Kanal-Array)</span><span class="sxs-lookup"><span data-stu-id="9d67d-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="9d67d-151">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d67d-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d67d-152">Die Kanäle, die von der Dienstinstanz ausgehen.</span><span class="sxs-lookup"><span data-stu-id="9d67d-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="9d67d-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="9d67d-153">ProcessId</span></span>  
 <span data-ttu-id="9d67d-154">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="9d67d-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="9d67d-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d67d-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d67d-156">Die Prozess-ID des Vorgangs, von dem der Dienst gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="9d67d-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d67d-157">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9d67d-157">Requirements</span></span>  
  
|<span data-ttu-id="9d67d-158">MOF</span><span class="sxs-lookup"><span data-stu-id="9d67d-158">MOF</span></span>|<span data-ttu-id="9d67d-159">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9d67d-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9d67d-160">Namespace</span><span class="sxs-lookup"><span data-stu-id="9d67d-160">Namespace</span></span>|<span data-ttu-id="9d67d-161">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9d67d-161">Defined in root\ServiceModel</span></span>|
