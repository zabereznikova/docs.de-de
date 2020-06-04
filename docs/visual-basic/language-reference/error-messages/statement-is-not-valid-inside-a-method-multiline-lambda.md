---
title: Die Anweisung ist innerhalb einer Methode oder eines mehrzeiligen Lambda-Ausdrucks nicht gültig.
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: f3c43d640259d5e1af545e2610088aab5d70453d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396245"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a>Die Anweisung ist innerhalb einer Methode oder eines mehrzeiligen Lambda-Ausdrucks nicht gültig.
Die-Anweisung ist in einer-,-,-oder-Eigenschaften `Sub` `Function` Prozedur ungültig `Get` `Set` . Einige-Anweisungen können auf Modul-oder Klassenebene platziert werden. Andere, wie z `Option Strict` . b., müssen sich auf der Namespace Ebene befinden und vor allen anderen Deklarationen stehen.  
  
 **Fehler-ID:** BC30024  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Entfernen Sie die-Anweisung aus der Prozedur.  
  
## <a name="see-also"></a>Weitere Informationen

- [Sub-Anweisung](../statements/sub-statement.md)
- [Function-Anweisung](../statements/function-statement.md)
- [Get-Anweisung](../statements/get-statement.md)
- [Set-Anweisung](../statements/set-statement.md)
