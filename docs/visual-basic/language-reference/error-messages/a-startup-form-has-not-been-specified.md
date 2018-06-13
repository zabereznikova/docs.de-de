---
title: Es wurde kein Startformular angegeben.
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: 699d20e6afb2335336b3652be5907f0dd72299fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586785"
---
# <a name="a-startup-form-has-not-been-specified"></a><span data-ttu-id="fc083-102">Es wurde kein Startformular angegeben.</span><span class="sxs-lookup"><span data-stu-id="fc083-102">A startup form has not been specified</span></span>
<span data-ttu-id="fc083-103">Die Anwendung verwendet die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> -Klasse jedoch nicht die Startformular angegeben.</span><span class="sxs-lookup"><span data-stu-id="fc083-103">The application uses the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class but does not specify the startup form.</span></span>  
  
 <span data-ttu-id="fc083-104">Dies kann auftreten, wenn die **Anwendungsframework aktivieren** Kontrollkästchen im Projekt-Designer jedoch **Startformular** nicht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fc083-104">This can occur if the **Enable application framework** check box is selected in the project designer but the **Startup form** is not specified.</span></span> <span data-ttu-id="fc083-105">Weitere Informationen finden Sie unter [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="fc083-105">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fc083-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="fc083-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="fc083-107">Geben Sie für die Anwendung Startobjekt.</span><span class="sxs-lookup"><span data-stu-id="fc083-107">Specify a startup object for the application.</span></span>  
  
     <span data-ttu-id="fc083-108">Weitere Informationen finden Sie unter [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="fc083-108">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
2.  <span data-ttu-id="fc083-109">Überschreiben der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> -Methode zum Festlegen der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> Eigenschaft, um die Startformular.</span><span class="sxs-lookup"><span data-stu-id="fc083-109">Override the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> method to set the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> property to the startup form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc083-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc083-110">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>  
 [<span data-ttu-id="fc083-111">Übersicht über das Visual Basic-Anwendungsmodell</span><span class="sxs-lookup"><span data-stu-id="fc083-111">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
