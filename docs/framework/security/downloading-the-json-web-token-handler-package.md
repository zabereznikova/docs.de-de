---
title: Herunterladen des JSON-Webtokenhandler-Pakets
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d12b3f5b-f1f1-4a9d-a159-0c13e5976c90
caps.latest.revision: "3"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: d3821ff1da945df7c6e07e5baf69730173eacc87
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="downloading-the-json-web-token-handler-package"></a><span data-ttu-id="157e1-102">Herunterladen des JSON-Webtokenhandler-Pakets</span><span class="sxs-lookup"><span data-stu-id="157e1-102">Downloading the JSON Web Token Handler Package</span></span>
<span data-ttu-id="157e1-103">In diesem Thema wird erläutert, wie der JSON-Webtokenhandler im Projekt heruntergeladen und verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="157e1-103">This topic discusses how to download and use the JSON Web Token Handler in your project.</span></span>  
  
## <a name="downloading-the-json-web-token-handler"></a><span data-ttu-id="157e1-104">Herunterladen des JSON-Webtokenhandlers</span><span class="sxs-lookup"><span data-stu-id="157e1-104">Downloading the JSON Web Token Handler</span></span>  
 <span data-ttu-id="157e1-105">Die JSON-Webtokenhandler-Erweiterung ist als NuGet-Paket verfügbar, das die erforderlichen Assemblys und Verweise im Projekt hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="157e1-105">The JSON Web Token Handler extension is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="157e1-106">Wenn Sie NuGet noch nicht installiert haben, wechseln Sie zu [nuget.org](http://nuget.org), um es zu installieren.</span><span class="sxs-lookup"><span data-stu-id="157e1-106">If you do not already have NuGet installed, go to [nuget.org](http://nuget.org) to install it.</span></span> <span data-ttu-id="157e1-107">Sie können den Versionsverlauf für die Erweiterung anzeigen, indem Sie auf NuGet [die Seite für den JSON-Webtokenhandler](http://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/) aufrufen.</span><span class="sxs-lookup"><span data-stu-id="157e1-107">You can see the versioning history for the extension by visiting its page on NuGet: [JSON Web Token Handler on NuGet](http://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)</span></span>  
  
#### <a name="downloading-the-json-web-token-handler-by-using-the-package-manager-gui"></a><span data-ttu-id="157e1-108">Herunterladen des JSON-Webtokenhandlers mithilfe der Paket-Manager-GUI</span><span class="sxs-lookup"><span data-stu-id="157e1-108">Downloading the JSON Web Token Handler by using the Package Manager GUI</span></span>  
  
1.  <span data-ttu-id="157e1-109">Klicken Sie mit der rechten Maustaste in Visual Studio im **Projektmappen-Explorer** auf Ihr Projekt, und wählen Sie dann **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="157e1-109">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>  
  
2.  <span data-ttu-id="157e1-110">Klicken Sie im Fenster **NuGet-Pakete verwalten** auf das Suchfeld, geben Sie `JWT Token Handler` ein, und drücken Sie die **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="157e1-110">In the **Manage NuGet Packages** window, click the search box and enter `JWT Token Handler` and press **Enter**.</span></span>  
  
3.  <span data-ttu-id="157e1-111">Klicken Sie im Ergebnisbereich auf die Schaltfläche **Installieren** für das erste Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="157e1-111">From the results pane, click the **Install** button for the first result.</span></span>  
  
4.  <span data-ttu-id="157e1-112">Das Paket wird heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="157e1-112">The package will begin downloading.</span></span> <span data-ttu-id="157e1-113">Bevor es dem Projekt hinzugefügt wird, erscheint das Dialogfeld zum Akzeptieren der Lizenz.</span><span class="sxs-lookup"><span data-stu-id="157e1-113">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="157e1-114">Wenn Sie den Lizenzbedingungen zustimmen, klicken Sie auf **Ich stimme zu**.</span><span class="sxs-lookup"><span data-stu-id="157e1-114">If you agree to the license terms, click **I Accept**.</span></span>  
  
5.  <span data-ttu-id="157e1-115">Die neueste JSON-Webtokenhandler-Assemblys werden heruntergeladen und dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="157e1-115">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>  
  
#### <a name="downloading-the-json-web-token-handler-by-using-the-package-manager-console"></a><span data-ttu-id="157e1-116">Herunterladen des JSON-Webtokenhandlers mithilfe der Paket-Manager-Konsole</span><span class="sxs-lookup"><span data-stu-id="157e1-116">Downloading the JSON Web Token Handler by using the Package Manager Console</span></span>  
  
1.  <span data-ttu-id="157e1-117">Klicken Sie in Visual Studio auf **Extras**, den **Bibliotheks-Paket-Manager** und anschließend auf **Paket-Manager-Konsole**.</span><span class="sxs-lookup"><span data-stu-id="157e1-117">In Visual Studio, click **Tools**, **Library Package Manager**, and then **Package Manager Console**.</span></span>  
  
2.  <span data-ttu-id="157e1-118">Die **Paket-Manager-Konsole** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="157e1-118">The **Package Manager Console** appears.</span></span> <span data-ttu-id="157e1-119">Geben Sie folgenden Text ein, und drücken Sie die **EINGABETASTE**:</span><span class="sxs-lookup"><span data-stu-id="157e1-119">Enter the following text and press **Enter**:</span></span>  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.Jwt  
    ```  
  
3.  <span data-ttu-id="157e1-120">Die neueste JSON-Webtokenhandler-Assemblys werden heruntergeladen und dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="157e1-120">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>
