---
title: 'Vorgehensweise: Anzeigen von Validierungsfehlern in einem neu gehosteten Designer'
ms.date: 03/30/2017
ms.assetid: 5aa8fb53-8f75-433b-bc06-7c7d33583d5d
ms.openlocfilehash: a3d993f55bf130039905f1a6512a7ae104512432
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761481"
---
# <a name="how-to-display-validation-errors-in-a-rehosted-designer"></a><span data-ttu-id="1c7bd-102">Vorgehensweise: Anzeigen von Validierungsfehlern in einem neu gehosteten Designer</span><span class="sxs-lookup"><span data-stu-id="1c7bd-102">How to: Display Validation Errors in a Rehosted Designer</span></span>
<span data-ttu-id="1c7bd-103">In diesem Thema wird beschrieben, wie Validierungsfehler in einem neu gehosteten [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] abgerufen und veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="1c7bd-103">This topic describes how to retrieve and publish validation errors in a rehosted [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].</span></span> <span data-ttu-id="1c7bd-104">Er stellt ein Verfahren zur Verfügung, mit dem bestätigt werden kann, dass ein Workflow in einem neu gehosteten Designer gültig ist.</span><span class="sxs-lookup"><span data-stu-id="1c7bd-104">This provides us with a procedure to confirm that a workflow in a rehosted designer is valid.</span></span>  
  
 <span data-ttu-id="1c7bd-105">Diese Aufgabe besteht aus zwei Teilen.</span><span class="sxs-lookup"><span data-stu-id="1c7bd-105">This task has two parts.</span></span> <span data-ttu-id="1c7bd-106">Zuerst muss ein <xref:System.Activities.Presentation.Validation.IValidationErrorService> für die Implementierung zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1c7bd-106">The first is to provide an implementation <xref:System.Activities.Presentation.Validation.IValidationErrorService>.</span></span>  <span data-ttu-id="1c7bd-107">Es gibt eine wichtige Methode für die Implementierung auf dieser Schnittstelle, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>, die eine Liste von <xref:System.Activities.Presentation.Validation.ValidationErrorInfo>-Objekten übergibt, die Informationen zu den Fehlern im Debugprotokoll enthält.</span><span class="sxs-lookup"><span data-stu-id="1c7bd-107">There is one critical method to implement on this interface, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> which will pass you a list of <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> objects containing information about the errors to the debug log.</span></span>  <span data-ttu-id="1c7bd-108">Nachdem Sie die Schnittstelle implementiert haben, rufen Sie die Fehlerinformationen ab, indem Sie im Bearbeitungskontext eine Instanz dieser Implementierung veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="1c7bd-108">After implementing the interface, you retrieve the error information by publishing an instance of that implementation to the editing context.</span></span>  
  
### <a name="implement-the-ivalidationerrorservice-interface"></a><span data-ttu-id="1c7bd-109">Implementieren der IValidationErrorService-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c7bd-109">Implement the IValidationErrorService Interface</span></span>  
  
1. <span data-ttu-id="1c7bd-110">Das Folgende ist ein Codebeispiel für eine einfache Implementierung, die die Validierungsfehler in das Debugprotokoll schreibt.</span><span class="sxs-lookup"><span data-stu-id="1c7bd-110">Here is a code sample for a simple implementation that will write out the validation errors to the debug log.</span></span>  
  
    ```  
    using System.Activities.Presentation.Validation;  
    using System.Collections.Generic;  
    using System.Diagnostics;  
    using System.Linq;  
  
    namespace VariableFinderShell  
    {  
        class DebugValidationErrorService : IValidationErrorService  
        {  
            public void ShowValidationErrors(IList<ValidationErrorInfo> errors)  
            {  
                errors.ToList().ForEach(vei => Debug.WriteLine(string.Format("Error: {0} ", vei.Message)));  
            }  
        }  
    }  
    ```  
  
### <a name="publishing-to-the-editing-context"></a><span data-ttu-id="1c7bd-111">Veröffentlichen im Bearbeitungskontext</span><span class="sxs-lookup"><span data-stu-id="1c7bd-111">Publishing to the Editing Context</span></span>  
  
1. <span data-ttu-id="1c7bd-112">Mit diesem Code erfolgt die Veröffentlichung im Bearbeitungskontext.</span><span class="sxs-lookup"><span data-stu-id="1c7bd-112">Here is the code that will publish this to the editing context.</span></span>  
  
    ```  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```
