---
title: 'Dienst: Sicherheitsvalidierung und Authentifizierungsfehler'
ms.date: 03/30/2017
ms.assetid: 55c98268-b1ad-459d-851b-25ef52248187
ms.openlocfilehash: 399249926bcb1383fd33f60510c2c212c6f4261c
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204578"
---
# <a name="service-security-validation-and-authentication-failures"></a><span data-ttu-id="97ee6-102">Dienst: Sicherheitsvalidierung und Authentifizierungsfehler</span><span class="sxs-lookup"><span data-stu-id="97ee6-102">Service: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="97ee6-103">Indikatorname: Sicherheitsvalidierung und Authentifizierungsfehler</span><span class="sxs-lookup"><span data-stu-id="97ee6-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="97ee6-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="97ee6-104">Description</span></span>  
 <span data-ttu-id="97ee6-105">Dieser Zähler wird jedes Mal inkrementiert, wenn eine Nachricht wegen eines Sicherheitsproblems abgelehnt wird, das nicht von dem Zähler "Nicht autorisierte Sicherheitsanrufe" abgedeckt wird.</span><span class="sxs-lookup"><span data-stu-id="97ee6-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="97ee6-106">Zu derartigen Problemen gehören:</span><span class="sxs-lookup"><span data-stu-id="97ee6-106">Such problems include:</span></span>  
  
- <span data-ttu-id="97ee6-107">Clienttoken kann nicht aus der Nachricht gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="97ee6-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="97ee6-108">Clienttoken hat die Authentifizierung (z. B. ungültiges Kennwort) nicht bestanden.</span><span class="sxs-lookup"><span data-stu-id="97ee6-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="97ee6-109">Signaturüberprüfung ist fehlgeschlagen (die Nachricht wurde z. B. manipuliert).</span><span class="sxs-lookup"><span data-stu-id="97ee6-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="97ee6-110">Die Nachricht ist ein Duplikat einer vorherigen; dies kann während eines Replay-Angriffs geschehen.</span><span class="sxs-lookup"><span data-stu-id="97ee6-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="97ee6-111">Ein Entschlüsselungsfehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="97ee6-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="97ee6-112">Einige erforderliche Elemente (z. B. fehlender Timestamp oder verschlüsselter Datenblock) fehlen in der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="97ee6-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="97ee6-113">Während des TLSNEGO-/SPNEGO-Handshakes sind Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="97ee6-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
