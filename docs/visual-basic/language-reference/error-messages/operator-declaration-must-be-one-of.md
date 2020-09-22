---
title: 'Die Operator Deklaration muss einer der folgenden sein: +,-, *,-,-, ^, &amp; , like, mod, and, or, Xor, not,  <<,  >>, =,  <>, <, <=, >, >=, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: c388b1b0762dd7475ca365a8a62228d0b5d59414
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873620"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a>Die Operator Deklaration muss eine der folgenden sein: +,-, *, \, /, ^, &amp; , like, mod, and, or, Xor, not, \<\<, >>...

Sie können nur einen Operator deklarieren, der für das überladen geeignet ist. In der folgenden Tabelle sind die zu deklarierenden Operatoren aufgelistet.  
  
|type|Operatoren|  
|----------|---------------|  
|Unär|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binary|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Konvertierung (unär)|`CType`|  
  
 Beachten Sie, dass der- `=` Operator in der binären Liste der Vergleichs Operator und nicht der Zuweisungs Operator ist.  
  
 **Fehler-ID:** BC33000  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Wählen Sie einen Operator aus der Gruppe der überladbaren Operatoren aus.  
  
2. Wenn Sie die Funktionalität des Überladens eines Operators benötigen, der nicht direkt überladen werden kann, erstellen Sie eine `Function` -Prozedur, die die entsprechenden Parameter übernimmt und den entsprechenden Wert zurückgibt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Operator Statement](../statements/operator-statement.md)
- [Operatorprozeduren](../../programming-guide/language-features/procedures/operator-procedures.md)
- [Vorgehensweise: Definieren eines Operators](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Vorgehensweise: Definieren eines Konvertierungsoperators](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Function-Anweisung](../statements/function-statement.md)
