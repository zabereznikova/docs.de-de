---
title: Herunterladen des Pakets zur Validierung der Ausstellernamenregistration
ms.date: 10/10/2018
ms.assetid: ff8b0014-c5d4-4614-90f0-13fcc0ba777a
ms.openlocfilehash: 833a0722fdd27df4e488ed7fac99444c6d9b8905
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2018
ms.locfileid: "49316186"
---
# <a name="download-the-validating-issuer-name-registry-package"></a><span data-ttu-id="dca75-102">Der Aussteller Pakets zur Validierung der herunterladen</span><span class="sxs-lookup"><span data-stu-id="dca75-102">Download the Validating Issuer Name Registry Package</span></span>

<span data-ttu-id="dca75-103">In diesem Thema wird erläutert, wie "Überprüfen der Ausstellernamensregistrierung" (VINR) im Projekt heruntergeladen und verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dca75-103">This topic discusses how to download and use the Validating Issuer Name Registry (VINR) in your project.</span></span>

<span data-ttu-id="dca75-104">Die VINR ist als NuGet-Paket verfügbar, das die erforderlichen Assemblys und Verweise im Projekt hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="dca75-104">The VINR is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="dca75-105">Wenn Sie NuGet noch nicht installiert haben, wechseln Sie zu [nuget.org](https://nuget.org), um es zu installieren.</span><span class="sxs-lookup"><span data-stu-id="dca75-105">If you do not already have NuGet installed, go to [nuget.org](https://nuget.org) to install it.</span></span> <span data-ttu-id="dca75-106">Sie können den Versionsverlauf für die Erweiterung anzeigen, indem Sie deren Seite auf NuGet aufrufen: [Überprüfen der Ausstellernamensregistrierung auf NuGet von Microsoft](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/).</span><span class="sxs-lookup"><span data-stu-id="dca75-106">You can see the versioning history for the extension by visiting its page on NuGet: [Microsoft Validating Issuer Name Registry on NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)</span></span>

## <a name="use-the-package-manager-gui"></a><span data-ttu-id="dca75-107">Verwenden Sie die Paket-Manager-GUI</span><span class="sxs-lookup"><span data-stu-id="dca75-107">Use the Package Manager GUI</span></span>

1. <span data-ttu-id="dca75-108">Klicken Sie mit der rechten Maustaste in Visual Studio im **Projektmappen-Explorer** auf Ihr Projekt, und wählen Sie dann **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="dca75-108">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>

2. <span data-ttu-id="dca75-109">Klicken Sie im Fenster **NuGet-Pakete verwalten** auf das Suchfeld, geben Sie `ValidatingIssuerNameRegistry` ein, und drücken Sie die **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="dca75-109">In the **Manage NuGet Packages** window, click the search box and enter `ValidatingIssuerNameRegistry` and press **Enter**.</span></span>

3. <span data-ttu-id="dca75-110">Klicken Sie im Ergebnisbereich auf die Schaltfläche **Installieren** für das erste Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="dca75-110">From the results pane, click the **Install** button for the first result.</span></span>

4. <span data-ttu-id="dca75-111">Das Paket wird heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="dca75-111">The package will begin downloading.</span></span> <span data-ttu-id="dca75-112">Bevor es dem Projekt hinzugefügt wird, erscheint das Dialogfeld zum Akzeptieren der Lizenz.</span><span class="sxs-lookup"><span data-stu-id="dca75-112">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="dca75-113">Wenn Sie den Lizenzbedingungen zustimmen, klicken Sie auf **Ich stimme zu**.</span><span class="sxs-lookup"><span data-stu-id="dca75-113">If you agree to the license terms, click **I Accept**.</span></span>

5. <span data-ttu-id="dca75-114">Die neuesten VINR-Assemblys werden heruntergeladen und dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dca75-114">The latest VINR assemblies will be downloaded and added to your project.</span></span>

## <a name="use-the-package-manager-console"></a><span data-ttu-id="dca75-115">Verwenden Sie die Paket-Manager-Konsole</span><span class="sxs-lookup"><span data-stu-id="dca75-115">Use the Package Manager Console</span></span>

1. <span data-ttu-id="dca75-116">Klicken Sie in Visual Studio auf **Tools** > **NuGet Package Manager** > **-Paket-Manager-Konsole**.</span><span class="sxs-lookup"><span data-stu-id="dca75-116">In Visual Studio, click **Tools** > **NuGet Package Manager** > **Package Manager Console**.</span></span>

2. <span data-ttu-id="dca75-117">Die **Paket-Manager-Konsole** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dca75-117">The **Package Manager Console** appears.</span></span> <span data-ttu-id="dca75-118">Geben Sie folgenden Text ein, und drücken Sie die **EINGABETASTE**:</span><span class="sxs-lookup"><span data-stu-id="dca75-118">Enter the following text and press **Enter**:</span></span>

    ```powershell
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry
    ```

3. <span data-ttu-id="dca75-119">Die neuesten VINR-Assemblys werden heruntergeladen und dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dca75-119">The latest VINR assemblies will be downloaded and added to your project.</span></span>