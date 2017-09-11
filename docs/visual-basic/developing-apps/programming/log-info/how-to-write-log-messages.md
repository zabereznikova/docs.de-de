---
title: 'Gewusst wie: Schreiben von Protokollmeldungen (Visual Basic)'
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
- My.Application.Log object, writing log messags
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ffc45b93250ba9e909776352b702be2e8295435d
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-log-messages-visual-basic"></a><span data-ttu-id="1e06b-102">Gewusst wie: Schreiben von Protokollmeldungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e06b-102">How to: Write Log Messages (Visual Basic)</span></span>
<span data-ttu-id="1e06b-103">Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen über Ihre Anwendung zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="1e06b-103">You can use the `My.Application.Log` and `My.Log` objects to log information about your application.</span></span> <span data-ttu-id="1e06b-104">Dieses Beispiel zeigt die Verwendung der `My.Application.Log.WriteEntry` -Methode zum Protokollieren von Ablaufprotokollinformationen.</span><span class="sxs-lookup"><span data-stu-id="1e06b-104">This example shows how to use the `My.Application.Log.WriteEntry` method to log tracing information.</span></span>  
  
 <span data-ttu-id="1e06b-105">Verwenden Sie für die Protokollierung von Ausnahmeinformationen die Methode `My.Application.Log.WriteException`; weitere Informationen finden Sie unter [Vorgehensweise: Protokollieren von Ausnahmen](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="1e06b-105">For logging exception information, use the `My.Application.Log.WriteException` method; see [How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e06b-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1e06b-106">Example</span></span>  
 <span data-ttu-id="1e06b-107">In diesem Beispiel wird die Methode `My.Application.Log.WriteEntry` verwendet, um die Ablaufverfolgungsinformationen zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="1e06b-107">This example uses the `My.Application.Log.WriteEntry` method to write out the trace information.</span></span>  
  
 <span data-ttu-id="1e06b-108">[!code-vb[VbVbalrMyApplicationLog#11](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-write-log-messages_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="1e06b-108">[!code-vb[VbVbalrMyApplicationLog#11](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-write-log-messages_1.vb)]</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1e06b-109">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1e06b-109">.NET Framework Security</span></span>  
 <span data-ttu-id="1e06b-110">Achten Sie darauf, dass die in das Protokoll geschriebenen Daten keine vertraulichen Informationen enthalten, wie etwa Benutzerkennwörter.</span><span class="sxs-lookup"><span data-stu-id="1e06b-110">Make sure the data you write to the log does not include sensitive information such as user passwords.</span></span> <span data-ttu-id="1e06b-111">Weitere Informationen finden Sie unter [Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span><span class="sxs-lookup"><span data-stu-id="1e06b-111">For more information, see [Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e06b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e06b-112">See Also</span></span>  
 <span data-ttu-id="1e06b-113"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="1e06b-113"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="1e06b-114"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span><span class="sxs-lookup"><span data-stu-id="1e06b-114"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>   
 <span data-ttu-id="1e06b-115"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span><span class="sxs-lookup"><span data-stu-id="1e06b-115"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span></span>   
 <span data-ttu-id="1e06b-116">[Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span><span class="sxs-lookup"><span data-stu-id="1e06b-116">[Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span></span>  
 <span data-ttu-id="1e06b-117">[Vorgehensweise: Protokollieren von Ausnahmen](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md) </span><span class="sxs-lookup"><span data-stu-id="1e06b-117">[How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md) </span></span>  
 <span data-ttu-id="1e06b-118">[Walkthrough: Determining Where My.Application.Log Writes Information (Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt)](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md) </span><span class="sxs-lookup"><span data-stu-id="1e06b-118">[Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md) </span></span>  
 <span data-ttu-id="1e06b-119">[Exemplarische Vorgehensweise: Ändern des Orts, in den „My.Application.Log“ Informationen schreibt](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md) </span><span class="sxs-lookup"><span data-stu-id="1e06b-119">[Walkthrough: Changing Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md) </span></span>  
 [<span data-ttu-id="1e06b-120">Exemplarische Vorgehensweise: Filtern der Ausgabe von „My.Application.Log“</span><span class="sxs-lookup"><span data-stu-id="1e06b-120">Walkthrough: Filtering My.Application.Log Output</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)

