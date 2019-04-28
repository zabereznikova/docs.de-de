---
title: Typ "<typename>" ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: 243f51b3e6c798c82fdbe7b28557c4f96c728bf2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61764373"
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