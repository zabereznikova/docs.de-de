---
title: <keyword> ist nur innerhalb einer Instanzenmethode gültig.
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: af436b8fd57ff0d2747c766a64af175760931009
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873903"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a>\<keyword> ist nur innerhalb einer Instanzenmethode gültig.

Die `Me` `MyClass` `MyBase` Schlüsselwörter, und verweisen auf bestimmte Klassen Instanzen. Sie können Sie nicht in einer freigegebenen- `Function` oder- `Sub` Prozedur verwenden.  
  
 **Fehler-ID:** BC30043  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Entfernen Sie das-Schlüsselwort aus der Prozedur, oder entfernen Sie das- `Shared` Schlüsselwort aus der Prozedur Deklaration.  
  
## <a name="see-also"></a>Weitere Informationen

- [Zuweisung von Objektvariablen](../../programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase und MyClass](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Grundlagen der Vererbung](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
