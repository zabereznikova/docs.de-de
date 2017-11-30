---
title: Sicherheitsaushandlung und Timeouts
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: b4d0b2953a91040c37afe88d9499fd4be1970f31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="security-negotiation-and-timeouts"></a><span data-ttu-id="427bf-102">Sicherheitsaushandlung und Timeouts</span><span class="sxs-lookup"><span data-stu-id="427bf-102">Security Negotiation and Timeouts</span></span>
<span data-ttu-id="427bf-103">Bei der Authentifizierung von Clients und Diensten unterstützt [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] einen Modus, in dem die Dienstanmeldeinformationen im Rahmen der Authentifizierung ausgehandelt werden.</span><span class="sxs-lookup"><span data-stu-id="427bf-103">When clients and services authenticate, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] supports a mode where the service credential is negotiated as part of authentication.</span></span> <span data-ttu-id="427bf-104">In derartigen Szenarien erfolgt ein potenziell bilateraler Austausch zwischen Client und Dienst zur Weitergabe der Dienstanmeldeinformationen an den Client.</span><span class="sxs-lookup"><span data-stu-id="427bf-104">In such scenarios, a potentially multi-leg exchange occurs between the client and the service to propagate the service credential to the client.</span></span> <span data-ttu-id="427bf-105">Die <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>-Eigenschaft steuert die Dauer des bilateralen Austauschs.</span><span class="sxs-lookup"><span data-stu-id="427bf-105">The <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property controls how long the multi-leg exchange can take to complete.</span></span> <span data-ttu-id="427bf-106">Dieses Timeout ist jedoch nur gültig, wenn der Austausch tatsächlich mehr erfordert als ein einzelnes Anforderung-Antwort-Paar.</span><span class="sxs-lookup"><span data-stu-id="427bf-106">However, this timeout only applies if the exchange actually takes more that a single request-response.</span></span> <span data-ttu-id="427bf-107">In Fällen, in denen die Aushandlung in einem einzelnen Roundtrip abgeschlossen wird, ist das Timeout nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="427bf-107">In cases where the negotiation completes in a single round trip, the timeout does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="427bf-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="427bf-108">See Also</span></span>  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
 [<span data-ttu-id="427bf-109">Vorgehensweise: Festlegen einer Max Taktverschiebung</span><span class="sxs-lookup"><span data-stu-id="427bf-109">How to: Set a Max Clock Skew</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
