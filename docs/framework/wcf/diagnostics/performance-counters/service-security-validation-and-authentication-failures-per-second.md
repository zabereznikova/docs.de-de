---
title: 'Dienst: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 4af18009-e778-490b-9ba6-e76485285830
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: fb0d4fdebf07dacfa7f33d8645332348270128e4
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44081791"
---
# <a name="service-security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="ae071-102">Dienst: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="ae071-102">Service: Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="ae071-103">Indikatorname: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="ae071-103">Counter name: Security Validation and Authentication Failures Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ae071-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ae071-104">Description</span></span>  
 <span data-ttu-id="ae071-105">Dieser Zähler wird jedes Mal inkrementiert, wenn eine Nachricht wegen eines Sicherheitsproblems abgelehnt wird, das nicht von dem Zähler "Nicht autorisierte Sicherheitsanrufe" abgedeckt wird.</span><span class="sxs-lookup"><span data-stu-id="ae071-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="ae071-106">Zu derartigen Problemen gehören:</span><span class="sxs-lookup"><span data-stu-id="ae071-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="ae071-107">Clienttoken kann nicht aus der Nachricht gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="ae071-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="ae071-108">Clienttoken hat die Authentifizierung (z. B. ungültiges Kennwort) nicht bestanden.</span><span class="sxs-lookup"><span data-stu-id="ae071-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="ae071-109">Signaturüberprüfung ist fehlgeschlagen (die Nachricht wurde z. B. manipuliert).</span><span class="sxs-lookup"><span data-stu-id="ae071-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="ae071-110">Die Nachricht ist ein Duplikat einer vorherigen; dies kann während eines Replay-Angriffs geschehen.</span><span class="sxs-lookup"><span data-stu-id="ae071-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="ae071-111">Ein Entschlüsselungsfehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ae071-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="ae071-112">Einige erforderliche Elemente (z. B. fehlender Timestamp oder verschlüsselter Datenblock) fehlen in der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="ae071-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="ae071-113">Während des TLSNEGO-/SPNEGO-Handshakes sind Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ae071-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="ae071-114">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert mit der folgenden Formel berechnet wird</span><span class="sxs-lookup"><span data-stu-id="ae071-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula,</span></span>  
  
 <span data-ttu-id="ae071-115">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="ae071-115">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
