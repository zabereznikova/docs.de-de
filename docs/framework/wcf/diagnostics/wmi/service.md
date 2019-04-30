---
title: Dienst
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: c59672b3b7617d9c28d99f7d534b6e7f2f2e9fbb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991444"
---
# <a name="service"></a><span data-ttu-id="bf856-102">Dienst</span><span class="sxs-lookup"><span data-stu-id="bf856-102">Service</span></span>
<span data-ttu-id="bf856-103">Dienst</span><span class="sxs-lookup"><span data-stu-id="bf856-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf856-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf856-104">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="bf856-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="bf856-105">Methods</span></span>  
 <span data-ttu-id="bf856-106">Die Dienstklasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="bf856-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bf856-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="bf856-107">Properties</span></span>  
 <span data-ttu-id="bf856-108">Die Dienstklasse hat die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="bf856-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="bf856-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="bf856-109">BaseAddresses</span></span>  
 <span data-ttu-id="bf856-110">Datentyp: Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="bf856-110">Data type: string array</span></span>  
  
 <span data-ttu-id="bf856-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="bf856-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf856-112">Die vom Dienst verwendeten Basisadressen.</span><span class="sxs-lookup"><span data-stu-id="bf856-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="bf856-113">Verhalten</span><span class="sxs-lookup"><span data-stu-id="bf856-113">Behaviors</span></span>  
 <span data-ttu-id="bf856-114">Datentyp: Behavior-array</span><span class="sxs-lookup"><span data-stu-id="bf856-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="bf856-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="bf856-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf856-116">Die diesem Dienst zugewiesenen Verhalten.</span><span class="sxs-lookup"><span data-stu-id="bf856-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="bf856-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="bf856-117">ConfigurationName</span></span>  
 <span data-ttu-id="bf856-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="bf856-118">Data type: string</span></span>  
  
 <span data-ttu-id="bf856-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="bf856-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf856-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="bf856-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="bf856-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="bf856-121">CounterInstanceName</span></span>  
 <span data-ttu-id="bf856-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="bf856-122">Data type: string</span></span>  
  
 <span data-ttu-id="bf856-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="bf856-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf856-124">Name der Instanz der Leistungsindikatoren des Dienstes.</span><span class="sxs-lookup"><span data-stu-id="bf856-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="bf856-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="bf856-125">DistinguishedName</span></span>  
 <span data-ttu-id="bf856-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="bf856-126">Data type: string</span></span>  
  
 <span data-ttu-id="bf856-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="bf856-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf856-128">Der Dienstname an der Adresse.</span><span class="sxs-lookup"><span data-stu-id="bf856-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="bf856-129">Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="bf856-129">Extensions</span></span>  
 <span data-ttu-id="bf856-130">Datentyp: Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="bf856-130">Data type: string array</span></span>  
  
 <span data-ttu-id="bf856-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="bf856-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf856-132">Die Instanzkontexte für die Erweiterungen der Dienstinstanz.</span><span class="sxs-lookup"><span data-stu-id="bf856-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="bf856-133">Metadaten</span><span class="sxs-lookup"><span data-stu-id="bf856-133">Metadata</span></span>  
 <span data-ttu-id="bf856-134">Datentyp: Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="bf856-134">Data type: string array</span></span>  
  
 <span data-ttu-id="bf856-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="bf856-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf856-136">Die Dienstmetadateneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="bf856-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="bf856-137">Name</span><span class="sxs-lookup"><span data-stu-id="bf856-137">Name</span></span>  
 <span data-ttu-id="bf856-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="bf856-138">Data type: string</span></span>  
  
 <span data-ttu-id="bf856-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="bf856-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf856-140">Der eindeutige Name des Diensts.</span><span class="sxs-lookup"><span data-stu-id="bf856-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="bf856-141">Namespace</span><span class="sxs-lookup"><span data-stu-id="bf856-141">Namespace</span></span>  
 <span data-ttu-id="bf856-142">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="bf856-142">Data type: string</span></span>  
  
 <span data-ttu-id="bf856-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="bf856-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf856-144">Der Namespace des Dienstes.</span><span class="sxs-lookup"><span data-stu-id="bf856-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="bf856-145">Opened</span><span class="sxs-lookup"><span data-stu-id="bf856-145">Opened</span></span>  
 <span data-ttu-id="bf856-146">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="bf856-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="bf856-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="bf856-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf856-148">Die Zeit, zu der der Dienst geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="bf856-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="bf856-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="bf856-149">OutgoingChannels</span></span>  
 <span data-ttu-id="bf856-150">Datentyp: Channel-array</span><span class="sxs-lookup"><span data-stu-id="bf856-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="bf856-151">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="bf856-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf856-152">Die Kanäle, die von der Dienstinstanz ausgehen.</span><span class="sxs-lookup"><span data-stu-id="bf856-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="bf856-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="bf856-153">ProcessId</span></span>  
 <span data-ttu-id="bf856-154">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="bf856-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="bf856-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="bf856-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf856-156">Die Prozess-ID des Vorgangs, von dem der Dienst gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="bf856-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf856-157">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bf856-157">Requirements</span></span>  
  
|<span data-ttu-id="bf856-158">MOF</span><span class="sxs-lookup"><span data-stu-id="bf856-158">MOF</span></span>|<span data-ttu-id="bf856-159">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="bf856-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bf856-160">Namespace</span><span class="sxs-lookup"><span data-stu-id="bf856-160">Namespace</span></span>|<span data-ttu-id="bf856-161">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bf856-161">Defined in root\ServiceModel</span></span>|
