---
title: "Der in \"EventLogSource\" angegebene Quellenname ist für ein anderes als in \"EventLogName\" angegebenes Protokoll registriert"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e0a100789486dda403f483489e73accbf219374c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a>Der in "EventLogSource" angegebene Quellenname ist für ein anderes als in "EventLogName" angegebenes Protokoll registriert
`EventLog` versucht, auf eine Quelle zu verweisen, die für ein anderes Protokoll registriert ist. Wenn Sie Einträge in ein Ereignisprotokoll schreiben, müssen Sie die <xref:System.Diagnostics.EventLog.Source%2A> -Eigenschaft angeben. Die <xref:System.Diagnostics.EventLog.Source%2A> -Eigenschaft registriert die Komponente beim Ereignisprotokoll als gültige Quelle für Einträge. Eine einzelne Quelle kann nur jeweils einem Ereignisprotokoll zugeordnet werden (und somit Einträge jeweils in nur ein Ereignisprotokoll schreiben).  
  
 Wenn Sie den Versuch unternehmen, einen Eintrag zu schreiben, ohne zuerst die Komponente als gültige Quelle zu registrieren, registriert das System standardmäßig die Quelle automatisch beim Ereignisprotokoll. Dazu wird der Wert der <xref:System.Diagnostics.EventLog.Source%2A> -Eigenschaft als Quellzeichenfolge verwendet.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass die Quelle beim richtigen Protokoll registriert ist. Verwenden Sie dazu die <xref:System.Diagnostics.EventLog.CreateEventSource%2A> -Methode oder eine ihrer Überladungen, um eine Zeichenfolge anzugeben, die die Komponente beim Ereignisprotokoll eindeutig identifiziert.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwalten von Ereignisprotokollen](http://msdn.microsoft.com/library/35f53238-bdd2-417b-acd8-2fd9f7397f18)  
 [-Ereignisprotokollverweise](http://msdn.microsoft.com/library/4af0661c-6c96-49f4-961d-b26ed9bc3e87)  
 [Vorgehensweise: Hinzufügen von Ihrer Anwendung als Quelle für Einträge im Ereignisprotokoll](http://msdn.microsoft.com/library/948ff920-a739-4e66-a191-ee951512d42c)  
 [Vorgehensweise: entfernen eine Ereignisquelle](http://msdn.microsoft.com/library/bc66c900-4b8a-426a-b8e2-17031a20167e)
