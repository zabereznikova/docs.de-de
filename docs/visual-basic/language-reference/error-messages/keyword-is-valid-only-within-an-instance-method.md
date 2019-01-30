---
title: <keyword> ist nur innerhalb einer Instanzenmethode gültig.
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: af3bc95e2db88577c7c53e4b58fb60aed8a83453
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267642"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a>"\<Schlüsselwort >' ist nur innerhalb einer Instanzenmethode gültig
Die `Me`, `MyClass`, und `MyBase` Schlüsselwörter beziehen sich auf bestimmte Klasseninstanzen. Können Sie nicht in einem gemeinsam verwendeten `Function` oder `Sub` Verfahren.  
  
 **Fehler-ID:** BC30043  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie das Schlüsselwort aus der Prozedur, oder Entfernen der `Shared` -Schlüsselwort aus der Deklaration der Prozedur.  
  
## <a name="see-also"></a>Siehe auch
- [Zuweisen von Objektvariablen](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase und MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
