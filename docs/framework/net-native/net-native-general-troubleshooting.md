---
title: .NET Native Allgemeine Problembehandlung
ms.date: 03/30/2017
ms.assetid: ee8c5e17-35ea-48a1-8767-83298caac1e8
ms.openlocfilehash: 2bea81e380fed6c456898e9883658ef874c8dd97
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128238"
---
# <a name="net-native-general-troubleshooting"></a>.NET Native Allgemeine Problembehandlung

In diesem Thema wird beschrieben, wie Sie mögliche Probleme beheben, die bei der Entwicklung von apps mit .net Native auftreten können.

- **Problem:** Das Buildausgabefenster wird nicht ordnungsgemäß aktualisiert.

  **Lösung:** Das Buildausgabefenster wird erst aktualisiert, wenn der Build abgeschlossen ist. Buildzeiten können bis zu mehreren Minuten dauern, daher kann eine Verzögerung bei der Aktualisierung der Anzeige auftreten.

- **Problem:** Die Buildzeit der Verkaufsversion Ihrer App für ARM hat zugenommen.

  **Lösung:** Wenn Sie eine APP auf Ihrem Arm-Gerät bereitstellen, wird die .net Native-Infrastruktur aufgerufen. Bei dieser Kompilierung wird eine große Anzahl von Optimierungen ausgeführt und gleichzeitig sichergestellt, dass nicht statische Semantik, wie Reflektion, weiterhin funktioniert. Darüber hinaus wird der Teil von .NET Framework, den die App verwendet, für optimale Leistung statisch eingebunden und muss ebenfalls in nativen Code kompiliert werden. Deshalb dauert die Kompilierung länger.

  Allerdings liegen die Kompilierungszeiten für die meisten Apps auf einem Standardentwicklungscomputer bei Standardkompilierung noch innerhalb einer Minute.  Nur das Generieren von systemeigenen Images für .NET Framework auf einem Standardentwicklungscomputer dauert in der Regel mehrere Minuten.  Sogar mit allen Optimierungen zur Verbesserung des generierten Codes und mit Einschließen von .NET Framework liegen die Buildzeiten von Apps in der Regel bei ein oder zwei Minuten.

  Wir arbeiten weiterhin an der Verbesserung der Kompilierungsleistung, indem wir Multithreadkompilierung und andere Optimierungen untersuchen.

- **Problem:** Sie wissen nicht, ob Ihre APP mit .net Native kompiliert wurde.

  **Lösung:** Wenn der .net Native-Compiler aufgerufen wird, werden Sie längere Buildzeiten feststellen, und der Task-Manager zeigt verschiedene .net native Komponenten Prozesse wie "ILC. exe" und "nutc_driver. exe" an.

  Nachdem Sie Ihr Projekt erfolgreich mit .net Native erstellt haben, finden Sie die Ausgabe unter obj \\ *config* \  *arch* \\ *ProjectName*. ilc\out.  Der endgültige Native Paket Inhalt befindet sich unter bin \\ *arch* \\ *config*\appx. Der endgültige systemeigene Paket Inhalt befindet sich unter \bin \\ *arch* \\ *config*\appx, wenn Sie die APP bereitgestellt haben.

- **Problem:** Die mit .NET Native kompilierte App löst Laufzeitausnahmen aus (in der Regel [MissingMetadataException](missingmetadataexception-class-net-native.md)- oder [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md)-Ausnahmen), die beim Kompilieren ohne .NET Native nicht ausgelöst wurden.

  **Lösung:** Die Ausnahmen werden ausgelöst, da .NET Native weder Metadaten noch Implementierungscode bereitstellt, die andernfalls durch Reflektion verfügbar sind. (Weitere Informationen finden Sie unter [.net Native und Kompilierung](net-native-and-compilation.md).) Um die Ausnahme zu vermeiden, müssen Sie der [laufzeitdirektivendatei (RD. Xml)](runtime-directives-rd-xml-configuration-file-reference.md) einen Eintrag hinzufügen, damit die .net Native-Toolkette die Metadaten oder den Implementierungs Code zur Laufzeit zur Verfügung stellen kann. Es sind zwei Problembehandlungen verfügbar, die den entsprechenden Eintrag für die Laufzeitdirektivendatei zur Beseitigung der Ausnahme generieren:

  - Die [MissingMetadataException-Problembehandlung](https://dotnet.github.io/native/troubleshooter/type.html) für Typen.

  - Die [MissingMetadataException-Problembehandlung](https://dotnet.github.io/native/troubleshooter/method.html) für Methoden.

  Weitere Informationen finden Sie unter [Reflektion und .NET Native](reflection-and-net-native.md).

## <a name="see-also"></a>Weitere Informationen

- [Migrieren der Windows Store-App auf .NET Native](migrating-your-windows-store-app-to-net-native.md)
