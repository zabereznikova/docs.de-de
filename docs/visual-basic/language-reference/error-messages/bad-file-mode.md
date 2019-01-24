---
title: Fehlerhafter Dateimodus.
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: 1d85f49ce0aed44dea12c9ba16135425e6e2e431
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565747"
---
# <a name="bad-file-mode"></a>Fehlerhafter Dateimodus.
Anweisungen, die verwendet werden, in das Bearbeiten des Dateiinhalts müssen in den Modus geeignet sein, in denen die Datei geöffnet wurde. Mögliche Ursachen sind:  
  
-   Ein `FilePutObject` oder `FileGetObject` Anweisung gibt eine sequenzielle Datei.  
  
-   Ein `Print` -Anweisung gibt eine Datei, die für einen Zugriffsmodus geöffnet sind, außer `Output` oder `Append`.  
  
-   Ein `Input` -Anweisung gibt eine Datei, die für einen Zugriffsmodus geöffnet sind, anders als `Input`  
  
-   Es wurde versucht, in eine schreibgeschützte Datei zu schreiben.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass `FilePutObject` und `FileGetObject` verweisen nur auf Dateien, die für geöffnet `Random` oder `Binary` Zugriff.  
  
-   Stellen Sie sicher, dass `Print` gibt an, eine für eine geöffnete Datei `Output` oder `Append` Zugriffsmodus. Wenn dies nicht der Fall ist, eine andere Anweisung verwenden, um Daten in der Datei zu platzieren, oder öffnen Sie die Datei in einem entsprechenden Modus erneut.  
  
-   Stellen Sie sicher, dass `Input` gibt an, eine für die geöffnete Datei `Input`. Wenn dies nicht der Fall ist, verwenden Sie eine andere Anweisung zum Hinzufügen von Daten in der Datei oder erneutes Öffnen der Datei in einem entsprechenden Modus.  
  
-   Wenn Sie in einer schreibgeschützten Datei schreiben, ändern Sie den Lese-/Schreibzugriff-Status der Datei, oder versuchen Sie nicht, um darin schreiben.  
  
-   Verwenden Sie die im `My.Computer.FileSystem` -Objekt verfügbare Funktionalität.  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.FileSystem>
- [Problembehandlung: Lesen und Schreiben in Textdateien](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
