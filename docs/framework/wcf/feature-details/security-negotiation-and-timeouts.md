---
title: Sicherheitsaushandlung und Timeouts
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
ms.openlocfilehash: 38dce9bd6587850a5e3327600bb8bc13c48b93e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592613"
---
# <a name="security-negotiation-and-timeouts"></a>Sicherheitsaushandlung und Timeouts
Wenn sich Clients und Diensten authentifizieren zu können, unterstützt Windows Communication Foundation (WCF) einen Modus, in dem die Dienstanmeldeinformationen im Rahmen der Authentifizierung ausgehandelt werden. In derartigen Szenarien erfolgt ein potenziell bilateraler Austausch zwischen Client und Dienst zur Weitergabe der Dienstanmeldeinformationen an den Client. Die <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>-Eigenschaft steuert die Dauer des bilateralen Austauschs. Dieses Timeout ist jedoch nur gültig, wenn der Austausch tatsächlich mehr erfordert als ein einzelnes Anforderung-Antwort-Paar. In Fällen, in denen die Aushandlung in einem einzelnen Roundtrip abgeschlossen wird, ist das Timeout nicht gültig.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [Vorgehensweise: Festlegen der maximalen Zeitdehnung Uhrabweichung](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
