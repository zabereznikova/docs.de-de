---
title: Ausführen von Aufgaben mit My.Application, My.Computer und My.User
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: 55961d6857b690fc2726f541df8a5497a3207928
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411693"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a>Ausführen von Aufgaben mit My.Application, My.Computer und My.User (Visual Basic)

Die drei zentralen `My`-Objekte, die Zugriff auf Informationen und häufig verwendete Funktionen bieten, sind `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>) und `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>). Sie können diese Objekte verwenden, um auf Informationen zuzugreifen, die im Zusammenhang mit der aktuellen Anwendung, dem Computer, auf dem die Anwendung installiert ist, oder dem aktuellen Benutzer der Anwendung stehen.  
  
## <a name="myapplication-mycomputer-and-myuser"></a>My.Application, My.Computer und My.User  

 In den folgenden Beispielen wird veranschaulicht, wie Informationen mithilfe von `My` abgerufen werden können.  
  
 [!code-vb[VbVbcnMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbcnMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#2)]  
  
 Zusätzlich zum Abrufen von Informationen ermöglichen die Member, die über diese drei Objekte verfügbar gemacht werden, auch das Ausführen von Methoden, die mit diesem Objekt verknüpft sind. Beispielsweise können Sie auf viele verschiedene Methoden zugreifen, um Dateien zu bearbeiten oder die Registrierung über `My.Computer` zu aktualisieren.  
  
 Datei-E/A-Vorgänge gestalten sich mit `My` bedeutend einfacher und schneller, da eine Vielzahl von Methoden und Eigenschaften zum Bearbeiten von Dateien, Verzeichnissen und Laufwerken enthalten sind. Das <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>-Objekt ermöglicht das Lesen aus großen strukturierten Dateien, die Felder mit Trennzeichen oder fester Breite enthalten. In diesem Beispiel wird `TextFieldParser` `reader` geöffnet und zum Lesen aus `C:\TestFolder1\test1.txt` verwendet.  
  
 [!code-vb[VbVbalrTextFieldParser#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#23)]  
  
 `My.Application` ermöglicht es Ihnen, die Kultur für Ihre Anwendung zu ändern. Das folgende Beispiel veranschaulicht, wie diese Methode aufgerufen werden kann.  
  
 [!code-vb[VbVbcnMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Merkmale von "My" auf Grundlage des Projekttyps](how-my-depends-on-project-type.md)
