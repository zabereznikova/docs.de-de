---
title: 'Dienst: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 4af18009-e778-490b-9ba6-e76485285830
ms.openlocfilehash: 2caebed85a28004ef038beee7d07c05a23da53c0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64613684"
---
# <a name="service-security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="d6ab9-102">Dienst: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="d6ab9-102">Service: Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="d6ab9-103">Indikatorname: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="d6ab9-103">Counter name: Security Validation and Authentication Failures Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d6ab9-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d6ab9-104">Description</span></span>  
 <span data-ttu-id="d6ab9-105">Dieser Zähler wird jedes Mal inkrementiert, wenn eine Nachricht wegen eines Sicherheitsproblems abgelehnt wird, das nicht von dem Zähler "Nicht autorisierte Sicherheitsanrufe" abgedeckt wird.</span><span class="sxs-lookup"><span data-stu-id="d6ab9-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="d6ab9-106">Zu derartigen Problemen gehören:</span><span class="sxs-lookup"><span data-stu-id="d6ab9-106">Such problems include:</span></span>  
  
- <span data-ttu-id="d6ab9-107">Clienttoken kann nicht aus der Nachricht gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="d6ab9-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="d6ab9-108">Clienttoken hat die Authentifizierung (z. B. ungültiges Kennwort) nicht bestanden.</span><span class="sxs-lookup"><span data-stu-id="d6ab9-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="d6ab9-109">Signaturüberprüfung ist fehlgeschlagen (die Nachricht wurde z. B. manipuliert).</span><span class="sxs-lookup"><span data-stu-id="d6ab9-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="d6ab9-110">Die Nachricht ist ein Duplikat einer vorherigen; dies kann während eines Replay-Angriffs geschehen.</span><span class="sxs-lookup"><span data-stu-id="d6ab9-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="d6ab9-111">Ein Entschlüsselungsfehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d6ab9-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="d6ab9-112">Einige erforderliche Elemente (z. B. fehlender Timestamp oder verschlüsselter Datenblock) fehlen in der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="d6ab9-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="d6ab9-113">Während des TLSNEGO-/SPNEGO-Handshakes sind Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d6ab9-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="d6ab9-114">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert mit der folgenden Formel berechnet wird</span><span class="sxs-lookup"><span data-stu-id="d6ab9-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula,</span></span>  
  
 <span data-ttu-id="d6ab9-115">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="d6ab9-115">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
