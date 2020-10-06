---
title: 'Verwenden von Paketverwaltung mit F # für Azure'
description: 'Verwenden von Paket oder nuget zum Verwalten von F #-Azure-Abhängigkeiten'
author: sylvanc
ms.date: 09/20/2016
ms.custom: devx-track-fsharp
ms.openlocfilehash: 7816c82e87db113a35fef967886c8c3e27959332
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756233"
---
# <a name="package-management-for-f-azure-dependencies"></a>Verwalten von Paketen für F#-Azure-Abhängigkeiten

Das Abrufen von Paketen für die Azure-Entwicklung ist einfach, wenn Sie einen Paket-Manager verwenden. Die beiden Optionen sind " [Paket](https://fsprojects.github.io/Paket/) " und " [nuget](https://www.nuget.org/)".

## <a name="using-paket"></a>Verwenden von Paket

Wenn Sie " [Paket](https://fsprojects.github.io/Paket/) " als Abhängigkeits-Manager verwenden, können Sie das Tool verwenden, `paket.exe` um Azure-Abhängigkeiten hinzuzufügen. Beispiel:

```console
> paket add nuget WindowsAzure.Storage
```

Oder wenn Sie [Mono](https://www.mono-project.com/) für die plattformübergreifende .net-Entwicklung verwenden:

```console
> mono paket.exe add nuget WindowsAzure.Storage
```

Dadurch wird `WindowsAzure.Storage` Ihrem Satz von Paketabhängigkeiten für das Projekt im aktuellen Verzeichnis hinzugefügt, die Datei geändert `paket.dependencies` und das Paket heruntergeladen. Wenn Sie zuvor Abhängigkeiten eingerichtet haben oder mit einem Projekt arbeiten, in dem Abhängigkeiten von einem anderen Entwickler eingerichtet wurden, können Sie Abhängigkeiten wie folgt lokal auflösen und installieren:

```console
> paket install
```

Oder für die Mono-Entwicklung:

```console
> mono paket.exe install
```

Sie können alle Paketabhängigkeiten wie folgt auf die neueste Version aktualisieren:

```console
> paket update
```

Oder für die Mono-Entwicklung:

```console
> mono paket.exe update
```

## <a name="using-nuget"></a>Verwenden von nuget

Wenn Sie [nuget](https://www.nuget.org/) als Abhängigkeits-Manager verwenden, können Sie das Tool verwenden, `nuget.exe` um Azure-Abhängigkeiten hinzuzufügen. Beispiel:

```console
> nuget install WindowsAzure.Storage -ExcludeVersion
```

Oder für die Mono-Entwicklung:

```console
> mono nuget.exe install WindowsAzure.Storage -ExcludeVersion
```

Dadurch wird `WindowsAzure.Storage` Ihrem Satz von Paketabhängigkeiten für das Projekt im aktuellen Verzeichnis hinzugefügt, und das Paket wird heruntergeladen. Wenn Sie zuvor Abhängigkeiten eingerichtet haben oder mit einem Projekt arbeiten, in dem Abhängigkeiten von einem anderen Entwickler eingerichtet wurden, können Sie Abhängigkeiten wie folgt lokal auflösen und installieren:

```console
> nuget restore
```

Oder für die Mono-Entwicklung:

```console
> mono nuget.exe restore
```

Sie können alle Paketabhängigkeiten wie folgt auf die neueste Version aktualisieren:

```console
> nuget update
```

Oder für die Mono-Entwicklung:

```console
> mono nuget.exe update
```

## <a name="referencing-assemblies"></a>Referenzierende Assemblys

Um die Pakete im F #-Skript verwenden zu können, müssen Sie mit einer-Direktive auf die Assemblys verweisen, die in den Paketen enthalten sind `#r` . Beispiel:

```fsharp
> #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"
```

Wie Sie sehen können, müssen Sie den relativen Pfad zur dll und den vollständigen DLL-Namen angeben, der möglicherweise nicht exakt mit dem Paketnamen identisch ist. Der Pfad enthält eine Framework-Version und möglicherweise eine Paket Versionsnummer. Wenn Sie alle installierten Assemblys suchen möchten, können Sie diese in einer Windows-Befehlszeile verwenden:

```console
> cd packages/WindowsAzure.Storage
> dir /s/b *.dll
```

Oder in einer Unix-Shell wie folgt:

```console
> find packages/WindowsAzure.Storage -name "*.dll"
```

Dadurch erhalten Sie die Pfade zu den installierten Assemblys. Von dort aus können Sie den richtigen Pfad für Ihre Frameworkversion auswählen.
