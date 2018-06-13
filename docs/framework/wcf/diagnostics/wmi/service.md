---
title: Dienst
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: 0cfeb178e26f6c93e29210accf5d7866cc1fca02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487146"
---
# <a name="service"></a><span data-ttu-id="dbdb8-102">Dienst</span><span class="sxs-lookup"><span data-stu-id="dbdb8-102">Service</span></span>
<span data-ttu-id="dbdb8-103">Dienst</span><span class="sxs-lookup"><span data-stu-id="dbdb8-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbdb8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dbdb8-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="dbdb8-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="dbdb8-105">Methods</span></span>  
 <span data-ttu-id="dbdb8-106">Die Dienstklasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="dbdb8-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="dbdb8-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="dbdb8-107">Properties</span></span>  
 <span data-ttu-id="dbdb8-108">Die Dienstklasse hat die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="dbdb8-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="dbdb8-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="dbdb8-109">BaseAddresses</span></span>  
 <span data-ttu-id="dbdb8-110">Datentyp: Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="dbdb8-110">Data type: string array</span></span>  
  
 <span data-ttu-id="dbdb8-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dbdb8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dbdb8-112">Die vom Dienst verwendeten Basisadressen.</span><span class="sxs-lookup"><span data-stu-id="dbdb8-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="dbdb8-113">Verhalten</span><span class="sxs-lookup"><span data-stu-id="dbdb8-113">Behaviors</span></span>  
 <span data-ttu-id="dbdb8-114">Datentyp: Behavior-Array</span><span class="sxs-lookup"><span data-stu-id="dbdb8-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="dbdb8-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dbdb8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dbdb8-116">Die diesem Dienst zugewiesenen Verhalten.</span><span class="sxs-lookup"><span data-stu-id="dbdb8-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="dbdb8-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="dbdb8-117">ConfigurationName</span></span>  
 <span data-ttu-id="dbdb8-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="dbdb8-118">Data type: string</span></span>  
  
 <span data-ttu-id="dbdb8-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dbdb8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dbdb8-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="dbdb8-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="dbdb8-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="dbdb8-121">CounterInstanceName</span></span>  
 <span data-ttu-id="dbdb8-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="dbdb8-122">Data type: string</span></span>  
  
 <span data-ttu-id="dbdb8-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dbdb8-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dbdb8-124">Name der Instanz der Leistungsindikatoren des Dienstes.</span><span class="sxs-lookup"><span data-stu-id="dbdb8-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="dbdb8-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="dbdb8-125">DistinguishedName</span></span>  
 <span data-ttu-id="dbdb8-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="dbdb8-126">Data type: string</span></span>  
  
 <span data-ttu-id="dbdb8-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dbdb8-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dbdb8-128">Der Dienstname an der Adresse.</span><span class="sxs-lookup"><span data-stu-id="dbdb8-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="dbdb8-129">Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="dbdb8-129">Extensions</span></span>  
 <span data-ttu-id="dbdb8-130">Datentyp: Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="dbdb8-130">Data type: string array</span></span>  
  
 <span data-ttu-id="dbdb8-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dbdb8-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dbdb8-132">Die Instanzkontexte für die Erweiterungen der Dienstinstanz.</span><span class="sxs-lookup"><span data-stu-id="dbdb8-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="dbdb8-133">Metadaten</span><span class="sxs-lookup"><span data-stu-id="dbdb8-133">Metadata</span></span>  
 <span data-ttu-id="dbdb8-134">Datentyp: Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="dbdb8-134">Data type: string array</span></span>  
  
 <span data-ttu-id="dbdb8-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dbdb8-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dbdb8-136">Die Dienstmetadateneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="dbdb8-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="dbdb8-137">name</span><span class="sxs-lookup"><span data-stu-id="dbdb8-137">Name</span></span>  
 <span data-ttu-id="dbdb8-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="dbdb8-138">Data type: string</span></span>  
  
 <span data-ttu-id="dbdb8-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dbdb8-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dbdb8-140">Der eindeutige Name des Diensts.</span><span class="sxs-lookup"><span data-stu-id="dbdb8-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="dbdb8-141">Namespace</span><span class="sxs-lookup"><span data-stu-id="dbdb8-141">Namespace</span></span>  
 <span data-ttu-id="dbdb8-142">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="dbdb8-142">Data type: string</span></span>  
  
 <span data-ttu-id="dbdb8-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dbdb8-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dbdb8-144">Der Namespace des Dienstes.</span><span class="sxs-lookup"><span data-stu-id="dbdb8-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="dbdb8-145">Opened</span><span class="sxs-lookup"><span data-stu-id="dbdb8-145">Opened</span></span>  
 <span data-ttu-id="dbdb8-146">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="dbdb8-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="dbdb8-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dbdb8-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dbdb8-148">Die Zeit, zu der der Dienst geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="dbdb8-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="dbdb8-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="dbdb8-149">OutgoingChannels</span></span>  
 <span data-ttu-id="dbdb8-150">Data type: Channel array (Kanal-Array)</span><span class="sxs-lookup"><span data-stu-id="dbdb8-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="dbdb8-151">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dbdb8-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dbdb8-152">Die Kanäle, die von der Dienstinstanz ausgehen.</span><span class="sxs-lookup"><span data-stu-id="dbdb8-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="dbdb8-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="dbdb8-153">ProcessId</span></span>  
 <span data-ttu-id="dbdb8-154">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="dbdb8-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="dbdb8-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dbdb8-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dbdb8-156">Die Prozess-ID des Vorgangs, von dem der Dienst gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="dbdb8-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbdb8-157">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dbdb8-157">Requirements</span></span>  
  
|<span data-ttu-id="dbdb8-158">MOF</span><span class="sxs-lookup"><span data-stu-id="dbdb8-158">MOF</span></span>|<span data-ttu-id="dbdb8-159">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="dbdb8-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="dbdb8-160">Namespace</span><span class="sxs-lookup"><span data-stu-id="dbdb8-160">Namespace</span></span>|<span data-ttu-id="dbdb8-161">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dbdb8-161">Defined in root\ServiceModel</span></span>|
