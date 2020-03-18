---
title: Zugriffsebenen – C#-Referenz
ms.date: 12/06/2017
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
ms.openlocfilehash: 26fbc2a6d86aead537465c304146630f8bcd3ad4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713815"
---
# <a name="accessibility-levels-c-reference"></a>Zugriffsebenen (C#-Referenz)

Verwenden Sie die Zugriffsmodifizierer `public`, `protected`, `internal` oder `private`, um eine der folgenden deklarierten Zugriffsebenen für Member anzugeben.  
  
|Deklarierter Zugriff|Bedeutung|  
|----------------------------|-------------|  
|[`public`](public.md)|Der Zugriff ist nicht beschränkt.|  
|[`protected`](protected.md)|Der Zugriff ist auf die enthaltende Klasse oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.|  
|[`internal`](internal.md)|Der Zugriff ist auf die aktuelle Assembly beschränkt.|  
|[`protected internal`](protected-internal.md)|Der Zugriff ist auf die aktuelle Assembly oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.|  
|[`private`](private.md)|Der Zugriff ist auf die enthaltende Klasse beschränkt.|  
|[`private protected`](private-protected.md)|Der Zugriff ist auf die enthaltende Klasse oder auf Typen beschränkt, die von der enthaltenden Klasse innerhalb der aktuellen Assembly abgeleitet sind. Verfügbar seit C# 7.2. |  
  
 Es ist nur ein Zugriffsmodifizierer für einen Member oder Typ zulässig, außer wenn Sie die `protected internal`- oder `private protected`-Kombination verwenden.  
  
 Zugriffsmodifizierer sind bei Namespaces nicht zulässig. Namespaces haben uneingeschränkten Zugriff.  
  
 Abhängig vom Kontext einer Memberdeklaration sind nur bestimmte deklarierte Zugriffe zulässig. Wenn in einer Memberdeklaration kein Zugriffsmodifizierer angegeben ist, wird ein Standardzugriff verwendet.  
  
 Typen der obersten Ebene, die nicht in anderen Typen geschachtelt sind, können nur Zugriff der Art `internal` oder `public` haben. Der Standardzugriff für diese Typen ist `internal`.  
  
 Geschachtelte Typen, die Member von anderen Typen sind, können deklarierte Zugriffe haben, wie in der folgenden Tabelle angegeben.  
  
|Member von|Standard-Memberzugriff|Zulässiger deklarierter Zugriffstyp des Members|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|Keiner|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|Keiner|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 Der Zugriff auf einen geschachtelten Typ hängt von seiner [Zugriffsdomäne](./accessibility-domain.md) ab, die sowohl durch den deklarierten Zugriffstyp des Members als auch durch die Zugriffsdomäne des direkt enthaltenden Typs bestimmt wird. Die Zugriffsdomäne eines geschachtelten Typs kann jedoch nicht über die des enthaltenden Typs hinausgehen.  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](./index.md)
- [Zugriffsmodifizierer](./access-modifiers.md)
- [Zugriffsdomäne](./accessibility-domain.md)
- [Einschränkungen bei der Verwendung von Zugriffsebenen](./restrictions-on-using-accessibility-levels.md)
- [Zugriffsmodifizierer](../../programming-guide/classes-and-structs/access-modifiers.md)
- [public](./public.md)
- [private](./private.md)
- [protected](./protected.md)
- [internal](./internal.md)
