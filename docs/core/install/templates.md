---
title: Installieren und Verwalten von SDK-Vorlagen (.NET Core)
description: Hier erfahren Sie, wie Sie .NET Core-Vorlagen unter Windows, Linux und macOS installieren.
author: adegeo
ms.author: adegeo
ms.date: 04/24/2020
zone_pivot_groups: operating-systems-set-one
no-loc:
- dotnet new
- dotnet nuget add source
ms.openlocfilehash: 09acae1409eb0492be10bd3a61b14da5be57c6c7
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324495"
---
# <a name="manage-net-project-and-item-templates"></a>Verwalten von .NET-Projekt- und -Elementvorlagen

.NET Core bietet ein Vorlagensystem, das Benutzern die Installation oder Deinstallation von Vorlagen über NuGet, NuGet-Paketdateien oder ein Dateisystemverzeichnis ermöglicht. In diesem Artikel wird beschrieben, wie Sie .NET Core-Vorlagen über die CLI des .NET Core SDK verwalten.

Weitere Informationen zum Erstellen von Vorlagen finden Sie unter [Tutorial: Erstellen von Vorlagen](../tutorials/cli-templates-create-item-template.md).

## <a name="install-template"></a>Installieren von Vorlagen

Vorlagen werden über den SDK-Befehl [dotnet new](../tools/dotnet-new.md) mit dem Parameter `-i` installiert. Sie können entweder den NuGet-Paketbezeichner einer Vorlage oder einen Ordner angeben, der die Vorlagendateien enthält.

### <a name="nuget-hosted-package"></a>Gehostetes NuGet-Paket

.NET-CLI-Vorlagen werden auf [NuGet](https://www.nuget.org/) hochgeladen, damit sie breitflächig verteilt und genutzt werden können. Vorlagen können auch über einen privaten Feed installiert werden. Anstatt eine Vorlage in einen NuGet-Feed hochzuladen, können *NUPKG*-Vorlagendateien verteilt und manuell installiert werden. Weitere Informationen hierzu finden Sie im Abschnitt [Lokales NuGet-Paket](#local-nuget-package).

Weitere Informationen zum Konfigurieren von NuGet-Feeds finden Sie unter [dotnet nuget add source](../tools/dotnet-nuget-add-source.md).

Verwenden Sie zum Installieren eines Vorlagenpakets über den NuGet-Standardfeed den `dotnet new -i {package-id}`-Befehl:

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates
```

Verwenden Sie zum Installieren eines Vorlagenpakets mit einer bestimmten Version über den NuGet-Standardfeed den `dotnet new -i {package-id}::{version}`-Befehl:

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.2.6
```

### <a name="local-nuget-package"></a>Lokales NuGet-Paket

Wenn ein Vorlagenpaket erstellt wird, wird eine *NUPKG*-Datei generiert. Wenn Sie eine *NUPKG*-Datei mit Vorlagen besitzen, können Sie diese mit dem Befehl `dotnet new -i {path-to-package}` installieren:

::: zone pivot="os-windows"

```dotnetcli
dotnet new -i c:\code\nuget-packages\Some.Templates.1.0.0.nupkg
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -i ~/code/nuget-packages/Some.Templates.1.0.0.nupkg
```

::: zone-end

### <a name="folder"></a>Ordner

Als Alternative zum Installieren der Vorlage über eine *NUPKG*-Datei können Sie Vorlagen auch direkt mit dem `dotnet new -i {folder-path}`-Befehl aus einem Ordner installieren. Der angegebene Ordner wird als Vorlagenpaketbezeichner für jede gefundene Vorlage behandelt. Alle Vorlagen, die in der Hierarchie des angegebenen Ordners gefunden werden, werden installiert.

::: zone pivot="os-windows"

```dotnetcli
dotnet new -i c:\code\nuget-packages\some-folder\
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -i ~/code/nuget-packages/some-folder/
```

::: zone-end

Der `{folder-path}`-Parameter im Befehl wird zum Vorlagenpaketbezeichner für alle gefundenen Vorlagen. Wie im Abschnitt [Auflisten von Vorlagen](#list-templates) erläutert wird, können Sie mit dem Befehl `dotnet new -u` eine Liste der installierten Vorlagen aufrufen. In diesem Beispiel wird der Vorlagenpaketbezeichner als der für die Installation verwendete Ordner angegeben:

::: zone pivot="os-windows"

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  c:\code\nuget-packages\some-folder
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u c:\code\nuget-packages\some-folder
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  /home/username/code/templates
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u /home/username/code/templates
```

::: zone-end

## <a name="uninstall-template"></a>Deinstallieren von Vorlagen

Vorlagen werden über den SDK-Befehl [dotnet new](../tools/dotnet-new.md) mit dem Parameter `-u` deinstalliert. Sie können entweder den NuGet-Paketbezeichner einer Vorlage oder einen Ordner angeben, der die Vorlagendateien enthält.

### <a name="nuget-package"></a>NuGet-Paket

Nachdem ein NuGet-Vorlagenpaket entweder über einen NuGet-Feed oder eine *NUPKG*-Datei installiert wurde, können Sie dieses deinstallieren, indem Sie auf den NuGet-Paketbezeichner verweisen.

Verwenden Sie zum Deinstallieren eines Vorlagenpakets den `dotnet new -u {package-id}`-Befehl:

```dotnetcli
dotnet new -u Microsoft.DotNet.Web.Spa.ProjectTemplates
```

### <a name="folder"></a>Ordner

Wenn Vorlagen über einen [Ordnerpfad](#folder) installiert werden, wird der Ordnerpfad zum Vorlagenpaketbezeichner.

Verwenden Sie zum Deinstallieren eines Vorlagenpakets den `dotnet new -u {package-folder-path}`-Befehl:

::: zone pivot="os-windows"

```dotnetcli
dotnet new -u c:\code\nuget-packages\some-folder
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -u /home/username/code/templates
```

::: zone-end

## <a name="list-templates"></a>Auflisten von Vorlagen

Wenn Sie den Standardbefehl zum Deinstallieren ohne Paketbezeichner verwenden, werden eine Liste der installierten Vorlagen und der Befehl angezeigt, mit dem Sie die jeweiligen Vorlagen deinstallieren können.

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  c:\code\nuget-packages\some-folder
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u c:\code\nuget-packages\some-folder
```

## <a name="install-templates-from-other-sdks"></a>Installieren von Vorlagen über andere SDKs

Wenn Sie jede SDK-Version sequenziell installiert haben, z. B. erst SDK 2.0, dann SDK 2.1 und so weiter, sind auch die Vorlagen aller SDKs installiert. Wenn Sie jedoch mit einer höheren SDK-Version wie 3.1 beginnen, sind nur die Vorlagen für [LTS-Releases (Long-Term Support, langfristige unterstützte Releases)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) enthalten, bei denen es sich zum Veröffentlichungszeitpunkt von SDK-Version 3.1 um Version 2.1 und 3.1 handelt. Vorlagen für ein andere Releases sind nicht enthalten.

Die .NET Core-Vorlagen sind auf NuGet verfügbar, und Sie können sie wie jede andere Vorlage installieren. Weitere Informationen finden Sie unter [Installieren von auf NuGet gehosteten Paketen](#nuget-hosted-package).

| SDK              | NuGet-Paketbezeichner                                                                                                      |
|------------------|-------------------------------------------------------------------------------------------------------------------------------|
| .NET Core 2.1    | [`Microsoft.DotNet.Common.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.1) |
| .NET Core 2.2    | [`Microsoft.DotNet.Common.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.2) |
| .NET Core 3.0    | [`Microsoft.DotNet.Common.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.0) |
| .NET Core 3.1    | [`Microsoft.DotNet.Common.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.1) |
| ASP.NET Core 2.1 | [`Microsoft.DotNet.Web.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.1)       |
| ASP.NET Core 2.2 | [`Microsoft.DotNet.Web.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.2)       |
| ASP.NET Core 3.0 | [`Microsoft.DotNet.Web.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.0)       |
| ASP.NET Core 3.1 | [`Microsoft.DotNet.Web.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.1)       |

Das .NET Core SDK enthält beispielsweise Vorlagen für eine Konsolen-App für .NET Core 2.1 und .NET Core 3.1. Wenn Sie die App für .NET Core 3.0 erstellen möchten, müssen Sie die Vorlagen für Version 3.0 installieren.

01. Versuchen Sie, eine App für .NET Core 3.0 zu erstellen.

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    Wenn folgende Fehlermeldung angezeigt wird, müssen Sie die Vorlagen installieren.

    > Couldn't find an installed template that matches the input, searching online for one that does... (Es wurde keine Vorlage gefunden, die mit der Eingabe übereinstimmt. Passende Vorlage wird gesucht...)

01. Installieren Sie die .NET Core 3.0-Projektvorlagen.

    ```dotnetcli
    dotnet new -i Microsoft.DotNet.Common.ProjectTemplates.3.0
    ```

01. Erstellen Sie die App ein zweites Mal.

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    Jetzt sollte eine Meldung angezeigt werden, die besagt, dass das Projekt erstellt wurde.

    > The template "Console Application" was created successfully. (Die Vorlage „Konsolenanwendung“ wurde erfolgreich erstellt.)
    >
    > Processing post-creation actions... (Aktionen nach der Erstellung werden verarbeitet...) Running 'dotnet restore' on path-to-project-file.csproj... (dotnet restore wird für „Pfad_der_Projektdatei.csproj“ ausgeführt...) Determining projects to restore... (Wiederherzustellende Projekte werden ermittelt...) Restore completed in 1.05 sec for path-to-project-file.csproj. (Die Wiederherstellung von „Pfad_zur_Projektdatei.csproj“ wurde in 1,05 Sekunden abgeschlossen.)
    >
    > Restore succeeded. (Wiederherstellung erfolgreich.)

## <a name="see-also"></a>Siehe auch

- [Tutorial: Erstellen einer Elementvorlage](../tutorials/cli-templates-create-item-template.md)
- [dotnet new](../tools/dotnet-new.md)
- [dotnet nuget add source](../tools/dotnet-nuget-add-source.md)
