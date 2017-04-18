---
title: Sub oder Funktion nicht definiert (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID35
dev_langs:
- VB
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7d32bc9c8f13b245e6333c4460cab541f6e9409e
ms.lasthandoff: 03/13/2017

---
# <a name="sub-or-function-not-defined-visual-basic"></a>Sub oder Funktion ist nicht definiert (Visual Basic)
Ein `Sub` oder `Function` muss definiert werden, um aufgerufen werden. Dieser Fehler kann folgende Ursachen haben:  
  
-   Der Prozedurname.  
  
-   Bei dem Versuch, eine Prozedur aus einem anderen Projekt aufrufen, ohne explizit einen Verweis auf das Projekt in der **Verweise** Dialogfeld.  
  
-   Angeben einer Prozedur, die für die aufrufende Prozedur nicht sichtbar ist.  
  
-   Deklarieren einer Windows-Dynamic Link Library (DLL)-Routine oder Macintosh-Coderessourcen-Routine, die nicht in der angegebenen Bibliothek oder Code-Ressource ist.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass der Prozedurname richtig geschrieben ist.  
  
2.  Suchen Sie den Namen des Projekts mit der Prozedur aufrufen, die der **Verweise** Dialogfeld. Wenn es nicht angezeigt wird, klicken Sie auf die **Durchsuchen** Schaltfläche, um ihn zu suchen. Wählen Sie das Kontrollkästchen links neben den Namen des Projekts, und klicken Sie dann auf **OK**.  
  
3.  Überprüfen Sie den Namen der Routine.  
  
## <a name="see-also"></a>Siehe auch  
 [Error Types (Fehlertypen)](../../../visual-basic/programming-guide/language-features/error-types.md)   
 [Verwalten von Verweise in einem Projekt](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)   
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
