---
title: 'Endpunkt: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 89a70b90-d7e4-4b03-9b84-4dc88ce3d605
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: bc68f49326818f0e6687c06a38e5e51fd6960c9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474733"
---
# <a name="endpoint-security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="848d3-102">Endpunkt: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="848d3-102">Endpoint: Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="848d3-103">Indikatorname: Security Validation and Authentication Failures Per Second</span><span class="sxs-lookup"><span data-stu-id="848d3-103">Counter name: Security Validation and Authentication Failures Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="848d3-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="848d3-104">Description</span></span>  
 <span data-ttu-id="848d3-105">Dieser Zähler wird jedes Mal inkrementiert, wenn eine Nachricht wegen eines Sicherheitsproblems abgelehnt wird, das nicht von dem Zähler "Nicht autorisierte Sicherheitsanrufe" abgedeckt wird.</span><span class="sxs-lookup"><span data-stu-id="848d3-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="848d3-106">Zu derartigen Problemen gehören:</span><span class="sxs-lookup"><span data-stu-id="848d3-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="848d3-107">Clienttoken kann nicht aus der Nachricht gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="848d3-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="848d3-108">Clienttoken hat die Authentifizierung (z. B. ungültiges Kennwort) nicht bestanden.</span><span class="sxs-lookup"><span data-stu-id="848d3-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="848d3-109">Signaturüberprüfung ist fehlgeschlagen (die Nachricht wurde z. B. manipuliert).</span><span class="sxs-lookup"><span data-stu-id="848d3-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="848d3-110">Die Nachricht ist ein Duplikat einer vorherigen; dies kann während eines Replay-Angriffs geschehen.</span><span class="sxs-lookup"><span data-stu-id="848d3-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="848d3-111">Ein Entschlüsselungsfehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="848d3-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="848d3-112">Einige erforderliche Elemente (z. B. fehlender Timestamp oder verschlüsselter Datenblock) fehlen in der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="848d3-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="848d3-113">Während des TLSNEGO-/SPNEGO-Handshakes sind Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="848d3-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="848d3-114">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird:</span><span class="sxs-lookup"><span data-stu-id="848d3-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="848d3-115">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="848d3-115">(N1-N0)/((D1-D0)/F)</span></span>
