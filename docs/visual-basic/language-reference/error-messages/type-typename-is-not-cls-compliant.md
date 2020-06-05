---
title: Typ "<typename>" ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: eacf5036ebc6fc31dfa0e8de39c4fb574c9072b3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386957"
---
# <a name="type-typename-is-not-cls-compliant"></a>Typ "\<typename>" ist nicht CLS-kompatibel.
Eine Variable, eine Eigenschaft oder eine Funktions Rückgabe wird mit einem Datentyp deklariert, der nicht CLS-kompatibel ist.  
  
 Damit eine Anwendung mit der [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel ist, darf Sie nur CLS-kompatible Typen verwenden.  
  
 Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:  
  
- [SByte-Datentyp](../data-types/sbyte-data-type.md)  
  
- [UInteger-Datentyp](../data-types/uinteger-data-type.md)  
  
- [ULong-Datentyp](../data-types/ulong-data-type.md)  
  
- [UShort-Datentyp](../data-types/ushort-data-type.md)  
  
 **Fehler-ID:** BC40041  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Wenn die Anwendung CLS-kompatibel sein muss, ändern Sie den Datentyp dieses Elements in den nächstgelegenen CLS-kompatiblen Typ. Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen. Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.  
  
- Wenn Ihre Anwendung nicht CLS-kompatibel sein muss, müssen Sie nichts ändern. Beachten Sie jedoch die Nichtkonformität.
