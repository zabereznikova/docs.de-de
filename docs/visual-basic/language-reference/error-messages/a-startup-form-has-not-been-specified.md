---
title: Es wurde kein Startformular angegeben.
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: 301f249e6222c929d2c513964ecbb21df5fbc47f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976193"
---
# <a name="a-startup-form-has-not-been-specified"></a><span data-ttu-id="48662-102">Es wurde kein Startformular angegeben.</span><span class="sxs-lookup"><span data-stu-id="48662-102">A startup form has not been specified</span></span>

<span data-ttu-id="48662-103">Die Anwendung verwendet die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>-Klasse, aber nicht das Start Formular.</span><span class="sxs-lookup"><span data-stu-id="48662-103">The application uses the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class but does not specify the startup form.</span></span>  
  
 <span data-ttu-id="48662-104">Dies kann vorkommen, wenn das Kontrollkästchen **Anwendungs Framework aktivieren** im Projekt-Designer aktiviert ist, aber das **Start Formular** nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="48662-104">This can occur if the **Enable application framework** check box is selected in the project designer but the **Startup form** is not specified.</span></span> <span data-ttu-id="48662-105">Weitere Informationen finden Sie unter [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="48662-105">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="48662-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="48662-106">To correct this error</span></span>  
  
1. <span data-ttu-id="48662-107">Geben Sie ein Start Objekt für die Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="48662-107">Specify a startup object for the application.</span></span>  
  
     <span data-ttu-id="48662-108">Weitere Informationen finden Sie unter [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="48662-108">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
2. <span data-ttu-id="48662-109">Überschreiben Sie die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>-Methode, um die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>-Eigenschaft auf das Start Formular festzulegen.</span><span class="sxs-lookup"><span data-stu-id="48662-109">Override the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> method to set the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> property to the startup form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48662-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48662-110">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>
- [<span data-ttu-id="48662-111">Übersicht über das Visual Basic-Anwendungsmodell</span><span class="sxs-lookup"><span data-stu-id="48662-111">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
