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
ms.openlocfilehash: bc2b0521598c00cdb398d936d61d65874a9cf274
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a>Ausführen von Aufgaben mit My.Application, My.Computer und My.User (Visual Basic)
Die drei wichtigsten `My` sind Objekte, die Zugriff auf Informationen und häufig verwendete Funktionen bereitstellen `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), und `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>). Sie können diese Objekte verwenden, auf Informationen, die mit der aktuellen Anwendung, die Computer, dem auf die Anwendung installiert ist oder der aktuelle Benutzer der Anwendung verknüpft ist.  
  
## <a name="myapplication-mycomputer-and-myuser"></a>My.Application, My.Computer und My.User  
 Die folgenden Beispiele zeigen Informationen wie möglich mit abgerufen `My`.  
  
 [!code-vb[VbVbcnMy#1](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_1.vb)]  
  
 [!code-vb[VbVbcnMy#2](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_2.vb)]  
  
 Zusätzlich zum Abrufen von Informationen ermöglichen die Elemente, die durch diese drei Objekte verfügbar gemacht werden darüber hinaus Methoden, die im Zusammenhang mit diesem Objekt auszuführen. Sie können z. B. eine Vielzahl von Methoden zum Bearbeiten von Dateien oder aktualisieren Sie die Registrierung über zugreifen `My.Computer`.  
  
 Datei-e/a ist deutlich einfacher und schneller mit `My`, darunter eine Vielzahl von Methoden und Eigenschaften zum Bearbeiten von Dateien, Verzeichnisse und Laufwerke. Die <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> Objekts können Sie große strukturierte Dateien, die getrennt wurden oder Felder mit fester Breite gelesen. In diesem Beispiel wird die `TextFieldParser``reader` und verwendet ihn zum Auslesen `C:\TestFolder1\test1.txt`.  
  
 [!code-vb[VbVbalrTextFieldParser#23](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_3.vb)]  
  
 `My.Application` können Sie die Kultur für die Anwendung zu ändern. Im folgende Beispiel wird veranschaulicht, wie diese Methode aufgerufen werden kann.  
  
 [!code-vb[VbVbcnMy#3](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_4.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [Merkmale von "My" auf Grundlage des Projekttyps](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
