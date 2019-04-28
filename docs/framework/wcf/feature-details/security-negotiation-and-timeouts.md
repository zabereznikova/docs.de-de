---
title: Sicherheitsaushandlung und Timeouts
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
ms.openlocfilehash: a02c9d7b42eadf9a5ce9af8022fe292d6c23249c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61748290"
---
# <a name="security-negotiation-and-timeouts"></a><span data-ttu-id="beb82-102">Sicherheitsaushandlung und Timeouts</span><span class="sxs-lookup"><span data-stu-id="beb82-102">Security Negotiation and Timeouts</span></span>
<span data-ttu-id="beb82-103">Wenn sich Clients und Diensten authentifizieren zu können, unterstützt Windows Communication Foundation (WCF) einen Modus, in dem die Dienstanmeldeinformationen im Rahmen der Authentifizierung ausgehandelt werden.</span><span class="sxs-lookup"><span data-stu-id="beb82-103">When clients and services authenticate, Windows Communication Foundation (WCF) supports a mode where the service credential is negotiated as part of authentication.</span></span> <span data-ttu-id="beb82-104">In derartigen Szenarien erfolgt ein potenziell bilateraler Austausch zwischen Client und Dienst zur Weitergabe der Dienstanmeldeinformationen an den Client.</span><span class="sxs-lookup"><span data-stu-id="beb82-104">In such scenarios, a potentially multi-leg exchange occurs between the client and the service to propagate the service credential to the client.</span></span> <span data-ttu-id="beb82-105">Die <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>-Eigenschaft steuert die Dauer des bilateralen Austauschs.</span><span class="sxs-lookup"><span data-stu-id="beb82-105">The <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property controls how long the multi-leg exchange can take to complete.</span></span> <span data-ttu-id="beb82-106">Dieses Timeout ist jedoch nur gültig, wenn der Austausch tatsächlich mehr erfordert als ein einzelnes Anforderung-Antwort-Paar.</span><span class="sxs-lookup"><span data-stu-id="beb82-106">However, this timeout only applies if the exchange actually takes more that a single request-response.</span></span> <span data-ttu-id="beb82-107">In Fällen, in denen die Aushandlung in einem einzelnen Roundtrip abgeschlossen wird, ist das Timeout nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="beb82-107">In cases where the negotiation completes in a single round trip, the timeout does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beb82-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="beb82-108">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [<span data-ttu-id="beb82-109">Vorgehensweise: Festlegen der maximalen Zeitdehnung Uhrabweichung</span><span class="sxs-lookup"><span data-stu-id="beb82-109">How to: Set a Max Clock Skew</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
