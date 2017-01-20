---
title: "Implements Clause (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.ImplementsClause"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "interface implementation, reimplementation"
  - "interface members, reimplementation"
  - "interface members, Implements keyword"
  - "interface members"
  - "members, reimplementation"
  - "interface implementation, Implements keyword"
  - "interface members, implementing"
  - "Implements keyword"
  - "Implements statement, about Implements"
  - "members, implementing"
  - "members, Implements keyword"
  - "reimplementation"
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Implements Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Kennzeichnet Klassen oder Strukturmember, die die Implementierung für einen in einer Schnittstelle definierten Member enthalten.  
  
## Hinweise  
 Das `Implements`\-Schlüsselwort ist nicht mit der [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md) identisch.  Mit der `Implements`\-Anweisung geben Sie an, dass eine Klasse oder Struktur eine oder mehrere Schnittstellen implementiert. Für jeden Member geben Sie dann mit dem `Implements`\-Schlüsselwort an, welche Schnittstelle und welcher Member implementiert werden.  
  
 Wenn eine Klasse oder eine Struktur eine Schnittstelle implementiert, muss die `Implements`\-Anweisung direkt auf die [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) oder die [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) folgen und alle durch die Schnittstelle definierten Member implementieren.  
  
## Erneute Implementierung  
 In einer abgeleiteten Klasse können Sie einen Schnittstellenmember, der bereits von der Basisklasse implementiert wurde, erneut implementieren.  Dieses Verfahren unterscheidet sich in folgenden Punkten vom Überschreiben des Basisklassenmembers:  
  
-   Der Basisklassenmember muss nicht [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) sein, um erneut implementiert werden zu können.  
  
-   Sie können den Member mit einem anderen Namen erneut implementieren.  
  
 Das `Implements`\-Schlüsselwort kann in den folgenden Kontexten verwendet werden:  
  
 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Siehe auch  
 [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)