---
title: AppDomainInfo
ms.date: 03/30/2017
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
ms.openlocfilehash: 0b7f8aadbd9a9dfcdd33fc65be3a5a41ea95f5be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61964254"
---
# <a name="appdomaininfo"></a><span data-ttu-id="5dace-102">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="5dace-102">AppDomainInfo</span></span>
<span data-ttu-id="5dace-103">Anwendungsdomäneninformationen</span><span class="sxs-lookup"><span data-stu-id="5dace-103">Application domain information</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dace-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5dace-104">Syntax</span></span>  
  
```csharp
class AppDomainInfo  
{  
  sint32 AppDomainId;  
  boolean IsDefault;  
  boolean LogMalformedMessages;  
  boolean LogMessagesAtServiceLevel;  
  boolean LogMessagesAtTransportLevel;  
  TraceListener MessageLoggingTraceListeners[];  
  string Name;  
  string PerformanceCounters;  
  sint32 ProcessId;  
  string ServiceConfigPath;  
  string TraceLevel;  
  TraceListener wmiTraceListeners[];  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="5dace-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="5dace-105">Methods</span></span>  
 <span data-ttu-id="5dace-106">Die AppDomainInfo-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="5dace-106">The AppDomainInfo class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="5dace-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="5dace-107">Properties</span></span>  
 <span data-ttu-id="5dace-108">Die AppDomainInfo-Klasse hat die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="5dace-108">The AppDomainInfo class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="5dace-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="5dace-109">AppDomainId</span></span>  
 <span data-ttu-id="5dace-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="5dace-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="5dace-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="5dace-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5dace-112">Die ID der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="5dace-112">The Id of the appdomain.</span></span>  
  
### <a name="isdefault"></a><span data-ttu-id="5dace-113">IsDefault</span><span class="sxs-lookup"><span data-stu-id="5dace-113">IsDefault</span></span>  
 <span data-ttu-id="5dace-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="5dace-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="5dace-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="5dace-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5dace-116">Gibt an, ob die Anwendungsdomäne die Standardanwendungsdomäne ist.</span><span class="sxs-lookup"><span data-stu-id="5dace-116">Indicates whether the appdomain is the default appdomain.</span></span>  
  
### <a name="logmalformedmessages"></a><span data-ttu-id="5dace-117">LogMalformedMessages</span><span class="sxs-lookup"><span data-stu-id="5dace-117">LogMalformedMessages</span></span>  
 <span data-ttu-id="5dace-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="5dace-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="5dace-119">Zugriffstyp: Lese-/Schreibzugriff</span><span class="sxs-lookup"><span data-stu-id="5dace-119">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="5dace-120">Ein Wert, der angibt, ob fehlerhafte Nachrichten protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="5dace-120">A value that specifies whether malformed messages are logged.</span></span>  
  
### <a name="logmessagesatservicelevel"></a><span data-ttu-id="5dace-121">LogMessagesAtServiceLevel</span><span class="sxs-lookup"><span data-stu-id="5dace-121">LogMessagesAtServiceLevel</span></span>  
 <span data-ttu-id="5dace-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="5dace-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="5dace-123">Zugriffstyp: Lese-/Schreibzugriff</span><span class="sxs-lookup"><span data-stu-id="5dace-123">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="5dace-124">Ein Wert, der angibt, ob Nachrichten auf Dienstebene (vor Verschlüsselung und transportbezogenen Transformationen) verfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="5dace-124">A value that specifies whether messages are traced at the service level (before encryption and transport-related transforms).</span></span>  
  
### <a name="logmessagesattransportlevel"></a><span data-ttu-id="5dace-125">LogMessagesAtTransportLevel</span><span class="sxs-lookup"><span data-stu-id="5dace-125">LogMessagesAtTransportLevel</span></span>  
 <span data-ttu-id="5dace-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="5dace-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="5dace-127">Zugriffstyp: Lese-/Schreibzugriff</span><span class="sxs-lookup"><span data-stu-id="5dace-127">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="5dace-128">Ein Wert, der angibt, ob Nachrichten auf der Transportebene verfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="5dace-128">A value that specifies whether messages are traced at the transport level.</span></span>  
  
### <a name="messageloggingtracelisteners"></a><span data-ttu-id="5dace-129">MessageLoggingTraceListeners</span><span class="sxs-lookup"><span data-stu-id="5dace-129">MessageLoggingTraceListeners</span></span>  
 <span data-ttu-id="5dace-130">Datentyp: TraceListener-array</span><span class="sxs-lookup"><span data-stu-id="5dace-130">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="5dace-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="5dace-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5dace-132">Die Sammlungsablaufverfolgungslistener, die die Ablaufverfolgungsquelle System.Wmi.MessageLogging abhören.</span><span class="sxs-lookup"><span data-stu-id="5dace-132">The collection trace listeners that listen to the System.Wmi.MessageLogging trace source.</span></span>  
  
### <a name="name"></a><span data-ttu-id="5dace-133">Name</span><span class="sxs-lookup"><span data-stu-id="5dace-133">Name</span></span>  
 <span data-ttu-id="5dace-134">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="5dace-134">Data type: string</span></span>  
  
 <span data-ttu-id="5dace-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="5dace-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5dace-136">Der Name der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="5dace-136">The name of the appdomain.</span></span>  
  
### <a name="performancecounters"></a><span data-ttu-id="5dace-137">PerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="5dace-137">PerformanceCounters</span></span>  
 <span data-ttu-id="5dace-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="5dace-138">Data type: string</span></span>  
  
 <span data-ttu-id="5dace-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="5dace-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5dace-140">Der Umfang der aktiven Leistungsindikatoren in der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="5dace-140">The scope of active performance counters in the appdomain.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="5dace-141">ProcessId</span><span class="sxs-lookup"><span data-stu-id="5dace-141">ProcessId</span></span>  
 <span data-ttu-id="5dace-142">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="5dace-142">Data type: sint32</span></span>  
  
 <span data-ttu-id="5dace-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="5dace-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5dace-144">Die Prozess-ID.</span><span class="sxs-lookup"><span data-stu-id="5dace-144">The process Id.</span></span>  
  
### <a name="serviceconfigpath"></a><span data-ttu-id="5dace-145">ServiceConfigPath</span><span class="sxs-lookup"><span data-stu-id="5dace-145">ServiceConfigPath</span></span>  
 <span data-ttu-id="5dace-146">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="5dace-146">Data type: string</span></span>  
  
 <span data-ttu-id="5dace-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="5dace-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5dace-148">Der Pfad zur Konfiguration des Dienstes.</span><span class="sxs-lookup"><span data-stu-id="5dace-148">The path to the configuration of the service.</span></span>  
  
### <a name="tracelevel"></a><span data-ttu-id="5dace-149">TraceLevel</span><span class="sxs-lookup"><span data-stu-id="5dace-149">TraceLevel</span></span>  
 <span data-ttu-id="5dace-150">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="5dace-150">Data type: string</span></span>  
  
 <span data-ttu-id="5dace-151">Zugriffstyp: Lese-/Schreibzugriff</span><span class="sxs-lookup"><span data-stu-id="5dace-151">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="5dace-152">Die Ablaufverfolgungsebene der Ablaufverfolgungsquelle System.Wmi.</span><span class="sxs-lookup"><span data-stu-id="5dace-152">The trace level of the System.Wmi trace source.</span></span>  
  
### <a name="servicemodeltracelisteners"></a><span data-ttu-id="5dace-153">ServiceModelTraceListeners</span><span class="sxs-lookup"><span data-stu-id="5dace-153">ServiceModelTraceListeners</span></span>  
 <span data-ttu-id="5dace-154">Datentyp: TraceListener-array</span><span class="sxs-lookup"><span data-stu-id="5dace-154">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="5dace-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="5dace-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5dace-156">Eine Listener-Sammlung aus der Ablaufverfolgungsquelle System.ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="5dace-156">A collection of listeners from the System.ServiceModel trace source.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dace-157">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5dace-157">Requirements</span></span>  
  
|<span data-ttu-id="5dace-158">MOF</span><span class="sxs-lookup"><span data-stu-id="5dace-158">MOF</span></span>|<span data-ttu-id="5dace-159">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="5dace-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5dace-160">Namespace</span><span class="sxs-lookup"><span data-stu-id="5dace-160">Namespace</span></span>|<span data-ttu-id="5dace-161">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5dace-161">Defined in root\ServiceModel</span></span>|
