---
title: Ein anderes Ereignisprotokoll hat bereits eine Quelle mit diesem Namen registriert.
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8beea344d233794ddc36d7fc53db1c01be84399f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a>Ein anderes Ereignisprotokoll hat bereits eine Quelle mit diesem Namen registriert.
Es wurde versucht, einen Eintrag in ein Ereignisprotokoll schreiben, bei dem die angegebene Quelle für ein anderes Ereignisprotokoll registriert ist.  
  
 Sie müssen die <xref:System.Diagnostics.EventLog.Source%2A> -Eigenschaft Ihrer <xref:System.Diagnostics.EventLog> -Komponenteninstanz festlegen, bevor die Komponente einen Eintrag in ein Protokoll schreibt. In diesem Fall überprüft das System, ob die angegebene Quelle mit dem Ereignisprotokoll registriert ist, in das die Komponente schreibt. Bei Bedarf wird dann <xref:System.Diagnostics.EventLog.CreateEventSource%2A> aufgerufen.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Entfernen Sie die Zuordnung der Quelle zum ersten Protokoll mithilfe der <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> - oder <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> -Methode.  
  
2.  Registrieren Sie die Quelle für das neue Protokoll.  
  
## <a name="see-also"></a>Siehe auch  
 [My.Application.Log-Objekt](../../visual-basic/language-reference/objects/my-application-log-object.md)  
 [Vorgehensweise: entfernen eine Ereignisquelle](http://msdn.microsoft.com/en-us/bc66c900-4b8a-426a-b8e2-17031a20167e)  
 [Vorgehensweise: Hinzufügen von Ihrer Anwendung als Quelle für Einträge im Ereignisprotokoll](http://msdn.microsoft.com/en-us/948ff920-a739-4e66-a191-ee951512d42c)
