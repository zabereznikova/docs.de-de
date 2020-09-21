---
title: Benutzerdefinierte Vorlagen für dotnet new
description: Erfahren Sie mehr zu benutzerdefinierten Vorlagen für alle Arten von .NET-Projekten und -Dateien.
author: adegeo
ms.date: 05/20/2020
ms.openlocfilehash: 1d2e5ffcb0b279f1686855834c2357827a4dc7d5
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538094"
---
# <a name="custom-templates-for-dotnet-new"></a>Benutzerdefinierte Vorlagen für dotnet new

Das [.NET Core SDK](https://dotnet.microsoft.com/download) enthält viele Vorlagen, die bereits installiert und sofort einsatzbereit sind. Der Befehl [`dotnet new`](dotnet-new.md) bietet nicht nur eine Möglichkeit, eine Vorlage zu verwenden, sondern auch, um Vorlagen zu installieren und zu deinstallieren. Ab .NET Core 2.0 können Sie Ihre eigenen benutzerdefinierten Vorlagen für jeden Projekttyp (App, Dienst, Tool, Klassenbibliothek usw.) erstellen. Sie könne sogar eine Vorlage erstellen, die mindestens eine unabhängige Datei ausgibt, wie z.B. eine Konfigurationsdatei.

Sie können benutzerdefinierte Vorlagen aus NuGet-Paketen in jedem NuGet-Feed installieren, indem Sie direkt auf eine NuGet-Datei des Typs *.nupkg* verweisen, oder indem Sie ein Dateisystemverzeichnis angeben, das die Vorlage enthält. Das Vorlagenmodul bietet Features, mit denen Sie Werte ersetzen, Dateien ein- oder ausschließen und benutzerdefinierte Verarbeitungsvorgänge ausführen können, wenn Ihre Vorlage verwendet wird.

Die Vorlagen-Engine ist Open Source, und das Onlinecoderepository befindet sich unter [dotnet/templating](https://github.com/dotnet/templating/) auf GitHub. Weitere Vorlagen, einschließlich Drittanbietervorlagen, finden Sie auf GitHub unter [Verfügbare Vorlagen für dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new). Weitere Informationen zum Erstellen und Verwenden von benutzerdefinierten Vorlagen finden Sie unter [How to create your own templates for dotnet new (Erstellen Ihrer eigenen Vorlage für dotnet new)](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/) und im [GitHub-Repositorywiki dotnet/templating](https://github.com/dotnet/templating/wiki).

> [!NOTE]
> Vorlagenbeispiele finden Sie im [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples)-GitHub-Repository. Obwohl diese Beispiele eine gute Ressource sind, um zu lernen, wie die Vorlagen funktionieren, wird das Repository archiviert und nicht mehr verwaltet. Die Beispiele sind möglicherweise veraltet und funktionieren nicht mehr.

Eine exemplarische Vorgehensweise zum Erstellen einer Vorlage finden Sie im Tutorial [Create a custom template for dotnet new (in englischer Sprache)](../tutorials/cli-templates-create-item-template.md).

### <a name="net-default-templates"></a>.NET-Standardvorlagen

Wenn Sie das [.NET Core SDK](https://dotnet.microsoft.com/download) installieren, erhalten Sie mehr als zwölf integrierte Vorlagen zum Erstellen von Projekten und Dateien, einschließlich Konsolenanwendungen, Klassenbibliotheken, Komponententestprojekten, ASP.NET Core-Apps (einschließlich [Angular](https://angular.io/)- und [React](https://facebook.github.io/react/)-Projekten), und von Konfigurationsdateien. Um die integrierten Vorlagen aufzulisten, führen Sie den `dotnet new`-Befehl mit der `-l|--list`-Option aus:

```dotnetcli
dotnet new --list
```

## <a name="configuration"></a>Konfiguration

Eine Vorlage besteht aus den folgenden Teilen:

- Quelldateien und -ordner
- Konfigurationsdatei (*template.json*)

### <a name="source-files-and-folders"></a>Quelldateien und -ordner

Die Quelldateien und -ordner enthalten die Dateien und Ordner, von denen Sie möchten, dass sie vom Vorlagenmodul verwendet werden, wenn der `dotnet new <TEMPLATE>`-Befehl ausgeführt wird. Die Vorlagen-Engine wurde so entwickelt, dass sie *ausführbare Projekte* als Quellcode verwendet, um Projekte zu erzeugen. Dies hat mehrere Vorteile:

- Sie müssen für die Vorlagen-Engine keine besonderen Token in den Quellcode Ihres Projekts einfügen.
- Die Codedateien sind keine besonderen Dateien. Sie werden auch nicht modifiziert, um mit der Vorlagen-Engine zu funktionieren. Die Tools, die Sie normalerweise mit Projekten verwenden, funktionieren auch mit Vorlageninhalt.
- Das Erstellen, Ausführen und Debuggen Ihrer Projekte erfolgt wie bei Ihren anderen Projekten.
- Sie können eine Vorlage schnell anhand eines vorhandenen Projekts erstellen, indem Sie einfach die Konfigurationsdatei *./.template.config/template.json* dem Projekt hinzufügen.

In der Vorlage gespeicherte Dateien und Ordner sind nicht auf formelle .NET-Projekttypen beschränkt. Quelldateien und -ordner können aus jedem beliebigen Inhalt bestehen, den Sie erstellen möchten, wenn die Vorlage verwendet wird, auch wenn das Vorlagenmodul nur eine Datei ausgibt.

Dateien, die anhand der Vorlage generiert werden, können basierend auf der Logik und den Einstellungen, die Sie in der Konfigurationsdatei *template.json* angegeben haben, geändert werden. Der Benutzer kann diese Einstellungen überschreiben, indem er Optionen an den Befehl `dotnet new <TEMPLATE>` übergibt. Ein häufiges Beispiel für benutzerdefinierte Logik ist die Bereitstellung eines Namens für eine Klasse oder Variable in der Codedatei, die von einer Vorlage bereitgestellt wird.

### <a name="templatejson"></a>template.json

Die Datei *template.json* wird in den Ordner *template.config* im Stammverzeichnis der Vorlage platziert. Die Datei bietet der Vorlagen-Engine Konfigurationsinformationen. Die Mindestkonfiguration erfordert die in der folgenden Tabelle aufgelisteten Member, was zum Erstellen einer funktionsfähigen Vorlage ausreicht.

| Member            | Typ          | Beschreibung |
| ----------------- | ------------- | ----------- |
| `$schema`         | URI           | Das JSON-Schema für die Datei *template.json*. Editor, die JSON-Schemas unterstützen, ermöglichen Features zum Bearbeiten von JSON-Dateien, wenn das Schema angegeben ist. [Visual Studio-Code](https://code.visualstudio.com/) erfordert z.B., dass dieser Member IntelliSense aktiviert. Verwenden Sie den Wert `http://json.schemastore.org/template`. |
| `author`          | string        | Der Autor der Vorlage. |
| `classifications` | array(string) | Null (0) oder mehr Merkmale der Vorlage, die ein Benutzer verwenden kann, um die Vorlage zu finden. Die Klassifizierungen werden auch in der Spalte *Tags* angezeigt, wenn diese in einer Liste von Vorlagen angezeigt wird, die mit dem `dotnet new -l|--list`-Befehl erzeugt wurden. |
| `identity`        | string        | Ein eindeutiger Namen für diese Vorlage |
| `name`            | string        | Der Name der Vorlage, der Benutzern angezeigt wird |
| `shortName`       | string        | Ein Standardkurzname zum Auswählen der Vorlage, die für Umgebungen gilt, in denen der Vorlagenname vom Benutzer angegeben wird und nicht über eine grafische Benutzeroberfläche. Die Kurzform kann z.B. nützlich sein, wenn Sie Vorlagen aus einer Eingabeaufforderung mit CLI-Befehlen verwenden. |

Das vollständige Schema für die Datei *template.json* finden Sie im [JSON-Schemaspeicher](http://json.schemastore.org/template). Weitere Informationen zur Datei *template.json* finden Sie im [Wiki zur Erstellung von .NET-Vorlagen](https://github.com/dotnet/templating/wiki).

#### <a name="example"></a>Beispiel

Hier ist zum Beispiel ein Vorlagenordner, der zwei Inhaltsdateien enthält: *console.cs* und *readme.txt*. Beachten Sie, dass es den erforderlichen Ordner namens *.template.config* gibt, der die Datei *template.json* enthält.

```text
└───mytemplate
    │   console.cs
    │   readme.txt
    │
    └───.template.config
            template.json
```

Die Datei *template.json* sieht wie folgt aus:

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Travis Chau",
  "classifications": [ "Common", "Console" ],
  "identity": "AdatumCorporation.ConsoleTemplate.CSharp",
  "name": "Adatum Corporation Console Application",
  "shortName": "adatumconsole"
}
```

Der Ordner *mytemplate* ist ein installierbares Vorlagenpaket. Sobald das Paket installiert ist, kann `shortName` mit dem Befehl `dotnet new` verwendet werden. Beispielsweise würde `dotnet new adatumconsole` die Dateien `console.cs` und `readme.txt` im aktuellen Ordner ausgeben.

## <a name="packing-a-template-into-a-nuget-package-nupkg-file"></a>Verpacken einer Vorlage in ein NuGet-Paket (NUPKG-Datei)

Eine benutzerdefinierte Vorlage wird mit dem Befehl [dotnet pack](dotnet-pack.md) und *CSPROJ*-Datei gepackt. Alternativ kann [NuGet](/nuget/tools/nuget-exe-cli-reference) mit dem Befehl [nuget pack](/nuget/tools/cli-ref-pack) zusammen mit einer *NUSPEC*-Datei verwendet werden. NuGet setzt jedoch .NET Framework unter Windows und [Mono](https://www.mono-project.com/) unter Linux und macOS voraus.

Die *CSPROJ*-Datei unterscheidet sich geringfügig von einer herkömmlichen Codeprojektdatei des Typs *.csproj*. Beachten Sie die folgenden Einstellungen:

01. Die Einstellung `<PackageType>` wird hinzugefügt und auf `Template` festgelegt.
01. Die Einstellung `<PackageVersion>` wird hinzugefügt und auf eine gültige [NuGet-Versionsnummer](/nuget/reference/package-versioning) festgelegt.
01. Die Einstellung `<PackageId>` wird hinzugefügt und auf einen eindeutigen Bezeichner festgelegt. Dieser Bezeichner dient zur Deinstallation des Vorlagenpakets und wird von NuGet-Feeds verwendet, um Ihr Vorlagenpaket zu registrieren.
01. Allgemeine Metadateneinstellungen müssen festgelegt werden: `<Title>`, `<Authors>`, `<Description>` und `<PackageTags>`.
01. Die Einstellung `<TargetFramework>` muss festgelegt werden, auch wenn die vom Vorlagenprozess generierte Binärdatei nicht verwendet wird. Im folgenden Beispiel wird sie auf `netstandard2.0` festgelegt.

Ein Vorlagenpaket in Form eines NuGet-Paket des Typs *.nupkg*. erfordert, dass alle Vorlagen im Ordner *content* innerhalb des Pakets gespeichert werden. Es gibt noch einige weitere Einstellungen, die einer *CSPROJ*-Datei hinzugefügt werden müssen, um sicherzustellen, dass die generierte *NUPKG*-Datei als Vorlagenpaket installiert werden kann:

01. Die Einstellung `<IncludeContentInPack>` wird auf `true` festgelegt, um jede Datei, die das Projekt als **Inhalt** einstuft, in das NuGet-Paket aufzunehmen.
01. Die Einstellung `<IncludeBuildOutput>` wird auf `false` festgelegt, um alle vom Compiler erzeugten Binärdateien aus dem NuGet-Paket auszuschließen.
01. Die Einstellung `<ContentTargetFolders>` wird auf `content` festgelegt. Dadurch wird sichergestellt, dass die als **Inhalt** festgelegten Dateien im Ordner *content* im NuGet-Paket gespeichert werden. Dieser Ordner im NuGet-Paket wird vom .NET-Vorlagensystem analysiert.

Eine einfache Möglichkeit, alle Codedateien von der Kompilierung durch Ihr Vorlagenprojekt auszuschließen, besteht darin, das Element `<Compile Remove="**\*" />` in Ihrer Projektdatei innerhalb eines Elements des Typs `<ItemGroup>` zu verwenden.

Eine einfache Möglichkeit, Ihr Vorlagenpaket zu strukturieren, besteht darin, alle Vorlagen in einzelnen Ordnern und dann jeden Vorlagenordner innerhalb eines Ordners des Typs *templates* abzulegen, der sich im gleichen Verzeichnis wie Ihre *CSPROJ*-Datei befindet. Auf diese Weise können Sie ein einzelnes Projektelement verwenden, um alle Dateien und Ordner als **Inhalt** in die *Vorlagen* aufzunehmen. Erstellen Sie innerhalb eines `<ItemGroup>`-Elements ein `<Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />`-Element.

Hier ein Beispiel einer *CSPROJ*-Datei, die alle obigen Vorgaben erfüllt. Der untergeordnete Ordner *templates* wird im Paketordner *content* gepackt, wobei alle Codedateien von der Kompilierung ausgeschlossen werden.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <PackageType>Template</PackageType>
    <PackageVersion>1.0</PackageVersion>
    <PackageId>AdatumCorporation.Utility.Templates</PackageId>
    <Title>AdatumCorporation Templates</Title>
    <Authors>Me</Authors>
    <Description>Templates to use when creating an application for Adatum Corporation.</Description>
    <PackageTags>dotnet-new;templates;contoso</PackageTags>
    <TargetFramework>netstandard2.0</TargetFramework>

    <IncludeContentInPack>true</IncludeContentInPack>
    <IncludeBuildOutput>false</IncludeBuildOutput>
    <ContentTargetFolders>content</ContentTargetFolders>
  </PropertyGroup>

  <ItemGroup>
    <Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />
    <Compile Remove="**\*" />
  </ItemGroup>

</Project>
```

Das folgende Beispiel veranschaulicht die Datei- und Ordnerstruktur bei Verwendung einer *CSPROJ*-Datei zum Erstellen eines Vorlagenpakets. Die Datei *MyDotnetTemplates.csproj* und der Ordner *templates* befinden sich beide im Stammverzeichnis eines Verzeichnisses namens *project_folder*. Der Ordner *templates* enthält zwei Vorlagen: *mytemplate1* und *mytemplate2*. Jede Vorlage weist Inhaltsdateien und den Ordner *.template.config* mit der Konfigurationsdatei *template.json* auf.

```text
project_folder
│   MyDotnetTemplates.csproj
│
└───templates
    ├───mytemplate1
    │   │   console.cs
    │   │   readme.txt
    │   │
    │   └───.template.config
    │           template.json
    │
    └───mytemplate2
        │   otherfile.cs
        │
        └───.template.config
                template.json
```

## <a name="installing-a-template"></a>Installieren einer Vorlage

Verwenden Sie den Befehl [dotnet new -i|----install](dotnet-new.md), um ein Paket zu installieren.

### <a name="to-install-a-template-from-a-nuget-package-stored-at-nugetorg"></a>So installieren Sie eine Vorlage aus einem NuGet-Paket, das auf nuget.org gespeichert ist.

Verwenden Sie die NuGet-Paket-ID, um ein Vorlagenpaket zu installieren.

```dotnetcli
dotnet new -i <NUGET_PACKAGE_ID>
```

### <a name="to-install-a-template-from-a-local-nupkg-file"></a>So installieren Sie eine Vorlage aus einer lokalen NUPKG-Datei

Geben Sie den Pfad zu einer NuGet-Paketdatei des Typs *.nupkg* an.

```dotnetcli
dotnet new -i <PATH_TO_NUPKG_FILE>
```

### <a name="to-install-a-template-from-a-file-system-directory"></a>So installieren Sie eine Vorlage aus einem Dateisystemverzeichnis

Vorlagen können aus einem Vorlagenordner installiert werden, z.B. dem Ordner *mytemplate1* im obigen Beispiel. Geben Sie den Ordnerpfad des Ordners *.template.config* an. Der Pfad zum Vorlagenverzeichnis muss nicht absolut sein. Allerdings ist ein absoluter Pfad erforderlich, um eine Vorlage zu deinstallieren, die aus einem Ordner installiert wird.

```dotnetcli
dotnet new -i <FILE_SYSTEM_DIRECTORY>
```

## <a name="get-a-list-of-installed-templates"></a>Abrufen einer Liste installierter Vorlagen

Der Deinstallationsbefehl (ohne weitere Parameter) listet alle installierten Vorlagen auf.

```dotnetcli
dotnet new -u
```

Dieser Befehl gibt etwas Ähnliches wie die folgende Ausgabe zurück:

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)
  Microsoft.DotNet.Common.ProjectTemplates.3.0
    Templates:
      Class library (classlib) C#
      Class library (classlib) F#
      Class library (classlib) VB
      Console Application (console) C#
      Console Application (console) F#
      Console Application (console) VB
...
```

Die erste Ebene der Elemente nach `Currently installed items:` sind die Bezeichner, die bei der Deinstallation einer Vorlage verwendet werden. Und im obigen Beispiel sind `Microsoft.DotNet.Common.ItemTemplates` und `Microsoft.DotNet.Common.ProjectTemplates.3.0` aufgelistet. Wenn die Vorlage unter Verwendung eines Dateisystempfads installiert wurde, wird dieser Bezeichner zum Ordnerpfad des Ordners *.template.config*.

## <a name="uninstalling-a-template"></a>Deinstallieren einer Vorlage

Verwenden Sie den Befehl [dotnet new -u|--uninstall](dotnet-new.md), um ein Paket zu deinstallieren.

Wenn das Paket entweder über einen NuGet-Feed oder direkt über eine *NUPKG*-Datei installiert wurde, geben Sie den Bezeichner an.

```dotnetcli
dotnet new -u <NUGET_PACKAGE_ID>
```

Wenn das Paket durch Angabe eines Pfads zum Ordner *.template.config* installiert wurde, verwenden Sie diesen **absoluten** Pfad, um das Paket zu deinstallieren. Sie können den absoluten Pfad der Vorlage in der Ausgabe des Befehls `dotnet new -u` finden. Weitere Informationen finden Sie im Abschnitt [Liste installierter Vorlagen](#get-a-list-of-installed-templates) weiter oben.

```dotnetcli
dotnet new -u <ABSOLUTE_FILE_SYSTEM_DIRECTORY>
```

## <a name="create-a-project-using-a-custom-template"></a>Erstellen einer Projekt mit einer benutzerdefinierten Vorlage

Nachdem eine Vorlage installiert wurde, verwenden Sie die Vorlage, indem Sie den `dotnet new <TEMPLATE>`-Befehl ausführen, wie Sie es auch mit jeder anderen vorinstallierten Vorlage machen würden. Sie können zudem [Optionen](dotnet-new.md#options) für den `dotnet new`-Befehl festlegen, einschließlich vorlagenspezifischer Optionen, die Sie in den Vorlageneinstellungen vorgenommen haben. Geben Sie die Kurzform des Namens der Vorlage für den Befehl an:

```dotnetcli
dotnet new <TEMPLATE>
```

## <a name="see-also"></a>Siehe auch

- [Create a custom template for dotnet new (tutorial) (Erstellen einer benutzerdefinierten Vorlage für dotnet new (Tutorial))](../tutorials/cli-templates-create-item-template.md)
- [dotnet/templating GitHub repo Wiki (GitHub-Repositorywiki dotnet/templating)](https://github.com/dotnet/templating/wiki)
- [dotnet/dotnet-template-samples-GitHub-Repository](https://github.com/dotnet/dotnet-template-samples)
- [How to create your own templates for dotnet new (So erstellen Sie Ihre eigenen Vorlagen für dotnet new)](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/)
- [*template.json*-Schema im JSON-Schemaspeicher](http://json.schemastore.org/template)
