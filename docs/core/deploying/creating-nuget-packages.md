---
title: Erstellen eines NuGet-Pakets mit Tools der .NET Core-Befehlszeilenschnittstelle (CLI)
description: Erfahren Sie, wie Sie ein NuGet-Paket mit dem Befehl „dotnet pack“ erstellen.
author: cartermp
ms.date: 06/20/2016
ms.technology: dotnet-cli
ms.custom: seodec18
ms.openlocfilehash: 2d876f921d079972e2a638788195aa69a2423c49
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771942"
---
# <a name="how-to-create-a-nuget-package-with-net-core-command-line-interface-cli-tools"></a>Erstellen eines NuGet-Pakets mit Tools der .NET Core-Befehlszeilenschnittstelle (CLI)

> [!NOTE]
> Nachfolgend einige Befehlszeilenbeispiele unter Unix. Der hier gezeigte Befehl `dotnet pack` funktioniert wie unter Windows.

.NET Standard- und .NET Core-Bibliotheken sollten als NuGet-Pakete verteilt werden. So werden alle .NET Standardbibliotheken verteilt und genutzt. Am einfachsten geht dies mit dem Befehl `dotnet pack`.

Stellen Sie sich vor, dass Sie eine fantastische neue Bibliothek geschrieben haben, die Sie über NuGet verteilen möchten. Sie können hierfür ein NuGet-Paket mit plattformübergreifenden Tools erstellen. Als Beispiel dient eine Bibliothek namens **SuperAwesomeLibrary** für `netstandard1.0`.

Wenn Sie transitive Abhängigkeiten haben, also ein Projekt, das von einem anderen Paket abhängig ist, müssen Sie sicherstellen, dass Pakete für die gesamte Projektmappe mit dem Befehl `dotnet restore` wiederhergestellt werden, bevor das NuGet-Paket erstellt wird. Andernfalls wird der Befehl `dotnet pack` nicht ordnungsgemäß funktionieren.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Nachdem Sie sichergestellt haben, dass Pakete wiederhergestellt wurden, können Sie zu dem Verzeichnis navigieren, in dem sich eine Bibliothek befindet:

```console
cd src/SuperAwesomeLibrary
```

Anschließend genügt ein einzelner Befehl von der Befehlszeile:

```dotnetcli
dotnet pack
```

Der Ordner */bin/debug* sieht nun wie folgt aus:

```console
$ ls bin/Debug
netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

Beachten Sie, dass dies ein Paket erzeugt, das debuggt werden kann. Wenn Sie ein NuGet-Paket mit Release-Binärdateien erstellen möchten, müssen Sie lediglich den Schalter `--configuration` (oder) `-c` und `release` als Argument verwenden.

```dotnetcli
dotnet pack --configuration release
```

Ihr Ordner */bin* weist nun einen Unterordner *release* mit dem NuGet-Paket und den Releasebinärdateien auf:

```console
$ ls bin/release
netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

Jetzt haben Sie die erforderlichen Dateien zum Veröffentlichen eines NuGet-Pakets.

## <a name="dont-confuse-dotnet-pack-with-dotnet-publish"></a>Verwechseln Sie nicht `dotnet pack` mit `dotnet publish`

Es ist wichtig zu beachten, dass zu keinem Zeitpunkt der Befehl `dotnet publish` beteiligt ist. Der Befehl `dotnet publish` dient der Bereitstellung von Clientanwendungen mit allen Abhängigkeiten im gleichen Paket – nicht für das Generieren eines NuGet-Pakets, das über NuGet verteilt und genutzt wird.

## <a name="see-also"></a>Siehe auch

- [Schnellstart: Erstellen und Veröffentlichen eines Pakets](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)
