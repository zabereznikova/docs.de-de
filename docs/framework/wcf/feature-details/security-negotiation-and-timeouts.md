---
title: Sicherheitsaushandlung und Timeouts
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
ms.openlocfilehash: 1b5fb15b4ea00ba33b741c96bcb423aefe9890fa
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600996"
---
# <a name="security-negotiation-and-timeouts"></a><span data-ttu-id="243b8-102">Sicherheitsaushandlung und Timeouts</span><span class="sxs-lookup"><span data-stu-id="243b8-102">Security Negotiation and Timeouts</span></span>
<span data-ttu-id="243b8-103">Bei der Authentifizierung von Clients und Diensten unterstützt Windows Communication Foundation (WCF) einen Modus, in dem die Dienst Anmelde Informationen als Teil der Authentifizierung ausgehandelt werden.</span><span class="sxs-lookup"><span data-stu-id="243b8-103">When clients and services authenticate, Windows Communication Foundation (WCF) supports a mode where the service credential is negotiated as part of authentication.</span></span> <span data-ttu-id="243b8-104">In derartigen Szenarien erfolgt ein potenziell bilateraler Austausch zwischen Client und Dienst zur Weitergabe der Dienstanmeldeinformationen an den Client.</span><span class="sxs-lookup"><span data-stu-id="243b8-104">In such scenarios, a potentially multi-leg exchange occurs between the client and the service to propagate the service credential to the client.</span></span> <span data-ttu-id="243b8-105">Die <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>-Eigenschaft steuert die Dauer des bilateralen Austauschs.</span><span class="sxs-lookup"><span data-stu-id="243b8-105">The <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property controls how long the multi-leg exchange can take to complete.</span></span> <span data-ttu-id="243b8-106">Dieses Timeout ist jedoch nur gültig, wenn der Austausch tatsächlich mehr erfordert als ein einzelnes Anforderung-Antwort-Paar.</span><span class="sxs-lookup"><span data-stu-id="243b8-106">However, this timeout only applies if the exchange actually takes more that a single request-response.</span></span> <span data-ttu-id="243b8-107">In Fällen, in denen die Aushandlung in einem einzelnen Roundtrip abgeschlossen wird, ist das Timeout nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="243b8-107">In cases where the negotiation completes in a single round trip, the timeout does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="243b8-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="243b8-108">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [<span data-ttu-id="243b8-109">Vorgehensweise: Festlegen der maximalen Zeitdehnung (Uhrabweichung)</span><span class="sxs-lookup"><span data-stu-id="243b8-109">How to: Set a Max Clock Skew</span></span>](how-to-set-a-max-clock-skew.md)
