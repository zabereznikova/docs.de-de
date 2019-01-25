---
title: '&#39;&lt;Schlüsselwort&gt; &#39; ist nur innerhalb einer Instanzenmethode gültig'
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: a464a059aa2d13e3472b9770960384b6be398092
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595941"
---
# <a name="39ltkeywordgt39-is-valid-only-within-an-instance-method"></a>&#39;&lt;Schlüsselwort&gt; &#39; ist nur innerhalb einer Instanzenmethode gültig
Die `Me`, `MyClass`, und `MyBase` Schlüsselwörter beziehen sich auf bestimmte Klasseninstanzen. Können Sie nicht in einem gemeinsam verwendeten `Function` oder `Sub` Verfahren.  
  
 **Fehler-ID:** BC30043  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie das Schlüsselwort aus der Prozedur, oder Entfernen der `Shared` -Schlüsselwort aus der Deklaration der Prozedur.  
  
## <a name="see-also"></a>Siehe auch
- [Zuweisen von Objektvariablen](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase und MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
