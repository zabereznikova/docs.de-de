---
title: Geschachtelte Funktion verfügt nicht über eine Signatur, mit dem Delegaten kompatibel ist &#39; &lt;Delegatname&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: abfda4ee6064ec9ea54b8a3c383d10f8263a1458
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506406"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-39ltdelegatenamegt39"></a>Geschachtelte Funktion verfügt nicht über eine Signatur, mit dem Delegaten kompatibel ist &#39; &lt;Delegatname&gt;&#39;
Ein Lambda-Ausdruck wurde in einen Delegaten zugewiesen, die über eine nicht kompatible Signatur verfügt. Im folgenden Code wird z. B. Delegieren `Del` verfügt über zwei ganzzahlige Parameter.  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 Der Fehler wird ausgelöst, wenn ein Lambda-Ausdruck mit einem Argument als Typ deklariert wird `Del`:  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 **Fehler-ID:** BC36532  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Passen Sie entweder die Delegatdefinition oder den zugewiesenen Lambda-Ausdruck, sodass die Signaturen kompatibel sind.  
  
## <a name="see-also"></a>Siehe auch
- [Gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
