---
title: Der Dateiname oder die Zahl ist ungültig.
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: 903be68e71ad590b4b669545afd077175534ef4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="bad-file-name-or-number"></a>Der Dateiname oder die Zahl ist ungültig.
Fehler beim Versuch, auf die angegebene Datei zuzugreifen. Zu den möglichen Ursachen für diesen Fehler sind:  
  
-   Eine Anweisung verweist auf eine Datei mit einem Dateinamen oder einer Zahl, die nicht im angegebenen der `FileOpen` -Anweisung oder, im angegebenen wurde eine `FileOpen` Anweisung statt anschließend geschlossen.  
  
-   Eine Anweisung verweist auf eine Datei mit einer Zahl, die außerhalb des Bereichs der Datei Zahlen ist.  
  
-   Eine Anweisung verweist auf einen Dateinamen oder eine Zahl, die nicht gültig ist.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass der Dateiname ist angegeben, eine `FileOpen` Anweisung. Beachten Sie, dass, wenn Sie aufgerufen, die `FileClose` Anweisung ohne Argumente, Sie möglicherweise versehentlich geschlossen haben alle geöffneten Dateien.  
  
2.  Wenn Ihr Code Datei Zahlen algorithmisch generiert, stellen Sie sicher, dass die Zahlen gültig sind.  
  
3.  Überprüfen Sie die Dateinamen, um sicherzustellen, dass sie Betriebssystem-Konventionen entsprechen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>  
 [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
