---
title: Für das Ereignisprotokoll wurde ein ungültiger Name angegeben.
ms.date: 07/20/2015
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
ms.openlocfilehash: 2b9c934272d0f3392c845dcd2f0062a98dc50c7b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940672"
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a>Für das Ereignisprotokoll wurde ein ungültiger Name angegeben.
Für das Ereignisprotokoll wurde ein ungültiger Name angegeben. Dies liegt in der Regel an ungültigen Zeichen im Namen, an einem leeren Dateinamen oder an einem zu langen Dateinamen.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Wenn der angegebene Name mehr als acht Zeichen lang ist, stellen Sie sicher, dass kein Konflikt mit den Namen anderer Ereignisprotokolle auftritt. Bei der Ermittlung, ob der Name eindeutig ist, werden nur die ersten acht Zeichen ausgewertet.  
  
- Stellen Sie beim Angeben eines Pfads sicher, dass er ordnungsgemäß analysiert wird.  
  
- Vergewissern Sie sich, dass sich keine ungültigen Zeichen im Namen befinden. Zu den Zeichen, die nicht in einem Dateinamen verwendet werden dürfen, zählen die Folgenden: `<`, `>`, `:`, `"`, `/`, `\`und `|`.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Analysieren von Dateipfaden](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
- [Vorgehensweise: Umbenennen einer Datei](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
