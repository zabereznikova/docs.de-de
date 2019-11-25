---
title: 'Problembehandlung: Protokolllistener'
ms.date: 07/20/2015
helpviewer_keywords:
- event logs, troubleshooting
- troubleshooting Visual Basic, event logs
- troubleshooting event logs
ms.assetid: ac6eb760-3d5d-461e-aedd-40599ee22e49
ms.openlocfilehash: dd139935dae7fe4d1334b861e6590df29bab7202
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346855"
---
# <a name="troubleshooting-log-listeners-visual-basic"></a>Problembehandlung: Protokolllistener (Visual Basic)

Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen über Ereignisse zu protokollieren, die in Ihrer Anwendung auftreten.  
  
 Weitere Informationen zu Protokolllistenern und wie diese Meldungen empfangen finden Sie unter [Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).  
  
 Das `Log`-Objekt kann das Filtern von Protokollen verwenden, um die Menge an Informationen zu beschränken, die protokolliert werden. Wenn die Filter falsch konfiguriert sind, können die Protokolle falsche Informationen enthalten. Weitere Informationen zur Filterung finden Sie unter [Exemplarische Vorgehensweise: Filterung der Ausgabe von „My.Application.Log“](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).  
  
 Wenn ein Protokoll falsch konfiguriert ist, könnten Sie weitere Informationen über die aktuelle Konfiguration benötigen. Sie können diese Informationen über die erweiterte Eigenschaft `TraceSource` des Protokolls erhalten.  
  
### <a name="to-determine-the-log-listeners-for-the-log-object-in-code"></a>Bestimmen der Protokolllistener für das Protokollobjekt im Code  
  
1. Importieren Sie am Anfang der Codedatei den <xref:System.Diagnostics>-Namespace. Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
     [!code-vb[VbVbalrMyApplicationLog#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#13)]  
  
2. Erstellen Sie eine Funktion, die eine Zeichenfolge mit Informationen für jeden Listener des Protokolls zurückgibt.  
  
     [!code-vb[VbVbalrMyApplicationLog#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#14)]  
  
3. Übergeben Sie die Auflistung der Ablaufverfolgungslistener des Protokolls an die `GetListeners`-Funktion und zeigen Sie den Rückgabewert.  
  
     [!code-vb[VbVbalrMyApplicationLog#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#19)]  
  
     Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
