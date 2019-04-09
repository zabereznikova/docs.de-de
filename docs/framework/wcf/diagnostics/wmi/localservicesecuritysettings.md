---
title: LocalServiceSecuritySettings
ms.date: 03/30/2017
ms.assetid: 490aa0e5-5242-4f8d-b505-5ec6287633b4
ms.openlocfilehash: 15304630eb8a14e01d4815ddddc84cd32796fdcf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133480"
---
# <a name="localservicesecuritysettings"></a><span data-ttu-id="47fbd-102">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="47fbd-102">LocalServiceSecuritySettings</span></span>
<span data-ttu-id="47fbd-103">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="47fbd-103">LocalServiceSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47fbd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="47fbd-104">Syntax</span></span>  
  
```csharp
class LocalServiceSecuritySettings  
{  
  boolean DetectReplays;  
  datetime InactivityTimeout;  
  datetime IssuedCookieLifetime;  
  sint32 MaxCachedCookies;  
  datetime MaxClockSkew;  
  sint32 MaxPendingSessions;  
  sint32 MaxStatefulNegotiations;  
  datetime NegotiationTimeout;  
  boolean ReconnectTransportOnFailure;  
  sint32 ReplayCacheSize;  
  datetime ReplayWindow;  
  datetime SessionKeyRenewalInterval;  
  datetime SessionKeyRolloverInterval;  
  datetime TimestampValidityDuration;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="47fbd-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="47fbd-105">Methods</span></span>  
 <span data-ttu-id="47fbd-106">Die LocalServiceSecuritySettings-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="47fbd-106">The LocalServiceSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="47fbd-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="47fbd-107">Properties</span></span>  
 <span data-ttu-id="47fbd-108">Die LocalServiceSecuritySettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="47fbd-108">The LocalServiceSecuritySettings class has the following properties:</span></span>  
  
### <a name="detectreplays"></a><span data-ttu-id="47fbd-109">DetectReplays</span><span class="sxs-lookup"><span data-stu-id="47fbd-109">DetectReplays</span></span>  
 <span data-ttu-id="47fbd-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="47fbd-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="47fbd-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="47fbd-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="47fbd-112">Ein boolescher Wert, der angibt, ob Replay-Angriffe auf den Kanal automatisch erkannt und behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="47fbd-112">A Boolean value that specifies whether replay attacks against the channel are detected and dealt with automatically.</span></span>  
  
### <a name="inactivitytimeout"></a><span data-ttu-id="47fbd-113">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="47fbd-113">InactivityTimeout</span></span>  
 <span data-ttu-id="47fbd-114">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="47fbd-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="47fbd-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="47fbd-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="47fbd-116">Die maximale Anzahl von ausstehenden Sicherheitssitzungen, die der Dienst unterstützt.</span><span class="sxs-lookup"><span data-stu-id="47fbd-116">The maximum number of pending security sessions that the service supports.</span></span>  
  
### <a name="issuedcookielifetime"></a><span data-ttu-id="47fbd-117">IssuedCookieLifetime</span><span class="sxs-lookup"><span data-stu-id="47fbd-117">IssuedCookieLifetime</span></span>  
 <span data-ttu-id="47fbd-118">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="47fbd-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="47fbd-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="47fbd-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="47fbd-120">Eine Zeitspanne, die die für alle neuen Sicherheitscookies ausgestellte Lebensdauer angibt.</span><span class="sxs-lookup"><span data-stu-id="47fbd-120">A TimeSpan that specifies the lifetime issued to all new security cookies.</span></span>  
  
### <a name="maxcachedcookies"></a><span data-ttu-id="47fbd-121">MaxCachedCookies</span><span class="sxs-lookup"><span data-stu-id="47fbd-121">MaxCachedCookies</span></span>  
 <span data-ttu-id="47fbd-122">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="47fbd-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="47fbd-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="47fbd-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="47fbd-124">Die maximale Anzahl von Cookies, die zwischengespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="47fbd-124">The maximum number of cookies that can be cached.</span></span>  
  
### <a name="maxclockskew"></a><span data-ttu-id="47fbd-125">MaxClockSkew</span><span class="sxs-lookup"><span data-stu-id="47fbd-125">MaxClockSkew</span></span>  
 <span data-ttu-id="47fbd-126">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="47fbd-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="47fbd-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="47fbd-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="47fbd-128">Eine Zeitspanne, die den maximal zulässigen Zeitunterschied zwischen den Systemuhren der beiden Kommunikationspartner angibt.</span><span class="sxs-lookup"><span data-stu-id="47fbd-128">A TimeSpan that specifies the maximum time difference between the system clocks of the two communicating parties.</span></span>  
  
### <a name="maxpendingsessions"></a><span data-ttu-id="47fbd-129">MaxPendingSessions</span><span class="sxs-lookup"><span data-stu-id="47fbd-129">MaxPendingSessions</span></span>  
 <span data-ttu-id="47fbd-130">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="47fbd-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="47fbd-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="47fbd-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="47fbd-132">Die maximale Anzahl ausstehender Verbindungen für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="47fbd-132">The maximum number of pending connections on the service.</span></span>  
  
### <a name="maxstatefulnegotiations"></a><span data-ttu-id="47fbd-133">MaxStatefulNegotiations</span><span class="sxs-lookup"><span data-stu-id="47fbd-133">MaxStatefulNegotiations</span></span>  
 <span data-ttu-id="47fbd-134">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="47fbd-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="47fbd-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="47fbd-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="47fbd-136">Die Anzahl von Sicherheitsverhandlungen, die gleichzeitig aktiv sein können.</span><span class="sxs-lookup"><span data-stu-id="47fbd-136">The number of security negotiations that can be active concurrently.</span></span>  
  
### <a name="negotiationtimeout"></a><span data-ttu-id="47fbd-137">NegotiationTimeout</span><span class="sxs-lookup"><span data-stu-id="47fbd-137">NegotiationTimeout</span></span>  
 <span data-ttu-id="47fbd-138">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="47fbd-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="47fbd-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="47fbd-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="47fbd-140">Eine Zeitspanne, die die maximale Dauer der Sicherheitsaushandlungsphase zwischen Server und Client angibt.</span><span class="sxs-lookup"><span data-stu-id="47fbd-140">A TimeSpan that specifies the maximum duration for the security negotiation phase between server and client.</span></span>  
  
### <a name="reconnecttransportonfailure"></a><span data-ttu-id="47fbd-141">ReconnectTransportOnFailure</span><span class="sxs-lookup"><span data-stu-id="47fbd-141">ReconnectTransportOnFailure</span></span>  
 <span data-ttu-id="47fbd-142">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="47fbd-142">Data type: boolean</span></span>  
  
 <span data-ttu-id="47fbd-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="47fbd-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="47fbd-144">Ein boolescher Wert, der angibt, ob mit zuverlässigem WS-Messaging hergestellte Verbindungen nach Transportfehlern erneut versuchen, eine Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="47fbd-144">A Boolean value that specifies whether connections using WS-Reliable messaging attempt to reconnect after transport failures.</span></span>  
  
### <a name="replaycachesize"></a><span data-ttu-id="47fbd-145">ReplayCacheSize</span><span class="sxs-lookup"><span data-stu-id="47fbd-145">ReplayCacheSize</span></span>  
 <span data-ttu-id="47fbd-146">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="47fbd-146">Data type: sint32</span></span>  
  
 <span data-ttu-id="47fbd-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="47fbd-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="47fbd-148">Die Anzahl zwischengespeicherter Nonces, die für die Wiedergabeerkennung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="47fbd-148">The number of cached nonces used for replay detection.</span></span>  
  
### <a name="replaywindow"></a><span data-ttu-id="47fbd-149">ReplayWindow</span><span class="sxs-lookup"><span data-stu-id="47fbd-149">ReplayWindow</span></span>  
 <span data-ttu-id="47fbd-150">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="47fbd-150">Data type: datetime</span></span>  
  
 <span data-ttu-id="47fbd-151">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="47fbd-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="47fbd-152">Eine Zeitspanne, die angibt, wie lange individuelle Nachrichtennonces gültig sind.</span><span class="sxs-lookup"><span data-stu-id="47fbd-152">A TimeSpan that specifies the duration in which individual message nonces are valid.</span></span>  
  
### <a name="sessionkeyrenewalinterval"></a><span data-ttu-id="47fbd-153">SessionKeyRenewalInterval</span><span class="sxs-lookup"><span data-stu-id="47fbd-153">SessionKeyRenewalInterval</span></span>  
 <span data-ttu-id="47fbd-154">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="47fbd-154">Data type: datetime</span></span>  
  
 <span data-ttu-id="47fbd-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="47fbd-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="47fbd-156">Eine Zeitspanne, die die Dauer angibt, nach der der Initiator den Schlüssel für die Sicherheitssitzung erneuert.</span><span class="sxs-lookup"><span data-stu-id="47fbd-156">A TimeSpan that specifies the duration after which the initiator renews the key for the security session.</span></span>  
  
### <a name="sessionkeyrolloverinterval"></a><span data-ttu-id="47fbd-157">SessionKeyRolloverInterval</span><span class="sxs-lookup"><span data-stu-id="47fbd-157">SessionKeyRolloverInterval</span></span>  
 <span data-ttu-id="47fbd-158">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="47fbd-158">Data type: datetime</span></span>  
  
 <span data-ttu-id="47fbd-159">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="47fbd-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="47fbd-160">Eine Zeitspanne, die das Zeitintervall angibt, in dem ein alter Sitzungsschlüssel während der Schlüsselerneuerung für eingehende Nachrichten gültig ist.</span><span class="sxs-lookup"><span data-stu-id="47fbd-160">A TimeSpan that specifies the time interval a previous session key is valid on incoming messages during a key renewal.</span></span>  
  
### <a name="timestampvalidityduration"></a><span data-ttu-id="47fbd-161">TimestampValidityDuration</span><span class="sxs-lookup"><span data-stu-id="47fbd-161">TimestampValidityDuration</span></span>  
 <span data-ttu-id="47fbd-162">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="47fbd-162">Data type: datetime</span></span>  
  
 <span data-ttu-id="47fbd-163">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="47fbd-163">Access type: Read-only</span></span>  
  
 <span data-ttu-id="47fbd-164">Eine Zeitspanne, die angibt, wie lange ein Zeitstempel gültig ist.</span><span class="sxs-lookup"><span data-stu-id="47fbd-164">A TimeSpan that specifies the duration in which a time stamp is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47fbd-165">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="47fbd-165">Requirements</span></span>  
  
|<span data-ttu-id="47fbd-166">MOF</span><span class="sxs-lookup"><span data-stu-id="47fbd-166">MOF</span></span>|<span data-ttu-id="47fbd-167">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="47fbd-167">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="47fbd-168">Namespace</span><span class="sxs-lookup"><span data-stu-id="47fbd-168">Namespace</span></span>|<span data-ttu-id="47fbd-169">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="47fbd-169">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="47fbd-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47fbd-170">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
