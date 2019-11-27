---
title: Fehler beim Laden der DLL
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: 36452cc6ff03042939cd4066aef76129b5bb8f0a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74329562"
---
# <a name="error-in-loading-dll-visual-basic"></a>Fehler beim Laden der DLL (Visual Basic)
Eine Dynamic Link Library (dll) ist eine Bibliothek, die in der `Lib`-Klausel einer `Declare`-Anweisung angegeben ist. Mögliche Ursachen für diesen Fehler:  
  
- Die Datei ist keine ausführbare DLL-Datei.  
  
- Bei der Datei handelt es sich nicht um eine Microsoft Windows-DLL.  
  
- Die dll verweist auf eine andere dll, die nicht vorhanden ist.  
  
- Die dll oder die referenzierte DLL befindet sich nicht in einem Verzeichnis, das im Pfad angegeben ist.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Handelt es sich bei der Datei um eine Quell Textdatei und somit nicht um eine ausführbare DLL-Datei, muss sie kompiliert und mit einem ausführbaren DLL-Formular verknüpft werden.  
  
- Wenn die Datei keine Microsoft Windows-dll ist, müssen Sie die Microsoft Windows-Entsprechung abrufen.  
  
- Wenn die dll auf eine andere dll verweist, die nicht vorhanden ist, können Sie die referenzierte DLL abrufen und verfügbar machen.  
  
- Wenn sich die dll oder die referenzierte DLL nicht in einem Verzeichnis befindet, das durch den Pfad angegeben ist, verschieben Sie die dll in ein referenziertes Verzeichnis.  
  
## <a name="see-also"></a>Siehe auch

- [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)
