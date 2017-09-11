---
title: Bereitstellen von Anwendungen, die auf Power Packs-Steuerelemente (Visual Studio) verweisen | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Power Packs, deploying
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ad1aba4f2e725abbe560f0c71fbb543e15741200
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="deploying-applications-that-reference-power-packs-controls-visual-studio"></a><span data-ttu-id="0a9ce-102">Bereitstellen von Anwendungen, die auf Power Packs-Steuerelemente (Visual Studio) verweisen.</span><span class="sxs-lookup"><span data-stu-id="0a9ce-102">Deploying applications that reference Power Packs controls (Visual Studio)</span></span>
<span data-ttu-id="0a9ce-103">Wenn Sie möchten eine Anwendung bereitstellen, die auf Power Packs-Steuerelemente verweist (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, oder <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), müssen die Steuerelemente auf dem Zielcomputer installiert werden.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> </xref:Microsoft.VisualBasic.PowerPacks.OvalShape> </xref:Microsoft.VisualBasic.PowerPacks.LineShape></span><span class="sxs-lookup"><span data-stu-id="0a9ce-103">If you want to deploy an application that references the Power Packs controls (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, or <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), the controls must be installed on the destination computer.</span></span>  
  
## <a name="installing-the-power-packs-controls-as-a-prerequisite"></a><span data-ttu-id="0a9ce-104">Installieren die Power Packs-Steuerelemente als erforderliche Komponente</span><span class="sxs-lookup"><span data-stu-id="0a9ce-104">Installing the Power Packs controls as a prerequisite</span></span>  
 <span data-ttu-id="0a9ce-105">Um eine Anwendung erfolgreich bereitzustellen, müssen auch alle Komponenten bereitgestellt werden, auf die die Anwendung verweist.</span><span class="sxs-lookup"><span data-stu-id="0a9ce-105">To successfully deploy an application, you must also deploy all components that are referenced by the application.</span></span> <span data-ttu-id="0a9ce-106">Der Vorgang des Installierens von erforderlichen Komponenten wird als *Bootstrapping*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0a9ce-106">The process of installing prerequisite components is known as *bootstrapping*.</span></span>  
  
 <span data-ttu-id="0a9ce-107">Wenn [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] installiert ist, auf dem Entwicklungscomputer ein Power Packs-Bootstrapperpaket hinzugefügt wird die [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Bootstrapperverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0a9ce-107">When [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] is installed on your development computer, a Power Packs bootstrapper package is added to the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] bootstrapper directory.</span></span> <span data-ttu-id="0a9ce-108">Dieses Paket ist dann verfügbar, wenn das Verfahren zum Hinzufügen von erforderlichen Komponenten für eine [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] oder Windows Installer-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="0a9ce-108">This package is then available when you follow the procedures for adding prerequisites for either [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] or Windows Installer deployment.</span></span>  
  
 <span data-ttu-id="0a9ce-109">Standardmäßig werden Bootstrappingkomponenten vom gleichen Speicherort wie das Installationspaket bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="0a9ce-109">By default, bootstrapped components are deployed from the same location as the installation package.</span></span> <span data-ttu-id="0a9ce-110">Alternativ können Sie die Komponenten über eine URL oder einen Dateifreigabe-Speicherort bereitstellen und Benutzern so den Download bei Bedarf ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="0a9ce-110">Alternatively, you can choose to deploy the components from a URL or file share location from which users can download them as necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a9ce-111">Zum Installieren von Bootstrapperkomponenten benötigt der Benutzer möglicherweise Administrator- oder ähnliche Benutzerberechtigungen auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="0a9ce-111">To install bootstrapped components, the user might need administrative or similar user permissions on the computer.</span></span> <span data-ttu-id="0a9ce-112">Für [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] Applications, bedeutet dies, dass der Benutzer Administratorrechte zur Installation der Anwendung, unabhängig von der Sicherheitsstufe, die von der Anwendung angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0a9ce-112">For [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] applications, this means that the user will need administrative permissions to install the application, regardless of the security level specified by the application.</span></span> <span data-ttu-id="0a9ce-113">Nach der Installation können die Benutzer die Anwendung ohne Administratorberechtigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="0a9ce-113">After the application is installed, the user can run the application without administrative permissions.</span></span>  
  
 <span data-ttu-id="0a9ce-114">Während der Installation werden Benutzer aufgefordert, die Power Packs-Steuerelemente zu installieren, wenn sie nicht auf dem Zielcomputer vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="0a9ce-114">During installation, users will be prompted to install the Power Packs controls if they are not present on the destination computer.</span></span>  
  
 <span data-ttu-id="0a9ce-115">Als Alternative zum bootstrapping können Sie die Power Packs-Steuerelemente vorab bereitstellen, mit einem elektronischen Softwareverteilungssystem wie Microsoft Systems Management Server.</span><span class="sxs-lookup"><span data-stu-id="0a9ce-115">As an alternative to bootstrapping, you can pre-deploy the Power Packs controls by using an electronic software distribution system such as Microsoft Systems Management Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a9ce-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a9ce-116">See also</span></span>  
 <span data-ttu-id="0a9ce-117">[Gewusst wie: Installieren von erforderlichen Komponenten mit einer ClickOnce-Anwendung](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5) </span><span class="sxs-lookup"><span data-stu-id="0a9ce-117">[How to: Install Prerequisites with a ClickOnce Application](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5) </span></span>  
<span data-ttu-id="0a9ce-118"> [Visual Basic Power Packs-Steuerelemente](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)</span><span class="sxs-lookup"><span data-stu-id="0a9ce-118"> [Visual Basic Power Packs Controls](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)</span></span>
