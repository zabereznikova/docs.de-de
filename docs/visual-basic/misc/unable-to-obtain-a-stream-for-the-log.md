---
title: Für das Protokoll kann kein Stream abgerufen werden
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
ms.openlocfilehash: 540ff3fbba72d33b2efaa58ad7a8019628f5e83f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922537"
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a><span data-ttu-id="f810a-102">Für das Protokoll kann kein Stream abgerufen werden</span><span class="sxs-lookup"><span data-stu-id="f810a-102">Unable to obtain a stream for the log</span></span>
<span data-ttu-id="f810a-103">Für das Protokoll kann kein Stream abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f810a-103">Unable to obtain a stream for the log.</span></span> <span data-ttu-id="f810a-104">Auf basierenden potenziellen Dateinamen \<Name > werden bereits verwendet.</span><span class="sxs-lookup"><span data-stu-id="f810a-104">Potential file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="f810a-105">Die <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> Klasse konnte keine neue Protokolldatei erstellt, da alle potenziellen Protokolldateinamen anhand \<Name > werden bereits verwendet.</span><span class="sxs-lookup"><span data-stu-id="f810a-105">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not create a new log file because all potential log file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="f810a-106">Eine zu große Anzahl von Protokolldateien kann auf ein Architekturproblem der Anwendung hinweisen.</span><span class="sxs-lookup"><span data-stu-id="f810a-106">Having too many log files may indicate an architectural problem with the application.</span></span> <span data-ttu-id="f810a-107">Weitere Informationen finden Sie in der Dokumentation zur <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> -Klasse.</span><span class="sxs-lookup"><span data-stu-id="f810a-107">See the documentation for the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class for more information.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f810a-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f810a-108">To correct this error</span></span>  
  
1. <span data-ttu-id="f810a-109">Legen Sie die <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> -Eigenschaft auf <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> oder <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> fest, um einen Datumsstempel in den Protokolldateinamen einzufügen.</span><span class="sxs-lookup"><span data-stu-id="f810a-109">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> property to <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> or <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> to include a date-stamp in the log file name.</span></span>  
  
2. <span data-ttu-id="f810a-110">Archivieren Sie die vorhandenen Protokolle, und entfernen Sie diese vom Computer, damit das <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> -Objekt neue Protokolle erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="f810a-110">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f810a-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f810a-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>
- [<span data-ttu-id="f810a-112">My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="f810a-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [<span data-ttu-id="f810a-113">My.Application.Info.DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="f810a-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
