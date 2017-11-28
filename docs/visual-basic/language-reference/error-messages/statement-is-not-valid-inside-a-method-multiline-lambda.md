---
title: "Die Anweisung ist innerhalb einer Methode mehrzeiligen Lambda ungültig"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords: BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 80673fc7a1497b4148a6505d29581c6403115558
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a>Die Anweisung ist innerhalb einer Methode oder eines mehrzeiligen Lambda-Ausdrucks nicht gültig.
Die Anweisung gilt nicht innerhalb einer `Sub`, `Function`, Eigenschaft `Get`, oder die Eigenschaft `Set` Prozedur. Einige Anweisungen können auf das Modul oder Klassenebene platziert werden. Andere, z. B. `Option Strict`, werden auf Namespaceebene und vor allen anderen Deklarationen stehen müssen.  
  
 **Fehler-ID:** BC30024  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie die Anweisung aus der Prozedur.  
  
## <a name="see-also"></a>Siehe auch  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md)  
 [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md)
