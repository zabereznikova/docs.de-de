---
title: Sicherheitsvalidierung und Authentifizierungsfehler
ms.date: 03/30/2017
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
ms.openlocfilehash: 32a7d41f93dd99f1950a073e1cac1b62177ff6c3
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185874"
---
# <a name="security-validation-and-authentication-failures"></a><span data-ttu-id="d4a8b-102">Sicherheitsvalidierung und Authentifizierungsfehler</span><span class="sxs-lookup"><span data-stu-id="d4a8b-102">Security Validation and Authentication Failures</span></span>
<span data-ttu-id="d4a8b-103">Indikatorname: Sicherheitsvalidierung und Authentifizierungsfehler</span><span class="sxs-lookup"><span data-stu-id="d4a8b-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="d4a8b-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4a8b-104">Description</span></span>  
 <span data-ttu-id="d4a8b-105">Dieser Zähler wird jedes Mal inkrementiert, wenn eine Nachricht wegen eines Sicherheitsproblems abgelehnt wird, das nicht von dem Zähler "Nicht autorisierte Sicherheitsanrufe" abgedeckt wird.</span><span class="sxs-lookup"><span data-stu-id="d4a8b-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="d4a8b-106">Zu derartigen Problemen gehören:</span><span class="sxs-lookup"><span data-stu-id="d4a8b-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="d4a8b-107">Clienttoken kann nicht aus der Nachricht gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="d4a8b-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="d4a8b-108">Clienttoken hat die Authentifizierung (z. B. ungültiges Kennwort) nicht bestanden.</span><span class="sxs-lookup"><span data-stu-id="d4a8b-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="d4a8b-109">Signaturüberprüfung ist fehlgeschlagen (die Nachricht wurde z. B. manipuliert).</span><span class="sxs-lookup"><span data-stu-id="d4a8b-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="d4a8b-110">Die Nachricht ist ein Duplikat einer vorherigen; dies kann während eines Replay-Angriffs geschehen.</span><span class="sxs-lookup"><span data-stu-id="d4a8b-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="d4a8b-111">Ein Entschlüsselungsfehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d4a8b-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="d4a8b-112">Einige erforderliche Elemente (z. B. fehlender Timestamp oder verschlüsselter Datenblock) fehlen in der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="d4a8b-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="d4a8b-113">Während des TLSNEGO-/SPNEGO-Handshakes sind Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d4a8b-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
