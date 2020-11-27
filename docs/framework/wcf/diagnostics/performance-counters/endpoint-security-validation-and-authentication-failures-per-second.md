---
title: 'Endpunkt: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 89a70b90-d7e4-4b03-9b84-4dc88ce3d605
ms.openlocfilehash: b2c5022caa5abe6154a3cb4dd4281dd212599b74
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256481"
---
# <a name="endpoint-security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="7a135-102">Endpunkt: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="7a135-102">Endpoint: Security Validation and Authentication Failures Per Second</span></span>

<span data-ttu-id="7a135-103">Indikatorname: Security Validation and Authentication Failures Per Second</span><span class="sxs-lookup"><span data-stu-id="7a135-103">Counter name: Security Validation and Authentication Failures Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="7a135-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7a135-104">Description</span></span>  

 <span data-ttu-id="7a135-105">Dieser Zähler wird jedes Mal inkrementiert, wenn eine Nachricht wegen eines Sicherheitsproblems abgelehnt wird, das nicht von dem Zähler "Nicht autorisierte Sicherheitsanrufe" abgedeckt wird.</span><span class="sxs-lookup"><span data-stu-id="7a135-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="7a135-106">Zu derartigen Problemen gehören:</span><span class="sxs-lookup"><span data-stu-id="7a135-106">Such problems include:</span></span>  
  
- <span data-ttu-id="7a135-107">Clienttoken kann nicht aus der Nachricht gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="7a135-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="7a135-108">Clienttoken hat die Authentifizierung (z. B. ungültiges Kennwort) nicht bestanden.</span><span class="sxs-lookup"><span data-stu-id="7a135-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="7a135-109">Signaturüberprüfung ist fehlgeschlagen (die Nachricht wurde z. B. manipuliert).</span><span class="sxs-lookup"><span data-stu-id="7a135-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="7a135-110">Die Nachricht ist ein Duplikat einer vorherigen; dies kann während eines Replay-Angriffs geschehen.</span><span class="sxs-lookup"><span data-stu-id="7a135-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="7a135-111">Ein Entschlüsselungsfehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7a135-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="7a135-112">Einige erforderliche Elemente (z. B. fehlender Timestamp oder verschlüsselter Datenblock) fehlen in der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="7a135-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="7a135-113">Während des TLSNEGO-/SPNEGO-Handshakes sind Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7a135-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="7a135-114">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird:</span><span class="sxs-lookup"><span data-stu-id="7a135-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="7a135-115">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="7a135-115">(N1-N0)/((D1-D0)/F)</span></span>
