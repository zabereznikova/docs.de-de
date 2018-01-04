---
title: "Visuelle Vererbung in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inheritance
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 857eb737-3602-4d49-bd8b-f70d33ace345
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 177b3034e9afc71a8ecc899364cc4911ef42a1a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-visual-inheritance"></a><span data-ttu-id="06aa8-102">Visuelle Vererbung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="06aa8-102">Windows Forms Visual Inheritance</span></span>
<span data-ttu-id="06aa8-103">Gelegentlich können Sie entscheiden, dass in einem Projekt ein Formular aufgerufen wird, das einem in einem früheren Projekt erstellten Formular ähnelt.</span><span class="sxs-lookup"><span data-stu-id="06aa8-103">Occasionally, you may decide that a project calls for a form similar to one that you have created in a previous project.</span></span> <span data-ttu-id="06aa8-104">Möglicherweise möchten Sie aber auch ein Basisformular mit Einstellungen wie z.B. Wasserzeichen oder einem bestimmten Steuerelementlayout erstellen, das Sie anschließend erneut in einem Projekt verwenden, wobei jede Iteration Änderungen an der ursprünglichen Formularvorlage umfasst.</span><span class="sxs-lookup"><span data-stu-id="06aa8-104">Or, you may want to create a basic form with settings such as a watermark or certain control layout that you will then use again within a project, with each iteration containing modifications to the original form template.</span></span> <span data-ttu-id="06aa8-105">Bei der Vererbung von Formularen können Sie ein Basisformular erstellen und anschließend von diesem Formular erben und Änderungen vornehmen, während alle ursprünglichen Einstellungen, die Sie benötigen, beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="06aa8-105">Form inheritance enables you to create a base form and then inherit from it and make modifications while preserving whatever original settings you need.</span></span>  
  
 <span data-ttu-id="06aa8-106">Sie können Formulare mit abgeleiteten Klassen programmgesteuert oder mithilfe der Vererbungsauswahl von Visual erstellen.</span><span class="sxs-lookup"><span data-stu-id="06aa8-106">You can create derived-class forms programmatically or by using the Visual Inheritance picker.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="06aa8-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="06aa8-107">In This Section</span></span>  
 [<span data-ttu-id="06aa8-108">Vorgehensweise: Erben von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="06aa8-108">How to: Inherit Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 <span data-ttu-id="06aa8-109">Gibt Anweisungen zum Erstellen geerbter Formulare in Code.</span><span class="sxs-lookup"><span data-stu-id="06aa8-109">Gives directions for creating inherited forms in code.</span></span>  
  
 [<span data-ttu-id="06aa8-110">Vorgehensweise: Erben von Formularen mithilfe des Dialogfelds „Vererbungsauswahl“</span><span class="sxs-lookup"><span data-stu-id="06aa8-110">How to: Inherit Forms Using the Inheritance Picker Dialog Box</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md)  
 <span data-ttu-id="06aa8-111">Gibt Anweisungen zum Erstellen geerbter Formulare mithilfe der Vererbungsauswahl.</span><span class="sxs-lookup"><span data-stu-id="06aa8-111">Gives directions for creating inherited forms with the Inheritance Picker.</span></span>  
  
 [<span data-ttu-id="06aa8-112">Auswirkungen beim Ändern der Darstellung von Basisformularen</span><span class="sxs-lookup"><span data-stu-id="06aa8-112">Effects of Modifying a Base Form's Appearance</span></span>](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md)  
 <span data-ttu-id="06aa8-113">Gibt Anweisungen zum Ändern der Steuerelemente eines Basisformulars und der zugehörigen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="06aa8-113">Gives directions for changing a base form's controls and their properties.</span></span>  
  
 [<span data-ttu-id="06aa8-114">Exemplarische Vorgehensweise: Demonstrieren der visuellen Vererbung</span><span class="sxs-lookup"><span data-stu-id="06aa8-114">Walkthrough: Demonstrating Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-demonstrating-visual-inheritance.md)  
 <span data-ttu-id="06aa8-115">Beschreibt, wie ein einfaches Windows Form erstellt und in eine Klassenbibliothek kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="06aa8-115">Describes how to create a base Windows Form and compile it into a class library.</span></span> <span data-ttu-id="06aa8-116">Sie importieren diese Klassenbibliothek in ein anderes Projekt und erstellen ein neues Formular, das vom Basisformular erbt.</span><span class="sxs-lookup"><span data-stu-id="06aa8-116">You will import this class library into another project, and create a new form that inherits from the base form.</span></span>  
  
 [<span data-ttu-id="06aa8-117">Vorgehensweise: Verwenden von Modifizierern und GenerateMember-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="06aa8-117">How to: Use the Modifiers and GenerateMember Properties</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-the-modifiers-and-generatemember-properties.md)  
 <span data-ttu-id="06aa8-118">Gibt Anweisungen zur Verwendung der Eigenschaften `GenerateMember` und `Modifiers`, die relevant sind, wenn der Windows Forms-Designer eine Membervariable für eine Komponente generiert.</span><span class="sxs-lookup"><span data-stu-id="06aa8-118">Gives directions for using the `GenerateMember` and `Modifiers` properties, which are relevant when the Windows Forms Designer generates a member variable for a component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="06aa8-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="06aa8-119">Related Sections</span></span>  
 [<span data-ttu-id="06aa8-120">Grundlagen der Vererbung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06aa8-120">Inheritance basics (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 <span data-ttu-id="06aa8-121">Beschreibt, wie Visual Basic-Klassen definiert werden, die als Grundlage für andere Klassen dienen.</span><span class="sxs-lookup"><span data-stu-id="06aa8-121">Describes how to define Visual Basic classes that serve as the basis for other classes.</span></span>  
  
 [<span data-ttu-id="06aa8-122">class</span><span class="sxs-lookup"><span data-stu-id="06aa8-122">class</span></span>](~/docs/csharp/language-reference/keywords/class.md)  
 <span data-ttu-id="06aa8-123">Beschreibt den C#-Ansatz von Klassen, in denen die einfache Vererbung zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="06aa8-123">Describes the C# approach of classes, in which single inheritance is allowed.</span></span>  
  
 [<span data-ttu-id="06aa8-124">Problembehandlung für geerbte Ereignishandler in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="06aa8-124">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 <span data-ttu-id="06aa8-125">Führt häufige Probleme auf, die bei Ereignishandlern in geerbten Komponenten auftreten.</span><span class="sxs-lookup"><span data-stu-id="06aa8-125">Lists common issues that arise with event handlers in inherited components</span></span>
