---
title: AppDomainInfo
ms.date: 03/30/2017
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
ms.openlocfilehash: 7189448a930298837089cf3ac2743cb7e073ae02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486980"
---
# <a name="appdomaininfo"></a><span data-ttu-id="f5d3c-102">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="f5d3c-102">AppDomainInfo</span></span>
<span data-ttu-id="f5d3c-103">Anwendungsdomäneninformationen</span><span class="sxs-lookup"><span data-stu-id="f5d3c-103">Application domain information</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5d3c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5d3c-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="f5d3c-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f5d3c-105">Methods</span></span>  
 <span data-ttu-id="f5d3c-106">Die AppDomainInfo-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="f5d3c-106">The AppDomainInfo class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f5d3c-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f5d3c-107">Properties</span></span>  
 <span data-ttu-id="f5d3c-108">Die AppDomainInfo-Klasse hat die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f5d3c-108">The AppDomainInfo class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="f5d3c-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="f5d3c-109">AppDomainId</span></span>  
 <span data-ttu-id="f5d3c-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="f5d3c-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="f5d3c-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f5d3c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f5d3c-112">Die ID der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="f5d3c-112">The Id of the appdomain.</span></span>  
  
### <a name="isdefault"></a><span data-ttu-id="f5d3c-113">IsDefault</span><span class="sxs-lookup"><span data-stu-id="f5d3c-113">IsDefault</span></span>  
 <span data-ttu-id="f5d3c-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="f5d3c-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="f5d3c-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f5d3c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f5d3c-116">Gibt an, ob die Anwendungsdomäne die Standardanwendungsdomäne ist.</span><span class="sxs-lookup"><span data-stu-id="f5d3c-116">Indicates whether the appdomain is the default appdomain.</span></span>  
  
### <a name="logmalformedmessages"></a><span data-ttu-id="f5d3c-117">LogMalformedMessages</span><span class="sxs-lookup"><span data-stu-id="f5d3c-117">LogMalformedMessages</span></span>  
 <span data-ttu-id="f5d3c-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="f5d3c-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="f5d3c-119">Zugriffstyp: Lesen/Schreiben</span><span class="sxs-lookup"><span data-stu-id="f5d3c-119">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="f5d3c-120">Ein Wert, der angibt, ob fehlerhafte Nachrichten protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="f5d3c-120">A value that specifies whether malformed messages are logged.</span></span>  
  
### <a name="logmessagesatservicelevel"></a><span data-ttu-id="f5d3c-121">LogMessagesAtServiceLevel</span><span class="sxs-lookup"><span data-stu-id="f5d3c-121">LogMessagesAtServiceLevel</span></span>  
 <span data-ttu-id="f5d3c-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="f5d3c-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="f5d3c-123">Zugriffstyp: Lesen/Schreiben</span><span class="sxs-lookup"><span data-stu-id="f5d3c-123">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="f5d3c-124">Ein Wert, der angibt, ob Nachrichten auf Dienstebene (vor Verschlüsselung und transportbezogenen Transformationen) verfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="f5d3c-124">A value that specifies whether messages are traced at the service level (before encryption and transport-related transforms).</span></span>  
  
### <a name="logmessagesattransportlevel"></a><span data-ttu-id="f5d3c-125">LogMessagesAtTransportLevel</span><span class="sxs-lookup"><span data-stu-id="f5d3c-125">LogMessagesAtTransportLevel</span></span>  
 <span data-ttu-id="f5d3c-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="f5d3c-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="f5d3c-127">Zugriffstyp: Lesen/Schreiben</span><span class="sxs-lookup"><span data-stu-id="f5d3c-127">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="f5d3c-128">Ein Wert, der angibt, ob Nachrichten auf der Transportebene verfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="f5d3c-128">A value that specifies whether messages are traced at the transport level.</span></span>  
  
### <a name="messageloggingtracelisteners"></a><span data-ttu-id="f5d3c-129">MessageLoggingTraceListeners</span><span class="sxs-lookup"><span data-stu-id="f5d3c-129">MessageLoggingTraceListeners</span></span>  
 <span data-ttu-id="f5d3c-130">Datentyp: TraceListener-Array</span><span class="sxs-lookup"><span data-stu-id="f5d3c-130">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="f5d3c-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f5d3c-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f5d3c-132">Die Sammlungsablaufverfolgungslistener, die die Ablaufverfolgungsquelle System.Wmi.MessageLogging abhören.</span><span class="sxs-lookup"><span data-stu-id="f5d3c-132">The collection trace listeners that listen to the System.Wmi.MessageLogging trace source.</span></span>  
  
### <a name="name"></a><span data-ttu-id="f5d3c-133">name</span><span class="sxs-lookup"><span data-stu-id="f5d3c-133">Name</span></span>  
 <span data-ttu-id="f5d3c-134">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f5d3c-134">Data type: string</span></span>  
  
 <span data-ttu-id="f5d3c-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f5d3c-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f5d3c-136">Der Name der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="f5d3c-136">The name of the appdomain.</span></span>  
  
### <a name="performancecounters"></a><span data-ttu-id="f5d3c-137">PerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="f5d3c-137">PerformanceCounters</span></span>  
 <span data-ttu-id="f5d3c-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f5d3c-138">Data type: string</span></span>  
  
 <span data-ttu-id="f5d3c-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f5d3c-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f5d3c-140">Der Umfang der aktiven Leistungsindikatoren in der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="f5d3c-140">The scope of active performance counters in the appdomain.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="f5d3c-141">ProcessId</span><span class="sxs-lookup"><span data-stu-id="f5d3c-141">ProcessId</span></span>  
 <span data-ttu-id="f5d3c-142">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="f5d3c-142">Data type: sint32</span></span>  
  
 <span data-ttu-id="f5d3c-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f5d3c-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f5d3c-144">Die Prozess-ID.</span><span class="sxs-lookup"><span data-stu-id="f5d3c-144">The process Id.</span></span>  
  
### <a name="serviceconfigpath"></a><span data-ttu-id="f5d3c-145">ServiceConfigPath</span><span class="sxs-lookup"><span data-stu-id="f5d3c-145">ServiceConfigPath</span></span>  
 <span data-ttu-id="f5d3c-146">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f5d3c-146">Data type: string</span></span>  
  
 <span data-ttu-id="f5d3c-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f5d3c-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f5d3c-148">Der Pfad zur Konfiguration des Dienstes.</span><span class="sxs-lookup"><span data-stu-id="f5d3c-148">The path to the configuration of the service.</span></span>  
  
### <a name="tracelevel"></a><span data-ttu-id="f5d3c-149">TraceLevel</span><span class="sxs-lookup"><span data-stu-id="f5d3c-149">TraceLevel</span></span>  
 <span data-ttu-id="f5d3c-150">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f5d3c-150">Data type: string</span></span>  
  
 <span data-ttu-id="f5d3c-151">Zugriffstyp: Lesen/Schreiben</span><span class="sxs-lookup"><span data-stu-id="f5d3c-151">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="f5d3c-152">Die Ablaufverfolgungsebene der Ablaufverfolgungsquelle System.Wmi.</span><span class="sxs-lookup"><span data-stu-id="f5d3c-152">The trace level of the System.Wmi trace source.</span></span>  
  
### <a name="servicemodeltracelisteners"></a><span data-ttu-id="f5d3c-153">ServiceModelTraceListeners</span><span class="sxs-lookup"><span data-stu-id="f5d3c-153">ServiceModelTraceListeners</span></span>  
 <span data-ttu-id="f5d3c-154">Datentyp: TraceListener-Array</span><span class="sxs-lookup"><span data-stu-id="f5d3c-154">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="f5d3c-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f5d3c-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f5d3c-156">Eine Listener-Sammlung aus der Ablaufverfolgungsquelle System.ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="f5d3c-156">A collection of listeners from the System.ServiceModel trace source.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5d3c-157">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f5d3c-157">Requirements</span></span>  
  
|<span data-ttu-id="f5d3c-158">MOF</span><span class="sxs-lookup"><span data-stu-id="f5d3c-158">MOF</span></span>|<span data-ttu-id="f5d3c-159">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f5d3c-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f5d3c-160">Namespace</span><span class="sxs-lookup"><span data-stu-id="f5d3c-160">Namespace</span></span>|<span data-ttu-id="f5d3c-161">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f5d3c-161">Defined in root\ServiceModel</span></span>|
