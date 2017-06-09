---
title: "Anwendungskompatibilit&#228;t in .NET Framework 4.6 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7a3fd352-a8ba-4f9a-8250-951f2c994248
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Anwendungskompatibilit&#228;t in .NET Framework 4.6
Dieses Thema enthält Links zu Informationen über Anwendungskompatibilitätsprobleme zwischen .NET Framework 4.5.2 und 4.6.  Die Probleme sind in zwei Kategorien unterteilt:  
  
 [Laufzeitänderungen](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)  
 Laufzeitänderungen beeinflussen alle Apps, die in [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] ausgeführt werden und die eine bestimmte Funktion verwenden.  
  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)  
 Neuausrichtungsänderungen können sich auf Apps auswirken, die für .NET Framework 4.5, 4.5.1, 4.5.2 oder 4.6 neu kompiliert wurden.  Dazu zählen:  
  
-   Änderungen in der Entwurfszeitumgebung.  Beispielsweise können Buildtools Warnungen ausgeben, obwohl dies zuvor nicht der Fall war.  
  
-   Änderungen in der Laufzeitumgebung.  Diese betreffen nur Apps, die speziell auf [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] abzielen.  Apps, die auf frühere Versionen von .NET Framework abzielen, verhalten sich so, als würden sie in diesen Versionen ausgeführt.  
  
 In den Themen, die die Laufzeitänderungen und Neuausrichtungsänderungen beschreiben, haben wir die einzelnen Punkte entsprechend ihrer erwarteten Auswirkung eingestuft:  
  
 Major  
 Dies ist eine wesentliche Änderung, die viele Apps beeinflusst oder erhebliche Änderungen des Codes erforderlich macht.  
  
 Minor  
 Dies ist eine Änderung, die eine kleine Anzahl von Apps beeinflusst oder geringfügige Änderungen des Codes erforderlich macht.  
  
 Grenzfall  
 Diese Änderung beeinflusst Apps nur in sehr spezifischen Szenarien, die nicht üblich sind.  
  
 Transparent  
 Diese Änderung hat keine nennenswerten Auswirkungen, die Entwickler oder Benutzer beachten müssten.  Die App sollte keine Änderung benötigen.  
  
## Siehe auch  
 [Versionen und Abhängigkeiten](../../../docs/framework/migration-guide/versions-and-dependencies.md)   
 [Anwendungskompatibilität](../../../docs/framework/migration-guide/application-compatibility.md)   
 [Anwendungskompatibilität in 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Anwendungskompatibilität in 4.5.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)   
 [Anwendungskompatibilität in 4.5.2](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)