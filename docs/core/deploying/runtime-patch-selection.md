---
title: Runtimebereitstellung für eigenständige .NET Core-App-Bereitstellungen.
description: Erfahren Sie mehr über die Änderungen an „dotnet publish“ für eigenständige Bereitstellungen.
author: KathleenDollard
ms.date: 05/31/2018
ms.openlocfilehash: 22385c7b5d2bf87755fd51cd6268d21fe3431c74
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740787"
---
# <a name="self-contained-deployment-runtime-roll-forward"></a>Rollforward der eigenständigen Runtimebereitstellung

[Eigenständige Anwendungsbereitstellungen](index.md) von .NET Core enthalten sowohl die .NET Core-Bibliotheken als auch die .NET Core-Runtime. Beginnend mit .NET Core SDK 2.1 (Version 2.1.300) veröffentlicht eine eigenständige Anwendungsbereitstellung [die höchste Patch-Runtime auf Ihrem Computer](https://github.com/dotnet/designs/pull/36). [`dotnet publish`](../tools/dotnet-publish.md) wählt für eine eigenständige Bereitstellung standardmäßig die aktuellste installierte Version als Teil des SDK auf dem veröffentlichenden Computer aus. Dadurch kann Ihre bereitgestellte Anwendung während `publish` mit Problembehebungen der Sicherheit (und anderen Problembehebungen) ausgeführt werden. Die Anwendung muss erneut veröffentlicht werden, um einen neuen Patch abzurufen. Eigenständige Anwendungen werden durch Angabe von `-r <RID>` auf dem Befehl `dotnet publish` oder durch Angabe des [Runtime-Bezeichners (RID)](../rid-catalog.md) in der Projektdatei (CSPROJ/VBPROJ) oder der Befehlszeile erstellt.

## <a name="patch-version-roll-forward-overview"></a>Übersicht über Rollforward der Patchversion

[`restore`](../tools/dotnet-restore.md), [`build`](../tools/dotnet-build.md) und [`publish`](../tools/dotnet-publish.md) sind `dotnet`-Befehle, die separat ausgeführt werden können. Die Auswahl der Runtime ist Teil des Vorgangs `restore`, nicht `publish` oder `build`. Wenn Sie `publish` aufrufen, wird die neueste Patchversion ausgewählt. Wenn Sie `publish` mit dem Argument `--no-restore` aufrufen, erhalten Sie möglicherweise nicht die gewünschte Patchversion, da ein vorheriger `restore`-Vorgang möglicherweise nicht mit der neuen Richtlinie für die Veröffentlichung eigenständiger Anwendungen ausgeführt wurde. In diesem Fall wird ein Buildfehler mit einem Text generiert, der dem Folgenden ähnelt:

  „Das Projekt wurde mit Microsoft.NETCore.App-Version 2.0.0 wiederhergestellt. Jedoch wird aufgrund der aktuellen Einstellungen stattdessen Version 2.0.6 verwendet. Stellen Sie sicher, dass die gleichen Einstellungen für „restore“ und nachfolgende Vorgänge wie „build“ oder „publish“ verwendet werden, um dieses Problem zu beheben. Dieser Fehler tritt in der Regel auf, wenn die Eigenschaft RuntimeIdentifier während den Vorgängen „build“ oder „publish“ festgelegt wird, jedoch nicht während „restore“.

> [!NOTE]
> `restore` und `build` können implizit als Teil eines anderen Befehls ausgeführt werden, z.B. `publish`. Wenn sie implizit als Teil eines anderen Befehls ausgeführt werden, wird zusätzlicher Kontext bereitgestellt, sodass die richtigen Artefakte erstellt werden. Wenn Sie `publish` mit einer Runtime ausführen (z.B. `dotnet publish -r linux-x64`), stellt `restore` Pakete implizit für die Linux-x64-Runtime wieder her. Wenn Sie `restore` explizit aufrufen, werden Runtime-Pakete nicht standardmäßig wiederhergestellt, da dieser Kontext nicht besteht.

## <a name="how-to-avoid-restore-during-publish"></a>Umgehen von restore während publish

Das Ausführen von `restore` als Teil des `publish`-Vorgangs kann für Ihr Szenario unangebracht sein. Führen Sie die folgenden Schritte aus, um `restore` während `publish` beim Erstellen eigenständiger Anwendungen zu vermeiden:

- Legen Sie die Eigenschaft `RuntimeIdentifiers` auf eine durch Semikolons getrennte Liste aller zu veröffentlichenden [RIDs](../rid-catalog.md) fest.
- Legen Sie die `TargetLatestRuntimePatch` -Eigenschaft auf `true`fest.

## <a name="no-restore-argument-with-dotnet-publish-options"></a>No-restore-Argument mit dotnet publish-Optionen

Wenn Sie sowohl eigenständige Anwendungen und [Framework-abhängige Anwendungen](index.md) mit derselben Projektdatei erstellen und das Argument `--no-restore` mit `dotnet publish` verwenden möchten, wählen Sie eine der folgenden Optionen aus:

1. Framework-abhängiges Verhalten bevorzugen. Wenn die Anwendung Framework-abhängig ist, ist dies das Standardverhalten. Wenn die Anwendung eigenständig ist und eine nicht gepatchte lokale Runtime (2.1.0) verwenden kann, legen Sie `false` für `TargetLatestRuntimePatch` in der Projektdatei fest.

2. Eigenständiges Verhalten bevorzugen. Wenn die Anwendung eigenständig ist, ist dies das Standardverhalten. Wenn die Anwendung Framework-abhängig ist und den neuesten Patch erfordert, legen Sie `true` für `TargetLatestRuntimePatch` in der Projektdatei fest.

3. Übernehmen Sie die explizite Kontrolle über die Runtime-Framework-Version, indem Sie für `RuntimeFrameworkVersion` die spezifische Patchversion in der Projektdatei festlegen.
