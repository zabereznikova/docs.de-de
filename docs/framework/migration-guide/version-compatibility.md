---
title: Versionskompatibilität im .NET Framework
description: Informationen zur Kompatibilität zwischen verschiedenen Versionen des .NET Framework, einschließlich Abwärtskompatibilität und paralleler Ausführung
ms.custom: updateeachrelease
ms.date: 04/02/2019
helpviewer_keywords:
- .NET Framework, version compatibility
- .NET Framework, compatibility with earlier versions
- .NET Framework versions, compatibility
ms.assetid: 2f25e522-456a-48c3-8a53-e5f39275649f
ms.openlocfilehash: dfdc5a977b69af8aa3a0d33ed8b833745cf6bf11
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475501"
---
# <a name="version-compatibility"></a>Versionskompatibilität

Abwärtskompatibilität bedeutet, dass eine für eine bestimmte Version einer Plattform entwickelte App in höheren Versionen dieser Plattform ausgeführt werden kann. Im .NET Framework wird versucht, die Abwärtskompatibilität zu maximieren: Quellcode, der für eine bestimmte Version des .NET Framework geschrieben wurde, kann in höheren Versionen des .NET Framework kompiliert werden. Auch Binärdateien, die in einer bestimmten Version des .NET Framework ausgeführt werden, sollten in höheren Versionen des .NET Framework dasselbe Verhalten aufweisen.

## <a name="version-compatibility-for-apps"></a><a name="Apps"></a>Versionskompatibilität für Apps

Standardmäßig wird eine App in der Version des .NET Framework ausgeführt, für die sie erstellt wurde. Wenn diese Version nicht vorhanden ist und die App-Konfigurationsdatei keine unterstützten Versionen definiert, tritt möglicherweise ein .NET Framework-Initialisierungsfehler auf. In diesem Fall schlägt der Versuch fehl, die App auszuführen.

Fügen Sie der Konfigurationsdatei der App mindestens ein [\<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md)-Element hinzu, um die Versionen zu definieren, in denen die App ausgeführt werden kann. Jedes `<supportedRuntime>`-Element führt eine unterstützte Version der Laufzeit auf. Dabei gibt das erste Element die bevorzugte Version der Laufzeit an und das letzte die am wenigsten bevorzugte Version.

```xml
<configuration>
   <startup>
      <supportedRuntime version="v2.0.50727" />
      <supportedRuntime version="v4.0" />
   </startup>
</configuration>
```

Weitere Informationen finden Sie unter [Vorgehensweise: Konfigurieren einer App zur Unterstützung von .NET Framework 4 oder 4.x](how-to-configure-an-app-to-support-net-framework-4-or-4-5.md).

## <a name="version-compatibility-for-components"></a>Versionskompatibilität für Komponenten

Eine App kann die Version von .NET Framework steuern, in der sie ausgeführt wird. Eine Komponente kann das jedoch nicht. Komponenten und Klassenbibliotheken werden im Kontext einer bestimmten App geladen und daher automatisch in der Version von .NET Framework ausgeführt, in der die App ausgeführt wird.

Wegen dieser Einschränkung sind Kompatibilitätsgarantien für Komponenten besonders wichtig. Ab .NET Framework 4 können Sie den Grad der Kompatibilität einer Komponente mit mehreren Versionen angeben. Dazu wenden Sie das <xref:System.Runtime.Versioning.ComponentGuaranteesAttribute?displayProperty=nameWithType>-Attribut auf diese Komponente an. Tools können mithilfe dieses Attributs potenzielle Verletzungen der Kompatibilitätsgarantie in zukünftigen Versionen einer Komponente erkennen.

## <a name="backward-compatibility"></a>Abwärtskompatibilität

.NET Framework 4.5 und höher ist mit Apps abwärtskompatibel, die mit früheren Versionen von .NET Framework erstellt wurden. Das heißt, Apps und Komponenten, die mit früheren Versionen von .NET Framework erstellt wurden, funktionieren ohne weitere Änderung auch in .NET Framework 4.5 und höher. Allerdings werden Apps standardmäßig in der Version der Common Language Runtime ausgeführt, für die sie entwickelt wurden. Daher müssen Sie eine Konfigurationsdatei bereitstellen, damit die App in .NET Framework 4.5 oder höher ausgeführt werden kann. Weitere Informationen finden Sie im Abschnitt [Versionskompatibilität für Apps](#Apps) weiter oben in diesem Artikel.

In der Praxis kann diese Kompatibilität von scheinbar belanglosen Änderungen in .NET Framework und von Änderungen in den Programmierverfahren aufgehoben werden. Leistungsverbesserungen an .NET Framework 4.5 können z. B. eine Racebedingung mit sich bringen, die unter früheren Versionen nicht aufgetreten ist. Auf ähnliche Weise sind das Verwenden eines hartcodierten Pfads zu .NET Framework-Assemblys, das Ausführen eines Gleichheitsvergleich mit einer bestimmten Version von .NET Framework und das Abrufen des Werts eines privaten Felds mithilfe einer Reflektion keine abwärtskompatiblen Maßnahmen. Außerdem schließt jede Version von .NET Framework Fehlerkorrekturen und sicherheitsbezogene Änderungen ein, die sich auf die Kompatibilität von einigen Apps und Komponenten auswirken können.

Wenn Ihre App oder Komponente nicht wie erwartet in .NET Framework 4.5 (einschließlich der zugehörigen Releases, .NET Framework 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2 oder 4.8) funktioniert, verwenden Sie die folgenden Checklisten:

- Wenn Ihre App für alle Versionen von .NET Framework ab .NET Framework 4.0 entwickelt wurde, finden Sie unter [Anwendungskompatibilität](application-compatibility.md) Informationen zum Generieren von Listen, die Änderungen zwischen der Version, mit der Ihre App ausgeführt wird, und der Zielversion von .NET Framework aufführt.

- Wenn Sie über eine App für .NET Framework 3.5 verfügen, finden Sie außerdem Informationen unter [Migrationsprobleme in .NET Framework 4](net-framework-4-migration-issues.md).

- Wenn Sie über eine App für .NET Framework 2.0 verfügen, finden Sie außerdem Informationen unter [Changes in .NET Framework 3.5 SP1 (Änderungen in .NET Framework 3.5 SP1)](https://docs.microsoft.com/previous-versions/dotnet/articles/dd310284(v=msdn.10)).

- Wenn Sie über eine App für .NET Framework 1.1 verfügen, finden Sie außerdem Informationen unter [Changes in .NET Framework 2.0 (Änderungen in .NET Framework 2.0)](https://docs.microsoft.com/previous-versions/aa570326(v=msdn.10)).

- Wenn Sie vorhandenen Quellcode neu kompilieren, sodass er in .NET Framework 4.5 oder den zugehörigen Releases ausgeführt werden kann, oder wenn Sie eine neue Version einer App oder einer Komponente entwickeln, die basierend auf vorhandenem Quellcode auf .NET Framework 4.5 oder die zugehörigen Releases ausgerichtet ist, überprüfen Sie [Veraltete Elemente in der Klassenbibliothek](../whats-new/whats-obsolete.md) auf veraltete Typen und Member, und wenden Sie die beschriebene Problemumgehung an. (Bereits kompilierter Code wird weiterhin mit Typen und Membern ausgeführt, die als veraltet markiert wurden.)

- Wenn Sie feststellen, dass eine Änderung in .NET Framework 4.5 verhindert, dass die App ordnungsgemäß funktioniert, überprüfen Sie im [Schema für Runtimeeinstellungen](../configure-apps/file-schema/runtime/index.md) und insbesondere für das [Element \<AppContextSwitchOverrides>](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md), ob Sie eine Runtimeeinstellung in der App-Konfigurationsdatei verwenden können, um das vorherige Verhalten wiederherzustellen.

- Wenn Sie auf ein Problem stoßen, das noch nicht dokumentiert ist, öffnen Sie ein Ticket auf der [Website für die .NET-Entwickler-Community](https://developercommunity.visualstudio.com/spaces/61/index.html) oder im [Microsoft/dotnet GitHub-Repository](https://github.com/microsoft/dotnet/issues).

## <a name="side-by-side-execution"></a>Parallele Ausführung

Wenn Sie keine geeignete Umgehung für das Problem finden können, beachten Sie, dass .NET Framework 4.5 (oder eine der Unterversionen) parallel mit den Versionen 1.1, 2.0 und 3.5 ausgeführt wird und ein direktes Update ist, das Version 4 ersetzt. Sie können für Apps, die auf die Versionen 1.1, 2.0 und 3.5 ausgerichtet sind, die entsprechende Version des .NET Framework auf dem Zielcomputer installieren, um die App in der optimalen Umgebung auszuführen. Weitere Informationen über die parallele Ausführung finden Sie unter [Parallele Ausführung](../deployment/side-by-side-execution.md).

## <a name="see-also"></a>Siehe auch

- [Neuigkeiten](../whats-new/index.md)
- [Veraltete Elemente in der Klassenbibliothek](../whats-new/whats-obsolete.md)
- [Anwendungskompatibilität](application-compatibility.md)
- [Offizielle .NET Framework-Supportrichtlinie](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework)
- [Migrationsprobleme in .NET Framework 4](net-framework-4-migration-issues.md)
