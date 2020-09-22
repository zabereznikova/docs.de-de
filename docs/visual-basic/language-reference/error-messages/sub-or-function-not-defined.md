---
title: "\"Sub\" oder \"Function\" ist nicht definiert"
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 24e290ce1193cd6bc6a0ec8985902576332423f2
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870524"
---
# <a name="sub-or-function-not-defined-visual-basic"></a>Sub oder Funktion ist nicht definiert (Visual Basic)

Ein `Sub` oder `Function` muss definiert werden, um aufgerufen werden zu können. Dieser Fehler kann folgende Ursachen haben:  
  
- Falsche Rechtschreibprüfung für den Namen der Prozedur.  
  
- Es wird versucht, eine Prozedur aus einem anderen Projekt aufzurufen, ohne explizit einen Verweis auf dieses Projekt im Dialogfeld **Verweise** hinzuzufügen.  
  
- Angeben einer Prozedur, die für die aufrufenden Prozeduren nicht sichtbar ist.  
  
- Deklarieren einer Windows-DLL-Routine (Dynamic-Link Library) oder einer Macintosh-Code Ressourcen Routine, die nicht in der angegebenen Bibliothek oder Code Ressource ist.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Stellen Sie sicher, dass der Name der Prozedur richtig geschrieben ist.  
  
2. Suchen Sie den Namen des Projekts, das die Prozedur enthält, die Sie im Dialogfeld **Verweise** aufzurufen möchten. Wenn Sie nicht angezeigt wird, klicken Sie auf die Schaltfläche **Durchsuchen** , um Sie zu suchen. Aktivieren Sie das Kontrollkästchen links neben dem Projektnamen, und klicken Sie dann auf **OK**.  
  
3. Überprüfen Sie den Namen der Routine.  
  
## <a name="see-also"></a>Weitere Informationen

- [Fehlertypen](../../programming-guide/language-features/error-types.md)
- [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project)
- [Sub-Anweisung](../statements/sub-statement.md)
- [Function-Anweisung](../statements/function-statement.md)
