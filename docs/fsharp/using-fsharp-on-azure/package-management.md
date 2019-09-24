---
title: Verwenden von Paketverwaltung F# mit für Azure
description: Verwenden von Paket oder nuget zum F# Verwalten von Azure-Abhängigkeiten
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 4aa32ace91f30d0e43b9c40067f5f0f456cc4069
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "71214226"
---
# <a name="package-management-for-f-azure-dependencies"></a>Verwalten von Paketen für F#-Azure-Abhängigkeiten

Das Abrufen von Paketen für die Azure-Entwicklung ist einfach, wenn Sie einen Paket-Manager verwenden. Die beiden Optionen sind " [Paket](https://fsprojects.github.io/Paket/) " und " [nuget](https://www.nuget.org/)".

## <a name="using-paket"></a>Verwenden von Paket

Wenn Sie " [Paket](https://fsprojects.github.io/Paket/) " als Abhängigkeits-Manager verwenden, können Sie `paket.exe` das Tool verwenden, um Azure-Abhängigkeiten hinzuzufügen. Beispiel:

```console
> paket add nuget WindowsAzure.Storage
```

Oder wenn Sie [Mono](https://www.mono-project.com/) für die plattformübergreifende .net-Entwicklung verwenden:

```console
> mono paket.exe add nuget WindowsAzure.Storage
```

Dadurch wird Ihrem `WindowsAzure.Storage` Satz von Paketabhängigkeiten für das Projekt im aktuellen Verzeichnis hinzugefügt, die `paket.dependencies` Datei geändert und das Paket heruntergeladen. Wenn Sie zuvor Abhängigkeiten eingerichtet haben oder mit einem Projekt arbeiten, in dem Abhängigkeiten von einem anderen Entwickler eingerichtet wurden, können Sie Abhängigkeiten wie folgt lokal auflösen und installieren:

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

Wenn Sie [nuget](https://www.nuget.org/) als Abhängigkeits-Manager verwenden, können Sie das `nuget.exe` Tool verwenden, um Azure-Abhängigkeiten hinzuzufügen. Beispiel:

```console
> nuget install WindowsAzure.Storage -ExcludeVersion
```

Oder für die Mono-Entwicklung:

```console
> mono nuget.exe install WindowsAzure.Storage -ExcludeVersion
```

Dadurch wird Ihrem `WindowsAzure.Storage` Satz von Paketabhängigkeiten für das Projekt im aktuellen Verzeichnis hinzugefügt, und das Paket wird heruntergeladen. Wenn Sie zuvor Abhängigkeiten eingerichtet haben oder mit einem Projekt arbeiten, in dem Abhängigkeiten von einem anderen Entwickler eingerichtet wurden, können Sie Abhängigkeiten wie folgt lokal auflösen und installieren:

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

Um die Pakete in Ihrem F# Skript verwenden zu können, müssen Sie mit einer `#r` -Direktive auf die Assemblys verweisen, die in den Paketen enthalten sind. Beispiel:

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
