---
title: Wiedergabe von Sound
ms.date: 07/20/2015
helpviewer_keywords:
- system sounds, playing
- system sounds
- playing sounds, Visual Basic
- sound loops
- My.Computer.Audio object, tasks
- sounds, playing
- sounds, background
- playing sounds
ms.assetid: f0d9e4ab-57c7-47b6-86d3-99ff07078040
ms.openlocfilehash: 416fedd011ff35d2b32d1b64932e3908a73ed14e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345523"
---
# <a name="playing-sounds-visual-basic"></a>Wiedergabe von Sound (Visual Basic)

Das `My.Computer.Audio`-Objekt stellt Methoden zur Soundwiedergabe bereit.  
  
## <a name="playing-sounds"></a>Wiedergabe von Sound  

 Die Wiedergabe im Hintergrund lässt die Anwendung einen anderen Code ausführen, während der Sound wiedergegeben wird. Die `My.Computer.Audio.Play`-Methode lässt die Anwendung nur einen Hintergrundsound gleichzeitig wiedergeben; wenn die Anwendung einen neuen Hintergrundsound wiedergibt, stoppt sie die Wiedergabe des vorherigen. Sie können auch einen Sound wiedergeben und warten, bis er zu Ende ist.  
  
 Im folgenden Beispiel gibt die `My.Computer.Audio.Play`-Methode einen Sound wieder. Wenn `AudioPlayMode.WaitToComplete` angegeben wird, wartet `My.Computer.Audio.Play`, bis der Sound fertig ist, bevor der aufrufende Code fortgesetzt wird. Sie sollten beim Verwenden dieses Beispiels sicherstellen, dass der Dateiname auf eine WAV-Sounddatei verweist, die sich auf Ihrem Computer befindet.  
  
 [!code-vb[VbVbalrMyComputer#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#15)]  
  
 Im folgenden Beispiel gibt die `My.Computer.Audio.Play`-Methode einen Sound wieder. Sie sollten beim Verwenden dieses Beispiels sicherstellen, dass die Anwendungsressourcen eine WAV-Sounddatei mit dem Namen „Waterfall“ enthält.  
  
 [!code-vb[VbVbalrMyComputer#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#16)]  
  
## <a name="playing-looping-sounds"></a>Wiedergabe von Sound als Schleife  

 Im folgenden Beispiel gibt die `My.Computer.Audio.Play`-Methode den angegebenen Sound im Hintergrund wieder, wenn `PlayMode.BackgroundLoop` angegeben wird. Sie sollten beim Verwenden dieses Beispiels sicherstellen, dass der Dateiname auf eine WAV-Sounddatei verweist, die sich auf Ihrem Computer befindet.  
  
 [!code-vb[VbVbalrMyComputer#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#11)]  
  
 Im folgenden Beispiel gibt die `My.Computer.Audio.Play`-Methode den angegebenen Sound im Hintergrund wieder, wenn `PlayMode.BackgroundLoop` angegeben wird. Sie sollten beim Verwenden dieses Beispiels sicherstellen, dass die Anwendungsressourcen eine WAV-Sounddatei mit dem Namen „Waterfall“ enthält.  
  
 [!code-vb[VbVbalrMyComputer#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#12)]  
  
 Das vorherige Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar. Er befindet sich in der Codeausschnittauswahl unter **Windows Forms-Anwendungen > Sound**. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).  
  
 Wenn normalerweise eine Anwendung einen Sound als Schleife wiedergibt, sollte sie den Sound am Ende anhalten.  
  
## <a name="stopping-the-playing-of-sounds-in-the-background"></a>Beenden der Wiedergabe von Sound im Hintergrund  

 Verwenden Sie die `My.Computer.Audio.Stop`-Methode, um den momentan im Hintergrund oder als Schleife wiedergegebenen Sound der Anwendung zu beenden.  
  
 Wenn eine Anwendung einen Sound als Schleife wiedergibt, sollte sie den Sound normalerweise irgendwann anhalten.  
  
 Im folgenden Beispiel wird ein Sound, der im Hintergrund abgespielt wird, beendet.  
  
 [!code-vb[VbVbalrMyComputer#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#18)]  
  
 Das vorherige Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar. Er befindet sich in der Codeausschnittauswahl unter **Windows Forms-Anwendungen > Sound**. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).  
  
## <a name="playing-system-sounds"></a>Wiedergabe von Systemsound  

 Verwenden Sie die `My.Computer.Audio.PlaySystemSound`-Methode, um den angegebenen Systemsound wiederzugeben.  
  
 Die `My.Computer.Audio.PlaySystemSound`-Methode verwendet als Parameter einen der freigegebenen Member der <xref:System.Media.SystemSound>-Klasse. Der Systemsound <xref:System.Media.SystemSounds.Asterisk%2A> wird im Allgemeinen für Fehler verwendet.  
  
 Im folgenden Beispiel wird die `My.Computer.Audio.PlaySystemSound`-Methode verwendet, um einen Systemsound wiederzugeben.  
  
 [!code-vb[VbVbalrMyComputer#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Devices.Audio>
- <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>
- <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>
- <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>
- <xref:Microsoft.VisualBasic.AudioPlayMode>
