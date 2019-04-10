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
ms.openlocfilehash: aad068b5857eb956ded63fa2a57cb163d3cf5c58
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59322692"
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a>Auf einen Instanzmember einer Klasse kann nicht ohne explizite Instanz einer Klasse von einer/m freigegebenen Methode/Member aus verwiesen werden.
Sie haben versucht, auf einen nicht freigegebenen Member einer Klasse über ein gemeinsames Verfahren zu verweisen. Das folgende Beispiel zeigt eine solche Situation.  
  
```  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 Im vorherigen Beispiel die zuweisungsanweisung `x = 10` generiert diese Fehlermeldung wird angezeigt. Dies ist, da ein gemeinsames Verfahren eine Instanzvariable zugreifen möchte.  
  
 Die Variable `x` ein Instanzmember ist, da er nicht als deklariert wird [Shared](../../../visual-basic/language-reference/modifiers/shared.md). Jede Instanz der Klasse `sample` enthält eine eigene Variable `x`. Wenn eine Instanz legt fest oder ändert den Wert des `x`, es hat keine Auswirkungen auf den Wert der `x` in einer anderen Instanz.  
  
 Allerdings die Prozedur `setX` ist `Shared` von allen Instanzen der Klasse `sample`. Dies bedeutet, es ist nicht mit einer Instanz der Klasse verknüpft und unabhängig von den einzelnen Instanzen angewendet wird. Da sie keine Verbindung mit einer bestimmten Instanz ist, hat `setX` eine Instanzvariable kann nicht zugegriffen werden kann. Es muss nur auf ausgeführt `Shared` Variablen. Wenn `setX` legt fest oder ändert den Wert für eine freigegebene Variable, dass der neue Wert für alle Instanzen der Klasse verfügbar ist.  
  
 **Fehler-ID:** BC30369  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Entscheiden Sie, ob das Element für alle Instanzen der Klasse freigegeben oder jeder Instanz beibehalten werden sollen.  
  
2. Wenn Sie eine einzelne Kopie des Elements, die für alle Instanzen freigegeben werden soll, Hinzufügen der `Shared` Schlüsselwort zur Memberdeklaration. Beibehalten der `Shared` -Schlüsselwort in der Deklaration der Prozedur.  
  
3. Wenn Sie jede Instanz über ein eigenes Exemplar des Elements haben möchten, geben Sie keine `Shared` für die Element-Deklaration. Entfernen Sie die `Shared` -Schlüsselwort aus der Deklaration der Prozedur.  
  
## <a name="see-also"></a>Siehe auch

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
