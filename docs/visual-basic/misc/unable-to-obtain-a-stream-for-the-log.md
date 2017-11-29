---
title: "Für das Protokoll kann kein Stream abgerufen werden"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dd3051b2331502c9f4f3430bbf88731b307d1b1a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a>Für das Protokoll kann kein Stream abgerufen werden
Für das Protokoll kann kein Stream abgerufen werden. Auf basierenden potenziellen Dateinamen \<Name > werden bereits verwendet.  
  
 Die <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> Klasse konnte keine neue Protokolldatei erstellt, da alle potenziellen Protokolldateinamen anhand \<Name > werden bereits verwendet.  
  
 Eine zu große Anzahl von Protokolldateien kann auf ein Architekturproblem der Anwendung hinweisen. Weitere Informationen finden Sie in der Dokumentation zur <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> -Klasse.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Legen Sie die <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> -Eigenschaft auf <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> oder <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> fest, um einen Datumsstempel in den Protokolldateinamen einzufügen.  
  
2.  Archivieren Sie die vorhandenen Protokolle, und entfernen Sie diese vom Computer, damit das <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> -Objekt neue Protokolle erstellen kann.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>  
 [My.Application.Log-Objekt](../../visual-basic/language-reference/objects/my-application-log-object.md)  
 [My.Log-Objekt](../../visual-basic/language-reference/objects/my-log-object.md)
