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
# <a name="security-negotiation-and-timeouts"></a>Sicherheitsaushandlung und Timeouts
Bei der Authentifizierung von Clients und Diensten unterstützt Windows Communication Foundation (WCF) einen Modus, in dem die Dienst Anmelde Informationen als Teil der Authentifizierung ausgehandelt werden. In derartigen Szenarien erfolgt ein potenziell bilateraler Austausch zwischen Client und Dienst zur Weitergabe der Dienstanmeldeinformationen an den Client. Die <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>-Eigenschaft steuert die Dauer des bilateralen Austauschs. Dieses Timeout ist jedoch nur gültig, wenn der Austausch tatsächlich mehr erfordert als ein einzelnes Anforderung-Antwort-Paar. In Fällen, in denen die Aushandlung in einem einzelnen Roundtrip abgeschlossen wird, ist das Timeout nicht gültig.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [Vorgehensweise: Festlegen der maximalen Zeitdehnung (Uhrabweichung)](how-to-set-a-max-clock-skew.md)
