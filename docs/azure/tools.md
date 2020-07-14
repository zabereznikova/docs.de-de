---
title: Tools für Azure .NET-Entwickler
description: Informationen zum Abrufen der Tools für das Verwenden der Azure .NET-Bibliotheken in einer Windows-, Linux- oder Mac-Umgebung
ms.date: 06/19/2020
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: fa645b152f15550b25a3542ba0cdbb43799536b9
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174834"
---
# <a name="azure-tools-for-developing-with-net"></a>Azure-Tools für die Entwicklung mit .NET

## <a name="sdk-downloads"></a>SDK-Downloads

Azure-Bibliotheken für .NET werden als [NuGet-Pakete](https://www.nuget.org/packages?q=windowsazureofficial) implementiert. In der [API-Referenz](/dotnet/api/overview/azure/?view=azure-dotnet) finden Sie die Referenzdokumentation, aufgeschlüsselt nach Azure-Diensten.

## <a name="development-tools"></a>Entwicklungstools

In Visual Studio sind Tools für viele Azure-Dienste integriert. Für bestimmte Azure-Dienste sind zusätzliche Tools oder Emulatoren verfügbar, z. B. für den [Azure Storage-Explorer](https://azure.microsoft.com/features/storage-explorer/). Wenn Sie weitere Tools für Ihren Azure-Dienst suchen, ziehen Sie die Dokumentation zurate.

Wählen Sie unten Ihre bevorzugte Entwicklungsumgebung aus.

## <a name="visual-studio-on-windows"></a>[Visual Studio unter Windows](#tab/vs)

Visual Studio 2017 und höher bietet integrierte Unterstützung für die Azure-Entwicklung. Die folgenden Schritten beschreiben, wie Sie die Unterstützung für die Azure-Entwicklung in Visual Studio einrichten.

Für Visual Studio 2015 und früher befolgen Sie <a href="vs2015-install.md">diese Anleitung</a>.

### <a name="step-1-download-visual-studio-2019"></a>Schritt 1: Herunterladen von Visual Studio 2019

Sie können diesen Schritt überspringen, wenn Sie bereits Visual Studio 2019 installiert haben.

> [!div class="nextstepaction"]
> [Herunterladen von Visual Studio 2019](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a>Schritt 2: Installieren der beiden Azure-Workloads

Installieren Sie im Visual Studio-Installer das Programm „Visual Studio“ (oder ändern Sie die vorhandene Installation). Stellen Sie sicher, dass die Arbeitsauslastungen *Azure-Entwicklung* und *ASP.NET und Webentwicklung* ausgewählt sind.

### <a name="step-3-develop-with-net-on-azure"></a>Schritt 3: Entwickeln mit .NET in Azure

Beginnen Sie der [Bereitstellung Ihrer ersten ASP.NET Core-Web-App in Azure App Service](/azure/app-service-web/app-service-web-get-started-dotnet).

## <a name="visual-studio-code-cross-platform"></a>[Visual Studio Code (plattformübergreifend)](#tab/vscode)

Visual Studio Code ist alles, was Sie für plattformübergreifende Azure-Entwicklung benötigen.

### <a name="step-1-download-the-net-core-sdk"></a>Schritt 1: Herunterladen des .NET Core SDK

Das SDK und Befehlszeilentools für .NET Core-Apps

> [!div class="nextstepaction"]
> [.NET Core SDK herunterladen](https://dotnet.microsoft.com/download)

### <a name="step-2-visual-studio-code"></a>Schritt 2: Visual Studio Code

Bearbeiten und Debuggen von .NET Core-Apps unter jedem Betriebssystem: Windows, Mac und Linux.

> [!div class="nextstepaction"]
> [Visual Studio Code herunterladen](https://code.visualstudio.com)

### <a name="step-3-azure-tools-extension"></a>Schritt 3: Azure Tools-Erweiterung

Installieren Sie die Azure Tools-Erweiterung in Visual Studio Code.

> [!div class="nextstepaction"]
> [Azure Tools-Erweiterung installieren](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack)

### <a name="step-4-develop-with-net-on-azure"></a>Schritt 4: Entwickeln mit .NET in Azure

Beginnen Sie der [Bereitstellung Ihrer ersten ASP.NET Core-Web-App in Azure App Serviceunter Linux](/azure/app-service/containers/quickstart-dotnetcore).

---
