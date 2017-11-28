---
title: Bereitstellen von Anwendungen, die auf Power Packs-Steuerelemente (Visual Studio) verweisen.
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: Power Packs, deploying
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2a9562acf05cd27eed7bc1ad963845af9a7ca5f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="deploying-applications-that-reference-power-packs-controls-visual-studio"></a><span data-ttu-id="08c7e-102">Bereitstellen von Anwendungen, die auf Power Packs-Steuerelemente (Visual Studio) verweisen.</span><span class="sxs-lookup"><span data-stu-id="08c7e-102">Deploying applications that reference Power Packs controls (Visual Studio)</span></span>
<span data-ttu-id="08c7e-103">Wenn Sie möchten eine Anwendung bereitstellen, die auf Power Packs-Steuerelemente verweist (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, oder <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), die Steuerelemente auf dem Zielcomputer installiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="08c7e-103">If you want to deploy an application that references the Power Packs controls (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, or <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), the controls must be installed on the destination computer.</span></span>  
  
## <a name="installing-the-power-packs-controls-as-a-prerequisite"></a><span data-ttu-id="08c7e-104">Installieren die Power Packs-Steuerelemente als erforderliche Komponente</span><span class="sxs-lookup"><span data-stu-id="08c7e-104">Installing the Power Packs controls as a prerequisite</span></span>  
 <span data-ttu-id="08c7e-105">Um eine Anwendung erfolgreich bereitzustellen, müssen auch alle Komponenten bereitgestellt werden, auf die die Anwendung verweist.</span><span class="sxs-lookup"><span data-stu-id="08c7e-105">To successfully deploy an application, you must also deploy all components that are referenced by the application.</span></span> <span data-ttu-id="08c7e-106">Der Vorgang des Installierens von erforderlichen Komponenten wird als *Bootstrapping*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="08c7e-106">The process of installing prerequisite components is known as *bootstrapping*.</span></span>  
  
 <span data-ttu-id="08c7e-107">Wenn [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] installiert ist, auf dem Entwicklungscomputer ein Power Packs-Bootstrapperpaket hinzugefügt wird die [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Bootstrapper-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="08c7e-107">When [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] is installed on your development computer, a Power Packs bootstrapper package is added to the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] bootstrapper directory.</span></span> <span data-ttu-id="08c7e-108">Dieses Paket steht dann beim Befolgen der Anweisungen zum Hinzufügen von erforderlichen Komponenten für die Bereitstellung mithilfe von [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] oder eines Windows-Installationsprogramms zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="08c7e-108">This package is then available when you follow the procedures for adding prerequisites for either [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] or Windows Installer deployment.</span></span>  
  
 <span data-ttu-id="08c7e-109">Standardmäßig werden Bootstrappingkomponenten vom gleichen Speicherort wie das Installationspaket bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="08c7e-109">By default, bootstrapped components are deployed from the same location as the installation package.</span></span> <span data-ttu-id="08c7e-110">Alternativ können Sie die Komponenten über eine URL oder einen Dateifreigabe-Speicherort bereitstellen und Benutzern so den Download bei Bedarf ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="08c7e-110">Alternatively, you can choose to deploy the components from a URL or file share location from which users can download them as necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08c7e-111">Zum Installieren von Bootstrapperkomponenten benötigt der Benutzer möglicherweise Administrator- oder ähnliche Benutzerberechtigungen auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="08c7e-111">To install bootstrapped components, the user might need administrative or similar user permissions on the computer.</span></span> <span data-ttu-id="08c7e-112">Im Fall von [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] -Anwendungen bedeutet dies, dass die Benutzer Administratorberechtigungen zum Installieren der Anwendung benötigen, unabhängig von der Sicherheitsstufe, die von der Anwendung vorgegeben ist.</span><span class="sxs-lookup"><span data-stu-id="08c7e-112">For [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] applications, this means that the user will need administrative permissions to install the application, regardless of the security level specified by the application.</span></span> <span data-ttu-id="08c7e-113">Nach der Installation können die Benutzer die Anwendung ohne Administratorberechtigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="08c7e-113">After the application is installed, the user can run the application without administrative permissions.</span></span>  
  
 <span data-ttu-id="08c7e-114">Während der Installation werden Benutzer aufgefordert, Power Packs-Steuerelemente zu installieren, wenn sie nicht auf dem Zielcomputer vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="08c7e-114">During installation, users will be prompted to install the Power Packs controls if they are not present on the destination computer.</span></span>  
  
 <span data-ttu-id="08c7e-115">Als Alternative zum bootstrapping können Sie die Power Packs-Steuerelemente vorab bereitstellen, mit einem elektronischen Softwareverteilungssystem wie Microsoft Systems Management Server.</span><span class="sxs-lookup"><span data-stu-id="08c7e-115">As an alternative to bootstrapping, you can pre-deploy the Power Packs controls by using an electronic software distribution system such as Microsoft Systems Management Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08c7e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08c7e-116">See also</span></span>  
 [<span data-ttu-id="08c7e-117">Gewusst wie: Installieren von erforderlichen Komponenten mit einer ClickOnce-Anwendung</span><span class="sxs-lookup"><span data-stu-id="08c7e-117">How to: Install Prerequisites with a ClickOnce Application</span></span>](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)  
 [<span data-ttu-id="08c7e-118">Visual Basic Power Packs-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="08c7e-118">Visual Basic Power Packs Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)
