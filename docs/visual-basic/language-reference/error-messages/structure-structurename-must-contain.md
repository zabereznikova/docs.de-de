---
title: Struktur &#39; &lt;Structurename&gt; &#39; muss mindestens eine Instanzmembervariable oder mindestens eine Instanzereignisdeklaration nicht gekennzeichnet enthalten &#39;benutzerdefinierte&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 85a4babc808e274a99f2c9faf08a02abf8aa4e93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="structure-39ltstructurenamegt39-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-39custom39"></a>Struktur &#39; &lt;Structurename&gt; &#39; muss mindestens eine Instanzmembervariable oder mindestens eine Instanzereignisdeklaration nicht gekennzeichnet enthalten &#39;benutzerdefinierte&#39;
Eine Strukturdefinition umfasst keine nicht freigegebene Variablen oder nicht freigegebene nicht benutzerdefinierte Ereignisse.  
  
 Jede Struktur benötigen, eine Variable oder ein Ereignis, das für jede spezifische Instanz (nicht freigegebene) anstelle von allen Instanzen gemeinsam gilt ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)). Nicht freigegebene Konstanten, Eigenschaften und Prozeduren erfüllen diese Anforderung nicht. Darüber hinaus treten keine nicht freigegebenen Variablen und nur ein nicht freigegebenes Ereignis, das Ereignis nicht mit einem `Custom` Ereignis.  
  
 **Fehler-ID:** BC30941  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Definieren Sie mindestens eine Variable oder ein Ereignis, das nicht `Shared`. Wenn Sie nur ein Ereignis definieren, muss es sowohl nicht benutzerdefinierte als auch nicht freigegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Gewusst wie: Deklarieren einer Struktur](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)
