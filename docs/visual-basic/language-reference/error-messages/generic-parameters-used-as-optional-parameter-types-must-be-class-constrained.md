---
title: "Generische Parameter, die als optionale Parametertypen verwendet werden, müssen eine Klassenbeschränkung aufweisen."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a13ea66f12e54db4e585577e20e1f5396669f1a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a>Generische Parameter, die als optionale Parametertypen verwendet werden, müssen eine Klassenbeschränkung aufweisen.
Eine Prozedur ist mit einem optionalen Parameter deklariert, der einen Typparameter, der nicht eingeschränkt wird verwendet, um ein Verweistyp sein muss.  
  
 Sie müssen immer einen Standardwert für jeden optionalen Parameter angeben. Wenn der Parameter ein Verweistyp ist, muss der optionale Wert `Nothing`, dies ist ein gültiger Wert für jeden Referenztyp. Wenn der Parameter ein Werttyp ist, muss dieses Typs einen elementaren Datentyp, der vom Visual Basic vordefiniert sein. Dies ist, da Sie ein zusammengesetzten Werttyp aufweist, z. B. eine benutzerdefinierte Struktur keine gültigen Standardwert verfügt.  
  
 Wenn Sie einen Typparameter für einen optionalen Parameter verwenden, müssen Sie sicherstellen, dass sie einen Verweistyp zum Vermeiden eines Werttyps verfügt über keinen gültigen Standardwert aufweist. Dies bedeutet, Sie müssen dem Typparameter entweder durch Einschränken der `Class` Schlüsselwort oder mit dem Namen einer bestimmten Klasse.  
  
 **Fehler-ID:** BC32124  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Schränken Sie den Typparameter um nur den Verweistyp akzeptiert, oder verwenden Sie es nicht für den optionalen Parameter.  
  
## <a name="see-also"></a>Siehe auch  
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Typliste](../../../visual-basic/language-reference/statements/type-list.md)  
 [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Optionale Parameter](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Nothing](../../../visual-basic/language-reference/nothing.md)
