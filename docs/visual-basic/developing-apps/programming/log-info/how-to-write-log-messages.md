---
title: 'Gewusst wie: Schreiben von Protokollmeldungen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, writing log messags
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
ms.openlocfilehash: 8b0d50e70572d849f20f01914d2380a64e4495a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-write-log-messages-visual-basic"></a>Gewusst wie: Schreiben von Protokollmeldungen (Visual Basic)
Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen über Ihre Anwendung zu protokollieren. Dieses Beispiel zeigt die Verwendung der `My.Application.Log.WriteEntry` -Methode zum Protokollieren von Ablaufprotokollinformationen.  
  
 Verwenden Sie für die Protokollierung von Ausnahmeinformationen die Methode `My.Application.Log.WriteException`; weitere Informationen finden Sie unter [Vorgehensweise: Protokollieren von Ausnahmen](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die Methode `My.Application.Log.WriteEntry` verwendet, um die Ablaufverfolgungsinformationen zu schreiben.  
  
 [!code-vb[VbVbalrMyApplicationLog#11](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-write-log-messages_1.vb)]  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Achten Sie darauf, dass die in das Protokoll geschriebenen Daten keine vertraulichen Informationen enthalten, wie etwa Benutzerkennwörter. Weitere Informationen finden Sie unter [Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>  
 [Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [Gewusst wie: Protokollieren von Ausnahmen](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)  
 [Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)  
 [Exemplarische Vorgehensweise: Ändern des Orts, in den „My.Application.Log“ Informationen schreibt](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)  
 [Exemplarische Vorgehensweise: Filtern der Ausgabe von „My.Application.Log“](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)
