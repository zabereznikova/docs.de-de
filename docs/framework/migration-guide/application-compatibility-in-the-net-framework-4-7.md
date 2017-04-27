---
title: "Anwendungskompatibilität in .NET Framework 4.7| Microsoft-Dokumentation"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility, .NET Framework
- application compatibility, .NET Framework 4.7
ms.assetid: 1d29b9b3-effd-41b9-b0a7-ef004f535ab6
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8880ae2f93e7dbfd681d79dfeb75e1baa484196a
ms.lasthandoff: 04/18/2017

---
# <a name="application-compatibility-in-the-net-framework-47"></a>Anwendungskompatibilität in .NET Framework 4.7
Dieses Thema enthält Links zu Informationen über Anwendungskompatibilitätsprobleme zwischen .NET Framework 4.6.2 und 4.7. Die Probleme sind in zwei Kategorien unterteilt:  
  
 [Änderungen zur Laufzeit](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-7.md)  
 Laufzeitänderungen betreffen alle Apps, die in .NET Framework 4.7 ausgeführt werden und die eine bestimmte Funktion verwenden.  
  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)  
 Neuausrichtungsänderungen können sich auf Apps auswirken, die für .NET Framework 4.7 neu kompiliert wurden. Dazu zählen:  
  
-   Änderungen in der Entwurfszeitumgebung. Beispielsweise können Buildtools Warnungen ausgeben, obwohl dies zuvor nicht der Fall war.  
  
-   Änderungen in der Laufzeitumgebung. Dies betrifft nur Apps, die speziell .NET Framework 4.7 als Ziel verwenden. Apps, die auf frühere Versionen von .NET Framework abzielen, verhalten sich so, als würden sie in diesen Versionen ausgeführt.  
  
In beiden Themen haben wir einzelne Elemente in folgender Weise nach den für sie erwarteten Auswirkungen klassifiziert:  
  
 Hauptversion  
 Dies ist eine wesentliche Änderung, die viele Apps beeinflusst oder erhebliche Änderungen des Codes erforderlich macht.  
  
 Minor  
 Dies ist eine Änderung, die eine kleine Anzahl von Apps beeinflusst oder geringfügige Änderungen des Codes erforderlich macht.  
  
 Grenzfall  
 Diese Änderung beeinflusst Apps nur in sehr spezifischen Szenarien, die nicht üblich sind.  
  
 Transparent  
 Diese Änderung hat keine nennenswerten Auswirkungen, die Entwickler oder Benutzer beachten müssten. Die App sollte keine Änderung benötigen.  
  
## <a name="see-also"></a>Siehe auch  
 [Versionen und Abhängigkeiten](~/docs/framework/migration-guide/versions-and-dependencies.md)   
 [Anwendungskompatibilität in 4.5](~/docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)      
 [Anwendungskompatibilität in 4.5.1](~/docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)   
 [Anwendungskompatibilität in 4.5.2](~/docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)   
 [Anwendungskompatibilität in 4.6](~/docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6.md)   
 [Anwendungskompatibilität in 4.6.1](~/docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)   
 [Anwendungskompatibilität in 4.6.2](~/docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)   
 [Anwendungskompatibilität](~/docs/framework/migration-guide/application-compatibility.md)    
   

