---
title: Erstellen von Projekten für .NET Framework 3.0 und 3.5 in Visual Studio 2010
ms.date: 03/30/2017
ms.assetid: 81858ab7-763c-4eac-83fe-d7205e5c4c98
ms.openlocfilehash: 1469ce2906c1101bae4098cbcabd4a10a64c1c7e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513818"
---
# <a name="writing-projects-targeting-the-net-framework-30-and-35-in-visual-studio-2010"></a><span data-ttu-id="a8119-102">Erstellen von Projekten für .NET Framework 3.0 und 3.5 in Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="a8119-102">Writing Projects Targeting the .NET Framework 3.0 and 3.5 in Visual Studio 2010</span></span>
<span data-ttu-id="a8119-103">Mit [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] können Sie Projekte für [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], Version 3.0 oder 3.5, erstellen.</span><span class="sxs-lookup"><span data-stu-id="a8119-103">You can use [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] to create projects that target the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] version 3.0 or 3.5.</span></span> <span data-ttu-id="a8119-104">In diesem Thema wird die dafür erforderliche Vorgehensweise beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a8119-104">This topic describes how to do this.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8119-105">Stellen Sie beim Hinzufügen von Aktivitäten sicher, dass die erforderliche Version von [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="a8119-105">When adding activities, make sure that the desired version of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] is set.</span></span> <span data-ttu-id="a8119-106">Wenn Sie die Zielversion des Workflows ändern, nachdem die Aktivitäten hinzugefügt wurden, kann der Workflow nicht überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="a8119-106">Changing the target version of the workflow after activities are added will cause the workflow to fail validation.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="a8119-107">Wenn Sie einen bestehenden Workflow mit .NET Framework 3.5-Aktivitäten in [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] öffnen, wird ein Fehler bei `this.SetValue()` verursacht.</span><span class="sxs-lookup"><span data-stu-id="a8119-107">Opening existing workflows in [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] that have .Net Framework 3.5 activities will cause an error at `this.SetValue()`.</span></span> <span data-ttu-id="a8119-108">Um Projekte zu öffnen, die mit früheren Versionen von .NET Framework erstellt wurden, öffnen Sie zunächst einen leeren Workflow im Designer, und fügen Sie eine .NET Framework 3.5-Aktivität hinzu.</span><span class="sxs-lookup"><span data-stu-id="a8119-108">In order to open projects created with previous versions of the .Net Framework, first open a blank workflow in the designer and add a .Net Framework 3.5 activity.</span></span>  
  
## <a name="to-create-a-net-framework--30-or-35-project-with-visual-studio-2010"></a><span data-ttu-id="a8119-109">So erstellen Sie ein .NET Framework 3.0- oder 3.5-Projekt mit Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="a8119-109">To create a .NET Framework  3.0 or 3.5 project with Visual Studio 2010</span></span>  
  
1.  <span data-ttu-id="a8119-110">Öffnen Sie [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8119-110">Open [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="a8119-111">Wählen Sie **Datei**, **neue**, **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="a8119-111">Select **File**, **New**, **Project**.</span></span>  
  
3.  <span data-ttu-id="a8119-112">Wählen Sie in der Dropdownliste oben im Dialogfeld die gewünschte Version von [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] aus.</span><span class="sxs-lookup"><span data-stu-id="a8119-112">In the drop-down list at the top of the dialog box, select the desired version of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="to-upgrade-the-targeted-version-of-the-net-framework"></a><span data-ttu-id="a8119-113">So aktualisieren Sie die Zielversion von .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a8119-113">To upgrade the targeted version of the .NET Framework</span></span>  
  
1.  <span data-ttu-id="a8119-114">Mit der rechten Maustaste des Projekts im Projektmappen-Explorer, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a8119-114">Right-click the project in Solution Explorer, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="a8119-115">In der **Zielframework** Dropdown-Liste, wählen Sie die gewünschte Version.</span><span class="sxs-lookup"><span data-stu-id="a8119-115">In the **Target Framework** drop-down list, select the desired version.</span></span>
