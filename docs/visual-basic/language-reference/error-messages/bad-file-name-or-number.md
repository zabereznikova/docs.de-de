---
title: Der Dateiname oder die Zahl ist ungültig.
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: d57a9e78e6ae179d3050e5a92399ca731fa16ba7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874908"
---
# <a name="bad-file-name-or-number"></a>Der Dateiname oder die Zahl ist ungültig.

Fehler beim Zugriff auf die angegebene Datei. Zu den möglichen Ursachen für diesen Fehler gehören:  
  
- Eine-Anweisung verweist auf eine Datei mit einem Dateinamen oder einer Zahl, der nicht in der-Anweisung angegeben wurde `FileOpen` oder der in einer-Anweisung angegeben wurde, `FileOpen` aber anschließend geschlossen wurde.  
  
- Eine-Anweisung verweist auf eine Datei mit einer Zahl außerhalb des Bereichs von Datei Nummern.  
  
- Eine-Anweisung verweist auf einen ungültigen Dateinamen oder eine ungültige Nummer.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Stellen Sie sicher, dass der Dateiname in einer-Anweisung angegeben ist `FileOpen` . Beachten Sie, dass Sie, wenn Sie die `FileClose` Anweisung ohne Argumente aufgerufen haben, möglicherweise versehentlich alle geöffneten Dateien geschlossen haben.  
  
2. Wenn Ihr Code Datei Nummern algorithmisch erzeugt, stellen Sie sicher, dass die Zahlen gültig sind.  
  
3. Überprüfen Sie die Dateinamen, um sicherzustellen, dass Sie den Betriebssystem Konventionen entsprechen.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [Benennungskonventionen in Visual Basic](../../programming-guide/program-structure/naming-conventions.md)
