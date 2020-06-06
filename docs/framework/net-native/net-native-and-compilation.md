---
title: .NET Native und Kompilierung
ms.date: 03/30/2017
ms.assetid: e38ae4f3-3e3d-42c3-a4b8-db1aa9d84f85
ms.openlocfilehash: cf5c9f05b2f2cb4ca15e4add5b53bc9bdca757a3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128244"
---
# <a name="net-native-and-compilation"></a>.NET Native und Kompilierung

Die meisten auf das .NET Framework ausgerichteten Windows 8.1- und Windows Desktop-Anwendungen sind in einer bestimmten Programmiersprache geschrieben und in eine Zwischensprache (Intermediate Language, IL) kompiliert. Zur Laufzeit ist ein JIT-Compiler (Just-In-Time) dafür zuständig, die Zwischensprache für den lokalen Computer in systemeigenen Code zu kompilieren, unmittelbar bevor eine Methode zum ersten Mal ausgeführt wird. Im Gegensatz dazu konvertiert die .NET Native-Toolkette den Quellcode zur Kompilierzeit in systemeigenen Code. In diesem Abschnitt wird .NET Native mit anderen Kompilierungsverfahren verglichen, die für .NET Framework-Apps verfügbar sind. Zudem enthält dieser Abschnitt einen konkreten Überblick über die Erzeugung von nativem Code mit .NET Native, der Ihnen dabei helfen kann zu verstehen, warum Ausnahmen nicht im JIT-kompilierten Code auftreten, die hingegen in Code auftreten, der mit .NET Native kompiliert wurde.

## <a name="net-native-generating-native-binaries"></a>.NET Native: Generieren von systemeigenen Binärdateien

Eine Anwendung, die auf das .NET Framework ausgerichtet ist und nicht mithilfe der .NET Native-Toolkette kompiliert wurde, besteht aus Ihrer Anwendungsassembly, die Folgendes umfasst:

- [Metadaten](../../standard/metadata-and-self-describing-components.md), die die Assembly, ihre Abhängigkeiten, die enthaltenen Typen und ihre Member beschreiben. Die Metadaten werden für die Reflektion und den spät gebunden Zugriff sowie in einigen Fällen auch vom Compiler und den Buildtools verwendet.

- Implementierungscode. Dieser besteht aus Opcodes der Zwischensprache (Intermediate Language, IL). Zur Laufzeit übersetzt der JIT-Compiler (Just-In-Time) den Implementierungscode für die Zielplattform in systemeigenen Code.

 Zusätzlich zur Assembly der Hauptanwendung erfordert eine App Folgendes:

- Alle zusätzlichen Klassenbibliotheken oder Assemblys von Drittanbietern, die für die App erforderlich sind. Diese Assemblys schließen gleichermaßen die Assembly, ihre Typen und Member beschreibende Metadaten sowie die Zwischensprache (IL) ein, die alle Typmember implementiert.

- Die .NET Framework-Klassenbibliothek. Hierbei handelt es sich um eine Auflistung von Assemblys, die während der Installation des .NET Frameworks auf dem lokalen System installiert werden. Die in der .NET Framework-Klassenbibliothek einbezogenen Assemblys umfassen einen vollständigen Satz von Metadaten und Implementierungscode.

- Die Common Language Runtime. Hierbei handelt es sich um eine Auflistung von DLLs (Dynamic Link Library), die Dienste wie die Folgenden ausführen: Laden von Assemblys, Speicherverwaltung und Garbage Collection, Ausnahmebehandlung, JIT-Kompilierung (Just-In-Time), Remoting und Interoperabilität. Wie die Klassenbibliothek wird die Common Language Runtime im Rahmen der .NET Framework-Installation auf dem lokalen System installiert.

Beachten Sie, dass die gesamte Common Language Runtime sowie die Metadaten und die Zwischensprache (Intermediate Language, IL) für alle Typen in anwendungsspezifischen Assemblys, Assemblys von Drittanbietern und Systemassemblys vorhanden sein müssen, damit die App erfolgreich ausgeführt werden kann.

## <a name="net-native-and-just-in-time-compilation"></a>.NET Native- und JIT-Kompilierung (Just-In-Time)

Die Eingabe für die .NET Native-Toolkette ist die vom C#- oder Visual Basic-Compiler erstellte Windows Store-App. Die .NET Native-Toolkette beginnt die Ausführung somit nach Abschluss der Kompilierung einer Windows Store-App durch den Sprachcompiler.

> [!TIP]
> Da es sich bei der Eingabe für .NET Native um die in verwaltete Assemblys geschriebene Zwischensprache (Intermediate Language) und die Metadaten handelt, können Sie weiterhin benutzerdefinierten Code generieren oder andere benutzerdefinierte Operationen mithilfe von Bildvorstufen- oder Postbuild-Ereignissen oder durch Ändern der MSBuild-Projektdatei ausführen.
>
> Kategorien von Tools, die die Zwischensprache ändern und dadurch die .NET-Toolkette daran hindern, die Zwischensprache einer App zu analysieren, werden jedoch nicht unterstützt. Obfuskatoren sind die bemerkenswertesten Tools dieses Typs.

Beim Konvertieren einer App aus der Zwischensprache in nativen Code führt die .NET Native-Toolkette Vorgänge wie die Folgenden aus:

- Für bestimmte Codepfade wird Code ersetzt, der auf Reflektion und Metadaten mit statischem systemeigenem Code beruht. Wenn ein Werttyp z. B. die <xref:System.ValueType.Equals%2A?displayProperty=nameWithType>-Methode nicht außer Kraft setzt, verwendet der Standardtest zur Ermittlung der Gleichheit die Reflektion, um <xref:System.Reflection.FieldInfo>-Objekte abzurufen, die die Felder des Werttyps darstellen. Anschließend werden die Feldwerte von zwei Instanzen verglichen. Beim Kompilieren in nativen Code ersetzt die .NET Native-Toolkette den Reflektionscode und die Metadaten durch einen statischen Vergleich der Feldwerte.

- Dabei wird nach Möglichkeit versucht, alle Metadaten zu beseitigen.

- In die Assemblys der endgültigen App wird nur der Implementierungscode einbezogen, der tatsächlich von der App aufgerufen wird. Dies betrifft vor allem Code in Bibliotheken von Drittanbietern und in der .NET Framework-Klassenbibliothek. Eine Anwendung hängt demzufolge nicht mehr von Bibliotheken von Drittanbietern oder der vollständigen .NET Framework-Klassenbibliothek ab. Der Code in Bibliotheken von Drittanbietern und in .NET Framework-Klassenbibliotheken ist jetzt stattdessen im Hinblick auf die Anwendung lokal verfügbar.

- Dadurch wird die vollständige Common Language Runtime (CLR) durch eine umgestaltete Common Language Runtime ersetzt, die in erster Linie den Garbage Collector enthält. Die umgestaltete Common Language Runtime befindet sich in einer Bibliothek namens "mrt100_app.dll", die für die Anwendung lokal verfügbar und nur wenige hundert Kilobyte groß ist. Dies ist dadurch möglich, dass die statische Verknüpfung den Bedarf an vielen der von der Common Language Runtime ausgeführten Dienste beseitigt.

  > [!NOTE]
  > .NET Native verwendet denselben Garbage Collector als Standard-CLR (Common Language Runtime). Beim .NET Native Garbage Collector ist die Garbage Collection im Hintergrund standardmäßig aktiviert. Weitere Informationen zur Garbage Collection finden Sie unter [Grundlagen der Garbage Collection](../../standard/garbage-collection/fundamentals.md).

> [!IMPORTANT]
> .NET Native kompiliert eine gesamte Anwendung in eine systemeigene Anwendung. Es ist Ihnen dabei nicht gestattet, einzelne Assemblys, die eine Klassenbibliothek enthalten, in nativen Code zu kompilieren, damit diese unabhängig vom verwalteten Code aufgerufen werden können.

Die von der .NET Native-Toolkette erzeugte resultierende App wird im Debug- oder Releaseverzeichnis Ihres Projektverzeichnisses in ein Verzeichnis namens „ilc.out“ geschrieben. Die App besteht aus den folgenden Dateien:

- *\<appName>*. exe, eine ausführbare Stubdatei, die die Steuerung einfach an einen speziellen `Main` Export in *\<appName>* . dll überträgt.

- *\<appName>*. dll, eine Windows Dynamic Link Library, die den gesamten Anwendungscode enthält, sowie Code aus der .NET Framework-Klassenbibliothek und allen Bibliotheken von Drittanbietern, von denen Sie abhängig sind.  Sie enthält auch Unterstützungscode, z. B. den für die Zusammenarbeit mit Windows und zum Serialisieren von Objekten in der App erforderlichen Code.

- "mrt100_app.dll": Eine umgestaltete Common Language Runtime, die Laufzeitdienste wie die Garbage Collection bereitstellt.

 Alle Abhängigkeiten werden vom APPX-Manifest der App erfasst.  Zusätzlich zur EXE- und DLL-Datei der Anwendung sowie zur Datei "mrt100_app.dll", die direkt im AppX-Paket gebündelt werden, sind zwei weitere Dateien enthalten:

- „msvcr140_app.dll“: Die von der Datei „mrt100_app.dll“ verwendete C-Laufzeitbibliothek (CRT). Sie ist über einen Frameworkverweis in das Paket einbezogen.

- "mrt100.dll": Diese Bibliothek enthält Funktionen, die die Leistung der Datei "mrt100_app.dll" verbessern können, obwohl die Funktionalität der Datei "mrt100_app.dll" nicht verhindert wird, wenn diese Bibliothek nicht vorhanden ist. Wenn die Bibliothek verfügbar ist, wird sie auf dem lokalen Computer aus dem Verzeichnis "system32" geladen.

Da die .NET Native-Toolkette den Implementierungscode in Ihrer App nur verknüpft, wenn ihr bekannt ist, dass die App den Code tatsächlich aufruft, werden die Metadaten oder der Implementierungscode möglicherweise nicht in die App einbezogen, die in den folgenden Szenarien erforderlich sind:

- Reflektion.

- Dynamischer oder spät gebundener Aufruf

- Serialisierung und Deserialisierung

- COM-Interop

Fehlen die erforderlichen Metadaten oder der Implementierungscode zur Laufzeit, löst die .NET Native Common Language Runtime eine Ausnahme aus. Sie können diese Ausnahmen verhindern und sicherstellen, dass die .NET Native-Toolkette die erforderlichen Metadaten und den Implementierungscode enthält, indem Sie eine [Laufzeitanweisungsdatei](runtime-directives-rd-xml-configuration-file-reference.md) (eine XML-Datei) verwenden, die die Programmelemente bezeichnet, deren Metadaten oder Implementierungscode zur Laufzeit verfügbar sein müssen, und ihnen eine Laufzeitrichtlinie zuweist. Nachfolgend finden Sie die standardmäßige Laufzeitdirektivendatei, die zu einem Windows Store-Projekt hinzugefügt wird, das von der .NET Native-Toolkette kompiliert wird:

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
    <Assembly Name="*Application*" Dynamic="Required All" />
  </Application>
</Directives>
```

Auf diese Weise werden sämtliche Typen und ihre Member in allen Assemblys im Anwendungspaket für die Reflektion und den dynamischen Aufruf aktiviert. Die Reflektion oder dynamische Aktivierung von Typen in Assemblys der .NET Framework-Klassenbibliothek werden jedoch nicht aktiviert. In vielen Fällen ist dies ausreichend.

## <a name="net-native-and-ngen"></a>.NET Native und NGEN

Der [Native Image Generator](../tools/ngen-exe-native-image-generator.md) (NGEN) kompiliert Assemblys in nativen Code und installiert sie auf dem lokalen Computer im nativen Imagecache. Obwohl NGEN wie .NET Native systemeigenen Code erzeugt, unterscheidet sich NGEN jedoch in einigen entscheidenden Punkten von .NET Native:

- Wenn für eine bestimmte Methode kein systemeigenes Image verfügbar ist, greift NGEN für den Code auf den JIT-Compiler zurück. Das bedeutet, dass systemeigene Images für den Fall weiterhin Metadaten und die Zwischensprache (Intermediate Language, IL) einbeziehen müssen, dass NGEN auf die JIT-Kompilierung zurückgreift. .NET Native erzeugt im Gegensatz dazu nur systemeigene Images und greift nicht auf die JIT-Kompilierung zurück. Daher müssen nur Metadaten erhalten bleiben, die für einige Reflektions-, Serialisierungs- und Interop-Szenarien erforderlich sind.

- NGEN beruht für Dienste wie Laden von Assemblys, Remoting, Interop, Speicherverwaltung, Garbage Collection und ggf. JIT-Kompilierung weiterhin auf der vollständigen Common Language Runtime. In .NET Native sind viele dieser Dienste entweder nicht erforderlich (JIT-Kompilierung) oder werden zur Buildzeit aufgelöst und in die App-Assembly einbezogen. Die verbleibenden Dienste, von denen der wichtigste die Garbage Collection ist, sind in einer wesentlich kleineren, umgestalteten Common Language Runtime namens "mrt100_app.dll" enthalten.

- NGEN-Images sind eher anfällig. Ein Patch oder eine Änderung für eine Abhängigkeit erfordert z. B. in der Regel, dass NGEN für die Assemblys, die diese verwenden, ebenfalls erneut durchgeführt wird. Dies gilt insbesondere für Systemassemblys in der .NET Framework-Klassenbibliothek. Im Gegensatz dazu gestattet .NET Native, dass Anwendungen unabhängig voneinander bereitgestellt werden.

## <a name="see-also"></a>Weitere Informationen

- [Metadaten und selbstbeschreibende Komponenten](../../standard/metadata-and-self-describing-components.md)
- [Inside .NET Native (Channel 9-Video)](https://channel9.msdn.com/Shows/Going+Deep/Inside-NET-Native)
- [Reflektion und .NET Native](reflection-and-net-native.md)
- [.NET Native Allgemeine Problembehandlung](net-native-general-troubleshooting.md)
