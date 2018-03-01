---
title: "Verwenden des Paketverwaltung mit f# für Azure"
description: "Verwenden von Paket \"oder\" NuGet-zum Verwalten der F#-Azure-Abhängigkeiten"
keywords: Visual f#, f#, funktionalen Programmierung, .NET, .NET Core, Azure
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: dd32ef9c-5416-467e-9fa3-c9ee3bb08456
ms.openlocfilehash: d1a807053f5c4c45492f206739922aacdf6d4122
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2018
---
# <a name="package-management-for-f-azure-dependencies"></a>Verwalten von Paketen für F#-Azure-Abhängigkeiten

Abrufen von Paketen für die Azure-Entwicklung ist einfach, wenn Sie einen Paket-Manager verwenden. Die beiden Optionen sind [Paket](https://fsprojects.github.io/Paket/) und [NuGet](https://www.nuget.org/).

## <a name="using-paket"></a>Paket verwenden

Bei Verwendung von [Paket](https://fsprojects.github.io/Paket/) als der Abhängigkeit-Managers können Sie die `paket.exe` Tool zum Hinzufügen von Azure-Abhängigkeiten. Zum Beispiel:

    > paket add nuget WindowsAzure.Storage

Oder, bei Verwendung von [Mono](https://www.mono-project.com/) für die plattformübergreifende .NET-Entwicklung:

    > mono paket.exe add nuget WindowsAzure.Storage

Dadurch wird hinzugefügt `WindowsAzure.Storage` für Ihren Abhängigkeiten des Pakets für das Projekt im aktuellen Verzeichnis ändern die `paket.dependencies` Datei, und Laden Sie das Paket. Wenn Sie Abhängigkeiten zuvor eingerichtet haben, oder Arbeiten mit einem Projekt, in denen Abhängigkeiten von anderen Entwicklern wurden eingerichtet sind, können Sie beheben und Installieren von Abhängigkeiten lokal wie folgt:

    > paket install

Oder für den Mono-Entwicklung:

    > mono paket.exe install

Sie können alle Ihre Abhängigkeiten des Pakets auf die neueste Version wie folgt aktualisieren:

    > paket update

Oder für den Mono-Entwicklung:

    > mono paket.exe update

## <a name="using-nuget"></a>Mithilfe von Nuget

Bei Verwendung von [NuGet](https://www.nuget.org/) als der Abhängigkeit-Managers können Sie die `nuget.exe` Tool zum Hinzufügen von Azure-Abhängigkeiten. Zum Beispiel:

    > nuget install WindowsAzure.Storage -ExcludeVersion

Oder für den Mono-Entwicklung:

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

Dadurch wird hinzugefügt `WindowsAzure.Storage` für Ihren Abhängigkeiten des Pakets für das Projekt im aktuellen Verzeichnis und der Download des Pakets. Wenn Sie Abhängigkeiten zuvor eingerichtet haben, oder Arbeiten mit einem Projekt, in denen Abhängigkeiten von anderen Entwicklern wurden eingerichtet sind, können Sie beheben und Installieren von Abhängigkeiten lokal wie folgt:

    > nuget restore 

Oder für den Mono-Entwicklung:

    > mono nuget.exe restore

Sie können alle Ihre Abhängigkeiten des Pakets auf die neueste Version wie folgt aktualisieren:

    > nuget update

Oder für den Mono-Entwicklung:

    > mono nuget.exe update

## <a name="referencing-assemblies"></a>Referenzierende Assemblys

Um die Pakete in Ihrem f#-Skript verwenden, müssen Sie die in den Paketen, die mit enthaltenen Assemblys verweisen eine `#r` Richtlinie. Zum Beispiel:

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

Wie Sie sehen können, müssen Sie den relativen Pfad zur DLL und den vollständigen DLL-Namen, der nicht genau identisch mit den Paketnamen möglicherweise angeben. Der Pfad wird ein Framework, Version und möglicherweise eine Paket-Versionsnummer enthalten. Um die installierten Assemblys zu suchen, können Sie etwa wie folgt in einer Windows-Befehlszeile verwenden:

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

Oder in einer Unix-Shell, etwa wie folgt:

    > find packages/WindowsAzure.Storage -name "*.dll"

Sie erhalten die Pfade zu den installierten Assemblys. Von dort aus können Sie den richtigen Pfad für die Framework-Version auswählen.
