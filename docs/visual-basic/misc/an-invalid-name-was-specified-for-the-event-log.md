---
title: "Für das Ereignisprotokoll wurde ein ungültiger Name angegeben."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fc5a2e93541063a129efaa0ce08fc19a98372126
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a>Für das Ereignisprotokoll wurde ein ungültiger Name angegeben.
Für das Ereignisprotokoll wurde ein ungültiger Name angegeben. Dies liegt in der Regel an ungültigen Zeichen im Namen, an einem leeren Dateinamen oder an einem zu langen Dateinamen.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn der angegebene Name mehr als acht Zeichen lang ist, stellen Sie sicher, dass kein Konflikt mit den Namen anderer Ereignisprotokolle auftritt. Bei der Ermittlung, ob der Name eindeutig ist, werden nur die ersten acht Zeichen ausgewertet.  
  
-   Stellen Sie beim Angeben eines Pfads sicher, dass er ordnungsgemäß analysiert wird.  
  
-   Vergewissern Sie sich, dass sich keine ungültigen Zeichen im Namen befinden. Zu den Zeichen, die nicht in einem Dateinamen verwendet werden dürfen, zählen die Folgenden: `<`, `>`, `:`, `"`, `/`, `\`und `|`.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Analysieren von Dateipfaden](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)  
 [Gewusst wie: Umbenennen einer Datei](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)  
 [Vorgehensweise: Erstellen und Entfernen von benutzerdefinierte Ereignisprotokolle](http://msdn.microsoft.com/en-us/af9b7da0-80c7-46ac-b7f7-897063ddd503)
