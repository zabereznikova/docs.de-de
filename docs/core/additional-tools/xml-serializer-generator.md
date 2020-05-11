---
title: Microsoft XML Serializer Generator
description: Übersicht zum Microsoft XML Serializer Generator. Verwenden Sie den XML Serializer Generator, um eine XML-Serialisierungsassembly für die in Ihrem Projekt enthaltenen Typen zu generieren.
author: mlacouture
ms.date: 01/19/2017
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c3f1fcda8a8a6abc58d35bf37e51485bb3590fa3
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794636"
---
# <a name="using-microsoft-xml-serializer-generator-on-net-core"></a>Verwenden des Microsoft XML Serializer Generators auf .NET Core

In diesem Tutorial erfahren Sie, wie Sie den Microsoft XML Serializer Generator in einer .NET Core-Anwendung für C# verwenden. Im Verlauf dieses Tutorials lernen Sie Folgendes:

> [!div class="checklist"]
>
> - Erstellen einer .NET Core-App
> - Hinzufügen eines Verweises zum Microsoft.XmlSerializer.Generator-Paket
> - Bearbeiten Ihrer MyApp.csproj-Datei zum Hinzufügen von Abhängigkeiten
> - Hinzufügen von „XmlSerializer“ und einer Klasse
> - Erstellen und Ausführen der Anwendung

Das [NuGet-Paket „Microsoft.XmlSerializer.Generator“](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) gilt (wie der [XML Serializer Generator (sgen.exe)](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) für .NET Framework) für .NET Core- und .NET Standard-Projekte. Es erstellt eine XML-Serialisierungsassembly für Typen, die in einer Assembly vorhanden sind, um die Startleistung der XML-Serialisierung zu verbessern, wenn Objekte dieser Typen mithilfe von <xref:System.Xml.Serialization.XmlSerializer> serialisiert oder deserialisiert werden.

## <a name="prerequisites"></a>Voraussetzungen

Zum Abschließen dieses Tutorials benötigen Sie Folgendes:

- [.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) oder höher
- Ihren bevorzugten Code-Editor

> [!TIP]
> Benötigen Sie einen Code-Editor? Testen Sie [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs).

## <a name="use-microsoft-xml-serializer-generator-in-a-net-core-console-application"></a>Verwenden des Microsoft XML Serializer Generators in einer .NET Core-Konsolenanwendung

In den folgenden Anweisungen wird erläutert, wie Sie den XML Serializer Generator in einer .NET Core-Konsolenanwendung verwenden.

### <a name="create-a-net-core-console-application"></a>Erstellen einer .NET Core-Konsolenanwendung

Öffnen Sie eine Eingabeaufforderung, und erstellen Sie einen Ordner mit dem Namen *MyApp*. Navigieren Sie zum erstellten Ordner, und geben Sie den folgenden Befehl ein:

```dotnetcli
dotnet new console
```

### <a name="add-a-reference-to-the-microsoftxmlserializergenerator-package-in-the-myapp-project"></a>Hinzufügen eines Verweises zum Microsoft.XmlSerializer.Generator-Paket im MyApp-Projekt

Verwenden Sie den [`dotnet add package`](../tools/dotnet-add-package.md)-Befehl, um den Verweis Ihrem Projekt hinzuzufügen.

Typ:

```dotnetcli
dotnet add package Microsoft.XmlSerializer.Generator -v 1.0.0
```

### <a name="verify-changes-to-myappcsproj-after-adding-the-package"></a>Überprüfen der Änderungen an der MyApp.csproj-Datei nach dem Hinzufügen des Pakets

Öffnen Sie Ihren Code-Editor, um zu beginnen. Sie arbeiten weiterhin mit dem *MyApp*-Verzeichnis, in dem die App erstellt wurde.

Öffnen Sie *MyApp.csproj* in Ihrem Text-Editor.

Wenn Sie den Befehl [`dotnet add package`](../tools/dotnet-add-package.md) ausführen, werden die folgenden Zeilen zu Ihrer *MyApp.csproj*-Projektdatei hinzugefügt:

 ```xml
 <ItemGroup>
    <PackageReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```

### <a name="add-another-itemgroup-section-for-net-core-cli-tool-support"></a>Hinzufügen eines weiteren ItemGroup-Abschnitts zur Unterstützung des .NET Core-CLI-Tools

Fügen Sie nach dem zuvor betrachteten Abschnitt `ItemGroup` die folgenden Zeilen hinzu:

 ```xml
 <ItemGroup>
    <DotNetCliToolReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```

### <a name="add-a-class-in-the-application"></a>Hinzufügen einer Klasse zu der Anwendung

Öffnen Sie *Program.cs* in Ihrem Text-Editor. Fügen Sie die Klasse mit dem Namen *MyClass* unter *Program.cs* hinzu.

```csharp
public class MyClass
{
   public int Value;
}
```

### <a name="create-an-xmlserializer-for-myclass"></a>Erstellen eines `XmlSerializer` für MyClass

Fügen Sie die folgende Zeile unter *Main* hinzu, um einen `XmlSerializer` für MyClass zu erstellen:

```csharp
var serializer = new System.Xml.Serialization.XmlSerializer(typeof(MyClass));
```

### <a name="build-and-run-the-application"></a>Erstellen und Ausführen der Anwendung

Führen Sie (immer noch im Ordner *MyApp*) die Anwendung über [`dotnet run`](../tools/dotnet-run.md) aus. Dann werden die zuvor generierten Serializer zur Runtime automatisch geladen und verwendet.

Geben Sie den folgenden Befehl in Ihr Konsolenfenster ein:

```dotnetcli
dotnet run
```

> [!NOTE]
> [`dotnet run`](../tools/dotnet-run.md) ruft [`dotnet build`](../tools/dotnet-build.md) auf, um sicherzustellen, dass die Buildziele erstellt wurden, und ruft anschließend `dotnet <assembly.dll>` auf, um die Zielanwendung auszuführen.

> [!IMPORTANT]
> Die Befehle und Schritte zum Ausführen der Anwendung, die in diesem Tutorial dargestellt werden, werden nur während zur Entwicklungszeit verwendet. Wenn Ihre Anwendung bereitgestellt werden kann, sollten Sie einen Blick auf die verschiedenen [Bereitstellungsstrategien](../deploying/index.md) für .NET Core-Apps und den [`dotnet publish`](../tools/dotnet-publish.md)-Befehl werfen.

Wenn alle Vorgänge erfolgreich ausgeführt werden, wird eine Assembly mit dem Namen *MyApp.XmlSerializers.dll* im Ausgabeordner generiert.

Herzlichen Glückwunsch! Sie haben gerade:
> [!div class="checklist"]
>
> - eine lokale .NET Core-App erstellt
> - einen Verweis zum Microsoft.XmlSerializer.Generator-Paket hinzugefügt
> - Ihre MyApp.csproj-Datei bearbeitet, um Abhängigkeiten hinzuzufügen
> - „XmlSerializer“ und eine Klasse hinzugefügt
> - die Anwendung erstellt und ausgeführt

## <a name="related-resources"></a>Verwandte Ressourcen

- [Einführung in die XML-Serialisierung](../../standard/serialization/introducing-xml-serialization.md)
- [Vorgehensweise: Serialisieren mit XmlSerializer (C#)](../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)
- [How to: Serialize Using XmlSerializer (Visual Basic) (Vorgehensweise: Serialisieren mit „XmlSerializer“ (Visual Basic))](../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)
