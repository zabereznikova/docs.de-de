---
title: "Verwenden von auf NULL festlegbaren Typen (C# Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
caps.latest.revision: 31
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
ms.openlocfilehash: 0721d9f60abc4e158135d6b050953b3e63ab8cb5
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="using-nullable-types-c-programming-guide"></a>Verwenden von auf NULL festlegbaren Typen (C# Programmierhandbuch)
Auf NULL festlegbare Typen können alle Werte eines zugrundeliegenden Typs und einen zusätzlichen [NULL](../../../csharp/language-reference/keywords/null.md)-Wert darstellen. Auf NULL festlegbare Typen können auf zwei verschiedene Arten deklariert werden:  
  
 `System.Nullable<T> variable`  
  
 - oder -   
  
 `T? variable`  
  
 `T` ist der zugrundeliegende Typ des Typs, der NULL-Werte zulässt. `T` kann jeder Werttyp, auch `struct`, sein; allerdings kann es kein Verweistyp sein.  
  
 Denken Sie z.B. an eine normalen Boolesche Variable, die zwei Werte aufweisen kann: TRUE und FALSE; so ähnlich verhält es sich auch mit dem Einsatz eines Typs, der NULL-Werte zulässt. Es gibt keinen Wert, der für „nicht definiert“ steht. In den meisten Programmierungsanwendungen – allen voran Datenbankinteraktionen – können Variablen in einem nicht definierten Zustand vorkommen. Ein Feld in einer Datenbank kann z.B. die Werte TRUE und FALSE enthalten; ebenso kann es aber auch gar keinen Wert enthalten. Ebenso können Verweistypen auf `null` festgelegt werden, um zu kennzeichnen, dass sie nicht initialisiert wurden.  
  
 Durch diese Ungleichheit kann weiteres Programmieren erforderlich sein: zusätzliche Variablen zum Speichern von Zustandsinformationen, der Einsatz von besonderen Werten usw. Mit dem Modifizierer für Typen, die NULL-Werte zulassen, kann C# value-type-Variablen erstellen, die einen nicht definierten Wert kennzeichnen.  
  
## <a name="examples-of-nullable-types"></a>Beispiele für Typen, die NULL-Werte zulassen  
 Jeder Werttyp kann als Grundlage für einen Typ, der NULL-Werte zulässt, verwendet werden. Beispiel:  
  
 [!code-cs[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]  
  
## <a name="the-members-of-nullable-types"></a>Member von Typen, die NULL-Werte zulassen  
 Jede Instanz eines Typs, der auf NULL festgelegt werden kann, hat zwei öffentliche schreibgeschützte Eigenschaften:  
  
-   `HasValue`  
  
     `HasValue` ist vom Typ `bool`. Es wird auf `true` festgelegt, wenn die Variable einen Wert enthält, der ungleich NULL ist.  
  
-   `Value`  
  
     `Value` hat denselben Typ wie der zugrunde liegende Typ. Wenn `HasValue` `true` ist, enthält `Value` einen sinnvollen Wert. Wenn `HasValue` auf `false` festgelegt ist, wird bei Zugriff auf `Value` eine <xref:System.InvalidOperationException> ausgelöst.  
  
 Der `HasValue`-Member in diesem Beispiel wird dazu verwendet, zu prüfen, ob eine Variable einen Wert enthält, bevor er diesen anzeigt.  
  
 [!code-cs[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]  
  
 Das Prüfen auf einen Wert kann auch wie im folgenden Beispiel durchgeführt werden:  
  
 [!code-cs[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]  
  
## <a name="explicit-conversions"></a>Explizite Konvertierungen  
 Ein Typ, der NULL-Werte zulässt, kann in einen gängigen Typ umgewandelt werden; dies können Sie entweder durch eine explizite Umwandlung oder mithilfe der `Value`-Eigenschaft erzielen. Beispiel:  
  
 [!code-cs[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]  
  
 Wenn eine benutzerdefinierte Konvertierung zwischen zwei Datentypen definiert ist, kann die gleiche Konvertierung auch mit der Version dieser Datentypen verwendet werden, die NULL-Werte zulassen.  
  
## <a name="implicit-conversions"></a>Implizite Konvertierungen  
 Eine Variable mit einem Typ, der NULL-Werte zulässt, kann wie in folgendem Beispiel mit dem Schlüsselwort `null` auf NULL festgelegt werden:  
  
 [!code-cs[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]  
  
 Die Konvertierung von einem gängigen in einen auf NULL-festlegbaren Typ ist implizit.  
  
 [!code-cs[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]  
  
## <a name="operators"></a>Operatoren  
 Die vordefinierten unären und binären Operatoren und alle benutzerdefinierten Operatoren für Werttypen können auch von auf NULL festlegbaren Typen verwende werden. Die Operatoren erzeugen einen NULL-Wert, wenn die Operanden NULL sind; andernfalls verwenden die Operatoren den enthaltenen Wert zur Berechnung eines Ergebnisses. Zum Beispiel:  
  
 [!code-cs[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]  
  
 Wenn Sie Vergleiche mit auf NULL-festlegbaren Typen durchführen, ergeben alle Vergleiche `false`, nur `!=` nicht (ungleich), wenn der Wert von lediglich einem auf NULL festlegbaren Wert NULL ist. Es ist wichtig, dass Sie nicht davon ausgehen, dass der entgegengesetzte Fall `true` zurückgeben würde, nur wenn ein Vergleich `false` zurückgibt. Im folgenden Beispiel ist 10 weder größer noch kleiner noch gleich NULL. Nur `num1 != num2` ergibt `true`.  
  
 [!code-cs[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]  
  
 Ein Gleichheitsvergleich zweier auf NULL festlegbarer Typen, die beide NULL sind, ergibt `true`.  
  
## <a name="the--operator"></a>Der ??- Operator  
 Der `??`-Operator definiert einen Standardwert, der zurückgegeben wird, wenn ein auf NULL festlegbarer Typ einem nicht auf NULL festlegbaren Typ zugewiesen wird.  
  
 [!code-cs[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]  
  
 Dieser Operator kann auch mit mehreren auf NULL festlegbaren Typen verwendet werden. Zum Beispiel:  
  
 [!code-cs[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]  
  
## <a name="the-bool-type"></a>Der „bool?“-Typ  
 Der `bool?`-Typ, der NULL-Werte zulässt, kann drei verschiedene Werte enthalten: [TRUE](../../../csharp/language-reference/keywords/true.md), [FALSE](../../../csharp/language-reference/keywords/false.md) und [NULL](../../../csharp/language-reference/keywords/null.md). Weitere Informationen zur Umwandlung von „bool?“ in „bool“ finden Sie unter [Vorgehensweise: Sichere Umwandlung von bool? in bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).  
  
 Boolesche Werte, die auf NULL festgelegt werden können, verhalten sich ähnlich wie der in SQL verwendete Boolesche Variablentyp. Folgende vordefinierte Operatoren stehen zur Verfügung, um sicherzustellen, dass die von den Operatoren `&` und `|` erzeugten Ergebnisse zu dem dreiwertigen Booleschen Typ in SQL passen:  
  
 `bool? operator &(bool? x, bool? y)`  
  
 `bool? operator |(bool? x, bool? y)`  
  
 Die Ergebnisse dieser Operatoren sind in der folgenden Tabelle aufgeführt:  
  
|X|u|x&y|x&#124;y|  
|-------|-------|---------|--------------|  
|true|true|true|true|  
|true|false|false|true|  
|true|NULL|NULL|true|  
|false|true|false|true|  
|false|false|false|false|  
|false|NULL|false|NULL|  
|NULL|true|NULL|true|  
|NULL|false|false|NULL|  
|NULL|NULL|NULL|NULL|  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Typen, die NULL-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md)   
 [Boxing von Typen mit NULL-Werten](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)   
 [Auf NULL festlegbare Werttypen](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)

