---
title: dotnet-msbuild-Befehl | .NET Core SDK
description: "Der dotnet-msmsbuild-Befehl ermöglicht den Zugriff auf die MSmsbuild-Befehlszeile"
keywords: dotnet-msmsbuild, CLI, CLI-Befehl, .NET Core
author: mairaw
manager: wpickett
ms.date: 10/13/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: ffdc40ba-ef33-463e-aa35-b0af1fe615a2
translationtype: Human Translation
ms.sourcegitcommit: cde9d9577246a9025d646ce2a6d574a18512146e
ms.openlocfilehash: 51a3afdcf591b8147790d78471c6fee63ceb7f2d

---

#<a name="dotnet-msbuild"></a>dotnet-msbuild

## <a name="name"></a>Name 
dotnet-msbuild – Erstellt ein Projekt und alle seine Abhängigkeiten 

## <a name="synopsis"></a>Übersicht

`dotnet msbuild <msbuild_arguments>`

## <a name="description"></a>Beschreibung
Der `dotnet msbuild`-Befehl ermöglicht den Zugriff auf eine voll funktionsfähige MSBuild-Instanz 

Der Befehl weist genau die gleichen Funktionen wie der vorhandene MSBuild-Befehlszeilenclient auf. Alle Optionen sind gleich. Sie können die [vorhandene Dokumentation](https://msdn.microsoft.com/en-us/library/ms164311.aspx) nutzen, um sich mit der Befehlsreferenz vertraut zu machen. 

## <a name="examples"></a>Beispiele

Erstellt ein Projekt und seine Abhängigkeiten:

`dotnet msbuild`

Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:

`dotnet msbuild /p:Configuration=Release`

Führt das Veröffentlichungsziel aus und veröffentlicht für die RID `osx.10.11-x64`:

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`



<!--HONumber=Nov16_HO3-->


