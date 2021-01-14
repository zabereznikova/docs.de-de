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
# <a name="net-on-azure-development-environment-checklist"></a><span data-ttu-id="56824-103">Checkliste für die Entwicklungsumgebung von .NET in Azure</span><span class="sxs-lookup"><span data-stu-id="56824-103">.NET on Azure development environment checklist</span></span>

<span data-ttu-id="56824-104">Mithilfe dieser Checkliste können Sie sicherstellen, dass Ihre Entwicklungsumgebung für die .NET-Entwicklung in Azure ordnungsgemäß konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="56824-104">This checklist is provided to help you make sure you have your development environment correctly configured for .NET development with Azure</span></span>

## <a name="create-an-azure-account"></a><span data-ttu-id="56824-105">Erstellen eines Azure-Kontos</span><span class="sxs-lookup"><span data-stu-id="56824-105">Create an Azure account</span></span>

<span data-ttu-id="56824-106">Für den Zugriff auf Azure-Dienste oder das Ausführen von Anwendungen in Azure benötigen Sie ein Azure-Konto.</span><span class="sxs-lookup"><span data-stu-id="56824-106">To access Azure services or run applications in Azure, you need an Azure account.</span></span>

* <span data-ttu-id="56824-107">Wenn Sie ein Visual Studio-Abonnent sind, stehen Ihnen monatlich [kostenlose Azure-Gutschriften](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="56824-107">If you are a Visual Studio subscriber, you have monthly [free Azure credits](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/) available to you every month</span></span>
* <span data-ttu-id="56824-108">[Erstellen Sie ein kostenloses Azure-Konto](https://azure.microsoft.com/free/dotnet/). Sie erhalten dann 200 USD in Gutschriften und können Dienste auswählen, die 12 Monate lang kostenlos sind.</span><span class="sxs-lookup"><span data-stu-id="56824-108">[Create a free Azure account](https://azure.microsoft.com/free/dotnet/) and receive $200 in credits and select services free for 12 months</span></span>
* <span data-ttu-id="56824-109">Verwenden Sie ein Konto, das Ihnen vom Azure-Administrator Ihres Unternehmens zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="56824-109">Use an account assigned to you by your company's Azure administrator</span></span>

## <a name="configure-your-ide"></a><span data-ttu-id="56824-110">Konfigurieren der IDE</span><span class="sxs-lookup"><span data-stu-id="56824-110">Configure your IDE</span></span>

<span data-ttu-id="56824-111">Beliebte Tools wie Visual Studio und Visual Studio Code verfügen über Erweiterungen, mit denen Sie direkt von Ihrer IDE aus mit Azure arbeiten können.</span><span class="sxs-lookup"><span data-stu-id="56824-111">Popular tools like Visual Studio and Visual Studio Code have extensions available to let you work with Azure right from your IDE.</span></span>

* <span data-ttu-id="56824-112">[Konfigurieren von Visual Studio](./configure-visual-studio.md) für die .NET-Entwicklung mit Azure</span><span class="sxs-lookup"><span data-stu-id="56824-112">[Configure Visual Studio](./configure-visual-studio.md) for .NET development using Azure</span></span>
* <span data-ttu-id="56824-113">[Konfigurieren von Visual Studio Code](./configure-vs-code.md) für die .NET-Entwicklung mit Azure</span><span class="sxs-lookup"><span data-stu-id="56824-113">[Configure Visual Studio Code](./configure-vs-code.md) for .NET Development using Azure</span></span>

## <a name="install-the-azure-cli"></a><span data-ttu-id="56824-114">Installieren der Azure CLI</span><span class="sxs-lookup"><span data-stu-id="56824-114">Install the Azure CLI</span></span>

<span data-ttu-id="56824-115">Zusätzlich zur Verwendung des Azure-Portals sollten Sie die Azure CLI zum Erstellen und Verwalten von Azure-Ressourcen installieren.</span><span class="sxs-lookup"><span data-stu-id="56824-115">In addition to using the Azure portal, you will want to install the Azure CLI to create and manage Azure resources.</span></span>

* <span data-ttu-id="56824-116">[Installieren der Azure CLI für Windows](/cli/azure/install-azure-cli-windows?tabs=azure-cli)</span><span class="sxs-lookup"><span data-stu-id="56824-116">[Install the Azure CLI for Windows](/cli/azure/install-azure-cli-windows?tabs=azure-cli))</span></span>
* [<span data-ttu-id="56824-117">Installieren der Azure-Befehlszeilenschnittstelle für macOS</span><span class="sxs-lookup"><span data-stu-id="56824-117">Install the Azure CLI for macOS</span></span>](/cli/azure/install-azure-cli-macos)
* [<span data-ttu-id="56824-118">Installieren der Azure CLI für Linux</span><span class="sxs-lookup"><span data-stu-id="56824-118">Install the Azure CLI for Linux</span></span>](/cli/azure/install-azure-cli-linux)

## <a name="install-additional-tools-and-utilities"></a><span data-ttu-id="56824-119">Installieren zusätzlicher Tools und Hilfsprogramme</span><span class="sxs-lookup"><span data-stu-id="56824-119">Install additional tools and utilities</span></span>

<span data-ttu-id="56824-120">Diese zusätzlichen Tools sind so konzipiert, dass Sie damit produktiver mit Azure arbeiten können.</span><span class="sxs-lookup"><span data-stu-id="56824-120">These additional tools are designed to make you more productive when working with Azure.</span></span>

* <span data-ttu-id="56824-121">[Installieren Sie Azure PowerShell](/powershell/azure/install-az-ps), wenn Sie PowerShell-Skripts zum Erstellen und Verwalten von Azure-Ressourcen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="56824-121">[Install Azure PowerShell](/powershell/azure/install-az-ps) if you plan on using PowerShell scripts to create and manage Azure resources</span></span>
* <span data-ttu-id="56824-122">[Installieren Sie den Azure Storage-Explorer](https://azure.microsoft.com/features/storage-explorer/), um Daten in Azure-Speicherressourcen, einschließlich Blobs, Warteschlangen, Tabellen und CosmosDB-Datenbanken, hochzuladen, herunterzuladen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="56824-122">[Install Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/) to upload, download, and manage data in Azure storage resources including blobs, queues, tables, and CosmosDB.</span></span>
* <span data-ttu-id="56824-123">[Installieren Sie Azure Data Studio](/sql/azure-data-studio/download-azure-data-studio), wenn Sie mit Azure SQL arbeiten.</span><span class="sxs-lookup"><span data-stu-id="56824-123">[Install Azure Data Studio](/sql/azure-data-studio/download-azure-data-studio) if you are working with Azure SQL</span></span>

## <a name="bookmark-the-following-sites"></a><span data-ttu-id="56824-124">Lesezeichen für die folgenden Websites</span><span class="sxs-lookup"><span data-stu-id="56824-124">Bookmark the following sites</span></span>

<span data-ttu-id="56824-125">Diese Websites werden Sie bei der Azure-Entwicklung häufig verwenden.</span><span class="sxs-lookup"><span data-stu-id="56824-125">You will use these sites frequently when doing Azure development.</span></span>  <span data-ttu-id="56824-126">Setzen Sie sich Lesezeichen für diese Websites, damit Sie schnell darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="56824-126">Bookmark them for quick reference.</span></span>

* <span data-ttu-id="56824-127">Azure-Portal: [https://portal.azure.com/](https://portal.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="56824-127">Azure Portal - [https://portal.azure.com/](https://portal.azure.com/)</span></span>
* <span data-ttu-id="56824-128">Azure Cloud Shell: [https://shell.azure.com/](https://shell.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="56824-128">Azure Cloud Shell - [https://shell.azure.com/](https://shell.azure.com/)</span></span>
