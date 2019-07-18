---
title: Mit der Paketverwaltung mit F# für Azure
description: Verwenden Sie zum Verwalten von Paket-Abhängigkeits oder Nuget F# Azure-Abhängigkeiten
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: b180024e2276a2fd7786f35cb922b1aa1d91f0ad
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880019"
---
# <a name="package-management-for-f-azure-dependencies"></a>Verwalten von Paketen für F#-Azure-Abhängigkeiten

Abrufen von Paketen für Azure-Entwicklung ist einfach, wenn Sie einen Paket-Manager verwenden. Die beiden Optionen sind [Paket-Abhängigkeits](https://fsprojects.github.io/Paket/) und [NuGet](https://www.nuget.org/).

## <a name="using-paket"></a>Mithilfe der Paket-Abhängigkeits

Bei Verwendung von [Paket-Abhängigkeits](https://fsprojects.github.io/Paket/) als Ihre Abhängigkeits-Manager können Sie mit der `paket.exe` Tool, um die Azure-Abhängigkeiten hinzufügen. Zum Beispiel:

```
> paket add nuget WindowsAzure.Storage
```

Oder, bei Verwendung von [Mono](https://www.mono-project.com/) für die .NET-Entwicklung Cross-Platform:

```
> mono paket.exe add nuget WindowsAzure.Storage
```

Hiermit wird `WindowsAzure.Storage` zu Ihren paketabhängigkeiten für das Projekt im aktuellen Verzeichnis, Ändern der `paket.dependencies` Datei, und Laden Sie das Paket. Wenn Sie Abhängigkeiten bereits eingerichtet haben, oder Arbeiten mit einem Projekt, in denen Abhängigkeiten von anderen Entwicklern wurden eingerichtet sind, können zu beheben und installieren Sie die Abhängigkeiten lokal wie folgt:

```
> paket install
```

Oder, für die Mono-Entwicklung:

```
> mono paket.exe install
```

Sie können alle Ihre paketabhängigkeiten auf die neueste Version wie folgt aktualisieren:

```
> paket update
```

Oder, für die Mono-Entwicklung:

```
> mono paket.exe update
```

## <a name="using-nuget"></a>Mithilfe von Nuget

Bei Verwendung von [NuGet](https://www.nuget.org/) als Ihre Abhängigkeits-Manager können Sie mit der `nuget.exe` Tool, um die Azure-Abhängigkeiten hinzufügen. Zum Beispiel:

```
> nuget install WindowsAzure.Storage -ExcludeVersion
```

Oder, für die Mono-Entwicklung:

```
> mono nuget.exe install WindowsAzure.Storage -ExcludeVersion
```

Hiermit wird `WindowsAzure.Storage` der Gruppe der paketabhängigkeiten für das Projekt in das aktuelle Verzeichnis und das Herunterladen des Pakets. Wenn Sie Abhängigkeiten bereits eingerichtet haben, oder Arbeiten mit einem Projekt, in denen Abhängigkeiten von anderen Entwicklern wurden eingerichtet sind, können zu beheben und installieren Sie die Abhängigkeiten lokal wie folgt:

```
> nuget restore
```

Oder, für die Mono-Entwicklung:

```
> mono nuget.exe restore
```

Sie können alle Ihre paketabhängigkeiten auf die neueste Version wie folgt aktualisieren:

```
> nuget update
```

Oder, für die Mono-Entwicklung:

```
> mono nuget.exe update
```

## <a name="referencing-assemblies"></a>Referenzierende Assemblys

Um verwenden Ihre Pakete in Ihre F# Skript müssen Sie auf die Assemblys enthalten, die in den Paketen, die mit einem `#r` Richtlinie. Zum Beispiel:

```
> #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"
```

Wie Sie sehen können, müssen Sie geben den relativen Pfad der DLL und der vollständige Name der DLL, der genau identisch mit den Paketnamen möglicherweise nicht. Der Pfad wird eine Framework-Version und ggf. eine Versionsnummer des Pakets enthalten. Um alle installierten Assemblys zu suchen, können Sie etwa wie folgt in einer Windows-Befehlszeile verwenden:

```
> cd packages/WindowsAzure.Storage
> dir /s/b *.dll
```

Oder in einer Unix-Shell, dann etwa wie folgt:

```
> find packages/WindowsAzure.Storage -name "*.dll"
```

Dadurch erhalten die Pfade zu den installierten Assemblys Sie. Von dort aus können Sie den richtigen Pfad für Ihre Frameworkversion auswählen.
