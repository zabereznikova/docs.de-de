---
title: Herunterladen des JSON-Webtokenhandler-Pakets
ms.date: 10/10/2018
ms.assetid: d12b3f5b-f1f1-4a9d-a159-0c13e5976c90
ms.openlocfilehash: a8685a71d46778d932595965f32c0041b176bd83
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633527"
---
# <a name="download-the-json-web-token-handler-package"></a><span data-ttu-id="f29f3-102">Herunterladen des JSON-Webtokenhandler-Pakets</span><span class="sxs-lookup"><span data-stu-id="f29f3-102">Download the JSON Web Token Handler Package</span></span>

<span data-ttu-id="f29f3-103">In diesem Thema wird erläutert, wie der JSON-Webtokenhandler im Projekt heruntergeladen und verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f29f3-103">This topic discusses how to download and use the JSON Web Token Handler in your project.</span></span>

<span data-ttu-id="f29f3-104">Die JSON-Webtokenhandler-Erweiterung ist als NuGet-Paket verfügbar, das die erforderlichen Assemblys und Verweise im Projekt hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="f29f3-104">The JSON Web Token Handler extension is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="f29f3-105">Wenn Sie NuGet noch nicht installiert haben, wechseln Sie zu [nuget.org](https://nuget.org), um es zu installieren.</span><span class="sxs-lookup"><span data-stu-id="f29f3-105">If you do not already have NuGet installed, go to [nuget.org](https://nuget.org) to install it.</span></span> <span data-ttu-id="f29f3-106">Sie können den Versionsverlauf für die Erweiterung anzeigen, indem Sie auf der Seite auf NuGet: [JSON-Webtokenhandler für NuGet](https://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)</span><span class="sxs-lookup"><span data-stu-id="f29f3-106">You can see the versioning history for the extension by visiting its page on NuGet: [JSON Web Token Handler on NuGet](https://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)</span></span>

## <a name="use-the-package-manager-gui"></a><span data-ttu-id="f29f3-107">Verwenden Sie die Paket-Manager-GUI</span><span class="sxs-lookup"><span data-stu-id="f29f3-107">Use the Package Manager GUI</span></span>

1. <span data-ttu-id="f29f3-108">Klicken Sie mit der rechten Maustaste in Visual Studio im **Projektmappen-Explorer** auf Ihr Projekt, und wählen Sie dann **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="f29f3-108">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>

2. <span data-ttu-id="f29f3-109">Klicken Sie im Fenster **NuGet-Pakete verwalten** auf das Suchfeld, geben Sie `JWT Token Handler` ein, und drücken Sie die **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="f29f3-109">In the **Manage NuGet Packages** window, click the search box and enter `JWT Token Handler` and press **Enter**.</span></span>

3. <span data-ttu-id="f29f3-110">Klicken Sie im Ergebnisbereich auf die Schaltfläche **Installieren** für das erste Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="f29f3-110">From the results pane, click the **Install** button for the first result.</span></span>

4. <span data-ttu-id="f29f3-111">Das Paket wird heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="f29f3-111">The package will begin downloading.</span></span> <span data-ttu-id="f29f3-112">Bevor es dem Projekt hinzugefügt wird, erscheint das Dialogfeld zum Akzeptieren der Lizenz.</span><span class="sxs-lookup"><span data-stu-id="f29f3-112">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="f29f3-113">Wenn Sie den Lizenzbedingungen zustimmen, klicken Sie auf **Ich stimme zu**.</span><span class="sxs-lookup"><span data-stu-id="f29f3-113">If you agree to the license terms, click **I Accept**.</span></span>

5. <span data-ttu-id="f29f3-114">Die neueste JSON-Webtokenhandler-Assemblys werden heruntergeladen und dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f29f3-114">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>

## <a name="use-the-package-manager-console"></a><span data-ttu-id="f29f3-115">Verwenden Sie die Paket-Manager-Konsole</span><span class="sxs-lookup"><span data-stu-id="f29f3-115">Use the Package Manager Console</span></span>

1. <span data-ttu-id="f29f3-116">Klicken Sie in Visual Studio auf **Tools** > **NuGet Package Manager** > **-Paket-Manager-Konsole**.</span><span class="sxs-lookup"><span data-stu-id="f29f3-116">In Visual Studio, click **Tools** > **NuGet Package Manager** > **Package Manager Console**.</span></span>

2. <span data-ttu-id="f29f3-117">Die **Paket-Manager-Konsole** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f29f3-117">The **Package Manager Console** appears.</span></span> <span data-ttu-id="f29f3-118">Geben Sie folgenden Text ein, und drücken Sie die **EINGABETASTE**:</span><span class="sxs-lookup"><span data-stu-id="f29f3-118">Enter the following text and press **Enter**:</span></span>

    ```powershell
    Install-Package System.IdentityModel.Tokens.Jwt
    ```

3. <span data-ttu-id="f29f3-119">Die neueste JSON-Webtokenhandler-Assemblys werden heruntergeladen und dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f29f3-119">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>
