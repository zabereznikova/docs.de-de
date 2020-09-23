---
title: Der in "EventLogSource" angegebene Quellenname ist für ein anderes als in "EventLogName" angegebenes Protokoll registriert
ms.date: 07/20/2015
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
ms.openlocfilehash: 1b577e3b0613001b6241dcfdc59c8c84029197d2
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058929"
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a>Der in "EventLogSource" angegebene Quellenname ist für ein anderes als in "EventLogName" angegebenes Protokoll registriert

`EventLog` versucht, auf eine Quelle zu verweisen, die für ein anderes Protokoll registriert ist. Wenn Sie Einträge in ein Ereignisprotokoll schreiben, müssen Sie die <xref:System.Diagnostics.EventLog.Source%2A> -Eigenschaft angeben. Die <xref:System.Diagnostics.EventLog.Source%2A> -Eigenschaft registriert die Komponente beim Ereignisprotokoll als gültige Quelle für Einträge. Eine einzelne Quelle kann nur jeweils einem Ereignisprotokoll zugeordnet werden (und somit Einträge jeweils in nur ein Ereignisprotokoll schreiben).  
  
 Wenn Sie den Versuch unternehmen, einen Eintrag zu schreiben, ohne zuerst die Komponente als gültige Quelle zu registrieren, registriert das System standardmäßig die Quelle automatisch beim Ereignisprotokoll. Dazu wird der Wert der <xref:System.Diagnostics.EventLog.Source%2A> -Eigenschaft als Quellzeichenfolge verwendet.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Stellen Sie sicher, dass die Quelle beim richtigen Protokoll registriert ist. Verwenden Sie dazu die <xref:System.Diagnostics.EventLog.CreateEventSource%2A> -Methode oder eine ihrer Überladungen, um eine Zeichenfolge anzugeben, die die Komponente beim Ereignisprotokoll eindeutig identifiziert.  
  
## <a name="see-also"></a>Siehe auch

- [Verwalten von Ereignisprotokollen](/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))
- [Ereignisprotokollverweise](/previous-versions/visualstudio/visual-studio-2008/k43k9z2a(v=vs.90))
- [Gewusst wie: Hinzufügen der Anwendung als Quelle von Ereignisprotokoll Einträgen](/previous-versions/visualstudio/visual-studio-2008/xz73e171(v=vs.90))
- [Vorgehensweise: Entfernen einer Ereignis Quelle](/previous-versions/visualstudio/visual-studio-2008/k57466fc(v=vs.90))
