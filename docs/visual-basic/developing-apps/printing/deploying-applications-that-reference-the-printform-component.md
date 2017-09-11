---
title: Bereitstellen von Anwendungen, die sich auf die PrintForm-Komponente (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- PrintForm component [Visual Basic], deploying
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7b625e0c58653f1ee9a2d263d7d2d29ad3b2e3c1
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="deploying-applications-that-reference-the-printform-component-visual-basic"></a><span data-ttu-id="6f7be-102">Bereitstellen von Anwendungen, die sich auf die PrintForm-Komponente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f7be-102">Deploying applications that reference the PrintForm component (Visual Basic)</span></span>
<span data-ttu-id="6f7be-103">Wenn Sie möchten eine Anwendung bereitstellen, verweist die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>Komponente, die die Komponente muss auf dem Zielcomputer installiert werden.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm></span><span class="sxs-lookup"><span data-stu-id="6f7be-103">If you want to deploy an application that references the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component, the component must be installed on the destination computer.</span></span>  
  
 <span data-ttu-id="6f7be-104">Die PowerPack-Steuerelemente sind nicht mehr in Visual Studio enthalten, Sie können sie jedoch aus dem [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="6f7be-104">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
## <a name="installing-the-printform-as-a-prerequisite"></a><span data-ttu-id="6f7be-105">Installieren der PrintForm als erforderliche Komponente</span><span class="sxs-lookup"><span data-stu-id="6f7be-105">Installing the PrintForm as a prerequisite</span></span>  
 <span data-ttu-id="6f7be-106">Um eine Anwendung erfolgreich bereitzustellen, müssen auch alle Komponenten bereitgestellt werden, auf die die Anwendung verweist.</span><span class="sxs-lookup"><span data-stu-id="6f7be-106">To successfully deploy an application, you must also deploy all components that are referenced by the application.</span></span> <span data-ttu-id="6f7be-107">Der Vorgang des Installierens von erforderlichen Komponenten wird als *Bootstrapping*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="6f7be-107">The process of installing prerequisite components is known as *bootstrapping*.</span></span>  
  
 <span data-ttu-id="6f7be-108">Wenn die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>Komponente auf dem Entwicklungscomputer installiert ist, ein Microsoft Visual Basic Power Packs-Bootstrapperpaket hinzugefügt wird die [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Bootstrapperverzeichnis.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm></span><span class="sxs-lookup"><span data-stu-id="6f7be-108">When the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is installed on your development computer, a Microsoft Visual Basic Power Packs bootstrapper package is added to the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] bootstrapper directory.</span></span> <span data-ttu-id="6f7be-109">Dieses Paket ist dann verfügbar, wenn das Verfahren zum Hinzufügen von erforderlichen Komponenten für eine [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] oder Windows Installer-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="6f7be-109">This package is then available when you follow the procedures for adding prerequisites for either [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] or Windows Installer deployment.</span></span>  
  
 <span data-ttu-id="6f7be-110">Standardmäßig werden Bootstrappingkomponenten vom gleichen Speicherort wie das Installationspaket bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="6f7be-110">By default, bootstrapped components are deployed from the same location as the installation package.</span></span> <span data-ttu-id="6f7be-111">Alternativ können Sie die Komponenten über eine URL oder einen Dateifreigabe-Speicherort bereitstellen und Benutzern so den Download bei Bedarf ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="6f7be-111">Alternatively, you can choose to deploy the components from a URL or file share location from which users can download them as necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f7be-112">Zum Installieren von Bootstrapperkomponenten benötigt der Benutzer möglicherweise Administrator- oder ähnliche Benutzerberechtigungen auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="6f7be-112">To install bootstrapped components, the user might need administrative or similar user permissions on the computer.</span></span> <span data-ttu-id="6f7be-113">Für [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] Applications, bedeutet dies, dass der Benutzer Administratorrechte zur Installation der Anwendung, unabhängig von der Sicherheitsstufe, die von der Anwendung angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6f7be-113">For [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] applications, this means that the user will need administrative permissions to install the application, regardless of the security level specified by the application.</span></span> <span data-ttu-id="6f7be-114">Nach der Installation können die Benutzer die Anwendung ohne Administratorberechtigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="6f7be-114">After the application is installed, the user can run the application without administrative permissions.</span></span>  
  
 <span data-ttu-id="6f7be-115">Während der Installation werden Benutzer aufgefordert werden, installieren die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>Komponente, wenn es nicht auf dem Zielcomputer vorhanden ist.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm></span><span class="sxs-lookup"><span data-stu-id="6f7be-115">During installation, users will be prompted to install the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component if it is not present on the destination computer.</span></span>  
  
 <span data-ttu-id="6f7be-116">Als Alternative zum bootstrapping können Sie vorab Bereitstellen der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>Komponente mit einem elektronischen Softwareverteilungssystem wie Microsoft Systems Management Server.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm></span><span class="sxs-lookup"><span data-stu-id="6f7be-116">As an alternative to bootstrapping, you can pre-deploy the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component by using an electronic software distribution system like Microsoft Systems Management Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f7be-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f7be-117">See also</span></span>  
 <span data-ttu-id="6f7be-118">[Gewusst wie: Installieren von erforderlichen Komponenten mit einer ClickOnce-Anwendung](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5) </span><span class="sxs-lookup"><span data-stu-id="6f7be-118">[How to: Install Prerequisites with a ClickOnce Application](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5) </span></span>  
<span data-ttu-id="6f7be-119"> [PrintForm-Komponente](../../../visual-basic/developing-apps/printing/printform-component.md)</span><span class="sxs-lookup"><span data-stu-id="6f7be-119"> [PrintForm Component](../../../visual-basic/developing-apps/printing/printform-component.md)</span></span>
