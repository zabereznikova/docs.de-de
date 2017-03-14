---
title: "Declaration Contexts and Default Access Levels (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "module level, defined"
  - "declaration contexts, Visual Basic"
  - "procedure level, defined"
  - "namespace level, defined"
  - "access levels, Visual Basic"
  - "access levels, default levels"
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Declaration Contexts and Default Access Levels (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

In diesem Thema wird erläutert, welche Visual Basic\-Typen innerhalb welcher anderer Typen deklariert werden können und welche Zugriffsebenen standardmäßig für die Typen gelten, wenn sie nicht festgelegt werden.  
  
## Deklarationskontextebenen  
 Der *Deklarationskontext* eines Programmierelements ist der Codebereich, in dem es deklariert wird.  Häufig handelt es sich dabei um ein anderes Programmierelement, das dann als *enthaltendes Element* bezeichnet wird.  
  
 Es gibt folgende Ebenen für Deklarationskontexte:  
  
-   *Namespaceebene* – innerhalb einer Quelldatei oder eines Namespaces, aber nicht innerhalb einer Klasse, einer Struktur, eines Moduls oder einer Schnittstelle  
  
-   *Modulebene* – innerhalb einer Klasse, einer Struktur, eines Moduls oder einer Schnittstelle, aber nicht innerhalb einer Prozedur oder eines Blocks  
  
-   *Prozedurebene* – innerhalb einer Prozedur oder eines Blocks \(z. B. `If` oder `For`\)  
  
 In der folgenden Tabelle werden die Standardzugriffsebenen für verschiedene deklarierte Programmierelemente je nach ihren Deklarationskontexten angezeigt.  
  
|Deklariertes Element|Namespaceebene|Modulebene|Prozedurebene|  
|--------------------------|--------------------|----------------|-------------------|  
|Variable \([Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)\)|Nicht zulässig|`Private` \(`Public` in `Structure`, nicht zulässig in `Interface`\)|`Public`|  
|Konstante \([Const Statement](../../../visual-basic/language-reference/statements/const-statement.md)\)|Nicht zulässig|`Private` \(`Public` in `Structure`, nicht zulässig in `Interface`\)|`Public`|  
|Enumeration \([Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md)\)|`Friend`|`Public`|Nicht zulässig|  
|Klasse \([Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)\)|`Friend`|`Public`|Nicht zulässig|  
|Struktur \([Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)\)|`Friend`|`Public`|Nicht zulässig|  
|Modul \([Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)\)|`Friend`|Nicht zulässig|Nicht zulässig|  
|Schnittstelle \([Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md)\)|`Friend`|`Public`|Nicht zulässig|  
|Prozedur \([Function Statement](../../../visual-basic/language-reference/statements/function-statement.md) oder [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)\)|Nicht zulässig|`Public`|Nicht zulässig|  
|Externer Verweis \([Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)\)|Nicht zulässig|`Public` \(nicht zulässig in `Interface`\)|Nicht zulässig|  
|Operator \([Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)\)|Nicht zulässig|`Public` \(nicht zulässig in `Interface` oder `Module`\)|Nicht zulässig|  
|Eigenschaft \([Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)\)|Nicht zulässig|`Public`|Nicht zulässig|  
|Standardeigenschaft \([Default](../../../visual-basic/language-reference/modifiers/default.md)\)|Nicht zulässig|`Public` \(nicht zulässig in `Module`\)|Nicht zulässig|  
|Ereignis \([Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)\)|Nicht zulässig|`Public`|Nicht zulässig|  
|Delegat \([Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md)\)|`Friend`|`Public`|Nicht zulässig|  
  
 Weitere Informationen finden Sie unter [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## Siehe auch  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Public](../../../visual-basic/language-reference/modifiers/public.md)