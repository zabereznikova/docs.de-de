---
title: Sicherheitsaushandlung und Timeouts
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
author: BrucePerlerMS
ms.openlocfilehash: 6b6c9c6ed44eb3ebefb21f2fbff1e73171262ed7
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47194900"
---
# <a name="security-negotiation-and-timeouts"></a>Sicherheitsaushandlung und Timeouts
Wenn sich Clients und Diensten authentifizieren zu können, unterstützt Windows Communication Foundation (WCF) einen Modus, in dem die Dienstanmeldeinformationen im Rahmen der Authentifizierung ausgehandelt werden. In derartigen Szenarien erfolgt ein potenziell bilateraler Austausch zwischen Client und Dienst zur Weitergabe der Dienstanmeldeinformationen an den Client. Die <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>-Eigenschaft steuert die Dauer des bilateralen Austauschs. Dieses Timeout ist jedoch nur gültig, wenn der Austausch tatsächlich mehr erfordert als ein einzelnes Anforderung-Antwort-Paar. In Fällen, in denen die Aushandlung in einem einzelnen Roundtrip abgeschlossen wird, ist das Timeout nicht gültig.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
 [Vorgehensweise: Festlegen der maximalen Zeitdehnung (Uhrabweichung)](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
