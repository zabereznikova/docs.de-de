---
title: Fehler beim Laden der DLL (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cc557dcc6709178b6519adb56f31debcbd1d1c39
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
