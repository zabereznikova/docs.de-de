---
title: Netzwerkablaufverfolgung in .NET Framework
description: Hier erfahren Sie mehr über die Netzwerkablaufverfolgung im .NET Framework, die Informationen über den Aufruf von Methoden sowie den Netzwerkdatenverkehr für eine verwaltete Anwendung bereitstellt.
ms.date: 03/30/2017
helpviewer_keywords:
- debugging [.NET Framework], network tracing
- methods, network tracing
- Networking
- trace enabled debugging
- network tracing, about network tracing
- network tracing
- network, network tracing
- traffic tracing
- tracing [.NET Framework], network
- deploying applications [.NET Framework], network traffic
- capturing network traffic
- Internet, network tracing
- Network Resources
- output, network tracing
- method invocations
ms.assetid: e993b7c3-087f-45d8-9c02-9dded936d804
ms.openlocfilehash: c3c710d99c9597120b0c4d9674439a27c3bedfcc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261682"
---
# <a name="network-tracing-in-the-net-framework"></a>Netzwerkablaufverfolgung in .NET Framework

Die Netzwerkablaufverfolgung im .NET Framework bietet Zugriff auf Informationen über den Aufruf von Methoden sowie Informationen zu dem von einer Anwendung generierten Netzwerkdatenverkehr. Dies ist nützlich für das Debuggen bei der Anwendungsentwicklung und für die Analyse von bereitgestellten Anwendungen. Die bei der Netzwerkablaufverfolgung ausgegebenen Informationen können für verschiedene Szenarien bei der Entwicklung und in Produktionsumgebungen angepasst werden.  
  
 Um die Netzwerkablaufverfolgung in .NET Framework zu aktivieren, müssen Sie ein Ziel für die Ausgabe der Ablaufverfolgung auswählen und Konfigurationseinstellungen für die Ablaufverfolgung entweder der Anwendungs- oder der Computerkonfigurationsdatei hinzufügen. Beschreibungen von Konfigurationsdateien und ihrer Verwendung finden Sie unter [Konfigurationsdateien](../configure-apps/index.md). Informationen zur Aktivierung der Netzwerkablaufverfolgung finden Sie unter [Aktivieren der Netzwerkablaufverfolgung](enabling-network-tracing.md). Informationen zu den Einstellungen, die Sie der Konfigurationsdatei hinzufügen müssen, finden Sie unter [Vorgehensweise: Konfigurieren der Netzwerkablaufverfolgung](how-to-configure-network-tracing.md).  
  
 Wenn die Ablaufverfolgung aktiviert ist, können Sie Ablaufverfolgungsinformationen sammeln, die von **System.Net**-Klassen ausgegeben werden. Member der Netzwerklassen, die Ablaufverfolgungsinformationen generieren, enthalten den folgenden Text im Abschnitt "Hinweise" ihrer .NET Framework-Klassenbibliotheksdokumentation:  
  
> [!NOTE]
> Dieser Member gibt Ablaufverfolgungsinformationen aus, wenn Sie die Netzwerkablaufverfolgung in der Anwendung aktivieren. Weitere Informationen finden Sie unter "Netzwerkablaufverfolgung".  
  
## <a name="see-also"></a>Siehe auch

- [Aktivieren der Netzwerkablaufverfolgung](enabling-network-tracing.md)
- [How to: Konfigurieren der Netzwerkablaufverfolgung](how-to-configure-network-tracing.md)
- [Interpretieren von Netzwerkablaufverfolgung](interpreting-network-tracing.md)
- [Ablaufverfolgung und Instrumentieren von Anwendungen](../debug-trace-profile/tracing-and-instrumenting-applications.md)
