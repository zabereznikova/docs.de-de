---
title: "&#39;&lt;typename&gt;&#39; cannot inherit from &lt;type&gt; &#39;&lt;basetypename&gt;&#39; because it expands the access of the base &lt;type&gt; outside the assembly | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30910"
  - "bc30910"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30910"
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# &#39;&lt;typename&gt;&#39; cannot inherit from &lt;type&gt; &#39;&lt;basetypename&gt;&#39; because it expands the access of the base &lt;type&gt; outside the assembly
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Eine Klasse oder Schnittstelle erbt von einer Basisklasse bzw. Schnittstelle, verfügt jedoch über eine weniger restriktive Zugriffsebene.  
  
 Eine `Public`\-Schnittstelle erbt beispielsweise von einer `Friend`\-Schnittstelle, oder eine `Protected`\-Klasse erbt von einer `Private`\-Klasse.  Hierdurch wird die Basisklasse bzw. Basisschnittstelle für den Zugriff außerhalb der vorgesehenen Ebene verfügbar.  
  
 **Fehler\-ID:** BC30910  
  
### So beheben Sie diesen Fehler  
  
-   Ändern Sie die Zugriffsebene der abgeleiteten Klasse bzw. Schnittstelle in eine Zugriffsebene, die mindestens so restriktiv wie die Zugriffsebene der Basisklasse bzw. Basisschnittstelle ist.  
  
     \- oder \-  
  
-   Wenn Sie die weniger restriktive Zugriffsebene benötigen, entfernen Sie die `Inherits`\-Anweisung.  Eine restriktivere Basisklasse oder Schnittstelle kann nicht geerbt werden.  
  
## Siehe auch  
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)