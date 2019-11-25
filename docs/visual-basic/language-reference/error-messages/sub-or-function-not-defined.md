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
A `Sub` or `Function` must be defined in order to be called. Dieser Fehler kann folgende Ursachen haben:  
  
- Misspelling the procedure name.  
  
- Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.  
  
- Specifying a procedure that is not visible to the calling procedure.  
  
- Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Make sure that the procedure name is spelled correctly.  
  
2. Find the name of the project containing the procedure you want to call in the **References** dialog box. If it does not appear, click the **Browse** button to search for it. Select the check box to the left of the project name, and then click **OK**.  
  
3. Check the name of the routine.  
  
## <a name="see-also"></a>Siehe auch

- [Fehlertypen](../../../visual-basic/programming-guide/language-features/error-types.md)
- [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project)
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
