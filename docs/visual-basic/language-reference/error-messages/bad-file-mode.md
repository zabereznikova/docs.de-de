---
title: Fehlerhafter Dateimodus.
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: bccbbbeb79f38790a4664b0152ca3378fb55448d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587383"
---
# <a name="bad-file-mode"></a>Fehlerhafter Dateimodus.
-Anweisungen in Bearbeiten des Dateiinhalts müssen in den Modus geeignet sein, in denen die Datei geöffnet wurde. Mögliche Ursachen sind:  
  
-   Ein `FilePutObject` oder `FileGetObject` -Anweisung gibt eine sequenzielle Datei.  
  
-   Ein `Print` -Anweisung gibt eine andere als für einen Zugriffsmodus geöffnete Datei `Output` oder `Append`.  
  
-   Ein `Input` -Anweisung gibt eine Datei für einen Zugriffsmodus außer geöffnet `Input`  
  
-   Fehler beim Schreiben in eine schreibgeschützte Datei.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass `FilePutObject` und `FileGetObject` verweisen nur auf Dateien, die für `Random` oder `Binary` Zugriff.  
  
-   Stellen Sie sicher, dass `Print` gibt an, eine für eine geöffnete Datei `Output` oder `Append` Zugriffsmodus. Wenn dies nicht der Fall ist, verwenden Sie eine andere Anweisung Daten in der Datei zu speichern, oder erneutes Öffnen der Datei im entsprechenden Modus.  
  
-   Stellen Sie sicher, dass `Input` gibt an, eine für die geöffnete Datei `Input`. Wenn dies nicht der Fall ist, verwenden Sie eine andere Anweisung zum Hinzufügen von Daten in der Datei, oder öffnen die Datei im entsprechenden Modus.  
  
-   Wenn Sie in eine schreibgeschützte Datei schreiben, ändern Sie den Lese-/Schreibzugriff Status der Datei, oder versuchen Sie nicht zu schreiben.  
  
-   Verwenden Sie die im `My.Computer.FileSystem` -Objekt verfügbare Funktionalität.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.FileSystem>  
 [Problembehandlung: Lesen aus und Schreiben in Textdateien](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
