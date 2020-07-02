---
title: Gruppen Steuerelemente mit GroupBox-Steuerelement
description: Erfahren Sie, wie Sie Steuerelemente mit dem Windows Forms GroupBox-Steuerelement gruppieren, sodass Sie eine visuelle Gruppierung verwandter Elemente erstellen können.
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: f84c495a18f4ae5e04367f024a1e2849f1ed59f9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618063"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="f66da-103">Vorgehensweise: Gruppieren von Steuerelementen mit dem GroupBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f66da-103">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="f66da-104">Windows Forms-Steuer <xref:System.Windows.Forms.GroupBox> Elemente werden verwendet, um andere Steuerelemente zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="f66da-104">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="f66da-105">Es gibt drei Gründe für das Gruppieren von Steuerelementen:</span><span class="sxs-lookup"><span data-stu-id="f66da-105">There are three reasons to group controls:</span></span>  
  
- <span data-ttu-id="f66da-106">Zum Erstellen einer visuellen Gruppierung verwandter Formularelemente für eine eindeutige Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="f66da-106">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
- <span data-ttu-id="f66da-107">Zum Erstellen einer programmatischen Gruppierung (z. b. von Options Feldern).</span><span class="sxs-lookup"><span data-stu-id="f66da-107">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
- <span data-ttu-id="f66da-108">Zum Verschieben der Steuerelemente als Einheit zur Entwurfszeit.</span><span class="sxs-lookup"><span data-stu-id="f66da-108">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="f66da-109">So erstellen Sie eine Gruppe von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="f66da-109">To create a group of controls</span></span>  
  
1. <span data-ttu-id="f66da-110">Zeichnen Sie ein- <xref:System.Windows.Forms.GroupBox> Steuerelement in einem Formular.</span><span class="sxs-lookup"><span data-stu-id="f66da-110">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2. <span data-ttu-id="f66da-111">Fügen Sie dem Gruppenfeld weitere Steuerelemente hinzu, und zeichnen Sie die einzelnen Elemente innerhalb des Gruppen Felds.</span><span class="sxs-lookup"><span data-stu-id="f66da-111">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="f66da-112">Wenn Sie über vorhandene Steuerelemente verfügen, die Sie in ein Gruppenfeld einschließen möchten, können Sie alle Steuerelemente auswählen, Sie in die Zwischenablage Ausschneiden, das Steuerelement auswählen <xref:System.Windows.Forms.GroupBox> und dann in das Gruppenfeld einfügen.</span><span class="sxs-lookup"><span data-stu-id="f66da-112">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="f66da-113">Sie können Sie auch in das Feld Gruppe ziehen.</span><span class="sxs-lookup"><span data-stu-id="f66da-113">You can also drag them into the group box.</span></span>  
  
3. <span data-ttu-id="f66da-114">Legen Sie die- <xref:System.Windows.Forms.GroupBox.Text%2A> Eigenschaft des Gruppen Felds auf eine entsprechende Beschriftung fest.</span><span class="sxs-lookup"><span data-stu-id="f66da-114">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f66da-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f66da-115">See also</span></span>

- <xref:System.Windows.Forms.GroupBox>
- [<span data-ttu-id="f66da-116">GroupBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f66da-116">GroupBox Control</span></span>](groupbox-control-windows-forms.md)
