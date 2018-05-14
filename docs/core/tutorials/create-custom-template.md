---
title: Erstellen eines benutzerdefinierten Vorlagen-Assistenten
description: In diesem interessanten Tutorial erfahren Sie, wie Sie eine benutzerdefinierte Vorlage für den dotnet new-Befehl erstellen.
author: guardrex
ms.author: mairaw
ms.date: 08/12/2017
ms.openlocfilehash: fee2709f54395b9926dae904a448cb92aafb5172
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="create-a-custom-template-for-dotnet-new"></a>Erstellen eines benutzerdefinierten Vorlagen-Assistenten

In diesem Tutorial lernen Sie:

- das Erstellen einer einfachen Vorlage aus einem vorhandenen Projekt oder einem neuen Konsolenanwendungsprojekt
- das Verpacken der Vorlage zur Verteilung auf nuget.org oder aus einer lokalen *NUPKG*-Datei
- das Installieren der Vorlage von nuget.org, aus einer lokalen *NUPKG*-Datei oder einem lokalen Dateisystem
- Deinstallieren Sie die Vorlage

Wenn Sie das Tutorial lieber mit einem vollständigen Beispiel durchlaufen möchten, laden Sie die [Beispielprojektvorlage](https://github.com/dotnet/dotnet-template-samples/tree/master/16-nuget-package) herunter. Die Beispielvorlage ist für die NuGet-Verteilung konfiguriert.

Wenn Sie das heruntergeladenen Beispiel mit einer Dateisystemverteilung verwenden möchten, führen Sie Folgendes durch:

- Verschieben Sie den Inhalt des Ordners *content* des Beispiels um eine Ebene nach oben in den Ordner *GarciaSoftware.ConsoleTemplate.CSharp*.
- Löschen Sie den leeren *content*-Ordner.
- Löschen Sie die *NUSPEC*-Datei.

## <a name="prerequisites"></a>Erforderliche Komponenten

- Installieren Sie das [.NET Core 2.0 SDK](https://www.microsoft.com/net/core) oder eine höhere Version.
- Lesen Sie den Referenzartikel [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](../tools/custom-templates.md).

## <a name="create-a-template-from-a-project"></a>Erstellen einer Vorlage aus einem Projekt

Verwenden Sie ein vorhandenes Projekt, von dem Sie wissen, dass es ordnungsgemäß kompiliert und ausgeführt wird, oder erstellen Sie ein neues Konsolen-App-Projekt in einem Ordner auf Ihrer Festplatte. In diesem Tutorial wird davon ausgegangen, dass der Name des Projektordners *GarciaSoftware.ConsoleTemplate.CSharp* ist und dieser unter *Documents\Templates* im Benutzerprofil gespeichert ist. Der Projektvorlagenname im Tutorial folgt dem Format *\<Unternehmensname>.\<Vorlagentyp>.\<Programmiersprache>*, aber Sie können Ihrem Projekt und Ihrer Vorlage einen beliebigen anderen Namen geben.

1. Fügen Sie dem Stamm des Projekts einen Ordner mit dem Namen *.template.config* hinzu.
1. Erstellen Sie im Ordner *.template.config* eine *template.json*-Datei, um Ihre Vorlage zu konfigurieren. Weitere Informationen und Memberdefinitionen für die *template.json*-Datei finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](../tools/custom-templates.md#templatejson) und im [*template.json*-Schema im JSON-Schemaspeicher](http://json.schemastore.org/template).

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

Die Vorlage ist fertig. Jetzt haben Sie zwei Optionen zum Verteilen der Vorlage. Um mit diesem Tutorial fortzufahren, wählen Sie eine der folgenden Optionen aus:

1. [NuGet-Verteilung](#use-nuget-distribution): Installieren Sie die Vorlage aus NuGet oder aus der lokalen *NUPKG*-Datei, und verwenden Sie die installierte Vorlage.
2. [Dateisystemverteilung](#use-file-system-distribution).

## <a name="use-nuget-distribution"></a>Verwenden der NuGet-Verteilung

### <a name="pack-the-template-into-a-nuget-package"></a>Verpacken der Vorlage in ein NuGet-Paket

1. Erstellen Sie einen Ordner für das NuGet-Paket. Im Tutorial ist der Name des Ordners *GarciaSoftware.ConsoleTemplate.CSharp*, und der Ordner wird im Ordner *Documents\NuGetTemplates* des Benutzerprofils erstellt. Erstellen Sie im neuen Vorlagenordner einen Ordner mit dem Namen *content* für die Projektdateien.
1. Kopieren Sie den Inhalt des Projektordners gemeinsam mit seiner Datei *.template.config/template.json* in den Ordner *content*, den Sie erstellt haben.
1. Fügen Sie neben dem *content*-Ordner eine [*NUSPEC*-Datei](/nuget/create-packages/creating-a-package) ein. Die NUSPEC-Datei ist eine XML-Manifestdatei, die den Inhalt eines Paktes beschreibt und den Erstellungsprozess des NuGet-Pakets vorantreibt.
   
   ![Verzeichnisstruktur mit dem Layout des NuGet-Pakets](./media/create-custom-template/nugetdirectorylayout.png)

1. Fügen Sie im **\<packageTypes>**-Element einer *NUSPEC*-Datei ein **\<packageType>** mit einem `name`-Attributwert von `Template` ein. Der Ordner *content* und die Datei *NUSPEC* sollten sich im gleichen Verzeichnis befinden. In der Tabelle werden die *NUSPEC*-Dateielemente gezeigt, die mindestens erforderlich sind, um eine Vorlage als NuGet-Paket zu erstellen.

   | Element            | Typ   | description |
   | ------------------ | ------ | ----------- |
   | **\<authors>**     | Zeichenfolge | Eine durch Kommas getrennte Liste der Paketautoren, die mit Profilnamen unter nuget.org übereinstimmen. Autoren werden im NuGet-Katalog unter nuget.org angezeigt und werden verwendet, um Querverweise auf Pakete der gleichen Autoren zu geben. |
   | **\<description>** | Zeichenfolge | Eine ausführliche Beschreibung des Pakets für die Anzeige der Benutzeroberfläche. |
   | **\<id>**          | Zeichenfolge | Der Paketbezeichner, der die Groß- und Kleinschreibung nicht beachtet, der auf nuget.org oder im für das Paket verwendeten Katalog eindeutig sein muss. IDs dürfen keine Leerzeichen oder für eine URL unzulässige Zeichen enthalten. Sie müssen den Regeln für .NET Namespaces entsprechen. Informationen finden Sie im Abschnitt [Wählen eines eindeutigen Paketbezeichners und Festlegen der Versionsnummer](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number). |
   | **\<packageType>** | Zeichenfolge | Fügen Sie dieses Element in ein **\<packageTypes>**-Element bei den **\<metadata>**-Elementen ein. Legen Sie das `name`-Attribut des **\<packageType>**-Elements auf `Template` fest. |
   | **\<version>**     | Zeichenfolge | Die Version des Pakets, die dem Format „hauptversion.nebenversion.patch“ folgt. Versionsnummern enthalten möglicherweise ein Suffix der Vorabversion, wie im Artikel zu [Vorabversionen](/nuget/create-packages/prerelease-packages#semantic-versioning) beschrieben. |

   Das vollständige *NUSPEC*-Dateischema finden Sie in der [.nuspec-Referenz](/nuget/schema/nuspec).

   Die *NUSPEC*-Datei im Tutorial heißt *GarciaSoftware.ConsoleTemplate.CSharp.nuspec* und enthält Folgendes:

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <package xmlns="http://schemas.microsoft.com/packaging/2012/06/nuspec.xsd">
     <metadata>
       <id>GarciaSoftware.ConsoleTemplate.CSharp</id>
       <version>1.0.0</version>
       <description>
         Creates the Garcia Software console app.
       </description>
       <authors>Catalina Garcia</authors>
       <packageTypes>
         <packageType name="Template" />
       </packageTypes>
     </metadata>
   </package>
   ```

1. [Erstellen Sie das Paket](/nuget/create-packages/creating-a-package#creating-the-package) mit dem Befehl `nuget pack <PATH_TO_NUSPEC_FILE>`. Der folgende Befehl geht davon aus, dass sich der Ordner, der die NuGet-Objekte enthält, unter *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp* befindet. Egal wo Sie den Ordner auf Ihrem System platzieren, der `nuget pack`-Befehl nimmt den Pfad der *NUSPEC*-Datei an:

   ```console
   nuget pack C:\Users\<USER>\Documents\NuGetTemplates\GarciaSoftware.ConsoleTemplate.CSharp\GarciaSoftware.ConsoleTemplate.CSharp.nuspec
   ```

### <a name="publishing-the-package-to-nugetorg"></a>Veröffentlichen des Pakets auf nuget.org

Um Ihr NuGet-Paket zu veröffentlichen, befolgen Sie die Anweisungen unter [Create and publish a package (Erstellen und Veröffentlichen eines Pakets)](/nuget/quickstart/create-and-publish-a-package#publish-the-package). Es wird allerdings empfohlen, dass Sie nicht die Vorlage aus dem Tutorial auf NuGet veröffentlichen, da Sie die Vorlage nicht mehr löschen können, wenn Sie einmal veröffentlicht wurde, sondern Sie können Sie nur aus der Liste entfernen. Jetzt wo Sie ein NuGet-Paket in Form einer *NUPKG*-Datei haben, wird empfohlen, dass Sie die unten stehenden Anweisungen befolgen, um die Vorlage direkt aus der lokalen *NUPKG*-Datei zu installieren.

### <a name="install-the-template-from-a-nuget-package"></a>Installieren der Vorlage aus einem NuGet-Paket

#### <a name="install-the-template-from-the-local-nupkg-file"></a>Installieren der Vorlage aus einer lokalen *NUPKG*-Datei

Um die Vorlage auf der *NUPKG*-Datei, die Sie erstellt haben, zu installieren, verwenden Sie den `dotnet new`-Befehl mit der `-i|--install`-Option,und stellen Sie den Pfad zur *NUPKG*-Datei bereit:

```console
dotnet new -i C:\Users\<USER>\GarciaSoftware.ConsoleTemplate.CSharp.1.0.0.nupkg
```

#### <a name="install-the-template-from-a-nuget-package-stored-at-nugetorg"></a>Installieren einer Vorlage aus einem NuGet-Paket, das auf nuget.org gespeichert ist

Wenn Sie eine Vorlage aus einem NuGet-Paket installieren möchten, das auf nuget.org gespeichert ist, verwenden Sie den `dotnet new`-Befehl mit der `-i|--install`-Option, und geben Sie den Namen des NuGet-Pakets an:

```console
dotnet new -i GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> Das Beispiel dient nur der Veranschaulichung. Auf nuget.org gibt es nur ein `GarciaSoftware.ConsoleTemplate.CSharp`-NuGet-Paket, und es wird empfohlen, dass Sie die Testvorlage von NuGet veröffentlichen und nutzen. Wenn Sie den Befehl ausführen, wird keine Vorlage installiert. Sie können allerdings eine Vorlage installieren, die noch nicht auf nuget.org veröffentlicht wurde, indem Sie direkt in Ihrem lokalen Dateisystem auf eine *NUPKG*-Datei verweisen, wie im vorherigen Abschnitt [Installieren der Vorlage aus einer lokalen NUPKG-Datei](#install-the-template-from-the-local-nupkg-file) gezeigt.

Ein Livebeispiel für die Installation eines Pakets von nuget.org finden Sie unter [NUnit 3 Template](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/). Diese Vorlage richtet ein Projekt für NUnit-Komponententests ein. Verwenden Sie folgenden Befehl, um sie zu installieren:

```console
dotnet new -i NUnit3.DotNetNew.Template
```

Wenn Sie die Vorlagen mit `dotnet new -l` auflisten, sehen Sie *NUnit 3-Testprojekt* mit dem Kurznamen *nunit* in der Vorlagenliste. Im nächsten Abschnitt können Sie die Vorlage verwenden.

![Konsolenfenster, das die NUnit-Vorlage mit anderen installierten Vorlagen zeigt](./media/create-custom-template/nunit1.png)

### <a name="create-a-project-from-the-template"></a>Erstellen eines neuen Projekts aus der Vorlage

Nachdem die Vorlage aus NuGet installiert wurde, verwenden Sie sie, indem Sie den `dotnet new <TEMPLATE>`-Befehl aus dem Verzeichnis ausführen, in das die Ausgabe der Vorlagen-Engine eingefügt werden soll (es sei denn, Sie verwenden die `-o|--output`-Option, um ein spezifisches Verzeichnis anzugeben). Weitere Informationen finden Sie unter [`dotnet new`-Optionen](~/docs/core/tools/dotnet-new.md#options): Geben Sie die Kurzform des Namens der Vorlage für den `dotnet new`-Befehl an. Um ein Projekt aus der NUnit-Vorlage zu erstellen, führen Sie den folgenden Befehl aus:

```console
dotnet new nunit
```

Die Konsole zeigt an, dass das Projekt erstellt wurde und dass die Pakete des Projekts wiederhergestellt wurden. Nachdem der Befehl ausgeführt wurde, ist das Projekt einsatzbereit.

![Konsolenfenster mit der Ausgabe des dotnet new-Befehls, während er das NUnit-Projekt erstellt und die Projektabhängigkeiten wiederherstellt.](./media/create-custom-template/nunit2.png)

### <a name="to-uninstall-a-template-from-a-nuget-package-stored-at-nugetorg"></a>So deinstallieren Sie eine Vorlage aus einem NuGet-Paket, das auf nuget.org gespeichert ist

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> Das Beispiel dient nur der Veranschaulichung. Es gibt kein `GarciaSoftware.ConsoleTemplate.CSharp`-NuGet-Paket auf nuget.org und auch keines, das mit dem .NET Core SDK installiert wurde. Wenn Sie den Befehl ausführen, werden keine Pakete bzw. Vorlagen deinstalliert, und Sie erhalten die folgende Ausnahme:
> 
> > Could not find something to uninstall called 'GarciaSoftware.ConsoleTemplate.CSharp'. (Das zu deinstallierende Objekt „GarciaSoftware.ConsoleTemplate.CSharp“ konnte nicht gefunden werden.)

Wenn Sie die [NUnit 3-Vorlage für dotnet new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/) installiert haben und diese deinstallieren möchten, verwenden Sie den folgenden Befehl:

```console
dotnet new -u NUnit3.DotNetNew.Template
```

### <a name="uninstall-the-template-from-a-local-nupkg-file"></a>So deinstallieren Sie eine Vorlage aus einer lokalen NUPKG-Datei

Wenn Sie eine Vorlage deinstallieren möchten, versuchen Sie dies nicht mit dem Pfad der *NUPKG*-Datei. *Die Deinstallation der Vorlage mit `dotnet new -u <PATH_TO_NUPKG_FILE>` schlägt fehl.* Verweisen Sie mit der entsprechenden `id` auf das Paket:

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp.1.0.0
```

## <a name="use-file-system-distribution"></a>Verwenden der Dateisystemverteilung

Um eine Vorlage zu verteilen, speichern Sie den Projektvorlagenordner auf Ihrem Netzwerk an einer Stelle, auf die Benutzer zugreifen können. Verwenden Sie den `dotnet new`-Befehl mit der `-i|--install`-Option, geben Sie den Pfad des Vorlagenordners an (der Projektordner, der das Projekt und den Ordner *.template.config* enthält).

Im Tutorial wird davon ausgegangen, dass die Projektvorlage im Ordner *Documents/Templates* des Benutzerprofils gespeichert ist. Installieren Sie von diesem Speicherort aus die Vorlage mit dem folgenden Befehl, wobei Sie \<BENUTZER> durch den Namen des Benutzerprofils ersetzen.

```console
dotnet new -i C:\Users\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp
```

### <a name="create-a-project-from-the-template"></a>Erstellen eines neuen Projekts aus der Vorlage

Nachdem die Vorlage aus dem Dateisystem installiert wurde, verwenden Sie sie, indem Sie den `dotnet new <TEMPLATE>`-Befehl aus dem Verzeichnis ausführen, in das die Ausgabe der Vorlagen-Engine eingefügt werden soll (es sei denn, Sie verwenden die `-o|--output`-Option, um ein spezifisches Verzeichnis anzugeben). Weitere Informationen finden Sie unter [`dotnet new`-Optionen](~/docs/core/tools/dotnet-new.md#options): Geben Sie die Kurzform des Namens der Vorlage für den `dotnet new`-Befehl an.

Erstellen Sie aus einem neuen Projektordner, der unter *C:\Benutzer\\\<BENUTZER>\Dokumente\Projekte\MeineKonsolenanwendung* erstellt wurde, ein Projekt aus der `garciaconsole`-Vorlage:

```console
dotnet new garciaconsole
```

### <a name="uninstall-the-template"></a>Deinstallieren der Vorlage

Wenn Sie die Vorlage in Ihrem Dateisystem unter *C:\Benutzer\\\<BENUTZER>\Dokumente\Vorlagen\GarciaSoftware.ConsoleTemplate.CSharp* erstellt haben, deinstallieren Sie sie mit `-u|--uninstall` und dem Pfad des Vorlagenordners:

```console
dotnet new -u C:\Users\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> Um die Vorlage aus Ihrem lokalen Dateisystem zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren. Beispielsweise funktioniert zwar *C:\Benutzer\\\<BENUTZER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *.\GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.
> Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.

## <a name="see-also"></a>Siehe auch

[dotnet/templating GitHub repo Wiki (GitHub-Repositorywiki dotnet/templating)](https://github.com/dotnet/templating/wiki)  
[dotnet/dotnet-template-samples-GitHub-Repository](https://github.com/dotnet/dotnet-template-samples)  
[How to create your own templates for dotnet new (So erstellen Sie Ihre eigenen Vorlagen für dotnet new)](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/)  
[*template.json*-Schema im JSON-Schemaspeicher](http://json.schemastore.org/template)  
