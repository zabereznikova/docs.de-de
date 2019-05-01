---
title: Die Anweisung ist innerhalb einer Methode-mehrzeiligen Lambda-Ausdrucks ungültig
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: 994cafc44a37d16d0f70caec560f530c6a836ec0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62055120"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a>Die Anweisung ist innerhalb einer Methode oder eines mehrzeiligen Lambda-Ausdrucks nicht gültig.
Die Anweisung gilt nicht innerhalb einer `Sub`, `Function`, Eigenschaft `Get`, oder die Eigenschaft `Set` Verfahren. Einige Anweisungen können auf der Ebene Projektmoduls oder der Klasse platziert werden. Andere, z. B. `Option Strict`, muss auf Namespaceebene und allen anderen Deklarationen voranstehen.  
  
 **Fehler-ID:** BC30024  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Entfernen Sie die Anweisung von der Prozedur.  
  
## <a name="see-also"></a>Siehe auch

- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
- [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md)
- [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md)
