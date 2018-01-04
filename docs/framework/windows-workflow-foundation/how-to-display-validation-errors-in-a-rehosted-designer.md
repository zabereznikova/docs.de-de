---
title: 'Gewusst wie: Anzeigen von Validierungsfehlern in einem neu gehosteten Designer'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5aa8fb53-8f75-433b-bc06-7c7d33583d5d
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f08d920b59d163b23aff63dfa7ced869048e73cd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-validation-errors-in-a-rehosted-designer"></a><span data-ttu-id="86ca6-102">Gewusst wie: Anzeigen von Validierungsfehlern in einem neu gehosteten Designer</span><span class="sxs-lookup"><span data-stu-id="86ca6-102">How to: Display Validation Errors in a Rehosted Designer</span></span>
<span data-ttu-id="86ca6-103">In diesem Thema wird beschrieben, wie Validierungsfehler in einem neu gehosteten [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] abgerufen und veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="86ca6-103">This topic describes how to retrieve and publish validation errors in a rehosted [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].</span></span> <span data-ttu-id="86ca6-104">Er stellt ein Verfahren zur Verfügung, mit dem bestätigt werden kann, dass ein Workflow in einem neu gehosteten Designer gültig ist.</span><span class="sxs-lookup"><span data-stu-id="86ca6-104">This provides us with a procedure to confirm that a workflow in a rehosted designer is valid.</span></span>  
  
 <span data-ttu-id="86ca6-105">Diese Aufgabe besteht aus zwei Teilen.</span><span class="sxs-lookup"><span data-stu-id="86ca6-105">This task has two parts.</span></span> <span data-ttu-id="86ca6-106">Zuerst muss ein <xref:System.Activities.Presentation.Validation.IValidationErrorService> für die Implementierung zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="86ca6-106">The first is to provide an implementation <xref:System.Activities.Presentation.Validation.IValidationErrorService>.</span></span>  <span data-ttu-id="86ca6-107">Es gibt eine wichtige Methode für die Implementierung auf dieser Schnittstelle, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>, die eine Liste von <xref:System.Activities.Presentation.Validation.ValidationErrorInfo>-Objekten übergibt, die Informationen zu den Fehlern im Debugprotokoll enthält.</span><span class="sxs-lookup"><span data-stu-id="86ca6-107">There is one critical method to implement on this interface, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> which will pass you a list of <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> objects containing information about the errors to the debug log.</span></span>  <span data-ttu-id="86ca6-108">Nachdem Sie die Schnittstelle implementiert haben, rufen Sie die Fehlerinformationen ab, indem Sie im Bearbeitungskontext eine Instanz dieser Implementierung veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="86ca6-108">After implementing the interface, you retrieve the error information by publishing an instance of that implementation to the editing context.</span></span>  
  
### <a name="implement-the-ivalidationerrorservice-interface"></a><span data-ttu-id="86ca6-109">Implementieren der IValidationErrorService-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="86ca6-109">Implement the IValidationErrorService Interface</span></span>  
  
1.  <span data-ttu-id="86ca6-110">Das Folgende ist ein Codebeispiel für eine einfache Implementierung, die die Validierungsfehler in das Debugprotokoll schreibt.</span><span class="sxs-lookup"><span data-stu-id="86ca6-110">Here is a code sample for a simple implementation that will write out the validation errors to the debug log.</span></span>  
  
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
  
### <a name="publishing-to-the-editing-context"></a><span data-ttu-id="86ca6-111">Veröffentlichen im Bearbeitungskontext</span><span class="sxs-lookup"><span data-stu-id="86ca6-111">Publishing to the Editing Context</span></span>  
  
1.  <span data-ttu-id="86ca6-112">Mit diesem Code erfolgt die Veröffentlichung im Bearbeitungskontext.</span><span class="sxs-lookup"><span data-stu-id="86ca6-112">Here is the code that will publish this to the editing context.</span></span>  
  
    ```  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```
