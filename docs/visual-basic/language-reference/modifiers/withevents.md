---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 240058a534456ae20c9c129a068bae575ac45eda
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="withevents-visual-basic"></a>WithEvents (Visual Basic)
Gibt an, dass eine oder mehrere deklarierten Member-Variablen mit einer Instanz einer Klasse verweisen, die Ereignisse auslösen kann.  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine Variable definiert ist mit `WithEvents`, können Sie deklarativ angeben, dass eine Methode Ereignisse der Variablen mit verarbeitet die `Handles` Schlüsselwort.  
  
 Sie können `WithEvents` nur auf Klassen-oder Modulebene. Dies bedeutet, dass der Deklarationskontext für eine `WithEvents` Variable muss eine Klasse oder ein Modul sein und darf keine Quelldatei, Namespace, Struktur oder Prozedur.  
  
 Sie können keine `WithEvents` auf einen Member einer Struktur.  
  
 Sie können nur einzelne Variablen deklarieren – keine arrays – mit `WithEvents`.  
  
## <a name="rules"></a>Regeln  
  
-   **Elementtypen.** Sie müssen deklarieren `WithEvents` -Klasseninstanzen für Variablen Objektvariablen sein, damit sie akzeptieren können. Allerdings kann nicht deklariert werden als `Object`. Sie müssen diese als spezifische Klasse deklarieren, die die Ereignisse auslösen kann.  
  
 Die `WithEvents` Modifizierer kann in diesem Kontext verwendet werden: [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)  
 [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)
