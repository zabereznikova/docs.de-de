---
title: WithEvents (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.WithEvents
- WithEvents
dev_langs:
- VB
helpviewer_keywords:
- WithEvents keyword
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 708cf6fec78faf2c7a5959a3a2694d237d728882
ms.lasthandoff: 03/13/2017

---
# <a name="withevents-visual-basic"></a>WithEvents (Visual Basic)
Gibt an, dass eine oder mehrere Membervariablen auf eine Instanz einer Klasse verweisen, die Ereignisse auslösen kann.  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine Variable mit definiert wird `WithEvents`, können Sie deklarativ angeben, dass eine Methode die Ereignisse der Variablen mit behandelt die `Handles` Schlüsselwort.  
  
 Sie können `WithEvents` nur auf Klassen-oder Modulebene. Dies bedeutet, dass der Deklarationskontext für eine `WithEvents` Variable muss eine Klasse oder ein Modul und eine Quelldatei, Namespace, Struktur oder Prozedur nicht möglich.  
  
 Sie können keine `WithEvents` auf einen Member einer Struktur.  
  
 Sie können nur einzelne Variablen deklarieren, keine arrays – mit `WithEvents`.  
  
## <a name="rules"></a>Regeln  
  
-   **Elementtypen.** Deklarieren Sie `WithEvents` Variablen als Objektvariablen, damit sie akzeptieren können Klasseninstanzen. Jedoch nicht Sie deklarieren diese als `Object`. Sie müssen diese als spezifische Klasse deklarieren, die Ereignisse auslösen kann.  
  
 Die `WithEvents` Modifizierer kann in diesem Kontext verwendet werden: [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)   
 [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)
