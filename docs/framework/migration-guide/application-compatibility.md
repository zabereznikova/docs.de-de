---
title: Änderungen der Runtime und Neuausrichtung in .NET Framework
ms.date: 10/29/2019
helpviewer_keywords:
- application compatibility
- .NET Framework application compatibility
- .NET Framework changes
ms.assetid: c4ba3ff2-fe59-4c5d-9e0b-86bba3cd865c
ms.openlocfilehash: c46f781d495b87a4f24e77935df7c4814c8567ae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73196696"
---
# <a name="application-compatibility-in-the-net-framework"></a>Anwendungskompatibilität in .NET Framework

Kompatibilität ist ein wichtiges Ziel jedes .NET-Release. Durch die Kompatibilität wird sichergestellt, dass jede Version additiv ist. Frühere Versionen funktionieren also weiterhin. Andererseits können Änderungen an früheren Versionen (z. B. zur Leistungssteigerung, Beheben von Sicherheitsproblemen oder Fehlerbehebungen) zu Kompatibilitätsproblemen im vorhandenen Code oder Anwendungen führen, die unter einer späteren Version ausgeführt werden.

Jede App wird wie folgt auf eine spezifische Version von .NET Framework ausgerichtet:

- Definieren eines Zielframeworks in Visual Studio
- Angeben des Zielframeworks in einer Projektdatei
- Anwenden einer <xref:System.Runtime.Versioning.TargetFrameworkAttribute> auf dem Quellcode

Bei der Migration von einer Version von .NET Framework zu einer anderen gibt es zwei Arten von Änderungen, die Sie berücksichtigen sollten:

- [Laufzeitänderungen](#runtime-changes)
- [Neuausrichtungsänderungen](#retargeting-changes)

## <a name="runtime-changes"></a>Laufzeitänderungen

Probleme mit der Runtime treten auf, wenn eine neue Runtime auf einem Computer platziert wird und sich das Verhalten einer App ändert. Wenn eine neuere Version als die Zielversion ausgeführt wird, nutzt .NET Framework ein *besonderes* Verhalten, um die ältere Zielversion zu imitieren. Die App wird in der neueren Version ausgeführt, fungiert jedoch, als würde sie in der älteren Version ausgeführt werden. Viele Kompatibilitätsprobleme zwischen den .NET Framework-Versionen werden durch dieses besondere Modell minimiert. Wenn eine Binärdatei beispielsweise für .NET Framework 4.0 kompiliert wurde, aber auf einem Computer mit .NET Framework 4.5 oder höher ausgeführt wird, wird sie im .NET Framework 4.0-Kompatibilitätsmodus ausgeführt. Das heißt, dass viele der Änderungen der neueren Version sich nicht auf die Binärdatei auswirken.

Die Version von .NET Framework, für die eine Anwendung ausgerichtet ist, wird durch die Zielversion der Einstiegsassembly für die Anwendungsdomäne bestimmt, in der der Code ausgeführt wird. Alle zusätzlichen in dieser Anwendungsdomäne geladenen Assemblys sind für diese Version ausgelegt. Beispielsweise entspricht die Zielversion bei einer ausführbaren Datei dem Kompatibilitätsmodus aller Assemblys, die in der Anwendungsdomäne ausgeführt werden.

Sie können eine Liste der Runtimeänderungen anzeigen, die für Ihre Umgebung gelten, indem Sie Ihre aktuelle .NET Framework-Zielversion und dann die Version auswählen, zu der Sie migrieren möchten:

[!INCLUDE[versionselector](../../../includes/migration-guide/runtime/versionselector.md)]

## <a name="retargeting-changes"></a>Neuausrichtungsänderungen

Neuausrichtungsänderungen beziehen sich auf Änderungen, die auftreten, wenn eine Assembly für eine neuere Zielversion neu kompiliert wird. Das Verwenden einer neuen Zielversion bedeutet, dass die Assembly die neuen Features verwendet und möglicherweise potenzielle Kompatibilitätsprobleme für alte Features auftreten.

Sie können eine Liste der Neuausrichtungsänderungen anzeigen, die für Ihre Umgebung gelten, indem Sie Ihre aktuelle .NET Framework-Zielversion und dann die Version auswählen, zu der Sie migrieren möchten:

[!INCLUDE[versionselector](../../../includes/migration-guide/retargeting/versionselector.md)]

## <a name="impact-classification"></a>Klassifizierung der Auswirkungen

In den Artikeln, in denen die Runtime- und Neuausrichtungsänderungen beschrieben werden, z. B. unter [Neuausrichtungsänderungen für die Migration von 4.7.2 zu 4.8](retargeting/4.7.2-4.8.md), werden einzelne Elemente wie folgt nach ihren erwarteten Auswirkungen klassifiziert:

**Major**\
Eine wesentliche Änderung, die viele Apps beeinflusst oder erhebliche Änderungen des Codes erforderlich macht.

**Minor**\
Eine Änderung, die eine kleine Anzahl von Apps beeinflusst oder geringfügige Änderungen des Codes erforderlich macht.

**Grenzfall**\
Eine Änderung, die nur Apps in sehr spezifischen Szenarien beeinflusst, die nicht üblich sind.

**Transparent**\
Eine Änderung, die keine nennenswerten Auswirkungen hat, die Entwickler oder Benutzer beachten müssten. Die App sollte keine Änderung benötigen.

## <a name="see-also"></a>Weitere Informationen

- [Versionen und Abhängigkeiten](versions-and-dependencies.md)
- [Neuigkeiten](../whats-new/index.md)
- [Veraltete Elemente](../whats-new/whats-obsolete.md)
