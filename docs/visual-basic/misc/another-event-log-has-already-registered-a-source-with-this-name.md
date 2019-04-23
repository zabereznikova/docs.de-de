---
title: Ein anderes Ereignisprotokoll hat bereits eine Quelle mit diesem Namen registriert.
ms.date: 07/20/2015
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
ms.openlocfilehash: d932869504b2d8a5f3a948b190e5528bfcfa664f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314671"
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a>Ein anderes Ereignisprotokoll hat bereits eine Quelle mit diesem Namen registriert.
Es wurde versucht, einen Eintrag in ein Ereignisprotokoll schreiben, bei dem die angegebene Quelle für ein anderes Ereignisprotokoll registriert ist.  
  
 Sie müssen die <xref:System.Diagnostics.EventLog.Source%2A> -Eigenschaft Ihrer <xref:System.Diagnostics.EventLog> -Komponenteninstanz festlegen, bevor die Komponente einen Eintrag in ein Protokoll schreibt. In diesem Fall überprüft das System, ob die angegebene Quelle mit dem Ereignisprotokoll registriert ist, in das die Komponente schreibt. Bei Bedarf wird dann <xref:System.Diagnostics.EventLog.CreateEventSource%2A> aufgerufen.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Entfernen Sie die Zuordnung der Quelle zum ersten Protokoll mithilfe der <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> - oder <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> -Methode.  
  
2. Registrieren Sie die Quelle für das neue Protokoll.  
  
## <a name="see-also"></a>Siehe auch

- [My.Application.Log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
