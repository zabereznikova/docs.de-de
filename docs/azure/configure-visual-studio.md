---
title: Konfigurieren von Visual Studio für die Azure-Entwicklung mit .NET
description: Dieser Artikel unterstützt Sie beim Konfigurieren von Visual Studio für die Azure-Entwicklung, einschließlich der Installation der richtigen Workloads und des Herstellens einer Verbindung zwischen Visual Studio und Ihrem Azure-Konto.
ms.date: 11/30/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 986469bd07657d968045465803047dc21d76dd62
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "97700940"
---
# <a name="configure-visual-studio-for-azure-development-with-net"></a><span data-ttu-id="75bb4-103">Konfigurieren von Visual Studio für die Azure-Entwicklung mit .NET</span><span class="sxs-lookup"><span data-stu-id="75bb4-103">Configure Visual Studio for Azure development with .NET</span></span>

<span data-ttu-id="75bb4-104">Visual Studio enthält Tools, die Sie bei der Entwicklung und Bereitstellung von Anwendungen in Azure unterstützen.</span><span class="sxs-lookup"><span data-stu-id="75bb4-104">Visual Studio includes tooling to help with the development and deployment of applications on Azure.</span></span>  <span data-ttu-id="75bb4-105">Dieser Leitfaden hilft Ihnen dabei, sicherzustellen, dass Sie Visual Studio ordnungsgemäß für die Azure-Entwicklung konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="75bb4-105">This guide will help you make sure that you have Visual Studio properly configured for Azure development.</span></span>

### <a name="download-visual-studio-2019"></a><span data-ttu-id="75bb4-106">Herunterladen von Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="75bb4-106">Download Visual Studio 2019</span></span>

<span data-ttu-id="75bb4-107">Wenn Visual Studio 2019 bereits installiert ist, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="75bb4-107">If you already have Visual Studio 2019 installed, you can skip this step.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="75bb4-108">Herunterladen von Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="75bb4-108">Download Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads/)

### <a name="install-azure-workloads"></a><span data-ttu-id="75bb4-109">Installieren von Azure-Workloads</span><span class="sxs-lookup"><span data-stu-id="75bb4-109">Install Azure workloads</span></span>

<span data-ttu-id="75bb4-110">Starten Sie den **Visual Studio-Installer**, und stellen Sie sicher, dass die Workloads **Azure-Entwicklung** und **ASP.NET und Webentwicklung** installiert sind.</span><span class="sxs-lookup"><span data-stu-id="75bb4-110">Launch the **Visual Studio Installer** and validate that you have the workloads **Azure development** and **ASP.NET and web development** are installed.</span></span>  <span data-ttu-id="75bb4-111">Wenn eine dieser Workloads nicht installiert ist, klicken Sie auf diese, um sie zu installieren.</span><span class="sxs-lookup"><span data-stu-id="75bb4-111">If either of these workloads is not installed, select these workloads to install them.</span></span>

![Screenshot: Der Visual Studio-Installer mit den ausgewählten Workloads „Azure-Entwicklung“ und „ASP.NET und Webentwicklung“](./media/visual-studio-installer-azure-development.png)

### <a name="authenticate-visual-studio-with-azure"></a><span data-ttu-id="75bb4-113">Authentifizieren von Visual Studio mit Azure</span><span class="sxs-lookup"><span data-stu-id="75bb4-113">Authenticate Visual Studio with Azure</span></span>

<span data-ttu-id="75bb4-114">Beim Debuggen von Apps über Visual Studio kann sich Visual Studio mit Ihrem Azure-Konto bei Azure-Ressourcen authentifizieren und auf diese Ressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="75bb4-114">When debugging apps through Visual Studio, Visual Studio can use your Azure account to authenticate and access Azure Resources with.</span></span>  <span data-ttu-id="75bb4-115">Dieses Konto wird auch verwendet, wenn Sie Apps direkt aus Visual Studio in Azure veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="75bb4-115">This account is also used when you publish apps directly from Visual Studio to Azure.</span></span>

<span data-ttu-id="75bb4-116">Klicken Sie auf **Extras** > **Optionen**, um das Dialogfeld **Optionen** zu öffnen und Ihr Azure-Konto über Visual Studio zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="75bb4-116">To authenticate your Azure account from Visual Studio, select the **Tools** > **Options** menu to launch the **Options** dialog.</span></span> <span data-ttu-id="75bb4-117">Navigieren Sie zu den `Azure Service Authentication`-Optionen (Azure-Dienstauthentifizierung), und melden Sie sich mit Ihrem Azure-Konto an.</span><span class="sxs-lookup"><span data-stu-id="75bb4-117">Navigate to the `Azure Service Authentication` options and sign in using your Azure account.</span></span>

![Screenshot: Visual Studio-Dialogfeld „Optionen“ mit Azure-Anmeldung](./media/visual-studio-azure-login-dialog.png)

### <a name="next-steps"></a><span data-ttu-id="75bb4-119">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="75bb4-119">Next steps</span></span>

<span data-ttu-id="75bb4-120">Wenn Sie auch [Visual Studio Code](https://code.visualstudio.com/) für die Entwicklung in .NET oder einer anderen Sprache verwenden, sollten Sie außerdem [Visual Studio Code für die Azure-Entwicklung](./configure-vs-code.md) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="75bb4-120">If you also use [Visual Studio Code](https://code.visualstudio.com/) for development in .NET or any other language, you should also [configure Visual Studio Code for Azure development](./configure-vs-code.md).</span></span> <span data-ttu-id="75bb4-121">Fahren Sie andernfalls mit dem [Installieren der Azure CLI](./install-azure-cli.md) fort.</span><span class="sxs-lookup"><span data-stu-id="75bb4-121">Otherwise, proceed to [Installing the Azure CLI](./install-azure-cli.md).</span></span>
