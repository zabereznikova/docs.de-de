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
# <a name="unable-to-obtain-a-stream-for-the-log"></a><span data-ttu-id="54cce-102">Für das Protokoll kann kein Stream abgerufen werden</span><span class="sxs-lookup"><span data-stu-id="54cce-102">Unable to obtain a stream for the log</span></span>

<span data-ttu-id="54cce-103">Für das Protokoll kann kein Stream abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="54cce-103">Unable to obtain a stream for the log.</span></span> <span data-ttu-id="54cce-104">Mögliche Dateinamen, die auf basieren, \<name> werden bereits verwendet.</span><span class="sxs-lookup"><span data-stu-id="54cce-104">Potential file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="54cce-105">Die <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> Klasse konnte keine neue Protokolldatei erstellen, da alle möglichen Protokoll Dateinamen, die auf basieren, \<name> bereits verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="54cce-105">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not create a new log file because all potential log file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="54cce-106">Eine zu große Anzahl von Protokolldateien kann auf ein Architekturproblem der Anwendung hinweisen.</span><span class="sxs-lookup"><span data-stu-id="54cce-106">Having too many log files may indicate an architectural problem with the application.</span></span> <span data-ttu-id="54cce-107">Weitere Informationen finden Sie in der Dokumentation zur <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> -Klasse.</span><span class="sxs-lookup"><span data-stu-id="54cce-107">See the documentation for the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class for more information.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="54cce-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="54cce-108">To correct this error</span></span>  
  
1. <span data-ttu-id="54cce-109">Legen Sie die <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> -Eigenschaft auf <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> oder <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> fest, um einen Datumsstempel in den Protokolldateinamen einzufügen.</span><span class="sxs-lookup"><span data-stu-id="54cce-109">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> property to <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> or <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> to include a date-stamp in the log file name.</span></span>  
  
2. <span data-ttu-id="54cce-110">Archivieren Sie die vorhandenen Protokolle, und entfernen Sie diese vom Computer, damit das <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> -Objekt neue Protokolle erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="54cce-110">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54cce-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54cce-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>
- [<span data-ttu-id="54cce-112">My. Application. log</span><span class="sxs-lookup"><span data-stu-id="54cce-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [<span data-ttu-id="54cce-113">My. Application. info. directoriypath</span><span class="sxs-lookup"><span data-stu-id="54cce-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
