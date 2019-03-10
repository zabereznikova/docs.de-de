---
title: Auswirkungen beim Ändern der Darstellung von Basisformularen
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms [Windows Forms]
- inherited forms [Windows Forms], modifications to base form
- Windows Forms, base form appearance
- base forms
- inheritance [Windows Forms], forms
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
ms.openlocfilehash: a253fef2bc7220d13c0ca373a38a5bf2f5842415
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715554"
---
# <a name="effects-of-modifying-a-base-forms-appearance"></a><span data-ttu-id="85917-102">Auswirkungen beim Ändern der Darstellung von Basisformularen</span><span class="sxs-lookup"><span data-stu-id="85917-102">Effects of Modifying a Base Form's Appearance</span></span>
<span data-ttu-id="85917-103">Während der Anwendungsentwicklung müssen Sie möglicherweise häufig die Darstellung des Basisformulars ändern, dessen Merkmale an andere Formulare im Projekt (oder in anderen Projekten) vererbt werden.</span><span class="sxs-lookup"><span data-stu-id="85917-103">During application development, you may often need to change the appearance of the base form from which other forms in the project (or in other projects) are inheriting.</span></span>  
  
 <span data-ttu-id="85917-104">Zur Entwurfszeit werden Änderungen an der Darstellung des Basisformulars (z.B. das Festlegen von Eigenschaften oder die Addition und Subtraktion von Steuerelementen) in geerbten Formularen reflektiert, wenn das Projekt mit dem Basisformular erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="85917-104">At design time, changes to the base form's appearance (be it the setting of properties or the addition and subtraction of controls) are reflected on inherited forms when the project containing the base form is built.</span></span> <span data-ttu-id="85917-105">Es genügt nicht, wenn Sie die am Basisformular vorgenommenen Änderungen einfach speichern.</span><span class="sxs-lookup"><span data-stu-id="85917-105">It is not sufficient for you to simply save the changes to the base form.</span></span> <span data-ttu-id="85917-106">Wählen Sie aus dem Menü **Erstellen** die Option **Erstellen** aus, um ein Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="85917-106">To build a project, choose **Build** from the **Build** menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85917-107">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="85917-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="85917-108">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="85917-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="85917-109">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="85917-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
 <span data-ttu-id="85917-110">Änderungen, die zur Laufzeit am Basisformular vorgenommen werden, haben keine Auswirkungen auf geerbte Formulare, die bereits instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="85917-110">Modifications made to the base form at run time have no affect on inherited forms that are already instantiated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85917-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85917-111">See also</span></span>
- [<span data-ttu-id="85917-112">base</span><span class="sxs-lookup"><span data-stu-id="85917-112">base</span></span>](~/docs/csharp/language-reference/keywords/base.md)
- [<span data-ttu-id="85917-113">Vorgehensweise: Erben von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="85917-113">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
- [<span data-ttu-id="85917-114">Visuelle Vererbung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="85917-114">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
