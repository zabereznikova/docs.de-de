---
title: 'Endpunkt: Sicherheitsvalidierung und Authentifizierungsfehler'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5bad60aa-6084-4c7b-aefd-9b581f04382e
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 7d1f05ddc4b0fcf93c87e69932f860f3c7e2ff85
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-security-validation-and-authentication-failures"></a><span data-ttu-id="74f19-102">Endpunkt: Sicherheitsvalidierung und Authentifizierungsfehler</span><span class="sxs-lookup"><span data-stu-id="74f19-102">Endpoint: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="74f19-103">Indikatorname: Sicherheitsvalidierung und Authentifizierungsfehler</span><span class="sxs-lookup"><span data-stu-id="74f19-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="74f19-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74f19-104">Description</span></span>  
 <span data-ttu-id="74f19-105">Dieser Zähler wird jedes Mal inkrementiert, wenn eine Nachricht wegen eines Sicherheitsproblems abgelehnt wird, das nicht von dem Zähler "Nicht autorisierte Sicherheitsanrufe" abgedeckt wird.</span><span class="sxs-lookup"><span data-stu-id="74f19-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="74f19-106">Zu derartigen Problemen gehören:</span><span class="sxs-lookup"><span data-stu-id="74f19-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="74f19-107">Clienttoken kann nicht aus der Nachricht gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="74f19-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="74f19-108">Clienttoken hat die Authentifizierung nicht bestanden (ungültiges Kennwort).</span><span class="sxs-lookup"><span data-stu-id="74f19-108">Client token has failed authentication (bad password).</span></span>  
  
-   <span data-ttu-id="74f19-109">Signaturprüfung ist fehlgeschlagen (die Nachricht wurde manipuliert).</span><span class="sxs-lookup"><span data-stu-id="74f19-109">Signature verification has failed (the message has been tampered).</span></span>  
  
-   <span data-ttu-id="74f19-110">Die Nachricht ist ein Duplikat einer vorherigen; dies kann während eines Replay-Angriffs geschehen.</span><span class="sxs-lookup"><span data-stu-id="74f19-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="74f19-111">Ein Entschlüsselungsfehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="74f19-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="74f19-112">Einige erforderliche Elemente (fehlender Timestamp oder verschlüsselter Datenblock) fehlen in der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="74f19-112">Some required elements (missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="74f19-113">Während des TLSNEGO-/SPNEGO-Handshakes sind Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="74f19-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
