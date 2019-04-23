---
title: Der Dateiname oder die Zahl ist ungültig.
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: 2e5d4a3ddd66df85dc4758e22b36ac1ed495659a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322159"
---
# <a name="bad-file-name-or-number"></a>Der Dateiname oder die Zahl ist ungültig.
Fehler beim Versuch, die die angegebene Datei zuzugreifen. Zu den möglichen Ursachen für diesen Fehler sind:  
  
-   Eine Anweisung verweist auf eine Datei mit einem Dateinamen oder einer Zahl, die nicht in angegeben wurde der `FileOpen` -Anweisung oder die wurde angegeben, eine `FileOpen` -Anweisung war jedoch anschließend geschlossen.  
  
-   Eine Anweisung verweist auf eine Datei mit der eine Zahl, die außerhalb des Bereichs der Datei Zahlen.  
  
-   Eine Anweisung verweist auf einen Dateinamen oder eine Zahl, die nicht gültig ist.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Stellen Sie sicher, dass der Dateiname ist angegeben, einem `FileOpen` Anweisung. Beachten Sie, dass Sie aufgerufen haben die `FileClose` Anweisung ohne Argumente, Sie möglicherweise versehentlich geschlossen haben alle geöffneten Dateien.  
  
2. Wenn Ihr Code Dateinummern algorithmisch generiert, stellen Sie sicher, dass die Zahlen sind gültig.  
  
3. Überprüfen Sie die Dateinamen, um sicherzustellen, dass sie den Betriebssystem-Konventionen entsprechen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
