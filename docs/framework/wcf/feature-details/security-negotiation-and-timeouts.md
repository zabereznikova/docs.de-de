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
ms.workload: dotnet
ms.openlocfilehash: 6fbee18d31cb1774300c14587b0f7d973a4996ed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="security-negotiation-and-timeouts"></a>Sicherheitsaushandlung und Timeouts
Bei der Authentifizierung von Clients und Diensten unterstützt [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] einen Modus, in dem die Dienstanmeldeinformationen im Rahmen der Authentifizierung ausgehandelt werden. In derartigen Szenarien erfolgt ein potenziell bilateraler Austausch zwischen Client und Dienst zur Weitergabe der Dienstanmeldeinformationen an den Client. Die <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>-Eigenschaft steuert die Dauer des bilateralen Austauschs. Dieses Timeout ist jedoch nur gültig, wenn der Austausch tatsächlich mehr erfordert als ein einzelnes Anforderung-Antwort-Paar. In Fällen, in denen die Aushandlung in einem einzelnen Roundtrip abgeschlossen wird, ist das Timeout nicht gültig.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
 [Vorgehensweise: Festlegen der maximalen Zeitdehnung (Uhrabweichung)](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
