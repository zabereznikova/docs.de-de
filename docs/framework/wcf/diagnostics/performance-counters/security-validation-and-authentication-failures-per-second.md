---
title: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde
ms.date: 03/30/2017
ms.assetid: 266c3bd3-2ffc-4471-94b7-3675443be1ac
ms.openlocfilehash: e3db8cb20399bdff9b73a428ea2a53909da4eee1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61915771"
---
# <a name="security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="34548-102">Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="34548-102">Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="34548-103">Indikatorname: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="34548-103">Counter name: Security Validation and Authentication Failures Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="34548-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34548-104">Description</span></span>  
 <span data-ttu-id="34548-105">Dieser Zähler wird jedes Mal inkrementiert, wenn eine Nachricht wegen eines Sicherheitsproblems abgelehnt wird, das nicht von dem Zähler "Nicht autorisierte Sicherheitsanrufe" abgedeckt wird.</span><span class="sxs-lookup"><span data-stu-id="34548-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="34548-106">Zu derartigen Problemen gehören:</span><span class="sxs-lookup"><span data-stu-id="34548-106">Such problems include:</span></span>  
  
- <span data-ttu-id="34548-107">Clienttoken kann nicht aus der Nachricht gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="34548-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="34548-108">Clienttoken hat die Authentifizierung (z. B. ungültiges Kennwort) nicht bestanden.</span><span class="sxs-lookup"><span data-stu-id="34548-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="34548-109">Signaturüberprüfung ist fehlgeschlagen (die Nachricht wurde z. B. manipuliert).</span><span class="sxs-lookup"><span data-stu-id="34548-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="34548-110">Die Nachricht ist ein Duplikat einer vorherigen; dies kann während eines Replay-Angriffs geschehen.</span><span class="sxs-lookup"><span data-stu-id="34548-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="34548-111">Ein Entschlüsselungsfehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="34548-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="34548-112">Einige erforderliche Elemente (z. B. fehlender Timestamp oder verschlüsselter Datenblock) fehlen in der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="34548-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="34548-113">Während des TLSNEGO-/SPNEGO-Handshakes sind Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="34548-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="34548-114">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird:</span><span class="sxs-lookup"><span data-stu-id="34548-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="34548-115">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="34548-115">(N1-N0)/((D1-D0)/F)</span></span>
