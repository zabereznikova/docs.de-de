---
title: 'Endpunkt: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 89a70b90-d7e4-4b03-9b84-4dc88ce3d605
ms.openlocfilehash: 43886f79585fb9a63eeb51360cc869365c100a1d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129050"
---
# <a name="endpoint-security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="2fd29-102">Endpunkt: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="2fd29-102">Endpoint: Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="2fd29-103">Indikatorname: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="2fd29-103">Counter name: Security Validation and Authentication Failures Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="2fd29-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2fd29-104">Description</span></span>  
 <span data-ttu-id="2fd29-105">Dieser Zähler wird jedes Mal inkrementiert, wenn eine Nachricht wegen eines Sicherheitsproblems abgelehnt wird, das nicht von dem Zähler "Nicht autorisierte Sicherheitsanrufe" abgedeckt wird.</span><span class="sxs-lookup"><span data-stu-id="2fd29-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="2fd29-106">Zu derartigen Problemen gehören:</span><span class="sxs-lookup"><span data-stu-id="2fd29-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="2fd29-107">Clienttoken kann nicht aus der Nachricht gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="2fd29-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="2fd29-108">Clienttoken hat die Authentifizierung (z. B. ungültiges Kennwort) nicht bestanden.</span><span class="sxs-lookup"><span data-stu-id="2fd29-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="2fd29-109">Signaturüberprüfung ist fehlgeschlagen (die Nachricht wurde z. B. manipuliert).</span><span class="sxs-lookup"><span data-stu-id="2fd29-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="2fd29-110">Die Nachricht ist ein Duplikat einer vorherigen; dies kann während eines Replay-Angriffs geschehen.</span><span class="sxs-lookup"><span data-stu-id="2fd29-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="2fd29-111">Ein Entschlüsselungsfehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2fd29-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="2fd29-112">Einige erforderliche Elemente (z. B. fehlender Timestamp oder verschlüsselter Datenblock) fehlen in der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="2fd29-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="2fd29-113">Während des TLSNEGO-/SPNEGO-Handshakes sind Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2fd29-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="2fd29-114">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird:</span><span class="sxs-lookup"><span data-stu-id="2fd29-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="2fd29-115">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="2fd29-115">(N1-N0)/((D1-D0)/F)</span></span>
