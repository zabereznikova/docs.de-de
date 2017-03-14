---
title: "WithEvents (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.WithEvents"
  - "WithEvents"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "WithEvents keyword"
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# WithEvents (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Gibt an, dass mindestens eine deklarierte Membervariable auf die Instanz einer Klasse verweist, die Ereignisse auslösen kann.  
  
## Hinweise  
 Wenn eine Variable mit `WithEvents` definiert ist, können Sie deklarativ angeben, dass eine Methode die Ereignisse der Variablen mit dem `Handles`\-Schlüsselwort behandelt.  
  
 `WithEvents` kann nur auf Klassen\- oder Modulebene verwendet werden.  Dies bedeutet, dass der Deklarationskontext für eine `WithEvents`\-Variable eine Klasse oder ein Modul sein muss und keine Quelldatei, kein Namespace, keine Struktur und keine Prozedur sein kann.  
  
 Sie können `WithEvents` nicht für einen Strukturmember verwenden.  
  
 Sie können mit `WithEvents` nur einzelne Variablen und keine Arrays deklarieren.  
  
## Regeln  
  
-   **Elementtypen.** Sie müssen `WithEvents`\-Variablen als Objektvariablen deklarieren, damit sie Klasseninstanzen akzeptieren können.  Sie können sie jedoch nicht als `Object` deklarieren.  Sie müssen als die spezielle Klasse deklariert werden, die die Ereignisse auslösen kann.  
  
 Der `WithEvents`\-Modifizierer kann im folgenden Kontext verwendet werden: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## Siehe auch  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Stichwörter](../../../visual-basic/language-reference/keywords/index.md)   
 [Events](../../../visual-basic/programming-guide/language-features/events/events.md)