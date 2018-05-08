---
title: Die Anweisung ist innerhalb einer Methode mehrzeiligen Lambda ungültig
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: cef5beea16c8589a884b7d3533e0543454783999
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a>Die Anweisung ist innerhalb einer Methode oder eines mehrzeiligen Lambda-Ausdrucks nicht gültig.
Die Anweisung gilt nicht innerhalb einer `Sub`, `Function`, Eigenschaft `Get`, oder die Eigenschaft `Set` Prozedur. Einige Anweisungen können auf das Modul oder Klassenebene platziert werden. Andere, z. B. `Option Strict`, werden auf Namespaceebene und vor allen anderen Deklarationen stehen müssen.  
  
 **Fehler-ID:** BC30024  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie die Anweisung aus der Prozedur.  
  
## <a name="see-also"></a>Siehe auch  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md)  
 [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md)
