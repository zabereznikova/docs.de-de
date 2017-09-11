---
title: "Problembehandlung: Protokollüberwachungen (Visual Basic)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- event logs, troubleshooting
- troubleshooting Visual Basic, event logs
- troubleshooting event logs
ms.assetid: ac6eb760-3d5d-461e-aedd-40599ee22e49
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0542aef4dc60821939e85760e6fadf0dfb528dec
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="troubleshooting-log-listeners-visual-basic"></a><span data-ttu-id="7c7e9-102">Problembehandlung: Protokollüberwachungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c7e9-102">Troubleshooting: Log Listeners (Visual Basic)</span></span>
<span data-ttu-id="7c7e9-103">Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen über Ereignisse zu protokollieren, die in Ihrer Anwendung auftreten.</span><span class="sxs-lookup"><span data-stu-id="7c7e9-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span>  
  
 <span data-ttu-id="7c7e9-104">Weitere Informationen zur Bestimmung, welche Protokolllistener diese Nachrichten erhalten, finden Sie unter [Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="7c7e9-104">To determine which log listeners receive those messages, see [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span></span>  
  
 <span data-ttu-id="7c7e9-105">Das `Log`-Objekt kann das Filtern von Protokollen verwenden, um die Menge an Informationen zu beschränken, die protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="7c7e9-105">The `Log` object can use log filtering to limit the amount of information that it logs.</span></span> <span data-ttu-id="7c7e9-106">Wenn die Filter falsch konfiguriert sind, können die Protokolle falsche Informationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="7c7e9-106">If the filters are misconfigured, the logs might contain the wrong information.</span></span> <span data-ttu-id="7c7e9-107">Weitere Informationen zur Filterung finden Sie unter [Exemplarische Vorgehensweise: Filterung der Ausgaben von „My.Application.Log“](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="7c7e9-107">For more information about filtering, see [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span></span>  
  
 <span data-ttu-id="7c7e9-108">Wenn ein Protokoll falsch konfiguriert ist, könnten Sie weitere Informationen über die aktuelle Konfiguration benötigen.</span><span class="sxs-lookup"><span data-stu-id="7c7e9-108">However, if a log is configured incorrectly, you may need more information about its current configuration.</span></span> <span data-ttu-id="7c7e9-109">Sie können diese Informationen über die erweiterte Eigenschaft `TraceSource` des Protokolls erhalten.</span><span class="sxs-lookup"><span data-stu-id="7c7e9-109">You can get to this information through the log's advanced `TraceSource` property.</span></span>  
  
### <a name="to-determine-the-log-listeners-for-the-log-object-in-code"></a><span data-ttu-id="7c7e9-110">Bestimmen der Protokolllistener für das Protokollobjekt im Code</span><span class="sxs-lookup"><span data-stu-id="7c7e9-110">To determine the log listeners for the Log object in code</span></span>  
  
1.  <span data-ttu-id="7c7e9-111">Importieren Sie am Anfang der Codedatei den <xref:System.Diagnostics>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="7c7e9-111">Import the <xref:System.Diagnostics> namespace at the beginning of the code file.</span></span> <span data-ttu-id="7c7e9-112">Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="7c7e9-112">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
     <span data-ttu-id="7c7e9-113">[!code-vb[VbVbalrMyApplicationLog#13](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7c7e9-113">[!code-vb[VbVbalrMyApplicationLog#13](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_1.vb)]</span></span>  
  
2.  <span data-ttu-id="7c7e9-114">Erstellen Sie eine Funktion, die eine Zeichenfolge mit Informationen für jeden Listener des Protokolls zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7c7e9-114">Create a function that returns a string consisting of information for each of the log's listeners.</span></span>  
  
     <span data-ttu-id="7c7e9-115">[!code-vb[VbVbalrMyApplicationLog#14](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="7c7e9-115">[!code-vb[VbVbalrMyApplicationLog#14](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_2.vb)]</span></span>  
  
3.  <span data-ttu-id="7c7e9-116">Übergeben Sie die Auflistung der Ablaufverfolgungslistener des Protokolls an die `GetListeners`-Funktion und zeigen Sie den Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="7c7e9-116">Pass the collection of the log's trace listeners to the `GetListeners` function, and display the return value.</span></span>  
  
     <span data-ttu-id="7c7e9-117">[!code-vb[VbVbalrMyApplicationLog#19](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="7c7e9-117">[!code-vb[VbVbalrMyApplicationLog#19](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_3.vb)]</span></span>  
  
     <span data-ttu-id="7c7e9-118">Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="7c7e9-118">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c7e9-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c7e9-119">See Also</span></span>  
 <span data-ttu-id="7c7e9-120"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7c7e9-120"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="7c7e9-121">[Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span><span class="sxs-lookup"><span data-stu-id="7c7e9-121">[Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span></span>  
 [<span data-ttu-id="7c7e9-122">Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt</span><span class="sxs-lookup"><span data-stu-id="7c7e9-122">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)

