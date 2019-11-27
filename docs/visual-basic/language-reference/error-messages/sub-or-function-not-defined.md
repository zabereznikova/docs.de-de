---
title: "\"Sub\" oder \"Function\" ist nicht definiert"
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 8b81460eccb6be8baa2ea7bc68d0f80c9d16398e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349578"
---
# <a name="sub-or-function-not-defined-visual-basic"></a>Sub oder Funktion ist nicht definiert (Visual Basic)
Es muss ein `Sub` oder `Function` definiert werden, um aufgerufen werden zu können. Dieser Fehler kann folgende Ursachen haben:  
  
- Falsche Rechtschreibprüfung für den Namen der Prozedur.  
  
- Es wird versucht, eine Prozedur aus einem anderen Projekt aufzurufen, ohne explizit einen Verweis auf dieses Projekt im Dialogfeld **Verweise** hinzuzufügen.  
  
- Angeben einer Prozedur, die für die aufrufenden Prozeduren nicht sichtbar ist.  
  
- Deklarieren einer Windows-DLL-Routine (Dynamic-Link Library) oder einer Macintosh-Code Ressourcen Routine, die nicht in der angegebenen Bibliothek oder Code Ressource ist.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Stellen Sie sicher, dass der Name der Prozedur richtig geschrieben ist.  
  
2. Suchen Sie den Namen des Projekts, das die Prozedur enthält, die Sie im Dialogfeld **Verweise** aufzurufen möchten. Wenn Sie nicht angezeigt wird, klicken Sie auf die Schaltfläche **Durchsuchen** , um Sie zu suchen. Aktivieren Sie das Kontrollkästchen links neben dem Projektnamen, und klicken Sie dann auf **OK**.  
  
3. Überprüfen Sie den Namen der Routine.  
  
## <a name="see-also"></a>Siehe auch

- [Fehlertypen](../../../visual-basic/programming-guide/language-features/error-types.md)
- [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project)
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
