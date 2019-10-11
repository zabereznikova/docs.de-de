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
ms.openlocfilehash: 9b388685299469d5865d57b698e3a66de912fa84
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250208"
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a>Auf einen Instanzmember einer Klasse kann nicht ohne explizite Instanz einer Klasse von einer/m freigegebenen Methode/Member aus verwiesen werden.

Sie haben versucht, auf einen nicht freigegebenen Member einer Klasse in einer freigegebenen Prozedur zu verweisen. Das folgende Beispiel veranschaulicht eine solche Situation:
  
```vb  
Class Sample
    Public x as Integer  
    Public Shared Sub SetX()
        x = 10  
    End Sub  
End Class  
```  
  
 Im vorherigen Beispiel generiert die Zuweisungsanweisung `x = 10` diese Fehlermeldung. Dies liegt daran, dass eine freigegebene Prozedur versucht, auf eine Instanzvariable zuzugreifen.  
  
 Die Variable `x` ist ein Instanzmember, weil Sie nicht als " [Shared](../modifiers/shared.md)" deklariert ist. Jede Instanz der Klasse `Sample` enthält eine eigene Variable `x`. Wenn eine Instanz den Wert `x` festlegt oder ändert, wirkt sich dies nicht auf den Wert von `x` in einer anderen Instanz aus.
  
 Die Prozedur `SetX` ist jedoch für alle Instanzen der Klasse `Sample` `Shared`. Dies bedeutet, dass Sie keiner Instanz der-Klasse zugeordnet ist, sondern unabhängig von einzelnen Instanzen funktioniert. Da keine Verbindung mit einer bestimmten Instanz besteht, kann `setX` nicht auf eine Instanzvariable zugreifen. Er muss nur für `Shared`-Variablen verwendet werden. Wenn `SetX` den Wert einer freigegebenen Variablen festlegt oder ändert, ist dieser neue Wert für alle Instanzen der Klasse verfügbar.
  
 **Fehler-ID:** BC30369
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler
  
1. Entscheiden Sie, ob der Member für alle Instanzen der Klasse freigegeben werden soll, oder ob der Member für jede Instanz beibehalten werden soll.

2. Wenn Sie möchten, dass eine einzelne Kopie des Members von allen Instanzen gemeinsam verwendet wird, fügen Sie der Element Deklaration das Schlüsselwort `Shared` hinzu. Behalten Sie das `Shared`-Schlüsselwort in der Prozedur Deklaration bei.

3. Wenn jede Instanz über eine eigene Kopie des Members verfügen soll, geben Sie `Shared` nicht für die Element Deklaration an. Entfernen Sie das Schlüsselwort "`Shared`" aus der Prozedur Deklaration.
  
## <a name="see-also"></a>Siehe auch

- [Shared](../modifiers/shared.md)
