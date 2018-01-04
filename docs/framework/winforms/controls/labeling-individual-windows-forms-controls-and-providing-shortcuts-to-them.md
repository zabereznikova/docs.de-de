---
title: "Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], access keys
- shortcuts [Windows Forms], controls
- keyboard shortcuts [Windows Forms], controls
- Windows Forms controls, labels
ms.assetid: 6eaf868c-819f-4131-8f59-048e20c286f7
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5e64a2a858b9506ec08beff728e23da0f817f170
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them"></a><span data-ttu-id="3e79e-102">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="3e79e-102">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>
<span data-ttu-id="3e79e-103">In Windows Forms hinzugefügte Steuerelemente haben Eigenschaften und Methoden, die dazu verwendet werden, die Benutzerfreundlichkeit weiter zu spezialisieren.</span><span class="sxs-lookup"><span data-stu-id="3e79e-103">Controls added to Windows Forms have properties and methods that are used to further specialize the user experience.</span></span> <span data-ttu-id="3e79e-104">Ein Anpassen der Benutzeroberfläche an die Bedürfnisse der Benutzer ist äußerst wichtig für gut gestaltete Windows-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="3e79e-104">Customizing your user interface to suit the needs of the user is extremely important for well-designed Windows applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3e79e-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3e79e-105">In This Section</span></span>  
 [<span data-ttu-id="3e79e-106">Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Texts</span><span class="sxs-lookup"><span data-stu-id="3e79e-106">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 <span data-ttu-id="3e79e-107">Beschreibt das Zuweisen einer Textbezeichnung zu einem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="3e79e-107">Describes how to assign a text label to a control.</span></span>  
  
 [<span data-ttu-id="3e79e-108">Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Bildes</span><span class="sxs-lookup"><span data-stu-id="3e79e-108">How to: Set the Image Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md)  
 <span data-ttu-id="3e79e-109">Erläutert, wie ein Steuerelement konfiguriert wird, um Bilder anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3e79e-109">Explains how to configure a control to display images.</span></span>  
  
 [<span data-ttu-id="3e79e-110">Gewusst wie: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="3e79e-110">How to: Create Access Keys for Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)  
 <span data-ttu-id="3e79e-111">Enthält Informationen über das Erstellen von vordefinierten Tastenkombinationen.</span><span class="sxs-lookup"><span data-stu-id="3e79e-111">Gives information about creating predefined keyboard shortcuts.</span></span>  
  
 [<span data-ttu-id="3e79e-112">Informationen über Eingabehilfen für Steuerelemente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3e79e-112">Providing Accessibility Information for Controls on a Windows Form</span></span>](../../../../docs/framework/winforms/controls/providing-accessibility-information-for-controls-on-a-windows-form.md)  
 <span data-ttu-id="3e79e-113">Enthält Informationen über das Einrichten von Steuerelementen für die Arbeit mit Hilfen zur Barrierefreiheit.</span><span class="sxs-lookup"><span data-stu-id="3e79e-113">Gives information about enabling your controls to work with accessibility aids.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3e79e-114">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="3e79e-114">Related Sections</span></span>  
 [<span data-ttu-id="3e79e-115">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="3e79e-115">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 <span data-ttu-id="3e79e-116">Enthält Links zu weiteren grundlegenden Verwendungsmöglichkeiten für Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="3e79e-116">Links to other basic things you can do with controls.</span></span>  
  
 <span data-ttu-id="3e79e-117">Siehe auch [Vorgehensweise: Erstellen Zugriff Schlüssel für Windows Forms-Steuerelemente mithilfe des Designers](http://msdn.microsoft.com/library/ms233673\(v=vs.110\)), [wie: Festlegen der Text angezeigt, indem Sie ein Steuerelement in Windows Forms mithilfe den Designer](http://msdn.microsoft.com/library/ms233665\(v=vs.110\)), [wie: das Bild Angezeigt wird, indem Sie ein Windows Forms-Steuerelement mithilfe des Designers](http://msdn.microsoft.com/library/ms233656\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="3e79e-117">Also see [How to: Create Access Keys for Windows Forms Controls Using the Designer](http://msdn.microsoft.com/library/ms233673\(v=vs.110\)), [How to: Set the Text Displayed by a Windows Forms Control Using the Designer](http://msdn.microsoft.com/library/ms233665\(v=vs.110\)), [How to: Set the Image Displayed by a Windows Forms Control Using the Designer](http://msdn.microsoft.com/library/ms233656\(v=vs.110\)).</span></span>
