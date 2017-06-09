---
title: ".NET Core SDK – Übersicht"
description: ".NET Core SDK – Übersicht"
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 26bc9822-e42b-48ec-b0d6-499dc604add7
ms.translationtype: Human Translation
ms.sourcegitcommit: d97a1501ad25b683cbb5d7fbd8bd1b137f7f4046
ms.openlocfilehash: 5ecc2dd249ab0e1e25e2fcaa4f7548f91085e54a
ms.contentlocale: de-de
ms.lasthandoff: 04/10/2017

---

# <a name="net-core-sdk-overview"></a>.NET Core SDK – Übersicht 

## <a name="introduction"></a>Einführung
.NET Core Software Development Kit (SDK) ist eine Sammlung von Bibliotheken und Tools, mit der Entwickler .NET Core-Anwendungen und -Bibliotheken erstellen können. Dieses Paket wird von den meisten Entwicklern erworben. 

Es enthält die folgenden Komponenten:

1. Die .NET Core-Befehlszeilentools zum Erstellen von Anwendungen
2. .NET Core (Bibliotheken und Runtime) zum Erstellen sowie zum Ausführen von Anwendungen
3. Der `dotnet`-Treiber für das Ausführen der [CLI-Befehle](tools/index.md) sowie von Anwendungen


## <a name="acquiring-the-net-core-sdk"></a>.NET Core SDK erwerben
Wie bei allen Tools ist der erste Schritt, diese auf dem Computer zu installieren. Je nach Szenario können Sie entweder den nativen Installer oder das Shellskript verwenden, um das SDK zu installieren.

Der native Installer ist in erster Linie für Entwicklercomputer vorgesehen. Das SDK wird mithilfe des nativen Installationsmechanismus der jeweils unterstützten Plattform verteilt, z.B. Debian-Pakete unter Ubuntu oder MSI-Bündel unter Windows. Diese Installer installieren und richten die Umgebung je nach Bedarf des Nutzers ein, sodass das SDK sofort nach der Installation genutzt werden kann. Jedoch benötigen sie auch Administratorrechte auf dem Computer. Die Installationsanweisungen finden Sie im [.NET Core-Installationshandbuch](https://aka.ms/dotnetcoregs).

Installationsskripts hingegen erfordern keine Administratorrechte. Allerdings installieren diese auch keine erforderlichen Komponenten auf dem Computer, sodass Sie alle erforderlichen Komponenten manuell installieren müssen. Die Skripts werden hauptsächlich für das Einrichten von Buildservern verwendet oder in dem Fall, dass Sie die Tools ohne Administratorrechte installieren möchten (beachten Sie hierzu die oben genannten Einschränkungen hinsichtlich der erforderlichen Komponenten). Weitere Informationen finden Sie unter [dotnet-install scripts reference (Referenz zu dotnet-Installationsskripts)](tools/dotnet-install-script.md). Informationen dazu, wie Sie ein SDK auf Ihrem CI-Buildserver einrichten können, finden Sie in dem Dokument [Using .NET Core SDK and tools in Continuous Integration (CI) (Verwendung von .NET Core-SDK und Tools in der Fortlaufenden Integration (CI))](tools/using-ci-with-cli.md). 

Das SDK wird standardmäßig parallel installiert (SxS). Das bedeutet, dass auf einem Computer jederzeit mehrere Versionen der CLI-Tools nebeneinander verwendet werden können. Ausführlichere Erklärungen dazu, wie die korrekte Version verwendet wird, finden Sie auf der Seite „.NET Core Command-Line Interface Tools“ (Tools für die .NET Core-Befehlszeilenschnittstelle) im Abschnitt [Driver (Treiber)](tools/index.md#driver).
