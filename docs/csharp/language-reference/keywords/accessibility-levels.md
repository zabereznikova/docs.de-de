---
title: Zugriffsebenen (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 796802a407c486c1df5332d5b4920467f3a1171b
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="accessibility-levels-c-reference"></a>Zugriffsebenen (C#-Referenz)
Verwenden Sie die Zugriffsmodifizierer [öffentlich](../../../csharp/language-reference/keywords/public.md), [geschützt](../../../csharp/language-reference/keywords/protected.md), [intern](../../../csharp/language-reference/keywords/internal.md) oder [privat](../../../csharp/language-reference/keywords/private.md), um eine der folgenden deklarierten Zugriffsebenen für Member anzugeben.  
  
|Deklarierter Zugriff|Bedeutung|  
|----------------------------|-------------|  
|`public`|Der Zugriff ist nicht beschränkt.|  
|`protected`|Der Zugriff ist auf die enthaltende Klasse oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.|  
|`internal`|Der Zugriff ist auf die aktuelle Assembly beschränkt.|  
|`protected internal`|Der Zugriff ist auf die aktuelle Assembly oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.|  
|`private`|Der Zugriff ist auf die enthaltende Klasse beschränkt.|  
  
 Es ist nur ein Zugriffsmodifizierer für einen Member oder Typ zulässig, außer wenn Sie die `protected internal`-Kombination verwenden.  
  
 Zugriffsmodifizierer sind bei Namespaces nicht zulässig. Namespaces haben uneingeschränkten Zugriff.  
  
 Abhängig vom Kontext einer Memberdeklaration sind nur bestimmte deklarierte Zugriffe zulässig. Wenn in einer Memberdeklaration kein Zugriffsmodifizierer angegeben ist, wird ein Standardzugriff verwendet.  
  
 Typen der obersten Ebene, die nicht in anderen Typen geschachtelt sind, können nur Zugriff der Art `internal` oder `public` haben. Der Standardzugriff für diese Typen ist `internal`.  
  
 Geschachtelte Typen, die Member von anderen Typen sind, können deklarierte Zugriffe haben, wie in der folgenden Tabelle angegeben.  
  
|Member von|Standard-Memberzugriff|Zulässiger deklarierter Zugriffstyp des Members|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|Keine|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal`|  
|`interface`|`public`|Keine|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 Der Zugriff auf einen geschachtelten Typ hängt von seiner [Zugriffsdomäne](../../../csharp/language-reference/keywords/accessibility-domain.md) ab, die sowohl durch den deklarierten Zugriffstyp des Members als auch durch die Zugriffsdomäne des direkt enthaltenden Typs bestimmt wird. Die Zugriffsdomäne eines geschachtelten Typs kann jedoch nicht über die des enthaltenden Typs hinausgehen.  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Access Modifiers (Zugriffsmodifizierer)](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Zugriffsdomäne](../../../csharp/language-reference/keywords/accessibility-domain.md)   
 [Einschränkungen bei der Verwendung von Zugriffsebenen](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)   
 [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)

