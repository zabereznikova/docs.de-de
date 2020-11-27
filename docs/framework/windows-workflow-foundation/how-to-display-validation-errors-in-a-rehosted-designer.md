---
title: 'Vorgehensweise: Anzeigen von Validierungsfehlern in einem neu gehosteten Designer'
ms.date: 03/30/2017
ms.assetid: 5aa8fb53-8f75-433b-bc06-7c7d33583d5d
ms.openlocfilehash: ccdb8941f46683dd1fd12387c0c5db2abe1d8dec
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280038"
---
# <a name="how-to-display-validation-errors-in-a-rehosted-designer"></a>Vorgehensweise: Anzeigen von Validierungsfehlern in einem neu gehosteten Designer

In diesem Thema wird beschrieben, wie Validierungs Fehler in einem neu gehosteten Windows-Workflow-Designer abgerufen und veröffentlicht werden. Er stellt ein Verfahren zur Verfügung, mit dem bestätigt werden kann, dass ein Workflow in einem neu gehosteten Designer gültig ist.  
  
 Diese Aufgabe besteht aus zwei Teilen. Zuerst muss ein <xref:System.Activities.Presentation.Validation.IValidationErrorService> für die Implementierung zur Verfügung gestellt werden.  Es gibt eine wichtige Methode für die Implementierung auf dieser Schnittstelle, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>, die eine Liste von <xref:System.Activities.Presentation.Validation.ValidationErrorInfo>-Objekten übergibt, die Informationen zu den Fehlern im Debugprotokoll enthält.  Nachdem Sie die Schnittstelle implementiert haben, rufen Sie die Fehlerinformationen ab, indem Sie im Bearbeitungskontext eine Instanz dieser Implementierung veröffentlichen.  
  
### <a name="implement-the-ivalidationerrorservice-interface"></a>Implementieren der IValidationErrorService-Schnittstelle  
  
1. Das Folgende ist ein Codebeispiel für eine einfache Implementierung, die die Validierungsfehler in das Debugprotokoll schreibt.  
  
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
  
### <a name="publishing-to-the-editing-context"></a>Veröffentlichen im Bearbeitungskontext  
  
1. Mit diesem Code erfolgt die Veröffentlichung im Bearbeitungskontext.  
  
    ```csharp  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```
