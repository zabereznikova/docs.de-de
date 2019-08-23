---
title: Erste Schritte mit .NET Native
ms.date: 03/30/2017
ms.assetid: fc9e04e8-2d05-4870-8cd6-5bd276814afc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce43ef1a24a0b9bcf0248647245cc35838700295
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910503"
---
# <a name="getting-started-with-net-native"></a>Erste Schritte mit .NET Native

Unabhängig davon, ob Sie eine neue Windows-App für Windows 10 entwickeln, oder eine vorhandene Windows Store-App migrieren, können Sie dieselben Verfahren verwenden. Um eine .net Native-APP zu erstellen, führen Sie die folgenden Schritte aus:

1. [Entwickeln Sie eine UWP-App (Universelle Windows-Plattform), die auf Windows 10 ausgerichtet ist](#Step1), und testen Sie die Debugbuilds der App, um sicherzustellen, dass sie ordnungsgemäß funktioniert.

2. [Behandeln Sie zusätzliche Verwendungen von Reflektion und Serialisierung](#Step2).

3. [Deploy and test the release builds of your app (Stellen Sie die Releasebuilds Ihrer App bereit, und testen Sie sie)](#Step3).

4. [Manually resolve missing metadata (Beheben Sie fehlende Metadaten manuell)](#Step4), und wiederholen Sie [Schritt 3](#Step3), bis alle Probleme gelöst sind.

> [!NOTE]
> Wenn Sie eine vorhandene Windows Store-App zu .net Native migrieren, lesen Sie die Informationen unter [Migrieren Ihrer Windows Store-App zu .net Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md).

<a name="Step1"></a>

## <a name="step-1-develop-and-test-debug-builds-of-your-uwp-app"></a>Schritt 1: Entwickeln und Testen von Debugbuilds der UWP-App

Egal, ob Sie eine neue App entwickeln oder eine vorhandene migrieren, Sie verwenden immer dasselbe Verfahren wie für jede Windows-App.

1. Erstellen Sie ein neues UWP-Projekt in Visual Studio mithilfe der Vorlage für universelle Windows-Apps für Visual C# oder Visual Basic. Standardmäßig sind alle UWP-Apps auf CoreCLR ausgerichtet und ihre Releasebuilds werden mithilfe der .NET Native-Toolkette kompiliert.

2. Beachten Sie, dass es einige bekannte Kompatibilitätsprobleme zwischen dem Kompilieren von UWP-App-Projekten mit und ohne .NET Native-Toolkette gibt. Weitere Informationen finden Sie im [Migrationshandbuch](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md) .

Sie können nun Code C# für die .net Native-Oberfläche schreiben oder Visual Basic, die auf dem lokalen System (oder im Simulator) ausgeführt wird.

> [!IMPORTANT]
> Beachten Sie bei der Entwicklung Ihrer App jede Verwendung von Serialisierung oder Reflektion im Code.

Standardmäßig werden Debugbuilds JIT-kompiliert, um eine schnelle F5-Bereitstellung zu ermöglichen, während Releasebuilds mithilfe der .net Native vorkompilierungs Technologie kompiliert werden. Das bedeutet, dass Sie die Debugbuilds Ihrer App erstellen und testen sollten, um sicherzustellen, dass sie ordnungsgemäß funktionieren, bevor sie mit der .NET Native-Toolkette kompiliert werden.

<a name="Step2"></a>

## <a name="step-2-handle-additional-reflection-and-serialization-usage"></a>Schritt 2: Weitere Verwendung von Reflektion und Serialisierung

Eine Laufzeitdirektivendatei, "Default.rd.xml", die beim Erstellen automatisch Ihrem Projekt hinzugefügt wird. Wenn Sie in C# entwickeln, finden Sie die Datei im **Eigenschaften** -Ordner Ihres Projekts. Wenn Sie in Visual Basic entwickeln, finden Sie die Datei im **Mein Projekt** -Ordner Ihres Projekts.

> [!NOTE]
> Eine Übersicht über den .NET Native-Kompilierungsprozess mit Hintergrundinformationen, die verdeutlichen, warum eine Laufzeitdirektivendatei erforderlich ist, finden Sie unter [.NET Native und Kompilierung](../../../docs/framework/net-native/net-native-and-compilation.md).

Die Laufzeitdirektivendatei wird verwendet, um die von Ihrer App zur Laufzeit benötigten Metadaten zu definieren. In einigen Fällen sollte diese Standardversion der Datei ausreichend sein. Code, der die Serialisierung oder Reflektion nutzt, kann jedoch zusätzliche Einträge in der Laufzeitdirektivendatei erfordern.

**Serialisierung**

Es gibt zwei Kategorien von Serialisierungsprogrammen, und beide erfordern möglicherweise zusätzliche Einträge in der Laufzeitdirektivendatei:

- Nicht reflektionsbasierte Serialisierungsprogramme. Die Serialisierungsprogramme in der .NET Framework-Klassenbibliothek, wie die Klassen <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>und <xref:System.Xml.Serialization.XmlSerializer> , beruhen nicht auf Reflektion. Sie erfordern jedoch, dass Code basierend auf dem Objekt generiert wird, das serialisiert oder deserialisiert werden soll.  Weitere Informationen finden Sie im Abschnitt zu Serialisierungsprogrammen von Microsoft unter [Serialization and Metadata](../../../docs/framework/net-native/serialization-and-metadata.md).

- Serialisierungsprogramme von Drittanbietern. Serialisierungsbibliotheken von Drittanbietern, bei denen es sich am häufigsten um das Newton Soft JSON-Serialisierungsprogramm handelt, sind im allgemeinen reflektionsebasiert und erfordern Einträge in der \*. rd. XML-Datei, um Objektserialisierung und-Deserialisierung zu unterstützen. Weitere Informationen finden Sie im Abschnitt „Serialisierungsprogramme von Drittanbietern“ unter [Serialization and Metadata](../../../docs/framework/net-native/serialization-and-metadata.md).

**Auf Reflektion beruhende Methoden**

In einigen Fällen ist die Verwendung von Reflektion im Code nicht offensichtlich. Einige gängige APIs oder Programmiermuster gelten nicht als Teil der Reflektions-API, aber benötigen die Reflektion, um erfolgreich ausgeführt zu werden. Dazu zählen die folgenden Methoden zur Typinstanziierung und Methodenkonstruktion:

- Die <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> -Methode

- Die Methoden <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> und <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType>

- Die <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> -Methode.

Weitere Informationen finden Sie unter [APIs That Rely on Reflection](../../../docs/framework/net-native/apis-that-rely-on-reflection.md).

> [!NOTE]
> In Laufzeitdirektivendateien verwendete Typnamen müssen vollqualifiziert sein. Beispielsweise muss in der Datei "System.String" anstelle von "String" angegeben sein.

<a name="Step3"></a>

## <a name="step-3-deploy-and-test-the-release-builds-of-your-app"></a>Schritt 3: Bereitstellen und Testen der Releasebuilds Ihrer APP

Nachdem Sie die Laufzeitdirektivendatei aktualisiert haben, können Sie erneut Releasebuilds der App erstellen und bereitstellen. .NET Native-Binärdateien befinden sich im Unterverzeichnis ILC.out des Verzeichnisses, das im Textfeld **Buildausgabepfad** des Dialogfelds **Eigenschaften** des Projekts auf der Registerkarte **Kompilieren** angegeben ist. Binärdateien, die sich nicht in diesem Ordner befinden, wurden nicht mit .NET Native kompiliert. Testen Sie Ihre App gründlich, und testen Sie alle Szenarien, auch Ausfallszenarien, für sämtliche Zielplattformen.

Wenn Ihre APP nicht ordnungsgemäß funktioniert (insbesondere in Fällen, [in denen Sie zur Laufzeit [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) -oder [missinginteropdataexception](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md) -Ausnahmen auslöst), befolgen Sie die Anweisungen im nächsten Abschnitt Schritt 4: Fehlende Metadaten](#Step4)manuell auflösen. Das Aktivieren von Ausnahmen der ersten Chance kann hilfreich sein, um diese Fehler zu finden.

Wenn Sie die Debugbuilds Ihrer APP getestet und gedebuggt haben und sicher sind, dass Sie die Ausnahmen [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) und [missinginteropdataexception](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md) entfernt haben, sollten Sie Ihre APP als optimierte .net Native-App testen. Zu diesem Zweck ändern Sie die aktive Projektkonfiguration von **Debug** in **Release**.

<a name="Step4"></a>

## <a name="step-4-manually-resolve-missing-metadata"></a>Schritt 4: Fehlende Metadaten manuell auflösen

Der häufigste Fehler, der auftritt, wenn .net Native auf dem Desktop nicht angezeigt wird, ist eine Lauf Zeit [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)-, [missinginteropdataexception](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md)-oder [missingruntimeartifaktexception](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) -Ausnahme. In einigen Fällen kann das Fehlen von Metadaten zu unvorhersehbarem Verhalten oder sogar zu App-Fehlern führen. Dieser Abschnitt beschreibt, wie Sie diese Ausnahmen debuggen und beheben können, indem Sie Direktiven zur Laufzeitdirektivendatei hinzufügen. Informationen zu Laufzeitanweisungen finden Sie unter [Runtime Directives (rd.xml) Configuration File Reference (Verweis auf die Konfigurationsdatei von Laufzeitanweisungen (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md). Nach dem Hinzufügen von Laufzeitanweisungen sollten Sie [die App erneut bereitstellen und testen](#Step3) und ggf. alle neuen [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)-, [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md)- und [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)-Ausnahmen auflösen, bis keine Ausnahmen mehr auftreten.

> [!TIP]
> Geben Sie die Laufzeitdirektiven auf einer hohen Ebene an, um Ihre App flexibel in Bezug auf Codeänderungen zu machen.  Es wird empfohlen, Laufzeitdirektiven auf Namespace- und Typebene statt auf Memberebene hinzufügen. Beachten Sie, dass möglicherweise ein Kompromiss zwischen Flexibilität und größeren Binärdateien mit längeren Kompilierungszeiten gefunden werden muss.

Beim Behandeln einer Ausnahme wegen fehlender Metadaten sollten Sie Folgendes berücksichtigen:

- Was versuchte die App vor der Ausnahme auszuführen?

  - Versuchte sie beispielsweise Daten zu binden, zu serialisieren oder zu deserialisieren oder direkt die Reflektions-API zu verwenden?

- Ist dies ein Einzelfall, oder glauben Sie, dass das gleiche Problem für andere Typen auftreten wird?

  - Eine [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) -Ausnahme wird beispielsweise ausgelöst, wenn ein Typ im Objektmodell der App serialisiert wird.  Wenn Sie andere Typen kennen, die serialisiert werden, können Sie gleichzeitig Laufzeitdirektiven für diese Typen hinzufügen (oder für deren enthaltende Namespaces, je nachdem, wie gut der Code strukturiert ist).

- Können Sie den Code so umschreiben, dass die Reflektion nicht verwendet wird?

  - Verwendet der Code zum Beispiel das Schlüsselwort `dynamic` , wenn Sie wissen, welcher Typ zu erwarten ist?

  - Ruft der Code eine Methode auf, die von Reflektion abhängt, wenn eine bessere Alternative zur Verfügung steht?

> [!NOTE]
> Weitere Informationen zur Behandlung von Problemen, die aus Unterschieden in der Reflektion und der Verfügbarkeit von Metadaten in Desktop-Apps und .net Native resultieren, finden Sie unter [APIs, die auf Reflektion beruhen](../../../docs/framework/net-native/apis-that-rely-on-reflection.md).

Einige spezifische Beispiele für das Behandeln von Ausnahmen und anderen Problemen beim Testen der App finden Sie unter:

- [Anpassen von mit VSTU Behandeln von Ausnahmen beim Binden von Daten](../../../docs/framework/net-native/example-handling-exceptions-when-binding-data.md)

- [Anpassen von mit VSTU Problembehandlung bei dynamischer Programmierung](../../../docs/framework/net-native/example-troubleshooting-dynamic-programming.md)

- [Runtime Exceptions in .NET Native Apps (Laufzeitausnahmen in .NET Native-Apps)](../../../docs/framework/net-native/runtime-exceptions-in-net-native-apps.md)

## <a name="see-also"></a>Siehe auch

- [Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [.Net Native Setup und Konfiguration](https://docs.microsoft.com/previous-versions/dn600164(v=vs.110))
- [.NET Native and Compilation (.NET Native und Kompilierung)](../../../docs/framework/net-native/net-native-and-compilation.md)
- [Reflection and .NET Native (Reflektion und .NET Native)](../../../docs/framework/net-native/reflection-and-net-native.md)
- [APIs That Rely on Reflection (APIs, die die Reflektion benötigen)](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)
- [Serialization and Metadata (Serialisierung und Metadaten)](../../../docs/framework/net-native/serialization-and-metadata.md)
- [Migrieren der Windows Store-App zu .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)
