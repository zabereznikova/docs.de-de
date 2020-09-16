---
title: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde
ms.date: 03/30/2017
ms.assetid: 266c3bd3-2ffc-4471-94b7-3675443be1ac
ms.openlocfilehash: 7d680e9a5b03943fdec212c509b6d80a2d60246c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559134"
---
# <a name="security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="0b522-102">Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="0b522-102">Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="0b522-103">Indikatorname: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="0b522-103">Counter name: Security Validation and Authentication Failures Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0b522-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0b522-104">Description</span></span>  
 <span data-ttu-id="0b522-105">Dieser Zähler wird jedes Mal inkrementiert, wenn eine Nachricht wegen eines Sicherheitsproblems abgelehnt wird, das nicht von dem Zähler "Nicht autorisierte Sicherheitsanrufe" abgedeckt wird.</span><span class="sxs-lookup"><span data-stu-id="0b522-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="0b522-106">Zu derartigen Problemen gehören:</span><span class="sxs-lookup"><span data-stu-id="0b522-106">Such problems include:</span></span>  
  
- <span data-ttu-id="0b522-107">Clienttoken kann nicht aus der Nachricht gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="0b522-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="0b522-108">Clienttoken hat die Authentifizierung (z. B. ungültiges Kennwort) nicht bestanden.</span><span class="sxs-lookup"><span data-stu-id="0b522-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="0b522-109">Signaturüberprüfung ist fehlgeschlagen (die Nachricht wurde z. B. manipuliert).</span><span class="sxs-lookup"><span data-stu-id="0b522-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="0b522-110">Die Nachricht ist ein Duplikat einer vorherigen; dies kann während eines Replay-Angriffs geschehen.</span><span class="sxs-lookup"><span data-stu-id="0b522-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="0b522-111">Ein Entschlüsselungsfehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0b522-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="0b522-112">Einige erforderliche Elemente (z. B. fehlender Timestamp oder verschlüsselter Datenblock) fehlen in der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="0b522-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="0b522-113">Während des TLSNEGO-/SPNEGO-Handshakes sind Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0b522-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="0b522-114">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird:</span><span class="sxs-lookup"><span data-stu-id="0b522-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="0b522-115">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="0b522-115">(N1-N0)/((D1-D0)/F)</span></span>
