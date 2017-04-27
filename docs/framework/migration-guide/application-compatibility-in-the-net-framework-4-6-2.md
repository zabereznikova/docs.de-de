---
title: "Anwendungskompatibilität in .NET Framework 4.6.2| Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility,.NET Framework
- application compatibility,.NET Framework 4,6,2
ms.assetid: bdb8335a-a63f-43bb-b978-c1ee92870033
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e34651e87e9c1ccc58472910c0340987da7fc973
ms.lasthandoff: 04/18/2017

---
# <a name="application-compatibility-in-the-net-framework-462"></a>Anwendungskompatibilität in .NET Framework 4.6.2
Dieses Thema enthält Links zu Informationen über Anwendungskompatibilitätsprobleme zwischen .NET Framework 4.6.1 und 4.6.2. Die Probleme sind in zwei Kategorien unterteilt:  
  
 [Änderungen zur Laufzeit](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6-2.md)  
 Laufzeitänderungen beeinflussen alle Apps, die in [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgeführt werden und die eine bestimmte Funktion verwenden.  
  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)  
 Änderungen durch Neuausrichtung beeinflussen Apps, die für [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] neu kompiliert wurden. Dazu zählen:  
  
-   Änderungen in der Entwurfszeitumgebung. Beispielsweise können Buildtools Warnungen ausgeben, obwohl dies zuvor nicht der Fall war.  
  
-   Änderungen in der Laufzeitumgebung. Diese betreffen nur Apps, die speziell auf [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] abzielen. Apps, die auf frühere Versionen von .NET Framework abzielen, verhalten sich so, als würden sie in diesen Versionen ausgeführt.  
  
 In dem Thema, das Neuzuweisungsänderungen beschreibt, haben wir die einzelnen Punkte entsprechend ihrer erwarteten Auswirkung eingestuft:  
  
 Hauptversion  
 Dies ist eine wesentliche Änderung, die viele Apps beeinflusst oder erhebliche Änderungen des Codes erforderlich macht.  
  
 Minor  
 Dies ist eine Änderung, die eine kleine Anzahl von Apps beeinflusst oder geringfügige Änderungen des Codes erforderlich macht.  
  
 Grenzfall  
 Diese Änderung beeinflusst Apps nur in sehr spezifischen Szenarien, die nicht üblich sind.  
  
 Transparent  
 Diese Änderung hat keine nennenswerten Auswirkungen, die Entwickler oder Benutzer beachten müssten. Die App sollte keine Änderung benötigen.  
  
## <a name="see-also"></a>Siehe auch  
 [Versionen und Abhängigkeiten](../../../docs/framework/migration-guide/versions-and-dependencies.md)   
 [Anwendungskompatibilität in 4.5.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)   
 [Anwendungskompatibilität in 4.5.2](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)   
 [Anwendungskompatibilität in 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Anwendungskompatibilität in 4.6](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6.md)   
 [Anwendungskompatibilität in 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)   
 [Anwendungskompatibilität](../../../docs/framework/migration-guide/application-compatibility.md)   
 [.NET 4.6.2 – Liste der Änderungen auf GitHub](http://go.microsoft.com/fwlink/?LinkId=708778)
 
