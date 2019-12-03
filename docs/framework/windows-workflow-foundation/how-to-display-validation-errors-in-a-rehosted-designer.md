---
title: 'Gewusst wie: Anzeigen von Validierungsfehlern in einem neu gehosteten Designer'
ms.date: 03/30/2017
ms.assetid: 5aa8fb53-8f75-433b-bc06-7c7d33583d5d
ms.openlocfilehash: bd0c2c10665de4bc3364938167101655a9bdd056
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716285"
---
# <a name="how-to-display-validation-errors-in-a-rehosted-designer"></a><span data-ttu-id="84f3a-102">Gewusst wie: Anzeigen von Validierungsfehlern in einem neu gehosteten Designer</span><span class="sxs-lookup"><span data-stu-id="84f3a-102">How to: Display Validation Errors in a Rehosted Designer</span></span>
<span data-ttu-id="84f3a-103">In diesem Thema wird beschrieben, wie Validierungs Fehler in einem neu gehosteten Windows-Workflow-Designer abgerufen und veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="84f3a-103">This topic describes how to retrieve and publish validation errors in a rehosted Windows Workflow Designer.</span></span> <span data-ttu-id="84f3a-104">Er stellt ein Verfahren zur Verfügung, mit dem bestätigt werden kann, dass ein Workflow in einem neu gehosteten Designer gültig ist.</span><span class="sxs-lookup"><span data-stu-id="84f3a-104">This provides us with a procedure to confirm that a workflow in a rehosted designer is valid.</span></span>  
  
 <span data-ttu-id="84f3a-105">Diese Aufgabe besteht aus zwei Teilen.</span><span class="sxs-lookup"><span data-stu-id="84f3a-105">This task has two parts.</span></span> <span data-ttu-id="84f3a-106">Zuerst muss ein <xref:System.Activities.Presentation.Validation.IValidationErrorService> für die Implementierung zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="84f3a-106">The first is to provide an implementation <xref:System.Activities.Presentation.Validation.IValidationErrorService>.</span></span>  <span data-ttu-id="84f3a-107">Es gibt eine wichtige Methode für die Implementierung auf dieser Schnittstelle, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>, die eine Liste von <xref:System.Activities.Presentation.Validation.ValidationErrorInfo>-Objekten übergibt, die Informationen zu den Fehlern im Debugprotokoll enthält.</span><span class="sxs-lookup"><span data-stu-id="84f3a-107">There is one critical method to implement on this interface, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> which will pass you a list of <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> objects containing information about the errors to the debug log.</span></span>  <span data-ttu-id="84f3a-108">Nachdem Sie die Schnittstelle implementiert haben, rufen Sie die Fehlerinformationen ab, indem Sie im Bearbeitungskontext eine Instanz dieser Implementierung veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="84f3a-108">After implementing the interface, you retrieve the error information by publishing an instance of that implementation to the editing context.</span></span>  
  
### <a name="implement-the-ivalidationerrorservice-interface"></a><span data-ttu-id="84f3a-109">Implementieren der IValidationErrorService-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84f3a-109">Implement the IValidationErrorService Interface</span></span>  
  
1. <span data-ttu-id="84f3a-110">Das Folgende ist ein Codebeispiel für eine einfache Implementierung, die die Validierungsfehler in das Debugprotokoll schreibt.</span><span class="sxs-lookup"><span data-stu-id="84f3a-110">Here is a code sample for a simple implementation that will write out the validation errors to the debug log.</span></span>  
  
    ```csharp  
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
                errors.ToList().ForEach(vei => Debug.WriteLine($"Error: {vei.Message}"));  
            }  
        }  
    }  
    ```  
  
### <a name="publishing-to-the-editing-context"></a><span data-ttu-id="84f3a-111">Veröffentlichen im Bearbeitungskontext</span><span class="sxs-lookup"><span data-stu-id="84f3a-111">Publishing to the Editing Context</span></span>  
  
1. <span data-ttu-id="84f3a-112">Mit diesem Code erfolgt die Veröffentlichung im Bearbeitungskontext.</span><span class="sxs-lookup"><span data-stu-id="84f3a-112">Here is the code that will publish this to the editing context.</span></span>  
  
    ```csharp  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```
