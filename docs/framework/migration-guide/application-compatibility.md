---
title: "Anwendungskompatibilität im .NET Framework"
ms.custom: 
ms.date: 05/19/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
- app-compat
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- .NET Framework application compatibility
- .NET Framework changes
caps.latest.revision: "19"
ms.assetid: c4ba3ff2-fe59-4c5d-9e0b-86bba3cd865c
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e67fff19c4b187010b35519081f46e11effbad6c
ms.sourcegitcommit: d0f7646d67db5809cf43ff1d27b399a4020e8ee2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2017
---
# <a name="application-compatibility-in-the-net-framework"></a>Anwendungskompatibilität im .NET Framework

## <a name="introduction"></a>Einführung
Kompatibilität ist ein wichtiges Ziel jedes .NET-Release. Durch Kompatibilität wird sichergestellt, dass jede Version additiv ist; frühere Versionen funktionieren also weiterhin. Auf der anderen Seite können Änderungen an früheren Versionen (zur Leistungssteigerung, Beheben von Sicherheitsproblemen oder Fehlerbehebungen) zu Kompatibilitätsproblemen im vorhandenen Code oder Anwendungen führen, die unter einer späteren Version ausgeführt werden. .NET Framework erkennt Änderungen der Neuzuweisung und Laufzeitänderungen. Die Neuzuweisung von Änderungen beeinflussen Anwendungen, die auf eine bestimmte .NET Framework-Version abzielen, aber auf einer höheren Version ausgeführt werden. Laufzeitänderungen betreffen alle Anwendungen, die auf einer bestimmten Version ausgeführt werden.

Jede App hat eine bestimmte Version von .NET Framework als Ziel, die durch Folgendes angegeben werden kann:

* Definieren eines Zielframeworks in Visual Studio
* Angeben des Zielframeworks in einer Projektdatei
* Anwenden einer <xref:System.Runtime.Versioning.TargetFrameworkAttribute> auf dem Quellcode

Wenn .NET Framework auf einer neueren Version anstatt auf der beabsichtigten ausgeführt wird, wird ein besonderes Verhalten angewendet, um die ältere Zielversion zu imitieren. Anders ausgedrückt: Die App wird auf der neueren Version des Framework ausgeführt, sich aber so verhalten, als würde sie auf der älteren Version ausgeführt werden. Viele Kompatibilitätsprobleme zwischen den .NET Framework-Versionen werden durch dieses besondere Modell minimiert.

## <a name="runtime-changes"></a>Laufzeitänderungen

Laufzeitprobleme tauchen auf, wenn eine neue Laufzeit auf einem Gerät bereitgestellt wird und wenn die gleichen Binärdateien ausgeführt werden, es jedoch zu anderem Verhalten kommt. Wenn eine Binärdatei für .NET Framework 4.0 kompiliert wurde, wird Sie im .NET Framework 4.0-Kompatibilitätsmodus auf 4.5 oder späteren Versionen ausgeführt. Viele Änderungen, die 4.5 betreffen, werden für 4.0 kompilierte Binärdateien nicht betreffen. Dies ist spezifisch für AppDomain und ist von den Einstellungen der Einstiegsassembly abhängig.

## <a name="retargeting-changes"></a>Neuausrichtungsänderungen

Probleme bei der Neuzuweisung erscheinen, wenn eine Assembly, die ursprünglich 4.0 angepeilt hat, nun 4.5 als Ziel hat. Die Assembly wählt nun die neuen Funktionen sowie die potenziellen Kompatibilitätsprobleme für alte Funktionen. Dies wird erneut von der Einstiegsassembly bestimmt, also von der Konsolen-App, die die Assembly verwendet oder der Website, die auf die Assembly verweist.

## <a name="net-compatibility-diagnostics"></a>Diagnose der .NET-Kompatibilität

Die Diagnose der .NET Kompatibilität umfasst von Roslyn unterstützte Analyzer, die bei der Erkennung von Anwendungskompatibilitätsproblemen zwischen .NET Framework-Versionen helfen. Diese Liste enthält alle verfügbaren Analyzer, obwohl nur eine Teilmenge auf eine bestimmte Migration angewendet werden kann. Die Analyzer ermitteln, welche Probleme auf die geplante Migration zutreffen und beschreibt diese nur kurz.

Jedes Problem umfasst die folgenden Informationen:

-   Die Beschreibung der Änderungen von einer früheren Version.

-   Wie sich die Änderung auf Kunden auswirkt und ob Problemumgehungen verfügbar sind, um die Kompatibilität zwischen Versionen beizubehalten.

-   Eine Bewertung der Bedeutung der Änderung. Anwendungskompatibilitätsprobleme werden wie folgt kategorisiert:

    |   |   |
    |---|---|
    |Hauptversion|Eine wesentliche Änderung, die eine große Anzahl von Apps beeinflusst oder erhebliche Änderungen des Codes erforderlich macht.|
    |Nebenversion|Eine Änderung, die eine kleine Anzahl von Apps beeinflusst oder geringfügige Änderungen des Codes erforderlich macht.|
    |Grenzfall|Eine Änderung, die nur Apps in sehr spezifischen, nicht üblichen Szenarien beeinflusst.|
    |Transparent|Eine Änderung ohne nennenswerte Auswirkungen auf die Entwickler oder Benutzer der Anwendung.|

-   Die Version gibt an, wann die Änderung zum ersten Mal im Framework auftritt. Einige der Änderungen werden in einer bestimmten Version eingeführt und in einer späteren Version zurückgesetzt; dies wird ebenso beschrieben.

-   Art der Änderung:

    |   |   |
    |---|---|
    |Neuzuweisung|Die Änderung wirkt sich auf Apps aus, die neu kompiliert werden, um auf eine neue Version von .NET Framework ausgerichtet zu werden.|
    |Laufzeit|Die Änderung wirkt sich auf eine vorhandene Anwendung aus, die auf eine frühere Version von .NET Framework ausgerichtet ist, aber unter einer höheren Version ausgeführt wird.|

-   Die betroffenen APIs, falls vorhanden.

-   Die IDs der verfügbaren Diagnosen.

## <a name="usage"></a>Verwendung
Um zu starten, wählen Sie unten den Typ der Kompatibilitätsänderung aus:

* [Neuausrichtungsänderungen](./retargeting/index.md)
* [Änderungen zur Laufzeit](./runtime/index.md)


## <a name="see-also"></a>Siehe auch

* [Versionen und Abhängigkeiten](../../../docs/framework/migration-guide/versions-and-dependencies.md)
* [Neuigkeiten](../../../docs/framework/whats-new/index.md)
* [Veraltete Elemente in der Klassenbibliothek](../../../docs/framework/whats-new/whats-obsolete.md)
