---
title: Benutzerdefinierte Vorlagen für dotnet new
description: Erfahren Sie mehr zu benutzerdefinierten Vorlagen für alle Arten von .NET-Projekten und -Dateien.
author: guardrex
ms.author: mairaw
ms.date: 08/11/2017
ms.openlocfilehash: 5cb160683ad373f1192945163495bf3e7957567b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43525966"
---
# <a name="custom-templates-for-dotnet-new"></a>Benutzerdefinierte Vorlagen für dotnet new

Das [.NET Core SDK](https://www.microsoft.com/net/download/core) enthält viele vorinstallierte Vorlagen, die Sie mit dem [`dotnet new`-Befehl](dotnet-new.md) verwenden können. Ab .NET Core 2.0 können Sie Ihre eigenen benutzerdefinierten Vorlagen für jeden Projekttyp (App, Dienst, Tool, Klassenbibliothek usw.) erstellen. Sie könne sogar eine Vorlage erstellen, die mindestens eine unabhängige Datei ausgibt, wie z.B. eine Konfigurationsdatei.

Sie können benutzerdefinierte Vorlagen aus NuGet-Paketen in jedem NuGet-Feed installieren, indem Sie direkt auf eine *NUPKG*-NuGet-Datei verweisen, oder indem Sie ein Dateisystemverzeichnis angeben, das die Vorlage enthält. Die Vorlagen-Engine bietet Features, mit denen Sie Werte ersetzen, Dateien und Bereiche von Dateien ein- oder ausschließen und benutzerdefinierte Verarbeitungsvorgänge ausführen können, wenn Ihre Vorlage verwendet wird.

Die Vorlagen-Engine ist Open Source, und das Onlinecoderepository befindet sich unter [dotnet/templating](https://github.com/dotnet/templating/) auf GitHub. Navigieren Sie zum Repository [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples), wo sie Beispielvorlagen finden. Weitere Vorlagen, einschließlich Drittanbietervorlagen, finden Sie auf GitHub unter [Verfügbare Vorlagen für dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new). Weitere Informationen zum Erstellen und Verwenden von benutzerdefinierten Vorlagen finden Sie unter [How to create your own templates for dotnet new (Erstellen Ihrer eigenen Vorlage für dotnet new)](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/) und im [GitHub-Repositorywiki dotnet/templating](https://github.com/dotnet/templating/wiki).

Eine exemplarische Vorgehensweise zum Erstellen einer Vorlage finden Sie im Tutorial [Create a custom template for dotnet new (in englischer Sprache)](~/docs/core/tutorials/create-custom-template.md).

## <a name="configuration"></a>Konfiguration

Eine Vorlage besteht aus den folgenden Komponenten:

- Quelldateien und -ordnern
- einer Konfigurationsdatei (*template.json*)

### <a name="source-files-and-folders"></a>Quelldateien und -ordner

Die Quelldateien und -ordner enthalten die Dateien und Ordner, von denen Sie möchten, dass sie von der Vorlagen-Engine verwendet werden, wenn der `dotnet new <TEMPLATE>`-Befehl ausgeführt wird. Die Vorlagen-Engine wurde so entwickelt, dass sie *ausführbare Projekte* als Quellcode verwendet, um Projekte zu erzeugen. Dies hat mehrere Vorteile:

- Sie müssen für die Vorlagen-Engine keine besonderen Token in den Quellcode Ihres Projekts einfügen.
- Die Codedateien sind keine besonderen Dateien. Sie werden auch nicht modifiziert, um mit der Vorlagen-Engine zu funktionieren. Die Tools, die Sie normalerweise mit Projekten verwenden, funktionieren auch mit Vorlageninhalt.
- Das Erstellen, Ausführen und Debuggen Ihrer Projekte erfolgt wie bei Ihren anderen Projekten.
- Sie können eine Vorlage schnell aus einem vorhandenen Projekt erstellen, indem Sie einfach eine *template.json*-Konfigurationsdatei in dem Projekt einfügen.

In der Vorlage gespeicherte Dateien und Ordner sind auf formelle .NET-Projekttypen beschränkt, wie z.B. .NET Core- oder .NET Framework-Projektmappen. Quelldateien und -ordner können aus jedem beliebigen Inhalt bestehen, den Sie erstellen, wenn die Vorlage verwendet wird, auch wenn die Vorlagen-Engine nur eine Datei ausgibt, wie etwa eine Konfigurationsdatei oder eine Projektmappendatei. Sie können z.B. eine Vorlage erstellen, die eine *web.config*-Quelldatei enthält und eine modifizierte *web.config*-Datei für Projekte modifiziert, in denen die Vorlage verwendet wird. Die Modifizierungen von Quelldateien basieren auf Logik und Einstellungen, die Sie in der *template.json*-Konfigurationsdatei zusammen mit den vom Benutzer bereitgestellten Werten bereitgestellt haben. Diese Werte werden als Optionen an den `dotnet new <TEMPLATE>`-Befehl übergeben.

### <a name="templatejson"></a>template.json

Die Datei *template.json* wird in den Ordner *template.config* im Stammverzeichnis der Vorlage platziert. Die Datei bietet der Vorlagen-Engine Konfigurationsinformationen. Die Mindestkonfiguration erfordert die in der folgenden Tabelle aufgelisteten Member, was zum Erstellen einer funktionsfähigen Vorlage ausreicht.

| Member            | Typ          | Beschreibung  |
| ----------------- | ------------- | ----------- |
| `$schema`         | URI           | Das JSON-Schema für die Datei *template.json*. Editor, die JSON-Schemas unterstützen, ermöglichen Features zum Bearbeiten von JSON-Dateien, wenn das Schema angegeben ist. [Visual Studio-Code](https://code.visualstudio.com/) erfordert z.B., dass dieser Member IntelliSense aktiviert. Verwenden Sie den Wert `http://json.schemastore.org/template`. |
| `author`          | Zeichenfolge        | Der Autor der Vorlage. |
| `classifications` | array(string) | Null (0) oder mehr Merkmale der Vorlage, die ein Benutzer verwenden kann, um die Vorlage zu finden. Die Klassifizierungen werden auch in der Spalte *Tags* angezeigt, wenn diese in einer Liste von Vorlagen angezeigt wird, die mit dem <code>dotnet new -l&#124;--list</code>-Befehl erzeugt wurden. |
| `identity`        | Zeichenfolge        | Ein eindeutiger Namen für diese Vorlage |
| `name`            | Zeichenfolge        | Der Name der Vorlage, der Benutzern angezeigt wird |
| `shortName`       | Zeichenfolge        | Die Standardkurzform zum Auswählen der Vorlage, die für Umgebungen gilt, in denen der Vorlagenname vom Benutzer angegeben wird und nicht über eine GUI. Die Kurzform kann z.B. nützlich sein, wenn Sie Vorlagen aus einer Eingabeaufforderung mit CLI-Befehlen verwenden. |

#### <a name="example"></a>Beispiel:

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Catalina Garcia",
  "classifications": [ "Common", "Console" ],
  "identity": "GarciaSoftware.ConsoleTemplate.CSharp",
  "name": "Garcia Software Console Application",
  "shortName": "garciaconsole"
}
```

Das vollständige Schema für die Datei *template.json* finden Sie im [JSON-Schemaspeicher](http://json.schemastore.org/template).

## <a name="net-default-templates"></a>.NET-Standardvorlagen

Wenn Sie das [.NET Core SDK](https://www.microsoft.com/net/download/core) installieren, erhalten Sie mehr als zwölf integrierte Vorlagen zum Erstellen von Projekten und Dateien, einschließlich Konsolenanwendungen, Klassenbibliotheken, Komponententestprojekten, ASP.NET Core-Apps (einschließlich [Angular](https://angular.io/)- und [React](https://facebook.github.io/react/)-Projekten), und von Konfigurationsdateien. Um die integrierten Vorlagen aufzulisten, führen Sie den `dotnet new`-Befehl mit der `-l|--list`-Option aus:

```console
dotnet new -l
```

## <a name="packing-a-template-into-a-nuget-package-nupkg-file"></a>Verpacken einer Vorlage in ein NuGet-Paket (NUPKG-Datei)

Aktuell wird eine benutzerdefinierte Vorlage unter Windows mit der Datei [nuget.exe](https://dist.nuget.org/win-x86-commandline/latest/nuget.exe) verpackt (und nicht mit [dotnet pack](dotnet-pack.md)). Ziehen Sie für das plattformübergreifende Verpacken [NuGetizer 3000](https://github.com/NuGet/Home/wiki/NuGetizer-3000) in Betracht.

Der Inhalt des Projektordners wird gemeinsam mit seiner Datei *.template.config/template.json* in den Ordner *content* eingefügt. Fügen Sie neben dem *content*-Ordner eine [*NUSPEC*-Datei](/nuget/create-packages/creating-a-package) hinzu, die eine XML-Manifestdatei ist, die den Inhalt eines Paktes beschreibt und den Erstellungsprozess des NuGet-Pakets vorantreibt. Fügen Sie im **\<packageTypes>**-Element einer *NUSPEC*-Datei ein **\<packageType>** mit einem `name`-Attributwert von `Template` ein. Der Ordner *content* und die Datei *NUSPEC* sollten sich im gleichen Verzeichnis befinden. In der Tabelle werden die *NUSPEC*-Dateielemente gezeigt, die mindestens erforderlich sind, um eine Vorlage als NuGet-Paket zu erstellen.

| Element            | Typ   | Beschreibung  |
| ------------------ | ------ | ----------- |
| **\<authors>**     | Zeichenfolge | Eine durch Kommas getrennte Liste der Paketautoren, die mit Profilnamen unter nuget.org übereinstimmen. Autoren werden im NuGet-Katalog unter nuget.org angezeigt und werden verwendet, um Querverweise auf Pakete der gleichen Autoren zu geben. |
| **\<description>** | Zeichenfolge | Eine ausführliche Beschreibung des Pakets für die Anzeige der Benutzeroberfläche. |
| **\<id>**          | Zeichenfolge | Der Paketbezeichner, der die Groß- und Kleinschreibung nicht beachtet, der auf nuget.org oder im für das Paket verwendeten Katalog eindeutig sein muss. IDs dürfen keine Leerzeichen oder für eine URL unzulässige Zeichen enthalten. Sie müssen den Regeln für .NET Namespaces entsprechen. Informationen finden Sie im Abschnitt [Wählen eines eindeutigen Paketbezeichners und Festlegen der Versionsnummer](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number). |
| **\<packageType>** | Zeichenfolge | Fügen Sie dieses Element in ein **\<packageTypes>**-Element bei den **\<metadata>**-Elementen ein. Legen Sie das `name`-Attribut des **\<packageType>**-Elements auf `Template` fest. |
| **\<version>**     | Zeichenfolge | Die Version des Pakets, die dem Format „hauptversion.nebenversion.patch“ folgt. Versionsnummern enthalten möglicherweise ein Suffix der Vorabversion, wie im Artikel zu [Vorabversionen](/nuget/create-packages/prerelease-packages#semantic-versioning) beschrieben. |

Das vollständige *NUSPEC*-Dateischema finden Sie in der [.nuspec-Referenz](/nuget/schema/nuspec). Eine *NUSPEC*-Beispieldatei für eine Vorlage wird im Tutorial [Create a custom template for dotnet new (Erstellen einer benutzerdefinierten Vorlage für dotnet new)](~/docs/core/tutorials/create-custom-template.md) verwendet.

[Erstellen Sie ein Paket](/nuget/create-packages/creating-a-package#creating-the-package) mit dem Befehl `nuget pack <PATH_TO_NUSPEC_FILE>`.

## <a name="installing-a-template"></a>Installieren einer Vorlage

Installieren Sie benutzerdefinierte Vorlagen aus NuGet-Paketen in jedem NuGet-Feed, indem Sie direkt auf eine *NUPKG*-Datei verweisen, oder indem Sie ein Dateisystemverzeichnis angeben, das eine Vorlagenkonfiguration enthält. Verwenden Sie die `-i|--install`-Option mit dem [dotnet new](dotnet-new.md)-Befehl.

### <a name="to-install-a-template-from-a-nuget-package-stored-at-nugetorg"></a>So installieren Sie eine Vorlage aus einem NuGet-Paket, das auf nuget.org gespeichert ist.

```console
dotnet new -i <NUGET_PACKAGE_ID>
```

### <a name="to-install-a-template-from-a-local-nupkg-file"></a>So installieren Sie eine Vorlage aus einer lokalen NUPKG-Datei

```console
dotnet new -i <PATH_TO_NUPKG_FILE>
```

### <a name="to-install-a-template-from-a-file-system-directory"></a>So installieren Sie eine Vorlage aus einem Dateisystemverzeichnis

Das `FILE_SYSTEM_DIRECTORY` ist der Projektordner, der das Projekt und den Ordner *.template.config* enthält:

```console
dotnet new -i <FILE_SYSTEM_DIRECTORY>
```

## <a name="uninstalling-a-template"></a>Deinstallieren einer Vorlage

Deinstallieren Sie benutzerdefinierte Vorlagen, indem Sie mit der entsprechenden `id` auf ein NuGet-Paket verweisen, oder indem Sie ein Dateisystemverzeichnis angeben, das eine Vorlagenkonfiguration enthält. Verwenden Sie die `-u|--uninstall`-Installationsoption mit dem [dotnet new](dotnet-new.md)-Befehl.

### <a name="to-uninstall-a-template-from-a-nuget-package-stored-at-nugetorg"></a>So deinstallieren Sie eine Vorlage aus einem NuGet-Paket, das auf nuget.org gespeichert ist.

```console
dotnet new -u <NUGET_PACKAGE_ID>
```

### <a name="to-uninstall-a-template-from-a-local-nupkg-file"></a>So deinstallieren Sie eine Vorlage aus einer lokalen NUPKG-Datei

Wenn Sie eine Vorlage deinstallieren möchten, versuchen Sie dies nicht mit dem Pfad der *NUPKG*-Datei. *Die Deinstallation der Vorlage mit `dotnet new -u <PATH_TO_NUPKG_FILE>` schlägt fehl.* Verweisen Sie mit der entsprechenden `id` auf das Paket.

```console
dotnet new -u <NUGET_PACKAGE_ID>
```

### <a name="to-uninstall-a-template-from-a-file-system-directory"></a>So deinstallieren Sie eine Vorlage aus einem Dateisystemverzeichnis

Das `FILE_SYSTEM_DIRECTORY` ist der Projektordner, der das Projekt und den Ordner *.template.config* enthält:

```console
dotnet new -u <FILE_SYSTEM_DIRECTORY>
```

## <a name="create-a-project-using-a-custom-template"></a>Erstellen einer Projekt mit einer benutzerdefinierten Vorlage

Nachdem eine Vorlage installiert wurde, verwenden Sie die Vorlage, indem Sie den `dotnet new <TEMPLATE>`-Befehl ausführen, wie Sie es auch mit jeder anderen vorinstallierten Vorlage machen würden. Sie können zudem [Optionen](dotnet-new.md#options) für den `dotnet new`-Befehl festlegen, einschließlich vorlagenspezifischer Optionen, die Sie in den Vorlageneinstellungen vorgenommen haben. Geben Sie die Kurzform des Namens der Vorlage für den Befehl an:

```console
dotnet new <TEMPLATE>
```

## <a name="see-also"></a>Siehe auch

* [Create a custom template for dotnet new (tutorial) (Erstellen einer benutzerdefinierten Vorlage für dotnet new (Tutorial))](../tutorials/create-custom-template.md)  
* [dotnet/templating GitHub repo Wiki (GitHub-Repositorywiki dotnet/templating)](https://github.com/dotnet/templating/wiki)  
* [dotnet/dotnet-template-samples-GitHub-Repository](https://github.com/dotnet/dotnet-template-samples)  
* [How to create your own templates for dotnet new (So erstellen Sie Ihre eigenen Vorlagen für dotnet new)](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/)  
* [*template.json*-Schema im JSON-Schemaspeicher](http://json.schemastore.org/template)  
