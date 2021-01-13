---
title: Konfigurieren von Visual Studio Code für die Azure-Entwicklung mit .NET
description: Dieser Artikel unterstützt Sie beim Konfigurieren von Visual Studio Code für die Azure-Entwicklung, einschließlich der Installation und Konfiguration der richtigen Plug-Ins in VS Code.
ms.date: 11/30/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 65ced99befe12d137062b4ea6a59a1ccd3099e0b
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "97700937"
---
# <a name="configure-visual-studio-code-for-azure-development"></a><span data-ttu-id="93b0e-103">Konfigurieren von Visual Studio Code für die Azure-Entwicklung</span><span class="sxs-lookup"><span data-stu-id="93b0e-103">Configure Visual Studio Code for Azure development</span></span>

<span data-ttu-id="93b0e-104">Wenn Sie Visual Studio Code verwenden (ob nun für die .NET-Entwicklung, zum Erstellen von Single-Page-Webanwendungen mit Frameworks wie Angular, React oder Vue oder zum Programmieren von Anwendungen in einer anderen Sprache, z. B. Python), sollten Sie Visual Studio Code für die Azure-Entwicklung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="93b0e-104">If you are using Visual Studio Code, whether for .NET development, for building single page applications using frameworks like Angular, React or Vue, or for writing applications in another language like Python, you will want to configure Visual Studio Code for Azure development.</span></span>

### <a name="download-visual-studio-code"></a><span data-ttu-id="93b0e-105">Visual Studio Code herunterladen</span><span class="sxs-lookup"><span data-stu-id="93b0e-105">Download Visual Studio Code</span></span>

<span data-ttu-id="93b0e-106">Wenn Visual Studio Code bereits installiert ist, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="93b0e-106">If you already have Visual Studio Code installed, you can skip this step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="93b0e-107">Visual Studio Code herunterladen</span><span class="sxs-lookup"><span data-stu-id="93b0e-107">Download Visual Studio Code</span></span>](https://code.visualstudio.com/download)

### <a name="install-the-azure-tools-extension-pack"></a><span data-ttu-id="93b0e-108">Installieren des Azure-Tools-Erweiterungspakets</span><span class="sxs-lookup"><span data-stu-id="93b0e-108">Install the Azure Tools Extension Pack</span></span>

<span data-ttu-id="93b0e-109">Mit dem [Azure-Tools-Erweiterungspaket](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack) erhalten Sie Erweiterungen für die Arbeit mit Azure App Service, Azure Functions, Azure Storage, Cosmos DB und Azure Virtual Machines in einem einzigen praktischen Paket.</span><span class="sxs-lookup"><span data-stu-id="93b0e-109">The [Azure Tools Extension Pack](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack) contains extensions for working with Azure App Service, Azure Functions, Azure Storage, Cosmos DB, and Azure Virtual Machines all in one convenient package.</span></span>

<span data-ttu-id="93b0e-110">So installieren Sie die Erweiterung über Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="93b0e-110">To install the extension from Visual Studio Code:</span></span>

1. <span data-ttu-id="93b0e-111">Drücken Sie <kbd>STRG+UMSCHALT+X</kbd>, um das Fenster **Erweiterungen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="93b0e-111">Press <kbd>Ctrl+Shift+X</kbd> to open the **Extensions** window.</span></span>
1. <span data-ttu-id="93b0e-112">Suchen Sie nach der Erweiterung *Azure-Tools*.</span><span class="sxs-lookup"><span data-stu-id="93b0e-112">Search for the *Azure Tools* extension.</span></span>
1. <span data-ttu-id="93b0e-113">Wählen Sie die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="93b0e-113">Select the **Install** button.</span></span>

![Screenshot: Visual Studio Code mit Panel „Erweiterungen“ mit Suche nach dem Azure-Tools-Erweiterungspaket](./media/visual-studio-code-azure-tools.png)

<span data-ttu-id="93b0e-115">Weitere Informationen zur Installation von Erweiterungen in Visual Studio Code finden Sie im Dokument zum [Marketplace für Erweiterungen](https://code.visualstudio.com/docs/editor/extension-gallery) auf der Visual Studio Code-Website.</span><span class="sxs-lookup"><span data-stu-id="93b0e-115">To learn more about installing extensions in Visual Studio Code, refer to the [Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery) document on the Visual Studio Code website.</span></span>

### <a name="sign-in-to-your-azure-account-with-azure-tools"></a><span data-ttu-id="93b0e-116">Anmelden bei Ihrem Azure-Konto mit den Azure-Tools</span><span class="sxs-lookup"><span data-stu-id="93b0e-116">Sign in to your Azure account with Azure Tools</span></span>

<span data-ttu-id="93b0e-117">Im linken Panel wird ein Azure-Symbol angezeigt.</span><span class="sxs-lookup"><span data-stu-id="93b0e-117">On the left hand panel, you'll see an Azure icon.</span></span> <span data-ttu-id="93b0e-118">Klicken Sie auf dieses Symbol, um Einstellungen für Azure-Dienste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="93b0e-118">Select this icon, and a control panel for Azure services will appear.</span></span> <span data-ttu-id="93b0e-119">Klicken Sie unter einem beliebigen Dienst auf **Sign in to Azure...** (Bei Azure anmelden...), um den Authentifizierungsprozess für die Azure-Tools in Visual Studio Code abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="93b0e-119">Choose **Sign in to Azure...** under any service to complete the authentication process for the Azure tools in Visual Studio Code.</span></span>

![Screenshot: Anmeldung bei Azure für die Azure-Tools in Visual Studio Code](./media/visual-studio-code-azure-login.png)

### <a name="next-steps"></a><span data-ttu-id="93b0e-121">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="93b0e-121">Next steps</span></span>

<span data-ttu-id="93b0e-122">Als Nächstes sollten Sie die Azure CLI auf Ihrer Arbeitsstation installieren.</span><span class="sxs-lookup"><span data-stu-id="93b0e-122">Next, you will want to install the Azure CLI on your workstation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="93b0e-123">Installieren der Azure-Befehlszeilenschnittstelle</span><span class="sxs-lookup"><span data-stu-id="93b0e-123">Install the Azure CLI</span></span>](./install-azure-cli.md)
