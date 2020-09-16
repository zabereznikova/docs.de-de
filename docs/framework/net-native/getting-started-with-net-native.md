---
title: Erste Schritte mit .NET Native
ms.date: 03/30/2017
ms.assetid: fc9e04e8-2d05-4870-8cd6-5bd276814afc
ms.openlocfilehash: b6cd4acaa377de7fc172fb12c9fb9ff1b832f88a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551209"
---
# <a name="getting-started-with-net-native"></a>Erste Schritte mit .NET Native

Unabhängig davon, ob Sie eine neue Windows-App für Windows 10 entwickeln, oder eine vorhandene Windows Store-App migrieren, können Sie dieselben Verfahren verwenden. Um eine .net Native-APP zu erstellen, führen Sie die folgenden Schritte aus:

1. [Entwickeln Sie eine UWP-App (Universelle Windows-Plattform), die auf Windows 10 ausgerichtet ist](#Step1), und testen Sie die Debugbuilds der App, um sicherzustellen, dass sie ordnungsgemäß funktioniert.

2. [Behandeln Sie zusätzliche Verwendungen von Reflektion und Serialisierung](#Step2).

3. [Deploy and test the release builds of your app (Stellen Sie die Releasebuilds Ihrer App bereit, und testen Sie sie)](#Step3).

4. [Manually resolve missing metadata (Beheben Sie fehlende Metadaten manuell)](#Step4), und wiederholen Sie [Schritt 3](#Step3), bis alle Probleme gelöst sind.

> [!NOTE]
> Wenn Sie eine vorhandene Windows Store-App zu .net Native migrieren, lesen Sie die Informationen unter [Migrieren Ihrer Windows Store-App zu .net Native](migrating-your-windows-store-app-to-net-native.md).

<a name="Step1"></a>

## <a name="step-1-develop-and-test-debug-builds-of-your-uwp-app"></a>Schritt 1: Entwickeln und Testen von Debugbuilds der UWP-App

Egal, ob Sie eine neue App entwickeln oder eine vorhandene migrieren, Sie verwenden immer dasselbe Verfahren wie für jede Windows-App.

1. Erstellen Sie ein neues UWP-Projekt in Visual Studio mithilfe der Vorlage für universelle Windows-Apps für Visual C# oder Visual Basic. Standardmäßig sind alle UWP-Apps auf CoreCLR ausgerichtet und ihre Releasebuilds werden mithilfe der .NET Native-Toolkette kompiliert.

2. Beachten Sie, dass es einige bekannte Kompatibilitätsprobleme zwischen dem Kompilieren von UWP-App-Projekten mit und ohne .NET Native-Toolkette gibt. Weitere Informationen finden Sie im [Migrationshandbuch](migrating-your-windows-store-app-to-net-native.md) .

Sie können jetzt c#-oder Visual Basic Code für die .net Native-Oberfläche schreiben, die auf dem lokalen System (oder im Simulator) ausgeführt wird.

> [!IMPORTANT]
> Beachten Sie bei der Entwicklung Ihrer App jede Verwendung von Serialisierung oder Reflektion im Code.

Standardmäßig werden Debugbuilds JIT-kompiliert, um eine schnelle F5-Bereitstellung zu ermöglichen, während Releasebuilds mithilfe der .net Native vorkompilierungs Technologie kompiliert werden. Das bedeutet, dass Sie die Debugbuilds Ihrer App erstellen und testen sollten, um sicherzustellen, dass sie ordnungsgemäß funktionieren, bevor sie mit der .NET Native-Toolkette kompiliert werden.

<a name="Step2"></a>

## <a name="step-2-handle-additional-reflection-and-serialization-usage"></a>Schritt 2: Behandeln zusätzlicher Verwendungen von Reflektion und Serialisierung

Eine Laufzeitdirektivendatei, "Default.rd.xml", die beim Erstellen automatisch Ihrem Projekt hinzugefügt wird. Wenn Sie in C# entwickeln, finden Sie die Datei im **Eigenschaften** -Ordner Ihres Projekts. Wenn Sie in Visual Basic entwickeln, finden Sie die Datei im **Mein Projekt** -Ordner Ihres Projekts.

> [!NOTE]
> Eine Übersicht über den .NET Native-Kompilierungsprozess mit Hintergrundinformationen, die verdeutlichen, warum eine Laufzeitdirektivendatei erforderlich ist, finden Sie unter [.NET Native und Kompilierung](net-native-and-compilation.md).

Die Laufzeitdirektivendatei wird verwendet, um die von Ihrer App zur Laufzeit benötigten Metadaten zu definieren. In einigen Fällen sollte diese Standardversion der Datei ausreichend sein. Code, der die Serialisierung oder Reflektion nutzt, kann jedoch zusätzliche Einträge in der Laufzeitdirektivendatei erfordern.

**Serialisierung**

Es gibt zwei Kategorien von Serialisierungsprogrammen, und beide erfordern möglicherweise zusätzliche Einträge in der Laufzeitdirektivendatei:

- Nicht reflektionsbasierte Serialisierungsprogramme. Die Serialisierungsprogramme in der .NET Framework-Klassenbibliothek, wie die Klassen <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>und <xref:System.Xml.Serialization.XmlSerializer> , beruhen nicht auf Reflektion. Sie erfordern jedoch, dass Code basierend auf dem Objekt generiert wird, das serialisiert oder deserialisiert werden soll.  Weitere Informationen finden Sie im Abschnitt zu Serialisierungsprogrammen von Microsoft unter [Serialization and Metadata](serialization-and-metadata.md).

- Serialisierungsprogramme von Drittanbietern. Serialisierungsbibliotheken von Drittanbietern, bei denen es sich am häufigsten um das Newton Soft JSON-Serialisierungsprogramm handelt, sind im allgemeinen reflektionsebasiert und erfordern Einträge in der \*.rd.xml-Datei, um Objektserialisierung und-Deserialisierung zu unterstützen. Weitere Informationen finden Sie im Abschnitt „Serialisierungsprogramme von Drittanbietern“ unter [Serialization and Metadata](serialization-and-metadata.md).

**Auf Reflektion beruhende Methoden**

In einigen Fällen ist die Verwendung von Reflektion im Code nicht offensichtlich. Einige gängige APIs oder Programmiermuster gelten nicht als Teil der Reflektions-API, aber benötigen die Reflektion, um erfolgreich ausgeführt zu werden. Dazu zählen die folgenden Methoden zur Typinstanziierung und Methodenkonstruktion:

- Die <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> -Methode

- Die Methoden <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> und <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType>

- Die <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> -Methode.

Weitere Informationen finden Sie unter [APIs That Rely on Reflection](apis-that-rely-on-reflection.md).

> [!NOTE]
> In Laufzeitdirektivendateien verwendete Typnamen müssen vollqualifiziert sein. Beispielsweise muss in der Datei "System.String" anstelle von "String" angegeben sein.

<a name="Step3"></a>

## <a name="step-3-deploy-and-test-the-release-builds-of-your-app"></a>Schritt 3: Bereitstellen und Testen der Releasebuilds Ihrer App

Nachdem Sie die Laufzeitdirektivendatei aktualisiert haben, können Sie erneut Releasebuilds der App erstellen und bereitstellen. .Net Native Binärdateien werden in das Unterverzeichnis ILC. out des Verzeichnisses eingefügt, das im Textfeld Buildausgabepfad des Dialog Felds **Eigenschaften** des Projekts auf der Registerkarte **Kompilieren** angegeben ist. **Build output path** Binärdateien, die sich nicht in diesem Ordner befinden, wurden nicht mit .net Native kompiliert. Testen Sie Ihre App gründlich, und testen Sie alle Szenarien, auch Ausfallszenarien, für sämtliche Zielplattformen.

Wenn Ihre App nicht ordnungsgemäß funktioniert (insbesondere in Fällen, in denen zur Laufzeit die Ausnahmen [MissingMetadataException](missingmetadataexception-class-net-native.md) oder [MissingInteropDataException](missinginteropdataexception-class-net-native.md) ausgelöst werden), folgen Sie den Anweisungen im nächsten Abschnitt, [Step 4: Manually resolve missing metadata (Schritt 4: Manuelles Beheben fehlender Metadaten)](#Step4). Das Aktivieren von Ausnahmen der ersten Chance kann hilfreich sein, um diese Fehler zu finden.

Wenn Sie die Debugbuilds Ihrer APP getestet und gedebuggt haben und sicher sind, dass Sie die Ausnahmen [MissingMetadataException](missingmetadataexception-class-net-native.md) und [missinginteropdataexception](missinginteropdataexception-class-net-native.md) entfernt haben, sollten Sie Ihre APP als optimierte .net Native-App testen. Zu diesem Zweck ändern Sie die aktive Projektkonfiguration von **Debug** in **Release**.

<a name="Step4"></a>

## <a name="step-4-manually-resolve-missing-metadata"></a>Schritt 4: Manuelles Beheben fehlender Metadaten

Der häufigste Fehler, der auftritt, wenn .net Native auf dem Desktop nicht angezeigt wird, ist eine Lauf Zeit [MissingMetadataException](missingmetadataexception-class-net-native.md)-, [missinginteropdataexception](missinginteropdataexception-class-net-native.md)-oder [missingruntimeartifaktexception](missingruntimeartifactexception-class-net-native.md) -Ausnahme. In einigen Fällen kann das Fehlen von Metadaten zu unvorhersehbarem Verhalten oder sogar zu App-Fehlern führen. Dieser Abschnitt beschreibt, wie Sie diese Ausnahmen debuggen und beheben können, indem Sie Direktiven zur Laufzeitdirektivendatei hinzufügen. Informationen zu Laufzeitanweisungen finden Sie unter [Runtime Directives (rd.xml) Configuration File Reference (Verweis auf die Konfigurationsdatei von Laufzeitanweisungen (rd.xml))](runtime-directives-rd-xml-configuration-file-reference.md). Nach dem Hinzufügen von Laufzeitdirektiven sollten Sie [die App erneut bereitstellen und testen](#Step3) und ggf. alle neuen [MissingMetadataException](missingmetadataexception-class-net-native.md)-, [MissingInteropDataException](missinginteropdataexception-class-net-native.md)- und  [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) -Ausnahmen auflösen, bis keine Ausnahmen mehr auftreten.

> [!TIP]
> Geben Sie die Laufzeitdirektiven auf einer hohen Ebene an, um Ihre App flexibel in Bezug auf Codeänderungen zu machen.  Es wird empfohlen, Laufzeitdirektiven auf Namespace- und Typebene statt auf Memberebene hinzufügen. Beachten Sie, dass möglicherweise ein Kompromiss zwischen Flexibilität und größeren Binärdateien mit längeren Kompilierungszeiten gefunden werden muss.

Beim Behandeln einer Ausnahme wegen fehlender Metadaten sollten Sie Folgendes berücksichtigen:

- Was versuchte die App vor der Ausnahme auszuführen?

  - Versuchte sie beispielsweise Daten zu binden, zu serialisieren oder zu deserialisieren oder direkt die Reflektions-API zu verwenden?

- Ist dies ein Einzelfall, oder glauben Sie, dass das gleiche Problem für andere Typen auftreten wird?

  - Eine [MissingMetadataException](missingmetadataexception-class-net-native.md) -Ausnahme wird beispielsweise ausgelöst, wenn ein Typ im Objektmodell der App serialisiert wird.  Wenn Sie andere Typen kennen, die serialisiert werden, können Sie gleichzeitig Laufzeitdirektiven für diese Typen hinzufügen (oder für deren enthaltende Namespaces, je nachdem, wie gut der Code strukturiert ist).

- Können Sie den Code so umschreiben, dass die Reflektion nicht verwendet wird?

  - Verwendet der Code zum Beispiel das Schlüsselwort `dynamic` , wenn Sie wissen, welcher Typ zu erwarten ist?

  - Ruft der Code eine Methode auf, die von Reflektion abhängt, wenn eine bessere Alternative zur Verfügung steht?

> [!NOTE]
> Weitere Informationen zur Behandlung von Problemen, die aus Unterschieden in der Reflektion und der Verfügbarkeit von Metadaten in Desktop-Apps und .net Native resultieren, finden Sie unter [APIs, die auf Reflektion beruhen](apis-that-rely-on-reflection.md).

Einige spezifische Beispiele für das Behandeln von Ausnahmen und anderen Problemen beim Testen der App finden Sie unter:

- [Beispiel: Behandeln von Ausnahmen beim Binden von Daten](example-handling-exceptions-when-binding-data.md)

- [Beispiel: Problembehandlung bei dynamischer Programmierung](example-troubleshooting-dynamic-programming.md)

- [Laufzeitausnahmen in .NET Native-Apps](runtime-exceptions-in-net-native-apps.md)

## <a name="see-also"></a>Siehe auch

- [Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz](runtime-directives-rd-xml-configuration-file-reference.md)
- [.NET Native Einrichtung und Konfiguration](/previous-versions/dn600164(v=vs.110))
- [.NET Native und Kompilierung](net-native-and-compilation.md)
- [Reflektion und .NET Native](reflection-and-net-native.md)
- [APIs, die auf Refelktion beruhen](apis-that-rely-on-reflection.md)
- [Serialisierung und Metadaten](serialization-and-metadata.md)
- [Migrieren der Windows Store-App auf .NET Native](migrating-your-windows-store-app-to-net-native.md)
