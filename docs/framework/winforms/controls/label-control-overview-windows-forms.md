---
title: "Übersicht über das Label-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Label
helpviewer_keywords:
- images [Windows Forms], displaying in labels
- labels
- Label control [Windows Forms], about Label control
ms.assetid: dcad7f44-11b7-4c55-b0c0-d984ade43d7d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f55cfb6afa8ad533aac84b391a7cd6fef83d72d8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="label-control-overview-windows-forms"></a><span data-ttu-id="b1578-102">Übersicht über das Label-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b1578-102">Label Control Overview (Windows Forms)</span></span>
<span data-ttu-id="b1578-103">Windows Forms <xref:System.Windows.Forms.Label> Steuerelemente dienen zum Anzeigen von Text oder Bilder, die vom Benutzer bearbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="b1578-103">Windows Forms <xref:System.Windows.Forms.Label> controls are used to display text or images that cannot be edited by the user.</span></span> <span data-ttu-id="b1578-104">Sie werden verwendet, um Objekte in einem Formular zu identifizieren, ergeben eine Beschreibung, welche eines bestimmten Steuerelements wird Wenn geklickt haben, z. B., oder Informationen als Antwort auf ein Laufzeitereignis oder ein Prozess in der Anwendung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b1578-104">They are used to identify objects on a form — to provide a description of what a certain control will do if clicked, for example, or to display information in response to a run-time event or process in your application.</span></span> <span data-ttu-id="b1578-105">Bezeichnungen können Sie z. B. Textfelder, Listenfelder und Kombinationsfelder, usw. beschreibende Titel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b1578-105">For example, you can use labels to add descriptive captions to text boxes, list boxes, combo boxes, and so on.</span></span> <span data-ttu-id="b1578-106">Sie können auch Code schreiben, die den Text angezeigt, indem eine Bezeichnung als Antwort auf Ereignisse zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="b1578-106">You can also write code that changes the text displayed by a label in response to events at run time.</span></span> <span data-ttu-id="b1578-107">Wenn Ihre Anwendung ein paar Minuten verarbeitet eine Änderung dauert, können Sie z. B. eine Verarbeitungsstatus Nachricht in eine Bezeichnung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b1578-107">For example, if your application takes a few minutes to process a change, you can display a processing-status message in a label.</span></span>  
  
## <a name="working-with-the-label-control"></a><span data-ttu-id="b1578-108">Arbeiten mit dem Label-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b1578-108">Working with the Label Control</span></span>  
 <span data-ttu-id="b1578-109">Da die <xref:System.Windows.Forms.Label> Steuerelement den Fokus erhalten kann, können Sie auch zum Erstellen von Zugriffstasten für andere Steuerelemente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b1578-109">Because the <xref:System.Windows.Forms.Label> control cannot receive the focus, it can also be used to create access keys for other controls.</span></span> <span data-ttu-id="b1578-110">Eine Zugriffstaste ermöglicht einem Benutzer, die Steuerelemente durch Drücken der ALT-Taste und der Zugriffstaste auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="b1578-110">An access key allows a user to select the other control by pressing the ALT key with the access key.</span></span> <span data-ttu-id="b1578-111">Weitere Informationen finden Sie unter [Erstellen von Zugriffstasten für Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) und [Vorgehensweise: Erstellen von Zugriffstasten mit Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md).</span><span class="sxs-lookup"><span data-stu-id="b1578-111">For more information, see [Creating Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) and [How to: Create Access Keys with Windows Forms Label Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md).</span></span>  
  
 <span data-ttu-id="b1578-112">In der Bezeichnung angezeigte Beschriftung ist Bestandteil der <xref:System.Windows.Forms.Label.Text%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b1578-112">The caption displayed in the label is contained in the <xref:System.Windows.Forms.Label.Text%2A> property.</span></span> <span data-ttu-id="b1578-113">Die <xref:System.Windows.Forms.Label.TextAlign%2A> -Eigenschaft können Sie die Ausrichtung des Texts in die Bezeichnung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b1578-113">The <xref:System.Windows.Forms.Label.TextAlign%2A> property allows you to set the alignment of the text within the label.</span></span> <span data-ttu-id="b1578-114">Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen der Text, die durch ein Windows Forms-Steuerelement angezeigt](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).</span><span class="sxs-lookup"><span data-stu-id="b1578-114">For more information, see [How to: Set the Text Displayed by a Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1578-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1578-115">See Also</span></span>  
 <xref:System.Windows.Forms.Label>  
 [<span data-ttu-id="b1578-116">Gewusst wie: Anpassen der Größe des Label-Steuerelements in Windows Forms an seinen Inhalt</span><span class="sxs-lookup"><span data-stu-id="b1578-116">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)  
 [<span data-ttu-id="b1578-117">Gewusst wie: Erstellen von Zugriffstasten mit Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="b1578-117">How to: Create Access Keys with Windows Forms Label Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)
