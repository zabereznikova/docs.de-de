---
title: "Anwendungskompatibilität in .NET Framework 4.5.2| Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- .NET Framework 4.5.2
- application compatibility,.NET Framework
- application compatibility,.NET Framework 4.5.2
ms.assetid: 4c6a029d-c565-4f25-b87b-b2361634bd74
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2631cb6c9464954b18cf97e21b8f48b30458c0db
ms.lasthandoff: 04/18/2017

---
# <a name="application-compatibility-in-the-net-framework-452"></a>Anwendungskompatibilität in .NET Framework 4.5.2
Dieses Thema enthält Links zu Informationen über Anwendungskompatibilitätsprobleme zwischen .NET Framework 4.5.1 und 4.5.2. Die Probleme sind in zwei Kategorien unterteilt:  
  
 [Änderungen zur Laufzeit](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-2.md)  
 Laufzeitänderungen betreffen alle Apps, die in .NET Framework 4.5.2 ausgeführt werden und die eine bestimmte Funktion verwenden.  
  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-5-2.md)  
 Neuausrichtungsänderungen können sich auf Apps auswirken, die für .NET Framework 4.5, 4.5.1 oder 4.5.2 neu kompiliert wurden. Dazu zählen:  
  
-   Änderungen in der Entwurfszeitumgebung. Beispielsweise können Buildtools Warnungen ausgeben, obwohl dies zuvor nicht der Fall war.  
  
-   Änderungen in der Laufzeitumgebung. Dies betrifft nur Apps, die speziell .NET Framework 4.5.2 als Ziel verwenden. Apps, die auf frühere Versionen von .NET Framework abzielen, verhalten sich so, als würden sie in diesen Versionen ausgeführt.  
  
 In den Themen, die die Laufzeitänderungen und Neuausrichtungsänderungen beschreiben, haben wir die einzelnen Punkte entsprechend ihrer erwarteten Auswirkung eingestuft:  
  
 Major  
 Dies ist eine wesentliche Änderung, die viele Apps beeinflusst oder erhebliche Änderungen des Codes erforderlich macht.  
  
 Minor  
 Dies ist eine Änderung, die eine kleine Anzahl von Apps beeinflusst oder geringfügige Änderungen des Codes erforderlich macht.  
  
 Grenzfall  
 Diese Änderung beeinflusst Apps nur in sehr spezifischen Szenarien, die nicht üblich sind.  
  
 Transparent  
 Diese Änderung hat keine nennenswerten Auswirkungen, die Entwickler oder Benutzer beachten müssten. Die App sollte keine Änderung benötigen.  
  
## <a name="see-also"></a>Siehe auch  
 [Versionen und Abhängigkeiten](../../../docs/framework/migration-guide/versions-and-dependencies.md)   
 [Anwendungskompatibilität](../../../docs/framework/migration-guide/application-compatibility.md)   
 [Anwendungskompatibilität in 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Anwendungskompatibilität in 4.5.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)
