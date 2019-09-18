---
title: .NET Native Allgemeine Problembehandlung
ms.date: 03/30/2017
ms.assetid: ee8c5e17-35ea-48a1-8767-83298caac1e8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea5f61b0e250c4f51a966bc60959f7559d8e2fe2
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049402"
---
# <a name="net-native-general-troubleshooting"></a>.NET Native Allgemeine Problembehandlung

In diesem Thema wird beschrieben, wie Sie mögliche Probleme beheben, die bei der Entwicklung von apps mit .net Native auftreten können.

- **Betrifft** Das buildausgabefenster wird nicht ordnungsgemäß aktualisiert

  **Lösungs** Das Fenster Buildausgabe wird erst aktualisiert, wenn der Build abgeschlossen ist. Buildzeiten können bis zu mehreren Minuten dauern, daher kann eine Verzögerung bei der Aktualisierung der Anzeige auftreten.

- **Betrifft** Die Buildzeit der Verkaufsversion Ihrer APP für Arm hat sich gesteigert.

  **Lösungs** Wenn Sie eine APP auf Ihrem Arm-Gerät bereitstellen, wird die .net Native-Infrastruktur aufgerufen. Bei dieser Kompilierung wird eine große Anzahl von Optimierungen ausgeführt und gleichzeitig sichergestellt, dass nicht statische Semantik, wie Reflektion, weiterhin funktioniert. Darüber hinaus wird der Teil von .NET Framework, den die App verwendet, für optimale Leistung statisch eingebunden und muss ebenfalls in nativen Code kompiliert werden. Deshalb dauert die Kompilierung länger.

  Allerdings liegen die Kompilierungszeiten für die meisten Apps auf einem Standardentwicklungscomputer bei Standardkompilierung noch innerhalb einer Minute.  Nur das Generieren von systemeigenen Images für .NET Framework auf einem Standardentwicklungscomputer dauert in der Regel mehrere Minuten.  Sogar mit allen Optimierungen zur Verbesserung des generierten Codes und mit Einschließen von .NET Framework liegen die Buildzeiten von Apps in der Regel bei ein oder zwei Minuten.

  Wir arbeiten weiterhin an der Verbesserung der Kompilierungsleistung, indem wir Multithreadkompilierung und andere Optimierungen untersuchen.

- **Betrifft** Sie wissen nicht, ob Ihre APP mit .net Native kompiliert wurde.

  **Lösungs** Wenn der .net Native-Compiler aufgerufen wird, werden Sie längere Buildzeiten feststellen, und der Task-Manager zeigt verschiedene .net native Komponenten Prozesse wie "ILC. exe" und "nutc_driver. exe" an.

  Nachdem Sie Ihr Projekt erfolgreich mit .net Native erstellt haben, finden Sie die Ausgabe unter obj\\*config*\ *arch*\\*ProjectName*. ilc\out.  Der endgültige native Paketinhalt befindet sich unter „bin\\*arch*\\*config*\AppX“. Der endgültige native Paketinhalt steht unter „\bin\\*arch*\\*config*\AppX“, wenn Sie die App bereitgestellt haben.

- **Betrifft** Die .net Native kompilierte APP löst Lauf Zeit Ausnahmen aus (in der Regel [MissingMetadataException](missingmetadataexception-class-net-native.md) -oder [missingruntimeartifaktexception](missingruntimeartifactexception-class-net-native.md) -Ausnahmen), die beim Kompilieren ohne .net Native nicht ausgelöst wurden.

  **Lösungs** Die Ausnahmen werden ausgelöst, weil .net Native weder die Metadaten noch den Implementierungs Code bereitstellt, der andernfalls über Reflektion verfügbar ist. (Weitere Informationen finden Sie unter [.NET Native und Kompilierung](net-native-and-compilation.md).) Zur Beseitigung dieser Ausnahme müssen Sie Ihrer [Laufzeitanweisungsdatei (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md) einen Eintrag hinzufügen, damit die .NET Native-Toolkette die Metadaten oder den Implementierungscode zur Laufzeit bereitstellen kann. Es sind zwei Problembehandlungen verfügbar, die den entsprechenden Eintrag für die Laufzeitdirektivendatei zur Beseitigung der Ausnahme generieren:

  - Die [MissingMetadataException-Problembehandlung](https://dotnet.github.io/native/troubleshooter/type.html) für Typen.

  - Die [MissingMetadataException-Problembehandlung](https://dotnet.github.io/native/troubleshooter/method.html) für Methoden.

  Weitere Informationen finden Sie unter [Reflektion und .NET Native](reflection-and-net-native.md).

## <a name="see-also"></a>Siehe auch

- [Migrieren der Windows Store-App zu .NET Native](migrating-your-windows-store-app-to-net-native.md)
