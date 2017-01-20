---
title: "&#39;Extension&#39; attribute can be applied only to &#39;Module&#39;, &#39;Sub&#39;, or &#39;Function&#39; declarations | Microsoft Docs"
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
  - "bc36550"
  - "vbc36550"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36550"
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Extension&#39; attribute can be applied only to &#39;Module&#39;, &#39;Sub&#39;, or &#39;Function&#39; declarations
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Die einzige Möglichkeit, Datentypen in Visual Basic zu erweitern, ist die Definition einer Erweiterungsmethode innerhalb eines Standardmoduls.  Die Erweiterungsmethode kann eine `Sub`\-Prozedur oder eine `Function`\-Prozedur sein.  Alle Erweiterungsmethoden müssen mit dem Extension\-Attribut `<Extension()>` aus dem <xref:System.Runtime.CompilerServices?displayProperty=fullName>\-Namespace markiert werden.  Optional kann ein Modul, das eine Erweiterungsmethode enthält, auf die gleiche Weise markiert werden.  Eine andere Verwendung des Extension\-Attributs ist nicht gültig.  
  
 **Fehler\-ID:** BC36550  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie das Extension\-Attribut.  
  
-   Entwerfen Sie die Erweiterung als Methode, die in einem einschließenden Modul definiert ist.  
  
## Beispiel  
 Im folgenden Beispiel wird eine `Print`\-Methode für den `String`\-Datentyp definiert.  
  
```  
Imports StringUtility  
Imports System.Runtime.CompilerServices  
Namespace StringUtility  
    <Extension()>   
    Module StringExtensions  
        <Extension()>   
        Public Sub Print (ByVal str As String)  
            Console.WriteLine(str)  
        End Sub  
    End Module  
End Namespace  
  
```  
  
## Siehe auch  
 [Attribute](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)   
 [Erweiterungsmethoden](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)   
 [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)