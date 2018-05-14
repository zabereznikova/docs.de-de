---
title: .NET Core SDK – Übersicht
description: Erfahren Sie mehr über das .NET Core SDK, das ein Set von Bibliotheken und Tools zum Erstellen von .NET Core-Projekten ist.
author: blackdwarf
ms.author: mairaw
ms.date: 06/20/2016
ms.technology: dotnet-cli
ms.openlocfilehash: 5fc04c3ef5a1502251a9caf0b6a5f5809faad5b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
