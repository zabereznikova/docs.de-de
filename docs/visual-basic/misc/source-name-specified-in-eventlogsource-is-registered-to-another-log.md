---
title: Der in "EventLogSource" angegebene Quellenname ist für ein anderes als in "EventLogName" angegebenes Protokoll registriert
ms.date: 07/20/2015
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
ms.openlocfilehash: 03fcc41b0fbb84233aa037d7af17d168050a98b6
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2018
ms.locfileid: "44708931"
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a>Der in "EventLogSource" angegebene Quellenname ist für ein anderes als in "EventLogName" angegebenes Protokoll registriert
`EventLog` versucht, auf eine Quelle zu verweisen, die für ein anderes Protokoll registriert ist. Wenn Sie Einträge in ein Ereignisprotokoll schreiben, müssen Sie die <xref:System.Diagnostics.EventLog.Source%2A> -Eigenschaft angeben. Die <xref:System.Diagnostics.EventLog.Source%2A> -Eigenschaft registriert die Komponente beim Ereignisprotokoll als gültige Quelle für Einträge. Eine einzelne Quelle kann nur jeweils einem Ereignisprotokoll zugeordnet werden (und somit Einträge jeweils in nur ein Ereignisprotokoll schreiben).  
  
 Wenn Sie den Versuch unternehmen, einen Eintrag zu schreiben, ohne zuerst die Komponente als gültige Quelle zu registrieren, registriert das System standardmäßig die Quelle automatisch beim Ereignisprotokoll. Dazu wird der Wert der <xref:System.Diagnostics.EventLog.Source%2A> -Eigenschaft als Quellzeichenfolge verwendet.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass die Quelle beim richtigen Protokoll registriert ist. Verwenden Sie dazu die <xref:System.Diagnostics.EventLog.CreateEventSource%2A> -Methode oder eine ihrer Überladungen, um eine Zeichenfolge anzugeben, die die Komponente beim Ereignisprotokoll eindeutig identifiziert.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwalten von Ereignisprotokollen](https://msdn.microsoft.com/library/35f53238-bdd2-417b-acd8-2fd9f7397f18)  
 [Ereignisprotokollverweise](https://msdn.microsoft.com/library/4af0661c-6c96-49f4-961d-b26ed9bc3e87)  
 [Vorgehensweise: Hinzufügen Ihrer Anwendung als Quelle für Einträge im Ereignisprotokoll](https://msdn.microsoft.com/library/948ff920-a739-4e66-a191-ee951512d42c)  
 [Vorgehensweise: entfernen eine Ereignisquelle](https://msdn.microsoft.com/library/bc66c900-4b8a-426a-b8e2-17031a20167e)
