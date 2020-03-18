---
title: 'Gewusst wie: Schreiben von Protokollmeldungen'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, writing log messages
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
ms.openlocfilehash: 38570047db48e009aea2af376304430db1ec29f4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74352057"
---
# <a name="how-to-write-log-messages-visual-basic"></a><span data-ttu-id="3b968-102">Gewusst wie: Schreiben von Protokollmeldungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b968-102">How to: Write Log Messages (Visual Basic)</span></span>

<span data-ttu-id="3b968-103">Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen über Ihre Anwendung zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="3b968-103">You can use the `My.Application.Log` and `My.Log` objects to log information about your application.</span></span> <span data-ttu-id="3b968-104">Dieses Beispiel zeigt die Verwendung der `My.Application.Log.WriteEntry` -Methode zum Protokollieren von Ablaufprotokollinformationen.</span><span class="sxs-lookup"><span data-stu-id="3b968-104">This example shows how to use the `My.Application.Log.WriteEntry` method to log tracing information.</span></span>

<span data-ttu-id="3b968-105">Verwenden Sie für die Protokollierung von Ausnahmeinformationen die Methode `My.Application.Log.WriteException`; weitere Informationen finden Sie unter [Vorgehensweise: Protokollieren von Ausnahmen](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="3b968-105">For logging exception information, use the `My.Application.Log.WriteException` method; see [How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span></span>

## <a name="example"></a><span data-ttu-id="3b968-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3b968-106">Example</span></span>

<span data-ttu-id="3b968-107">In diesem Beispiel wird die Methode `My.Application.Log.WriteEntry` verwendet, um die Ablaufverfolgungsinformationen zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="3b968-107">This example uses the `My.Application.Log.WriteEntry` method to write out the trace information.</span></span>

[!code-vb[VbVbalrMyApplicationLog#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#11)]

## <a name="net-framework-security"></a><span data-ttu-id="3b968-108">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3b968-108">.NET Framework Security</span></span>

<span data-ttu-id="3b968-109">Achten Sie darauf, dass die in das Protokoll geschriebenen Daten keine vertraulichen Informationen enthalten, wie etwa Benutzerkennwörter.</span><span class="sxs-lookup"><span data-stu-id="3b968-109">Make sure the data you write to the log does not include sensitive information such as user passwords.</span></span> <span data-ttu-id="3b968-110">Weitere Informationen finden Sie unter [Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span><span class="sxs-lookup"><span data-stu-id="3b968-110">For more information, see [Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3b968-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3b968-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="3b968-112">Arbeiten mit Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="3b968-112">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [<span data-ttu-id="3b968-113">Gewusst wie: Protokollieren von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="3b968-113">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
- [<span data-ttu-id="3b968-114">Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt</span><span class="sxs-lookup"><span data-stu-id="3b968-114">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
- [<span data-ttu-id="3b968-115">Exemplarische Vorgehensweise: Ändern des Orts, in den „My.Application.Log“ Informationen schreibt</span><span class="sxs-lookup"><span data-stu-id="3b968-115">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
- [<span data-ttu-id="3b968-116">Exemplarische Vorgehensweise: Filtern der Ausgabe von „My.Application.Log“</span><span class="sxs-lookup"><span data-stu-id="3b968-116">Walkthrough: Filtering My.Application.Log Output</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)
