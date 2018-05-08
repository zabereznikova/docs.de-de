---
title: Fehler beim Laden der DLL (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: ac21c4d52b248025ee26bac3e511bb5b0a0b668e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="error-in-loading-dll-visual-basic"></a>Fehler beim Laden der DLL (Visual Basic)
Eine Dynamic Link Library (DLL) ist eine Bibliothek, die im angegebenen der `Lib` -Klausel eine `Declare` Anweisung. Mögliche Ursachen für diesen Fehler  
  
-   Die Datei ist keine ausführbare DLL-Datei.  
  
-   Die Datei ist nicht Microsoft Windows DLL.  
  
-   Die DLL verweist auf eine andere DLL, die nicht vorhanden ist.  
  
-   Die DLL oder die referenzierten DLL ist nicht in einem Verzeichnis im Pfad angegeben.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn die Datei eine Textdatei auf dem Quell- und daher nicht die ausführbare DLL ist, müssen Sie kompiliert und zu einem Formular ausführbare DLL verknüpft werden.  
  
-   Wenn die Datei nicht Microsoft Windows DLL ist, erhalten Sie Microsoft Windows-äquivalent.  
  
-   Wenn die DLL auf eine andere DLL, die nicht vorhanden ist verweist, erhalten Sie referenzierte DLL und machen Sie verfügbar zu.  
  
-   Wenn die DLL oder die referenzierten DLL nicht in einem Verzeichnis mit dem Pfad angegeben ist, verschieben Sie die DLL in ein Verzeichnis auf die verwiesen wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)
