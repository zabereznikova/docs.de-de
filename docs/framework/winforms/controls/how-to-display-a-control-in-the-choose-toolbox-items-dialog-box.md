---
title: "Gewusst wie: Anzeigen eines Steuerelements im Dialogfeld \"Toolboxelemente auswählen\""
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f7bbb13e8a2b877d0f503e091b5bb8b1e7e89d00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="3358f-102">Gewusst wie: Anzeigen eines Steuerelements im Dialogfeld "Toolboxelemente auswählen"</span><span class="sxs-lookup"><span data-stu-id="3358f-102">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>
<span data-ttu-id="3358f-103">Beim Entwickeln und Verteilen von Steuerelementen, sollten Sie diese Kontrollen, die in angezeigt werden die **Toolboxelemente** im Dialogfeld angezeigt wird, wenn Sie mit der rechten Maustaste die **Toolbox** , und wählen Sie  **Wählen Sie Elemente aus**.</span><span class="sxs-lookup"><span data-stu-id="3358f-103">As you develop and distribute controls, you may want those controls to appear in the **Choose Toolbox Items** dialog box, which is displayed when you right-click the **Toolbox** and select **Choose Items**.</span></span> <span data-ttu-id="3358f-104">Sie können das Steuerelement in diesem Dialogfeld angezeigt werden, mit der Registrierung-Prozedur "AssemblyFoldersEx" aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3358f-104">You can enable your control to appear in this dialog box by using the AssemblyFoldersEx registration procedure.</span></span>  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="3358f-105">Zum Anzeigen des Steuerelements im Dialogfeld "Toolboxelemente auswählen"</span><span class="sxs-lookup"><span data-stu-id="3358f-105">To display your control in the Choose Toolbox Items dialog box</span></span>  
  
-   <span data-ttu-id="3358f-106">Die Steuerelementassembly im globalen Assemblycache zu installieren.</span><span class="sxs-lookup"><span data-stu-id="3358f-106">Install your control assembly to the global assembly cache.</span></span> <span data-ttu-id="3358f-107">Weitere Informationen finden Sie unter [Vorgehensweise: Installieren einer Assembly im globalen Assemblycache](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)</span><span class="sxs-lookup"><span data-stu-id="3358f-107">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)</span></span>  
  
     <span data-ttu-id="3358f-108">- oder - </span><span class="sxs-lookup"><span data-stu-id="3358f-108">-or-</span></span>  
  
-   <span data-ttu-id="3358f-109">Registrieren Sie das Steuerelement und seine zugehörigen zur Entwurfszeit Assemblys mit der Registrierung-Prozedur "AssemblyFoldersEx" ein.</span><span class="sxs-lookup"><span data-stu-id="3358f-109">Register your control and its associated design-time assemblies by using the AssemblyFoldersEx registration procedure.</span></span> <span data-ttu-id="3358f-110">"AssemblyFoldersEx" ist ein Registrierungsspeicherort, an dem Drittanbieter Pfade für jede Version des Frameworks speichern, die sie unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3358f-110">AssemblyFoldersEx is a registry location where third-party vendors store paths for each version of the framework that they support.</span></span> <span data-ttu-id="3358f-111">An diesem Registrierungsspeicherort Verweisassemblys suchen kann während der Entwurfszeit-Lösung suchen.</span><span class="sxs-lookup"><span data-stu-id="3358f-111">Design-time resolution can look in this registry location to find reference assemblies.</span></span> <span data-ttu-id="3358f-112">Das Registrierungsskript kann die Steuerelemente angeben, in der Toolbox angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3358f-112">The registry script can specify the controls you want to appear in the Toolbox.</span></span> <span data-ttu-id="3358f-113">Weitere Informationen finden Sie unter [Bereitstellen eines benutzerdefinierten Steuerelements und zur Entwurfszeit Assemblys (Visual Studio 2013)](http://msdn.microsoft.com/en-us/96158eb0-b691-4ae1-9e7b-3c65a1b798cb).</span><span class="sxs-lookup"><span data-stu-id="3358f-113">For more information, see [Deploying a Custom Control and Design-time Assemblies (Visual Studio 2013)](http://msdn.microsoft.com/en-us/96158eb0-b691-4ae1-9e7b-3c65a1b798cb).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3358f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3358f-114">See Also</span></span>  
 [<span data-ttu-id="3358f-115">Dialogfeld „Toolboxelemente auswählen“ (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="3358f-115">Choose Toolbox Items Dialog Box (Visual Studio)</span></span>](http://msdn.microsoft.com/en-us/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [<span data-ttu-id="3358f-116">Bereitstellen eines benutzerdefinierten Steuerelements und zur Entwurfszeit Assemblys (Visual Studio 2013)</span><span class="sxs-lookup"><span data-stu-id="3358f-116">Deploying a Custom Control and Design-time Assemblies (Visual Studio 2013)</span></span>](http://msdn.microsoft.com/en-us/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)  
 [<span data-ttu-id="3358f-117">Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="3358f-117">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="3358f-118">Gewusst wie: Installieren einer Assembly in den globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="3358f-118">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 [<span data-ttu-id="3358f-119">Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten</span><span class="sxs-lookup"><span data-stu-id="3358f-119">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
