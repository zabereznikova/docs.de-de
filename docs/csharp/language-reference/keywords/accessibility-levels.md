---
title: "Zugriffsebenen (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Zugriffsmodifizierer [C#], Zugriffsebenen"
  - "Zugriffsebenen"
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# Zugriffsebenen (C#-Referenz)
Mit den Zugriffsmodifizierern [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) oder [private](../../../csharp/language-reference/keywords/private.md) kann einer der folgenden deklarierten Zugriffsebenen für Member angegeben werden.  
  
|Deklarierter Zugriff|Bedeutung|  
|--------------------------|---------------|  
|`public`|Der Zugriff ist nicht eingeschränkt.|  
|`protected`|Der Zugriff ist auf die enthaltende Klasse oder die von der enthaltenden Klasse abgeleiteten Typen begrenzt.|  
|`internal`|Der Zugriff ist auf die aktuelle Assembly begrenzt.|  
|`protected` `internal`|Der Zugriff ist auf die aktuelle Assembly oder die von der enthaltenden Klasse abgeleiteten Typen begrenzt.|  
|`private`|Der Zugriff ist auf den enthaltenden Typ begrenzt.|  
  
 Für einen Member oder einen Typ ist nur ein Zugriffsmodifizierer zulässig, außer bei Verwendung der `protected`\-`internal`\-Kombination.  
  
 Zugriffsmodifizierer sind für Namespaces nicht zulässig.  Namespaces weisen keine Zugriffsbeschränkungen auf.  
  
 Abhängig vom Kontext einer Memberdeklaration sind nur bestimmte deklarierte Zugriffe zulässig.  Wenn in einer Memberdeklaration kein Zugriffsmodifizierer angegeben ist, wird ein Standardzugriff verwendet.  
  
 Typen der obersten Ebene, die nicht in anderen Typen geschachtelt sind, können lediglich über `internal`\-Zugriff oder `public`\-Zugriff verfügen.  Der Standardzugriff auf diese Typen ist `internal`.  
  
 Geschachtelte Typen, die Member anderer Typen darstellen, können über deklarierte Zugriffe verfügen, wie in der nachstehenden Tabelle angegeben:  
  
|Member von|Standardmemberzugriff|Zulässiger deklarierter Memberzugriff|  
|----------------|---------------------------|-------------------------------------------|  
|`enum`|`public`|None|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected` `internal`|  
|`interface`|`public`|None|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 Der Zugriff eines geschachtelten Typs hängt von seiner [Zugriffsdomäne](../../../csharp/language-reference/keywords/accessibility-domain.md) ab, die sowohl durch den deklarierten Zugriff des Members als auch durch die Zugriffsdomäne des unmittelbar enthaltenden Typs bestimmt wird.  Die Zugriffsdomäne eines geschachtelten Typs kann jedoch nicht über die des enthaltenden Typs hinausgehen.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Zugriffsdomäne](../../../csharp/language-reference/keywords/accessibility-domain.md)   
 [Einschränkungen bei der Verwendung von Zugriffsebenen](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)   
 [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [Private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [interne](../../../csharp/language-reference/keywords/internal.md)