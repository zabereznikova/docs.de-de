---
title: "Anwendungskompatibilität in .NET Framework 4.5.1| Microsoft-Dokumentation"
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
- application compatibility,.NET Framework 4.5.1
- application compatibility,.NET Framework
ms.assetid: 2b07b729-e2bf-4925-8b83-9c9ee6c48612
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9f90929c7181e5a615b9c7fb757c49367f40bc85
ms.lasthandoff: 04/18/2017

---
# <a name="application-compatibility-in-the-net-framework-451"></a>Anwendungskompatibilität in .NET Framework 4.5.1
Dieses Thema enthält Links zu Informationen über Anwendungskompatibilitätsprobleme zwischen .NET Framework 4.5 und 4.5.1. Die Probleme sind in zwei Kategorien unterteilt:  
  
 [Laufzeitänderungen](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)  
 Laufzeitänderungen beeinflussen alle Apps, die in [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] ausgeführt werden und die eine bestimmte Funktion verwenden.  
  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-5-1.md)  
 Änderungen durch Neuausrichtung beeinflussen Apps, die für [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] neu kompiliert wurden. Dazu zählen:  
  
-   Änderungen in der Entwurfszeitumgebung. Beispielsweise können Buildtools Warnungen ausgeben, obwohl dies zuvor nicht der Fall war.  
  
-   Änderungen in der Laufzeitumgebung. Diese betreffen nur Apps, die speziell auf [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] abzielen. Apps, die auf frühere Versionen von .NET Framework abzielen, verhalten sich so, als würden sie in diesen Versionen ausgeführt.  
  
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
 [Anwendungskompatibilität in 4.5.2](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)
