---
title: 'Vorgehensweise: Anzeigen eines Steuerelements im Dialogfeld „Toolboxelemente auswählen“'
ms.date: 03/30/2017
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
ms.openlocfilehash: d504ace9e5571246ae0e78e165a7ad2bc23fa481
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085297"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="604cf-102">Vorgehensweise: Anzeigen eines Steuerelements im Dialogfeld „Toolboxelemente auswählen“</span><span class="sxs-lookup"><span data-stu-id="604cf-102">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>
<span data-ttu-id="604cf-103">Beim Entwickeln und Verteilen von Steuerelementen, sollten Sie die Steuerelemente angezeigt werden die **Toolboxelemente** dieses Dialogfeld wird angezeigt, wenn Sie mit der rechten Maustaste die **Toolbox** , und wählen Sie  **Wählen Sie Elemente aus**.</span><span class="sxs-lookup"><span data-stu-id="604cf-103">As you develop and distribute controls, you may want those controls to appear in the **Choose Toolbox Items** dialog box, which is displayed when you right-click the **Toolbox** and select **Choose Items**.</span></span> <span data-ttu-id="604cf-104">Sie können das Steuerelement in diesem Dialogfeld angezeigt werden, mithilfe der Registrierungsvorgang "AssemblyFoldersEx" aktivieren.</span><span class="sxs-lookup"><span data-stu-id="604cf-104">You can enable your control to appear in this dialog box by using the AssemblyFoldersEx registration procedure.</span></span>  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="604cf-105">Das Steuerelement im Dialogfeld "Toolboxelemente auswählen" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="604cf-105">To display your control in the Choose Toolbox Items dialog box</span></span>  
  
-   <span data-ttu-id="604cf-106">Installieren Sie die Steuerelementassembly im globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="604cf-106">Install your control assembly to the global assembly cache.</span></span> <span data-ttu-id="604cf-107">Weitere Informationen finden Sie unter [Vorgehensweise: Installieren einer Assembly im globalen Assemblycache](../../app-domains/how-to-install-an-assembly-into-the-gac.md)</span><span class="sxs-lookup"><span data-stu-id="604cf-107">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../app-domains/how-to-install-an-assembly-into-the-gac.md)</span></span>  
  
     <span data-ttu-id="604cf-108">- oder - </span><span class="sxs-lookup"><span data-stu-id="604cf-108">-or-</span></span>  
  
-   <span data-ttu-id="604cf-109">Registrieren Sie Ihr Steuerelement und seine zugehörigen Entwurfszeitassemblys mithilfe der Registrierungsvorgang "AssemblyFoldersEx" ein.</span><span class="sxs-lookup"><span data-stu-id="604cf-109">Register your control and its associated design-time assemblies by using the AssemblyFoldersEx registration procedure.</span></span> <span data-ttu-id="604cf-110">"AssemblyFoldersEx" ist ein Registrierungsspeicherort, in dem Drittanbieter Pfade für jede Version des Frameworks speichern, die sie unterstützen.</span><span class="sxs-lookup"><span data-stu-id="604cf-110">AssemblyFoldersEx is a registry location where third-party vendors store paths for each version of the framework that they support.</span></span> <span data-ttu-id="604cf-111">Design-Time-Lösung kann an diesem Registrierungsspeicherort Verweisassemblys suchen Suchen.</span><span class="sxs-lookup"><span data-stu-id="604cf-111">Design-time resolution can look in this registry location to find reference assemblies.</span></span> <span data-ttu-id="604cf-112">Das Registrierungsskript kann die Steuerelemente angeben, die in der Toolbox angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="604cf-112">The registry script can specify the controls you want to appear in the Toolbox.</span></span> <span data-ttu-id="604cf-113">Weitere Informationen finden Sie unter [Bereitstellen eines benutzerdefinierten Steuerelements und Entwurfszeitassemblys](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="604cf-113">For more information, see [Deploying a Custom Control and Design-time Assemblies](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="604cf-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="604cf-114">See also</span></span>

- <span data-ttu-id="604cf-115">[Dialogfeld „Toolboxelemente auswählen“ (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="604cf-115">[Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span></span>
- <span data-ttu-id="604cf-116">[Bereitstellen eines benutzerdefinierten Steuerelements und während der Entwurfszeit-Assemblys](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="604cf-116">[Deploying a Custom Control and Design-time Assemblies](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100))</span></span>
- [<span data-ttu-id="604cf-117">Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="604cf-117">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="604cf-118">Vorgehensweise: Installieren einer Assembly im globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="604cf-118">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../app-domains/how-to-install-an-assembly-into-the-gac.md)
- [<span data-ttu-id="604cf-119">Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten</span><span class="sxs-lookup"><span data-stu-id="604cf-119">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
