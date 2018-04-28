---
title: Bereitstellen von Anwendungen, die auf die PrintForm-Komponente (Visual Basic) verweisen.
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- PrintForm component [Visual Basic], deploying
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f49a5ef8dd4e36c9ab055ca01dc25ed05b083349
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="deploying-applications-that-reference-the-printform-component-visual-basic"></a><span data-ttu-id="76905-102">Bereitstellen von Anwendungen, die auf die PrintForm-Komponente (Visual Basic) verweisen.</span><span class="sxs-lookup"><span data-stu-id="76905-102">Deploying applications that reference the PrintForm component (Visual Basic)</span></span>
<span data-ttu-id="76905-103">Wenn Sie eine Anwendung bereitstellen möchten, die auf die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente verweist, muss die Komponente auf dem Zielcomputer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="76905-103">If you want to deploy an application that references the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component, the component must be installed on the destination computer.</span></span>  
  
 <span data-ttu-id="76905-104">Die PowerPack-Steuerelemente sind nicht mehr in Visual Studio enthalten, Sie können sie jedoch aus dem [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="76905-104">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
## <a name="installing-the-printform-as-a-prerequisite"></a><span data-ttu-id="76905-105">Installieren von PrintForm als erforderliche Komponente</span><span class="sxs-lookup"><span data-stu-id="76905-105">Installing the PrintForm as a prerequisite</span></span>  
 <span data-ttu-id="76905-106">Um eine Anwendung erfolgreich bereitzustellen, müssen auch alle Komponenten bereitgestellt werden, auf die die Anwendung verweist.</span><span class="sxs-lookup"><span data-stu-id="76905-106">To successfully deploy an application, you must also deploy all components that are referenced by the application.</span></span> <span data-ttu-id="76905-107">Der Vorgang des Installierens von erforderlichen Komponenten wird als *Bootstrapping*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="76905-107">The process of installing prerequisite components is known as *bootstrapping*.</span></span>  
  
 <span data-ttu-id="76905-108">Wenn die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Komponente auf dem Entwicklungscomputer installiert ist, wird das Visual Studio-Bootstrapper-Verzeichnis ein Microsoft Visual Basic Power Packs-Bootstrapperpaket hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="76905-108">When the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is installed on your development computer, a Microsoft Visual Basic Power Packs bootstrapper package is added to the Visual Studio bootstrapper directory.</span></span> <span data-ttu-id="76905-109">Dieses Paket steht dann beim Befolgen der Anweisungen zum Hinzufügen von erforderlichen Komponenten für die Bereitstellung mithilfe von [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] oder eines Windows-Installationsprogramms zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="76905-109">This package is then available when you follow the procedures for adding prerequisites for either [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] or Windows Installer deployment.</span></span>  
  
 <span data-ttu-id="76905-110">Standardmäßig werden Bootstrappingkomponenten vom gleichen Speicherort wie das Installationspaket bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="76905-110">By default, bootstrapped components are deployed from the same location as the installation package.</span></span> <span data-ttu-id="76905-111">Alternativ können Sie die Komponenten über eine URL oder einen Dateifreigabe-Speicherort bereitstellen und Benutzern so den Download bei Bedarf ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="76905-111">Alternatively, you can choose to deploy the components from a URL or file share location from which users can download them as necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="76905-112">Zum Installieren von Bootstrapperkomponenten benötigt der Benutzer möglicherweise Administrator- oder ähnliche Benutzerberechtigungen auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="76905-112">To install bootstrapped components, the user might need administrative or similar user permissions on the computer.</span></span> <span data-ttu-id="76905-113">Im Fall von [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] -Anwendungen bedeutet dies, dass die Benutzer Administratorberechtigungen zum Installieren der Anwendung benötigen, unabhängig von der Sicherheitsstufe, die von der Anwendung vorgegeben ist.</span><span class="sxs-lookup"><span data-stu-id="76905-113">For [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] applications, this means that the user will need administrative permissions to install the application, regardless of the security level specified by the application.</span></span> <span data-ttu-id="76905-114">Nach der Installation können die Benutzer die Anwendung ohne Administratorberechtigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="76905-114">After the application is installed, the user can run the application without administrative permissions.</span></span>  
  
 <span data-ttu-id="76905-115">Während der Installation werden die Benutzer zur Installation der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente aufgefordert, wenn sie auf dem Zielcomputer nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="76905-115">During installation, users will be prompted to install the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component if it is not present on the destination computer.</span></span>  
  
 <span data-ttu-id="76905-116">Als Alternative zum Bootstrapping bietet sich eine Vorabbereitstellung der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente mithilfe eines elektronischen Softwareverteilungssystems wie Microsoft Systems Management Server an.</span><span class="sxs-lookup"><span data-stu-id="76905-116">As an alternative to bootstrapping, you can pre-deploy the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component by using an electronic software distribution system like Microsoft Systems Management Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76905-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="76905-117">See also</span></span>  
 [<span data-ttu-id="76905-118">Gewusst wie: Installieren von erforderlichen Komponenten mit einer ClickOnce-Anwendung</span><span class="sxs-lookup"><span data-stu-id="76905-118">How to: Install Prerequisites with a ClickOnce Application</span></span>](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)  
 [<span data-ttu-id="76905-119">PrintForm-Komponente</span><span class="sxs-lookup"><span data-stu-id="76905-119">PrintForm Component</span></span>](../../../visual-basic/developing-apps/printing/printform-component.md)
