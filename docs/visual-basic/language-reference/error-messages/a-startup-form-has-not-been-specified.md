---
title: Ein Startformular wurde nicht angegeben. | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrAppModel_NoStartupForm
dev_langs:
- VB
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 37484a00a631577e80853822fff92b069dbad7f2
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="a-startup-form-has-not-been-specified"></a><span data-ttu-id="b7dd4-102">Es wurde kein Startformular angegeben.</span><span class="sxs-lookup"><span data-stu-id="b7dd4-102">A startup form has not been specified</span></span>
<span data-ttu-id="b7dd4-103">Die Anwendung verwendet die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>-Klasse jedoch kein Startformular.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase></span><span class="sxs-lookup"><span data-stu-id="b7dd4-103">The application uses the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class but does not specify the startup form.</span></span>  
  
 <span data-ttu-id="b7dd4-104">Dies kann auftreten, wenn die **Anwendungsframework aktivieren** im Projekt-Designer das Kontrollkästchen aktiviert ist, aber die **Startformular** nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="b7dd4-104">This can occur if the **Enable application framework** check box is selected in the project designer but the **Startup form** is not specified.</span></span> <span data-ttu-id="b7dd4-105">Weitere Informationen finden Sie unter [Anwendungsseite, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="b7dd4-105">For more information, see [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b7dd4-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="b7dd4-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="b7dd4-107">Geben Sie ein separates Startobjekt für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b7dd4-107">Specify a startup object for the application.</span></span>  
  
     <span data-ttu-id="b7dd4-108">Weitere Informationen finden Sie unter [Anwendungsseite, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="b7dd4-108">For more information, see [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
2.  <span data-ttu-id="b7dd4-109">Überschreiben der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>-Methode zum Festlegen der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>-Eigenschaft auf das Startformular.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> </xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A></span><span class="sxs-lookup"><span data-stu-id="b7dd4-109">Override the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> method to set the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> property to the startup form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7dd4-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7dd4-110">See Also</span></span>  
 <span data-ttu-id="b7dd4-111"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase></span><span class="sxs-lookup"><span data-stu-id="b7dd4-111"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase></span></span>   
 <span data-ttu-id="b7dd4-112"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A></span><span class="sxs-lookup"><span data-stu-id="b7dd4-112"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A></span></span>   
 <span data-ttu-id="b7dd4-113"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A></span><span class="sxs-lookup"><span data-stu-id="b7dd4-113"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A></span></span>   
<span data-ttu-id="b7dd4-114"> [Übersicht über das Visual Basic-Anwendungsmodell](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)</span><span class="sxs-lookup"><span data-stu-id="b7dd4-114"> [Overview of the Visual Basic Application Model](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)</span></span>
