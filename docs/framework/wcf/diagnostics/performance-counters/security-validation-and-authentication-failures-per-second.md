---
title: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde
ms.date: 03/30/2017
ms.assetid: 266c3bd3-2ffc-4471-94b7-3675443be1ac
ms.openlocfilehash: 546d81b73e912915d265fb194de4ad9e45d55cea
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163916"
---
# <a name="security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="5a6aa-102">Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="5a6aa-102">Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="5a6aa-103">Indikatorname: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="5a6aa-103">Counter name: Security Validation and Authentication Failures Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5a6aa-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a6aa-104">Description</span></span>  
 <span data-ttu-id="5a6aa-105">Dieser Zähler wird jedes Mal inkrementiert, wenn eine Nachricht wegen eines Sicherheitsproblems abgelehnt wird, das nicht von dem Zähler "Nicht autorisierte Sicherheitsanrufe" abgedeckt wird.</span><span class="sxs-lookup"><span data-stu-id="5a6aa-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="5a6aa-106">Zu derartigen Problemen gehören:</span><span class="sxs-lookup"><span data-stu-id="5a6aa-106">Such problems include:</span></span>  
  
- <span data-ttu-id="5a6aa-107">Clienttoken kann nicht aus der Nachricht gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="5a6aa-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="5a6aa-108">Clienttoken hat die Authentifizierung (z. B. ungültiges Kennwort) nicht bestanden.</span><span class="sxs-lookup"><span data-stu-id="5a6aa-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="5a6aa-109">Signaturüberprüfung ist fehlgeschlagen (die Nachricht wurde z. B. manipuliert).</span><span class="sxs-lookup"><span data-stu-id="5a6aa-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="5a6aa-110">Die Nachricht ist ein Duplikat einer vorherigen; dies kann während eines Replay-Angriffs geschehen.</span><span class="sxs-lookup"><span data-stu-id="5a6aa-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="5a6aa-111">Ein Entschlüsselungsfehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5a6aa-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="5a6aa-112">Einige erforderliche Elemente (z. B. fehlender Timestamp oder verschlüsselter Datenblock) fehlen in der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="5a6aa-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="5a6aa-113">Während des TLSNEGO-/SPNEGO-Handshakes sind Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5a6aa-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="5a6aa-114">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird:</span><span class="sxs-lookup"><span data-stu-id="5a6aa-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="5a6aa-115">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="5a6aa-115">(N1-N0)/((D1-D0)/F)</span></span>
