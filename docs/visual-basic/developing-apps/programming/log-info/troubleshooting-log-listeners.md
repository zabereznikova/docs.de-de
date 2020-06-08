---
title: 'Problembehandlung: Protokollüberwachungen'
ms.date: 07/20/2015
helpviewer_keywords:
- event logs, troubleshooting
- troubleshooting Visual Basic, event logs
- troubleshooting event logs
ms.assetid: ac6eb760-3d5d-461e-aedd-40599ee22e49
ms.openlocfilehash: 8d2d8294d9e9bb42d72fe4f6c37bf846bd644907
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398317"
---
# <a name="troubleshooting-log-listeners-visual-basic"></a><span data-ttu-id="e5d97-102">Problembehandlung: Protokollüberwachungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5d97-102">Troubleshooting: Log Listeners (Visual Basic)</span></span>

<span data-ttu-id="e5d97-103">Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen über Ereignisse zu protokollieren, die in Ihrer Anwendung auftreten.</span><span class="sxs-lookup"><span data-stu-id="e5d97-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span>  
  
 <span data-ttu-id="e5d97-104">Weitere Informationen zur Bestimmung, welche Protokolllistener diese Nachrichten erhalten, finden Sie unter [Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt](walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="e5d97-104">To determine which log listeners receive those messages, see [Walkthrough: Determining Where My.Application.Log Writes Information](walkthrough-determining-where-my-application-log-writes-information.md).</span></span>  
  
 <span data-ttu-id="e5d97-105">Das `Log`-Objekt kann das Filtern von Protokollen verwenden, um die Menge an Informationen zu beschränken, die protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="e5d97-105">The `Log` object can use log filtering to limit the amount of information that it logs.</span></span> <span data-ttu-id="e5d97-106">Wenn die Filter falsch konfiguriert sind, können die Protokolle falsche Informationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="e5d97-106">If the filters are misconfigured, the logs might contain the wrong information.</span></span> <span data-ttu-id="e5d97-107">Weitere Informationen zur Filterung finden Sie unter [Exemplarische Vorgehensweise: Filterung der Ausgaben von „My.Application.Log“](walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="e5d97-107">For more information about filtering, see [Walkthrough: Filtering My.Application.Log Output](walkthrough-filtering-my-application-log-output.md).</span></span>  
  
 <span data-ttu-id="e5d97-108">Wenn ein Protokoll falsch konfiguriert ist, könnten Sie weitere Informationen über die aktuelle Konfiguration benötigen.</span><span class="sxs-lookup"><span data-stu-id="e5d97-108">However, if a log is configured incorrectly, you may need more information about its current configuration.</span></span> <span data-ttu-id="e5d97-109">Sie können diese Informationen über die erweiterte Eigenschaft `TraceSource` des Protokolls erhalten.</span><span class="sxs-lookup"><span data-stu-id="e5d97-109">You can get to this information through the log's advanced `TraceSource` property.</span></span>  
  
### <a name="to-determine-the-log-listeners-for-the-log-object-in-code"></a><span data-ttu-id="e5d97-110">Bestimmen der Protokolllistener für das Protokollobjekt im Code</span><span class="sxs-lookup"><span data-stu-id="e5d97-110">To determine the log listeners for the Log object in code</span></span>  
  
1. <span data-ttu-id="e5d97-111">Importieren Sie am Anfang der Codedatei den <xref:System.Diagnostics>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="e5d97-111">Import the <xref:System.Diagnostics> namespace at the beginning of the code file.</span></span> <span data-ttu-id="e5d97-112">Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="e5d97-112">For more information, see [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#13)]  
  
2. <span data-ttu-id="e5d97-113">Erstellen Sie eine Funktion, die eine Zeichenfolge mit Informationen für jeden Listener des Protokolls zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e5d97-113">Create a function that returns a string consisting of information for each of the log's listeners.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#14)]  
  
3. <span data-ttu-id="e5d97-114">Übergeben Sie die Auflistung der Ablaufverfolgungslistener des Protokolls an die `GetListeners`-Funktion und zeigen Sie den Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="e5d97-114">Pass the collection of the log's trace listeners to the `GetListeners` function, and display the return value.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#19)]  
  
     <span data-ttu-id="e5d97-115">Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="e5d97-115">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5d97-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e5d97-116">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [<span data-ttu-id="e5d97-117">Arbeiten mit Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="e5d97-117">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="e5d97-118">Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt</span><span class="sxs-lookup"><span data-stu-id="e5d97-118">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](walkthrough-determining-where-my-application-log-writes-information.md)
