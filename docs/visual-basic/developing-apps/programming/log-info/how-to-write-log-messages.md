---
title: 'Gewusst wie: Schreiben von Protokollmeldungen'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, writing log messages
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
ms.openlocfilehash: 28c5fe77e2711dfcac96e621a90fb9506eb74775
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410048"
---
# <a name="how-to-write-log-messages-visual-basic"></a>Gewusst wie: Schreiben von Protokollmeldungen (Visual Basic)

Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen über Ihre Anwendung zu protokollieren. Dieses Beispiel zeigt die Verwendung der `My.Application.Log.WriteEntry` -Methode zum Protokollieren von Ablaufprotokollinformationen.

Verwenden Sie für die Protokollierung von Ausnahmeinformationen die Methode `My.Application.Log.WriteException`; weitere Informationen finden Sie unter [Vorgehensweise: Protokollieren von Ausnahmen](how-to-log-exceptions.md).

## <a name="example"></a>Beispiel

In diesem Beispiel wird die Methode `My.Application.Log.WriteEntry` verwendet, um die Ablaufverfolgungsinformationen zu schreiben.

[!code-vb[VbVbalrMyApplicationLog#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#11)]

## <a name="net-framework-security"></a>.NET Framework-Sicherheit

Achten Sie darauf, dass die in das Protokoll geschriebenen Daten keine vertraulichen Informationen enthalten, wie etwa Benutzerkennwörter. Weitere Informationen finden Sie unter [Arbeiten mit Anwendungsprotokollen](working-with-application-logs.md).

## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [Arbeiten mit Anwendungsprotokollen](working-with-application-logs.md)
- [Gewusst wie: Protokollieren von Ausnahmen](how-to-log-exceptions.md)
- [Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt](walkthrough-determining-where-my-application-log-writes-information.md)
- [Exemplarische Vorgehensweise: Ändern des Orts, in den „My.Application.Log“ Informationen schreibt](walkthrough-changing-where-my-application-log-writes-information.md)
- [Exemplarische Vorgehensweise: Filtern der Ausgabe von „My.Application.Log“](walkthrough-filtering-my-application-log-output.md)
