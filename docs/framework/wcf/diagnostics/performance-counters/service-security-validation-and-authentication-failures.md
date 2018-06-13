---
title: 'Dienst: Sicherheitsvalidierung und Authentifizierungsfehler'
ms.date: 03/30/2017
ms.assetid: 55c98268-b1ad-459d-851b-25ef52248187
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: e160b014b7aa7586566073b800084d44be15ccaf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474401"
---
# <a name="service-security-validation-and-authentication-failures"></a><span data-ttu-id="65af9-102">Dienst: Sicherheitsvalidierung und Authentifizierungsfehler</span><span class="sxs-lookup"><span data-stu-id="65af9-102">Service: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="65af9-103">Indikatorname: Sicherheitsvalidierung und Authentifizierungsfehler</span><span class="sxs-lookup"><span data-stu-id="65af9-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="65af9-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65af9-104">Description</span></span>  
 <span data-ttu-id="65af9-105">Dieser Zähler wird jedes Mal inkrementiert, wenn eine Nachricht wegen eines Sicherheitsproblems abgelehnt wird, das nicht von dem Zähler "Nicht autorisierte Sicherheitsanrufe" abgedeckt wird.</span><span class="sxs-lookup"><span data-stu-id="65af9-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="65af9-106">Zu derartigen Problemen gehören:</span><span class="sxs-lookup"><span data-stu-id="65af9-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="65af9-107">Clienttoken kann nicht aus der Nachricht gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="65af9-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="65af9-108">Clienttoken hat die Authentifizierung (z. B. ungültiges Kennwort) nicht bestanden.</span><span class="sxs-lookup"><span data-stu-id="65af9-108">Client token has failed authentication (for example,, bad password).</span></span>  
  
-   <span data-ttu-id="65af9-109">Signaturüberprüfung ist fehlgeschlagen (die Nachricht wurde z. B. manipuliert).</span><span class="sxs-lookup"><span data-stu-id="65af9-109">Signature verification has failed (for example,, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="65af9-110">Die Nachricht ist ein Duplikat einer vorherigen; dies kann während eines Replay-Angriffs geschehen.</span><span class="sxs-lookup"><span data-stu-id="65af9-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="65af9-111">Ein Entschlüsselungsfehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="65af9-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="65af9-112">Einige erforderliche Elemente (z. B. fehlender Timestamp oder verschlüsselter Datenblock) fehlen in der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="65af9-112">Some required elements (for example,, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="65af9-113">Während des TLSNEGO-/SPNEGO-Handshakes sind Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="65af9-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
