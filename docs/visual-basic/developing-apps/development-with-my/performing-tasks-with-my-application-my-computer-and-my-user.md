---
title: Ausführen von Aufgaben mit My.Application, My.Computer und My.User (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: 56d79691a216f87c847474ce4340b454850b9b11
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969699"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a>Ausführen von Aufgaben mit My.Application, My.Computer und My.User (Visual Basic)
Die drei wichtigsten `My` Objekte, die Zugriff auf Informationen und häufig verwendeten Funktionen bereitstellen, sind `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), und `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>). Sie können diese Objekte verwenden, auf Informationen, die mit der aktuellen Anwendung, die Computer, dem auf die Anwendung installiert ist oder der aktuelle Benutzer der Anwendung verknüpft ist.  
  
## <a name="myapplication-mycomputer-and-myuser"></a>My.Application, My.Computer und My.User  
 Die folgenden Beispiele zeigen Informationen wie möglich mit abgerufen `My`.  
  
 [!code-vb[VbVbcnMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbcnMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#2)]  
  
 Zusätzlich zum Abrufen von Informationen, können die Elemente, die über diese drei Objekte verfügbar gemacht werden auch, Sie Methoden, die im Zusammenhang mit diesem Objekt auszuführen. Sie können z. B. eine Vielzahl von Methoden zum Bearbeiten von Dateien oder aktualisieren Sie die Registrierung über zugreifen `My.Computer`.  
  
 Datei-e/a ist bedeutend einfacher und schneller mit `My`, wozu eine Vielzahl von Methoden und Eigenschaften zum Bearbeiten von Dateien, Verzeichnisse und Laufwerke. Die <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> Objekt ermöglicht Ihnen das Lesen von großen strukturierten Dateien, die getrennt wurden oder Felder mit fester Breite. In diesem Beispiel öffnet der `TextFieldParser` `reader` und verwendet ihn zum Lesen aus `C:\TestFolder1\test1.txt`.  
  
 [!code-vb[VbVbalrTextFieldParser#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#23)]  
  
 `My.Application` können Sie die Kultur für Ihre Anwendung zu ändern. Im folgende Beispiel wird veranschaulicht, wie diese Methode aufgerufen werden kann.  
  
 [!code-vb[VbVbcnMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Merkmale von "My" auf Grundlage des Projekttyps](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
