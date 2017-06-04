---
title: "Erste Schritte mit .NET Native | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fc9e04e8-2d05-4870-8cd6-5bd276814afc
caps.latest.revision: 29
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 29
---
# Erste Schritte mit .NET Native
Unabhängig davon, ob Sie eine neue Windows\-App für Windows 10 entwickeln, oder eine vorhandene Windows Store\-App migrieren, können Sie dieselben Verfahren verwenden. Um eine [!INCLUDE[net_native](../../../includes/net-native-md.md)]\-App zu erstellen, gehen Sie wie folgt vor:  
  
1.  [Entwickeln Sie eine UWP\-App \(Universelle Windows\-Plattform\), die auf Windows 10 ausgerichtet ist](#Step1), und testen Sie die Debugbuilds der App, um sicherzustellen, dass sie ordnungsgemäß funktioniert.  
  
2.  [Behandeln Sie zusätzliche Verwendungen von Reflektion und Serialisierung](#Step4).  
  
3.  [Stellen Sie die Releasebuilds Ihrer App bereit und testen Sie sie](#Step5).  
  
4.  [Beheben Sie fehlende Metadaten manuell](#Step6), und wiederholen Sie [Schritt 3](#Step5), bis alle Probleme gelöst sind.  
  
> [!NOTE]
>  Wenn Sie eine vorhandene Windows Store\-App zu [!INCLUDE[net_native](../../../includes/net-native-md.md)] migrieren, lesen Sie unbedingt auch [Migrieren der Windows Store\-App auf .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md).  
  
<a name="Step1"></a>   
## Schritt 1: Entwickeln und Testen von Debugbuilds der UWP\-App  
 Egal, ob Sie eine neue App entwickeln oder eine vorhandene migrieren, Sie verwenden immer dasselbe Verfahren wie für jede Windows\-App.  
  
1.  Erstellen Sie ein neues UWP\-Projekt in Visual Studio mithilfe der Vorlage für universelle Windows\-Apps für Visual C\# oder Visual Basic. Standardmäßig sind alle UWP\-Apps auf CoreCLR ausgerichtet und ihre Releasebuilds werden mithilfe der .NET Native\-Toolkette kompiliert.  
  
2.  Beachten Sie, dass es einige bekannte Kompatibilitätsprobleme zwischen dem Kompilieren von UWP\-App\-Projekten mit und ohne .NET Native\-Toolkette gibt. Weitere Informationen finden Sie im [Migrationshandbuch](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md).  
  
 Sie können jetzt C\#\- oder Visual Basic\-Code auf dem [!INCLUDE[net_native](../../../includes/net-native-md.md)]\-Oberflächenbereich schreiben, der auf einem lokalen System \(oder im Simulator\) ausgeführt wird.  
  
> [!IMPORTANT]
>  Beachten Sie bei der Entwicklung Ihrer App jede Verwendung von Serialisierung oder Reflektion im Code.  
  
 Standardmäßig werden Debugversionen mit JIT kompiliert, um eine schnelle F5\-Bereitstellung zu ermöglichen, während endgültige Versionen mit der [!INCLUDE[net_native](../../../includes/net-native-md.md)]\-Vorkompilierungstechnologie kompiliert werden. Das bedeutet, dass Sie die Debugbuilds Ihrer App erstellen und testen sollten, um sicherzustellen, dass sie ordnungsgemäß funktionieren, bevor sie mit der .NET Native\-Toolkette kompiliert werden.  
  
<a name="Step4"></a>   
## Schritt 2: Behandeln zusätzlicher Verwendungen von Reflektion und Serialisierung  
 Eine Laufzeitdirektivendatei, "Default.rd.xml", die beim Erstellen automatisch Ihrem Projekt hinzugefügt wird. Wenn Sie in C\# entwickeln, finden Sie die Datei im **Eigenschaften**\-Ordner Ihres Projekts. Wenn Sie in Visual Basic entwickeln, finden Sie die Datei im **Mein Projekt**\-Ordner Ihres Projekts.  
  
> [!NOTE]
>  Eine Übersicht über den .NET Native\-Kompilierungsprozess mit Hintergrundinformationen, die verdeutlichen, warum eine Laufzeitdirektivendatei erforderlich ist, finden Sie unter [.NET Native und Kompilierung](../../../docs/framework/net-native/net-native-and-compilation.md).  
  
 Die Laufzeitdirektivendatei wird verwendet, um die von Ihrer App zur Laufzeit benötigten Metadaten zu definieren. In einigen Fällen sollte diese Standardversion der Datei ausreichend sein. Code, der die Serialisierung oder Reflektion nutzt, kann jedoch zusätzliche Einträge in der Laufzeitdirektivendatei erfordern.  
  
 **Serialisierung**  
 Es gibt zwei Kategorien von Serialisierungsprogrammen, und beide erfordern möglicherweise zusätzliche Einträge in der Laufzeitdirektivendatei:  
  
-   Nicht reflektionsbasierte Serialisierungsprogramme. Die Serialisierungsprogramme in der .NET Framework\-Klassenbibliothek, wie die Klassen <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> und <xref:System.Xml.Serialization.XmlSerializer>, beruhen nicht auf Reflektion. Sie erfordern jedoch, dass Code basierend auf dem Objekt generiert wird, das serialisiert oder deserialisiert werden soll.  Weitere Informationen finden Sie im Abschnitt zu Serialisierungsprogrammen von Microsoft unter [Serialisierung und Metadaten](../../../docs/framework/net-native/serialization-and-metadata.md).  
  
-   Serialisierungsprogramme von Drittanbietern. Serialisierungsbibliotheken von Drittanbietern, von denen die verbreitetste das Newtonsoft JSON\-Serialisierungsprogramm ist, basieren im Allgemeinen auf Reflektion und benötigen Einträge in der Datei \*.rd.xml, um Objektserialisierung und Deserialisierung zu unterstützen. Weitere Informationen finden Sie im Abschnitt „Serialisierungsprogramme von Drittanbietern“ unter [Serialisierung und Metadaten](../../../docs/framework/net-native/serialization-and-metadata.md).  
  
 **Auf Reflektion beruhende Methoden**  
 In einigen Fällen ist die Verwendung von Reflektion im Code nicht offensichtlich. Einige gängige APIs oder Programmiermuster gelten nicht als Teil der Reflektions\-API, aber benötigen die Reflektion, um erfolgreich ausgeführt zu werden. Dazu zählen die folgenden Methoden zur Typinstanziierung und Methodenkonstruktion:  
  
-   Die <xref:System.Type.MakeGenericType%2A?displayProperty=fullName>\-Methode  
  
-   Die Methoden <xref:System.Array.CreateInstance%2A?displayProperty=fullName> und <xref:System.Type.MakeArrayType%2A?displayProperty=fullName>  
  
-   Die <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=fullName>\-Methode.  
  
 Weitere Informationen finden Sie unter [APIs, die auf Refelktion beruhen](../../../docs/framework/net-native/apis-that-rely-on-reflection.md).  
  
> [!NOTE]
>  In Laufzeitdirektivendateien verwendete Typnamen müssen vollqualifiziert sein. Beispielsweise muss in der Datei "System.String" anstelle von "String" angegeben sein.  
  
<a name="Step5"></a>   
## Schritt 3: Bereitstellen und Testen der Releasebuilds Ihrer App  
 Nachdem Sie die Laufzeitdirektivendatei aktualisiert haben, können Sie erneut Releasebuilds der App erstellen und bereitstellen. .NET Native\-Binärdateien befinden sich im Unterverzeichnis ILC.out des Verzeichnisses, das im Textfeld **Buildausgabepfad** des Dialogfelds **Eigenschaften** des Projekts auf der Registerkarte **Kompilieren** angegeben ist. Binärdateien, die sich nicht in diesem Ordner befinden, wurden nicht mit .NET Native kompiliert. Testen Sie Ihre App gründlich, und testen Sie alle Szenarien, auch Ausfallszenarien, für sämtliche Zielplattformen.  
  
 Wenn Ihre App nicht ordnungsgemäß funktioniert \(insbesondere in Fällen, in denen zur Laufzeit die Ausnahmen [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) oder [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md) ausgelöst werden\), folgen Sie den Anweisungen im nächsten Abschnitt, [Schritt 5: Manuelles Beheben fehlender Metadaten](#Step6). Das Aktivieren von Ausnahmen der ersten Chance kann hilfreich sein, um diese Fehler zu finden.  
  
 Wenn Sie die Debugversionen der App getestet und debuggt haben und sicher sind, dass Sie die Ausnahmen [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) und [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md) beseitigt haben, sollten Sie die App als optimierte [!INCLUDE[net_native](../../../includes/net-native-md.md)]\-App testen. Zu diesem Zweck ändern Sie die aktive Projektkonfiguration von **Debug** in **Release**.  
  
<a name="Step6"></a>   
## Schritt 4: Manuelles Beheben fehlender Metadaten  
 Der häufigste Fehler, der mit [!INCLUDE[net_native](../../../includes/net-native-md.md)] auftritt und auf dem Desktop nicht, ist eine [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)\-, [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md)\- oder [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)\-Laufzeitausnahme. In einigen Fällen kann das Fehlen von Metadaten zu unvorhersehbarem Verhalten oder sogar zu App\-Fehlern führen. Dieser Abschnitt beschreibt, wie Sie diese Ausnahmen debuggen und beheben können, indem Sie Direktiven zur Laufzeitdirektivendatei hinzufügen. Informationen zum Format von Laufzeitdirektiven finden Sie unter [Laufzeitdirektiven\-Konfigurationsdatei \(rd.xml\) Referenz](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md). Nach dem Hinzufügen von Laufzeitdirektiven sollten Sie [die App erneut bereitstellen und testen](#Step5) und ggf. alle neuen [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)\-, [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md)\- und  [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)\-Ausnahmen auflösen, bis keine Ausnahmen mehr auftreten.  
  
> [!TIP]
>  Geben Sie die Laufzeitdirektiven auf einer hohen Ebene an, um Ihre App flexibel in Bezug auf Codeänderungen zu machen.  Es wird empfohlen, Laufzeitdirektiven auf Namespace\- und Typebene statt auf Memberebene hinzufügen. Beachten Sie, dass möglicherweise ein Kompromiss zwischen Flexibilität und größeren Binärdateien mit längeren Kompilierungszeiten gefunden werden muss.  
  
 Beim Behandeln einer Ausnahme wegen fehlender Metadaten sollten Sie Folgendes berücksichtigen:  
  
-   Was versuchte die App vor der Ausnahme auszuführen?  
  
    -   Versuchte sie beispielsweise Daten zu binden, zu serialisieren oder zu deserialisieren oder direkt die Reflektions\-API zu verwenden?  
  
-   Ist dies ein Einzelfall, oder glauben Sie, dass das gleiche Problem für andere Typen auftreten wird?  
  
    -   Eine [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)\-Ausnahme wird beispielsweise ausgelöst, wenn ein Typ im Objektmodell der App serialisiert wird.  Wenn Sie andere Typen kennen, die serialisiert werden, können Sie gleichzeitig Laufzeitdirektiven für diese Typen hinzufügen \(oder für deren enthaltende Namespaces, je nachdem, wie gut der Code strukturiert ist\).  
  
-   Können Sie den Code so umschreiben, dass die Reflektion nicht verwendet wird?  
  
    -   Verwendet der Code zum Beispiel das Schlüsselwort `dynamic`, wenn Sie wissen, welcher Typ zu erwarten ist?  
  
    -   Ruft der Code eine Methode auf, die von Reflektion abhängt, wenn eine bessere Alternative zur Verfügung steht?  
  
> [!NOTE]
>  Weitere Informationen zur Behandlung von Problemen, die sich aus Unterschieden in der Reflektion und der Verfügbarkeit von Metadaten in Desktop\-Apps und [!INCLUDE[net_native](../../../includes/net-native-md.md)] ergeben, finden Sie unter [APIs, die auf Refelktion beruhen](../../../docs/framework/net-native/apis-that-rely-on-reflection.md).  
  
 Einige spezifische Beispiele für das Behandeln von Ausnahmen und anderen Problemen beim Testen der App finden Sie unter:  
  
-   [Beispiel: Behandeln von Ausnahmen beim Binden von Daten](../../../docs/framework/net-native/example-handling-exceptions-when-binding-data.md)  
  
-   [Beispiel: Problembehandlung bei dynamischer Programmierung](../../../docs/framework/net-native/example-troubleshooting-dynamic-programming.md)  
  
-   [Laufzeitausnahmen in .NET Native\-Apps](../../../docs/framework/net-native/runtime-exceptions-in-net-native-apps.md)  
  
## Siehe auch  
 [Laufzeitdirektiven\-Konfigurationsdatei \(rd.xml\) Referenz](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [NIB: .NET Native Einrichtung und Konfiguration](http://msdn.microsoft.com/de-de/7c9bc375-8b87-4c33-bede-72d513e362ec)   
 [.NET Native und Kompilierung](../../../docs/framework/net-native/net-native-and-compilation.md)   
 [Reflektion und .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md)   
 [APIs, die auf Refelktion beruhen](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)   
 [Serialisierung und Metadaten](../../../docs/framework/net-native/serialization-and-metadata.md)   
 [Migrieren der Windows Store\-App auf .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)