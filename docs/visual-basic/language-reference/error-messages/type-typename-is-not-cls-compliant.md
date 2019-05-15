---
title: Typ "<typename>" ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: 2805cac71cb36d21f5ab21a5875183803d07a4b4
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642364"
---
# <a name="type-typename-is-not-cls-compliant"></a>Typ \<Typname > ist nicht CLS-kompatibel.
Eine Variable, Eigenschaft oder Funktionsrückgabe wird mit einem Datentyp deklariert, die nicht CLS-kompatibel ist.  
  
 Für eine Anwendung einhalten der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS), müssen sie nur CLS-kompatible Typen verwenden.  
  
 Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:  
  
- [SByte-Datentyp](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [UInteger-Datentyp](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [ULong-Datentyp](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [UShort-Datentyp](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 **Fehler-ID:** BC40041  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Wenn Ihre Anwendung CLS-kompatibel sein muss, ändern Sie den Datentyp der dieses Element in den ähnlichsten CLS-kompatiblen Typ. Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen. Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.  
  
- Wenn Ihre Anwendung nicht CLS-kompatibel sein muss, müssen Sie keine Änderungen vornehmen. Sie sollten jedoch beachten die Nichtkompatibilität, sein.
