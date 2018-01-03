---
title: Herunterladen des Pakets zur Validierung der Ausstellernamenregistration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff8b0014-c5d4-4614-90f0-13fcc0ba777a
caps.latest.revision: "3"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9bf6869de939ed7eda7cd3de868e712126f71751
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="downloading-the-validating-issuer-name-registry-package"></a><span data-ttu-id="e99d1-102">Herunterladen des Pakets zur Validierung der Ausstellernamenregistration</span><span class="sxs-lookup"><span data-stu-id="e99d1-102">Downloading the Validating Issuer Name Registry Package</span></span>
<span data-ttu-id="e99d1-103">In diesem Thema wird erläutert, wie "Überprüfen der Ausstellernamensregistrierung" (VINR) im Projekt heruntergeladen und verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e99d1-103">This topic discusses how to download and use the Validating Issuer Name Registry (VINR) in your project.</span></span>  
  
## <a name="downloading-the-validating-issuer-name-registry"></a><span data-ttu-id="e99d1-104">Herunterladen von "Überprüfen der Ausstellernamensregistrierung" (VINR)</span><span class="sxs-lookup"><span data-stu-id="e99d1-104">Downloading the Validating Issuer Name Registry</span></span>  
 <span data-ttu-id="e99d1-105">Die VINR ist als NuGet-Paket verfügbar, das die erforderlichen Assemblys und Verweise im Projekt hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="e99d1-105">The VINR is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="e99d1-106">Wenn Sie NuGet noch nicht installiert haben, wechseln Sie zu [nuget.org](http://nuget.org), um es zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e99d1-106">If you do not already have NuGet installed, go to [nuget.org](http://nuget.org) to install it.</span></span> <span data-ttu-id="e99d1-107">Sie können den Versionsverlauf für die Erweiterung anzeigen, indem Sie deren Seite auf NuGet aufrufen: [Überprüfen der Ausstellernamensregistrierung auf NuGet von Microsoft](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/).</span><span class="sxs-lookup"><span data-stu-id="e99d1-107">You can see the versioning history for the extension by visiting its page on NuGet: [Microsoft Validating Issuer Name Registry on NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)</span></span>  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-gui"></a><span data-ttu-id="e99d1-108">Herunterladen von "Überprüfen der Ausstellernamensregistrierung" mithilfe des Paket-Managers GUI</span><span class="sxs-lookup"><span data-stu-id="e99d1-108">Downloading the Validating Issuer Name Registry by using the Package Manager GUI</span></span>  
  
1.  <span data-ttu-id="e99d1-109">Klicken Sie mit der rechten Maustaste in Visual Studio im **Projektmappen-Explorer** auf Ihr Projekt, und wählen Sie dann **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="e99d1-109">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>  
  
2.  <span data-ttu-id="e99d1-110">Klicken Sie im Fenster **NuGet-Pakete verwalten** auf das Suchfeld, geben Sie `ValidatingIssuerNameRegistry` ein, und drücken Sie die **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="e99d1-110">In the **Manage NuGet Packages** window, click the search box and enter `ValidatingIssuerNameRegistry` and press **Enter**.</span></span>  
  
3.  <span data-ttu-id="e99d1-111">Klicken Sie im Ergebnisbereich auf die Schaltfläche **Installieren** für das erste Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="e99d1-111">From the results pane, click the **Install** button for the first result.</span></span>  
  
4.  <span data-ttu-id="e99d1-112">Das Paket wird heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="e99d1-112">The package will begin downloading.</span></span> <span data-ttu-id="e99d1-113">Bevor es dem Projekt hinzugefügt wird, erscheint das Dialogfeld zum Akzeptieren der Lizenz.</span><span class="sxs-lookup"><span data-stu-id="e99d1-113">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="e99d1-114">Wenn Sie den Lizenzbedingungen zustimmen, klicken Sie auf **Ich stimme zu**.</span><span class="sxs-lookup"><span data-stu-id="e99d1-114">If you agree to the license terms, click **I Accept**.</span></span>  
  
5.  <span data-ttu-id="e99d1-115">Die neuesten VINR-Assemblys werden heruntergeladen und dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e99d1-115">The latest VINR assemblies will be downloaded and added to your project.</span></span>  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-console"></a><span data-ttu-id="e99d1-116">Herunterladen von "Überprüfen der Ausstellernamensregistrierung" mithilfe der Paket-Manager-Konsole</span><span class="sxs-lookup"><span data-stu-id="e99d1-116">Downloading the Validating Issuer Name Registry by using the Package Manager Console</span></span>  
  
1.  <span data-ttu-id="e99d1-117">Klicken Sie in Visual Studio auf **Extras**, den **Bibliotheks-Paket-Manager** und anschließend auf **Paket-Manager-Konsole**.</span><span class="sxs-lookup"><span data-stu-id="e99d1-117">In Visual Studio, click **Tools**, **Library Package Manager**, and then **Package Manager Console**.</span></span>  
  
2.  <span data-ttu-id="e99d1-118">Die **Paket-Manager-Konsole** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e99d1-118">The **Package Manager Console** appears.</span></span> <span data-ttu-id="e99d1-119">Geben Sie folgenden Text ein, und drücken Sie die **EINGABETASTE**:</span><span class="sxs-lookup"><span data-stu-id="e99d1-119">Enter the following text and press **Enter**:</span></span>  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry  
    ```  
  
3.  <span data-ttu-id="e99d1-120">Die neuesten VINR-Assemblys werden heruntergeladen und dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e99d1-120">The latest VINR assemblies will be downloaded and added to your project.</span></span>
