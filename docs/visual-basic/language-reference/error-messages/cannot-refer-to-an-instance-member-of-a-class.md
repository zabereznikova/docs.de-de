---
title: Auf einen Instanzmember einer Klasse kann nicht ohne explizite Instanz einer Klasse von einer/m freigegebenen Methode/Member aus verwiesen werden.
ms.date: 07/20/2015
f1_keywords:
- vbc30369
- bc30369
helpviewer_keywords:
- Shared
- BC30369
ms.assetid: 39d9466b-c1f3-4406-91a5-3d6c52d23a3d
ms.openlocfilehash: 368539ed24d9819c8d1ddbbb9e3e0dff21d27c32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a>Auf einen Instanzmember einer Klasse kann nicht ohne explizite Instanz einer Klasse von einer/m freigegebenen Methode/Member aus verwiesen werden.
Sie haben versucht, auf einen nicht freigegebenen Member einer Klasse von eine freigegebene Prozedur verweisen. Das folgende Beispiel zeigt eine solche Situation.  
  
```  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 Im vorhergehenden Beispiel die zuweisungsanweisung `x = 10` generiert diese Fehlermeldung. Dies ist eine freigegebene Prozedur versucht, auf eine Instanzvariablen zuzugreifen.  
  
 Die Variable `x` ein Instanzmember ist, da er nicht als deklariert wird [Shared](../../../visual-basic/language-reference/modifiers/shared.md). Jede Instanz der Klasse `sample` enthält ihre eigene Variable `x`. Wenn eine Instanz legt fest oder ändert den Wert des `x`, er hat keine Auswirkungen auf den Wert des `x` in einer anderen Instanz.  
  
 Allerdings die Prozedur `setX` ist `Shared` für alle Instanzen der Klasse `sample`. Dies bedeutet, es ist nicht mit einer Instanz der Klasse verknüpft, aber unabhängig von den einzelnen Instanzen angewendet wird. Da es keine Verbindung mit einer bestimmten Instanz besitzt `setX` eine Instanzvariablen kann nicht zugegriffen werden kann. Er muss ausgeführt werden, nur auf `Shared` Variablen. Wenn `setX` legt fest oder ändert den Wert für eine freigegebene Variable, dass der neue Wert für alle Instanzen der Klasse verfügbar ist.  
  
 **Fehler-ID:** BC30369  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Entscheiden Sie, ob das Element für alle Instanzen der Klasse freigegeben oder jeder Instanz beibehalten werden sollen.  
  
2.  Wenn Sie eine einzelne Kopie des Elements, die für alle Instanzen freigegeben werden soll, fügen die `Shared` Schlüsselwort, um die Memberdeklaration. Beibehalten der `Shared` -Schlüsselwort in der Deklaration der Prozedur.  
  
3.  Wenn Sie jede Instanz eine eigene Kopie des Elements haben soll, geben Sie keine `Shared` für die Memberdeklaration. Entfernen Sie die `Shared` -Schlüsselwort aus der Deklaration der Prozedur.  
  
## <a name="see-also"></a>Siehe auch  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
