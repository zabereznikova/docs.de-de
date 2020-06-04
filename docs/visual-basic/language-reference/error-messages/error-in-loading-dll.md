---
title: Fehler beim Laden der DLL
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: fd2e425f2dd3f4127cd777d4a1f7ab9809de9d45
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409625"
---
# <a name="error-in-loading-dll-visual-basic"></a>Fehler beim Laden der DLL (Visual Basic)
Eine Dynamic Link Library (dll) ist eine Bibliothek, die in der-Klausel einer-Anweisung angegeben ist `Lib` `Declare` . Mögliche Ursachen für diesen Fehler:  
  
- Die Datei ist keine ausführbare DLL-Datei.  
  
- Bei der Datei handelt es sich nicht um eine Microsoft Windows-DLL.  
  
- Die dll verweist auf eine andere dll, die nicht vorhanden ist.  
  
- Die dll oder die referenzierte DLL befindet sich nicht in einem Verzeichnis, das im Pfad angegeben ist.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Handelt es sich bei der Datei um eine Quell Textdatei und somit nicht um eine ausführbare DLL-Datei, muss sie kompiliert und mit einem ausführbaren DLL-Formular verknüpft werden.  
  
- Wenn die Datei keine Microsoft Windows-dll ist, müssen Sie die Microsoft Windows-Entsprechung abrufen.  
  
- Wenn die dll auf eine andere dll verweist, die nicht vorhanden ist, können Sie die referenzierte DLL abrufen und verfügbar machen.  
  
- Wenn sich die dll oder die referenzierte DLL nicht in einem Verzeichnis befindet, das durch den Pfad angegeben ist, verschieben Sie die dll in ein referenziertes Verzeichnis.  
  
## <a name="see-also"></a>Weitere Informationen

- [Declare Statement](../statements/declare-statement.md)
