---
title: Fehler beim Laden der DLL
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: 35733fe2e20d46207f6cfdaee32f6559fceed6eb
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874380"
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
