---
title: Fehlerhafter Dateimodus.
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: 534ea2d8316dc29cace798c5ad9b7697a290026f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409868"
---
# <a name="bad-file-mode"></a>Fehlerhafter Dateimodus.
Anweisungen, die zum Bearbeiten von Dateiinhalten verwendet werden, müssen für den Modus geeignet sein, in dem die Datei geöffnet wurde. Mögliche Ursachen sind:  
  
- Eine- `FilePutObject` oder- `FileGetObject` Anweisung gibt eine sequenzielle Datei an.  
  
- Eine- `Print` Anweisung gibt eine Datei an, die für einen anderen Zugriffsmodus als oder geöffnet wurde `Output` `Append` .  
  
- Eine- `Input` Anweisung gibt eine Datei an, die für einen anderen Zugriffsmodus geöffnet ist als`Input`  
  
- Der Versuch, in eine schreibgeschützte Datei zu schreiben.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Stellen Sie `FilePutObject` sicher `FileGetObject` , dass und nur auf Dateien verweisen, die für den- `Random` oder- `Binary` Zugriff geöffnet  
  
- Stellen Sie sicher, `Print` dass eine Datei für `Output` den `Append` Zugriffsmodus oder geöffnet ist. Wenn dies nicht der Wert ist, verwenden Sie eine andere Anweisung, um Daten in der Datei zu platzieren, oder öffnen Sie die Datei in einem entsprechenden Modus erneut.  
  
- Stellen Sie sicher, `Input` dass eine Datei für geöffnet ist `Input` . Wenn dies nicht der Wert ist, verwenden Sie eine andere Anweisung, um Daten in der Datei zu platzieren, oder öffnen Sie die Datei in einem entsprechenden Modus  
  
- Wenn Sie in eine schreibgeschützte Datei schreiben, ändern Sie den Lese-/Schreibstatus der Datei, oder versuchen Sie nicht, in die Datei zu schreiben.  
  
- Verwenden Sie die im `My.Computer.FileSystem` -Objekt verfügbare Funktionalität.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.FileSystem>
- [Problembehandlung: Lesen aus und Schreiben in Textdateien](../../developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
