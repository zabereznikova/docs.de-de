---
title: Checkliste für die Konfiguration der .NET-Entwicklung in Azure
description: In diesem Artikel werden kurz alle Tools zusammengefasst, die Sie für die .NET-Entwicklung mit Azure installiert haben sollten.
ms.date: 1/1/2021
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: a2ff9bbf1e6a8790ddc161a1a1c8d14e8fab6e41
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2021
ms.locfileid: "98027238"
---
# <a name="net-on-azure-development-environment-checklist"></a>Checkliste für die Entwicklungsumgebung von .NET in Azure

Mithilfe dieser Checkliste können Sie sicherstellen, dass Ihre Entwicklungsumgebung für die .NET-Entwicklung in Azure ordnungsgemäß konfiguriert ist.

## <a name="create-an-azure-account"></a>Erstellen eines Azure-Kontos

Für den Zugriff auf Azure-Dienste oder das Ausführen von Anwendungen in Azure benötigen Sie ein Azure-Konto.

* Wenn Sie ein Visual Studio-Abonnent sind, stehen Ihnen monatlich [kostenlose Azure-Gutschriften](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/) zur Verfügung.
* [Erstellen Sie ein kostenloses Azure-Konto](https://azure.microsoft.com/free/dotnet/). Sie erhalten dann 200 USD in Gutschriften und können Dienste auswählen, die 12 Monate lang kostenlos sind.
* Verwenden Sie ein Konto, das Ihnen vom Azure-Administrator Ihres Unternehmens zugewiesen wurde.

## <a name="configure-your-ide"></a>Konfigurieren der IDE

Beliebte Tools wie Visual Studio und Visual Studio Code verfügen über Erweiterungen, mit denen Sie direkt von Ihrer IDE aus mit Azure arbeiten können.

* [Konfigurieren von Visual Studio](./configure-visual-studio.md) für die .NET-Entwicklung mit Azure
* [Konfigurieren von Visual Studio Code](./configure-vs-code.md) für die .NET-Entwicklung mit Azure

## <a name="install-the-azure-cli"></a>Installieren der Azure CLI

Zusätzlich zur Verwendung des Azure-Portals sollten Sie die Azure CLI zum Erstellen und Verwalten von Azure-Ressourcen installieren.

* [Installieren der Azure CLI für Windows](/cli/azure/install-azure-cli-windows?tabs=azure-cli)
* [Installieren der Azure-Befehlszeilenschnittstelle für macOS](/cli/azure/install-azure-cli-macos)
* [Installieren der Azure CLI für Linux](/cli/azure/install-azure-cli-linux)

## <a name="install-additional-tools-and-utilities"></a>Installieren zusätzlicher Tools und Hilfsprogramme

Diese zusätzlichen Tools sind so konzipiert, dass Sie damit produktiver mit Azure arbeiten können.

* [Installieren Sie Azure PowerShell](/powershell/azure/install-az-ps), wenn Sie PowerShell-Skripts zum Erstellen und Verwalten von Azure-Ressourcen verwenden möchten.
* [Installieren Sie den Azure Storage-Explorer](https://azure.microsoft.com/features/storage-explorer/), um Daten in Azure-Speicherressourcen, einschließlich Blobs, Warteschlangen, Tabellen und CosmosDB-Datenbanken, hochzuladen, herunterzuladen und zu verwalten.
* [Installieren Sie Azure Data Studio](/sql/azure-data-studio/download-azure-data-studio), wenn Sie mit Azure SQL arbeiten.

## <a name="bookmark-the-following-sites"></a>Lesezeichen für die folgenden Websites

Diese Websites werden Sie bei der Azure-Entwicklung häufig verwenden.  Setzen Sie sich Lesezeichen für diese Websites, damit Sie schnell darauf zugreifen können.

* Azure-Portal: [https://portal.azure.com/](https://portal.azure.com/)
* Azure Cloud Shell: [https://shell.azure.com/](https://shell.azure.com/)
