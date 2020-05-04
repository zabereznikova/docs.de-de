---
title: Tools für Azure .NET- und .NET Core-Entwickler
description: Informationen zum Abrufen der Tools für das Verwenden der Azure .NET-Bibliotheken in einer Windows-, Linux- oder Mac-Umgebung
ms.date: 10/01/2018
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 1c6370e4b3e5e6e901ba6ef56c65d794f3da5abe
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2020
ms.locfileid: "81433163"
---
# <a name="tools-for-net-and-net-core-azure-developers"></a>Tools für .NET- und .NET Core-Azure-Entwickler

## <a name="sdk-downloads"></a>SDK-Downloads

Azure-Bibliotheken für .NET werden als [NuGet-Pakete](https://www.nuget.org/packages?q=windowsazureofficial) implementiert. In der [API-Referenz](/dotnet/api/overview/azure/?view=azure-dotnet) finden Sie alle Installationsanweisungen sortiert nach Azure-Diensten.

## <a name="development-tools"></a>Entwicklungstools

In Visual Studio sind Tools für viele Azure-Dienste integriert. Für bestimmte Azure-Dienste sind zusätzliche Tools oder Emulatoren verfügbar, z. B. für den [Azure Storage-Explorer](https://azure.microsoft.com/features/storage-explorer/). Wenn Sie weitere Tools für Ihren Azure-Dienst suchen, ziehen Sie die Dokumentation zurate.

Mit diesen Anleitungen können Sie die empfohlene Startentwicklungsumgebung für Ihr Betriebssystem installieren.

## <a name="windows"></a>[Windows](#tab/windows)

Visual Studio 2017 und höher bietet integrierte Unterstützung für die Azure-Entwicklung. Die folgenden Schritten beschreiben, wie Sie die Unterstützung für die Azure-Entwicklung in Visual Studio einrichten.

Für Visual Studio 2015 und früher befolgen Sie <a href="vs2015-install.md">diese Anleitung</a>.

### <a name="step-1-download-visual-studio-2019"></a>Schritt 1: Herunterladen von Visual Studio 2019

Sie können diesen Schritt überspringen, wenn Sie bereits Visual Studio 2019 installiert haben.

> [!div class="nextstepaction"]
> [Herunterladen von Visual Studio 2019](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a>Schritt 2: Installieren der beiden Azure-Workloads

Installieren Sie im Visual Studio-Installer das Programm „Visual Studio“ (oder ändern Sie die vorhandene Installation). Stellen Sie sicher, dass die Arbeitsauslastungen *Azure-Entwicklung* und *ASP.NET und Webentwicklung* ausgewählt sind.

### <a name="step-3-develop-with-net-on-azure"></a>Schritt 3: Entwickeln mit .NET in Azure

Beginnen Sie der [Bereitstellung Ihrer ersten ASP.NET Core-Web-App in Azure App Service](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet).

## <a name="macos"></a>[macOS](#tab/macos)

Visual Studio für Mac ist alles, was Sie für die Azure-Entwicklung brauchen.

### <a name="step-1-download-visual-studio-for-mac"></a>Schritt 1: Visual Studio für Mac herunterladen

> [!div class="nextstepaction"]
> [Visual Studio für Mac herunterladen](https://www.visualstudio.com/vs/visual-studio-mac/)

Während der Installation werden Azure-Tools automatisch ausgewählt.

## <a name="linux"></a>[Linux](#tab/linux)

Visual Studio Code ist alles, was Sie für die Azure-Entwicklung unter Linux brauchen.

### <a name="step-1-download-the-net-core-sdk"></a>Schritt 1: Herunterladen des .NET Core SDK

Das SDK und Befehlszeilentools für .NET Core-Apps

> [!div class="nextstepaction"]
> [.NET Core SDK herunterladen](https://dotnet.microsoft.com/download)

### <a name="step-2-visual-studio-code"></a>Schritt 2: Visual Studio Code

Bearbeiten und Debuggen von .NET Core-Apps unter jedem Betriebssystem: Windows, Mac und Linux.

> [!div class="nextstepaction"]
> [Visual Studio Code herunterladen](https://code.visualstudio.com)

---
