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
ms.openlocfilehash: a2a5ab99ff68e6dce783a2fd986ee6e8c15ae858
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701173"
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a>Auf einen Instanzmember einer Klasse kann nicht ohne explizite Instanz einer Klasse von einer/m freigegebenen Methode/Member aus verwiesen werden.
Sie haben versucht, auf einen nicht freigegebenen Member einer Klasse in einer freigegebenen Prozedur zu verweisen. Im folgenden Beispiel wird eine solche Situation veranschaulicht.  
  
```vb  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 Im vorherigen Beispiel generiert die Zuweisungsanweisung `x = 10` diese Fehlermeldung. Dies liegt daran, dass eine freigegebene Prozedur versucht, auf eine Instanzvariable zuzugreifen.  
  
 Die Variable `x` ist ein Instanzmember, weil Sie nicht als " [Shared](../../../visual-basic/language-reference/modifiers/shared.md)" deklariert ist. Jede Instanz der Klasse `sample` enthält eine eigene Variable `x`. Wenn eine Instanz den Wert `x` festlegt oder ändert, wirkt sich dies nicht auf den Wert von `x` in einer anderen Instanz aus.  
  
 Die Prozedur `setX` ist jedoch für alle Instanzen der Klasse `sample` `Shared`. Dies bedeutet, dass Sie keiner Instanz der-Klasse zugeordnet ist, sondern unabhängig von einzelnen Instanzen funktioniert. Da keine Verbindung mit einer bestimmten Instanz besteht, kann `setX` nicht auf eine Instanzvariable zugreifen. Er muss nur für `Shared`-Variablen verwendet werden. Wenn `setX` den Wert einer freigegebenen Variablen festlegt oder ändert, ist dieser neue Wert für alle Instanzen der Klasse verfügbar.  
  
 **Fehler-ID:** BC30369  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Entscheiden Sie, ob der Member für alle Instanzen der Klasse freigegeben werden soll, oder ob der Member für jede Instanz beibehalten werden soll.  
  
2. Wenn Sie möchten, dass eine einzelne Kopie des Members von allen Instanzen gemeinsam verwendet wird, fügen Sie der Element Deklaration das Schlüsselwort `Shared` hinzu. Behalten Sie das `Shared`-Schlüsselwort in der Prozedur Deklaration bei.  
  
3. Wenn jede Instanz über eine eigene Kopie des Members verfügen soll, geben Sie `Shared` nicht für die Element Deklaration an. Entfernen Sie das Schlüsselwort "`Shared`" aus der Prozedur Deklaration.  
  
## <a name="see-also"></a>Siehe auch

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
