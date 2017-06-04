---
title: "Netzwerkablaufverfolgung in .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Erfassen von Netzwerkdatenverkehr"
  - "Debuggen [.NET Framework], Netzwerkablaufverfolgung"
  - "Bereitstellen von Anwendungen [.NET Framework], Netzwerkdatenverkehr"
  - "Internet, Netzwerkablaufverfolgung"
  - "Methodenaufrufe"
  - "Methoden, Netzwerkablaufverfolgung"
  - "Netzwerkressourcen"
  - "Netzwerkablaufverfolgung"
  - "Netzwerkablaufverfolgung, Info zu Netzwerkablaufverfolgung"
  - "Netzwerk, Netzwerkablaufverfolgung"
  - "Netzwerk"
  - "Ausgabe, Netzwerkablaufverfolgung"
  - "Debuggen mit aktivierter Ablaufverfolgung"
  - "Ablaufverfolgung [.NET Framework], Netzwerk"
  - "Datenverkehr-Ablaufverfolgung"
ms.assetid: e993b7c3-087f-45d8-9c02-9dded936d804
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Netzwerkablaufverfolgung in .NET Framework
Die Netzwerkablaufverfolgung im .NET Framework bietet Zugriff auf Informationen über den Aufruf von Methoden sowie Informationen zu dem von einer Anwendung generierten Netzwerkdatenverkehr.  Dies ist nützlich für das Debuggen bei der Anwendungsentwicklung und für die Analyse von bereitgestellten Anwendungen.  Die bei der Netzwerkablaufverfolgung ausgegebenen Informationen können für verschiedene Szenarien bei der Entwicklung und in Produktionsumgebungen angepasst werden.  
  
 Um die Netzwerkablaufverfolgung in .NET Framework zu aktivieren, müssen Sie ein Ziel für die Ausgabe der Ablaufverfolgung auswählen und Konfigurationseinstellungen für die Ablaufverfolgung entweder der Anwendungs\- oder der Computerkonfigurationsdatei hinzufügen.  Beschreibungen von Konfigurationsdateien und ihrer Verwendung finden Sie unter [Konfigurationsdateien](../../../docs/framework/configure-apps/index.md).  Informationen über die Aktivierung der Netzwerkablaufverfolgung finden Sie unter [Aktivieren der Netzwerkablaufverfolgung](../../../docs/framework/network-programming/enabling-network-tracing.md).  Informationen zu den Einstellungen, die Sie der Konfigurationsdatei hinzufügen müssen, finden Sie unter [Gewusst wie: Konfigurieren der Netzwerkablaufverfolgung](../../../docs/framework/network-programming/how-to-configure-network-tracing.md).  
  
 Wenn die Ablaufverfolgung aktiviert ist, können Sie Ablaufverfolgungsinformationen sammeln, die von **System.Net**\-Klassen ausgegeben werden.  Member der Netzwerklassen, die Ablaufverfolgungsinformationen generieren, enthalten den folgenden Text im Abschnitt "Hinweise" ihrer .NET Framework\-Klassenbibliotheksdokumentation:  
  
> [!NOTE]
>  Dieser Member gibt Ablaufverfolgungsinformationen aus, wenn Sie die Netzwerkablaufverfolgung in der Anwendung aktivieren.  Weitere Informationen finden Sie unter "Netzwerkablaufverfolgung".  
  
## Siehe auch  
 [Aktivieren der Netzwerkablaufverfolgung](../../../docs/framework/network-programming/enabling-network-tracing.md)   
 [Gewusst wie: Konfigurieren Sie Netzwerkablaufverfolgung](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)   
 [Interpretieren von Netzwerkablaufverfolgung](../../../docs/framework/network-programming/interpreting-network-tracing.md)   
 [Introduction to Instrumentation and Tracing](http://msdn.microsoft.com/de-de/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)