---
title: '&#39;&lt;TypeName&gt; &#39; ein Delegattyp'
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: c6d4244ce72dedee50b65ba19978149ce86b9e87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="39lttypenamegt39-is-a-delegate-type"></a>&#39;&lt;TypeName&gt; &#39; ein Delegattyp
"\<Typname >' ein Delegattyp ist. Erstellen eines Delegaten kann nur einen einzelnen AddressOf-Ausdruck als Argument übergeben. AddressOf-Ausdruck kann häufig statt eine Delegatkonstruktion verwendet werden.  
  
 Ein `New` -Klausel erstellt eine Instanz einer Delegatklasse liefert eine ungültige Argumentliste an den Delegatkonstruktor.  
  
 Sie können angeben, dass nur ein einzelner `AddressOf` Ausdruck beim Erstellen einer neuen Delegatinstanz.  
  
 Dieser Fehler kann auftreten, wenn Sie keine Argumente an den Delegatkonstruktor übergeben wenn Sie mehr als ein Argument übergeben, oder wenn Sie ein einzelnes Argument übergeben, die keine gültige `AddressOf` Ausdruck.  
  
 **Fehler-ID:** BC32008  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Ein einzelnes `AddressOf` Ausdruck in der Argumentliste für die Delegate-Klasse in der `New` Klausel.  
  
## <a name="see-also"></a>Siehe auch  
 [New-Operator](../../../visual-basic/language-reference/operators/new-operator.md)  
 [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Gewusst wie: Aufrufen einer Delegatenmethode](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
