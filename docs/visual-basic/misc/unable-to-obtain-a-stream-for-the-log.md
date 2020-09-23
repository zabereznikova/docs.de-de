---
title: Für das Protokoll kann kein Stream abgerufen werden
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
ms.openlocfilehash: 887356fac3abe5c9d28751f7c4d3b1908ed35acb
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078384"
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a>Für das Protokoll kann kein Stream abgerufen werden

Für das Protokoll kann kein Stream abgerufen werden. Mögliche Dateinamen, die auf basieren, \<name> werden bereits verwendet.  
  
 Die <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> Klasse konnte keine neue Protokolldatei erstellen, da alle möglichen Protokoll Dateinamen, die auf basieren, \<name> bereits verwendet werden.  
  
 Eine zu große Anzahl von Protokolldateien kann auf ein Architekturproblem der Anwendung hinweisen. Weitere Informationen finden Sie in der Dokumentation zur <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> -Klasse.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Legen Sie die <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> -Eigenschaft auf <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> oder <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> fest, um einen Datumsstempel in den Protokolldateinamen einzufügen.  
  
2. Archivieren Sie die vorhandenen Protokolle, und entfernen Sie diese vom Computer, damit das <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> -Objekt neue Protokolle erstellen kann.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>
- [My. Application. log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [My. Application. info. directoriypath](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
