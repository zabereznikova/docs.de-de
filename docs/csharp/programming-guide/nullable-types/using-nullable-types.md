---
title: Verwenden von auf NULL festlegbaren Typen (C# Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: d2fe0f34c45d3de0516a71ca5ed4dc807df4bf93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
 Jeder Werttyp kann als Grundlage für einen Typ, der NULL-Werte zulässt, verwendet werden. Zum Beispiel:  
  
 [!code-csharp[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]  
  
## <a name="the-members-of-nullable-types"></a>Member von Typen, die NULL-Werte zulassen  
 Jede Instanz eines Typs, der auf NULL festgelegt werden kann, hat zwei öffentliche schreibgeschützte Eigenschaften:  
  
-   `HasValue`  
  
     `HasValue` ist vom Typ `bool`. Es wird auf `true` festgelegt, wenn die Variable einen Wert enthält, der ungleich NULL ist.  
  
-   `Value`  
  
     `Value` hat denselben Typ wie der zugrunde liegende Typ. Wenn `HasValue` `true` ist, enthält `Value` einen sinnvollen Wert. Wenn `HasValue` auf `false` festgelegt ist, wird bei Zugriff auf `Value` eine <xref:System.InvalidOperationException> ausgelöst.  
  
 Der `HasValue`-Member in diesem Beispiel wird dazu verwendet, zu prüfen, ob eine Variable einen Wert enthält, bevor er diesen anzeigt.  
  
 [!code-csharp[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]  
  
 Das Prüfen auf einen Wert kann auch wie im folgenden Beispiel durchgeführt werden:  
  
 [!code-csharp[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]  
  
## <a name="explicit-conversions"></a>Explizite Konvertierungen  
 Ein Typ, der NULL-Werte zulässt, kann in einen gängigen Typ umgewandelt werden; dies können Sie entweder durch eine explizite Umwandlung oder mithilfe der `Value`-Eigenschaft erzielen. Zum Beispiel:  
  
 [!code-csharp[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]  
  
 Wenn eine benutzerdefinierte Konvertierung zwischen zwei Datentypen definiert ist, kann die gleiche Konvertierung auch mit der Version dieser Datentypen verwendet werden, die NULL-Werte zulassen.  
  
## <a name="implicit-conversions"></a>Implizite Konvertierungen  
 Eine Variable mit einem Typ, der NULL-Werte zulässt, kann wie in folgendem Beispiel mit dem Schlüsselwort `null` auf NULL festgelegt werden:  
  
 [!code-csharp[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]  
  
 Die Konvertierung von einem gängigen in einen auf NULL-festlegbaren Typ ist implizit.  
  
 [!code-csharp[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]  
  
## <a name="operators"></a>Operatoren  
 Die vordefinierten unären und binären Operatoren und alle benutzerdefinierten Operatoren für Werttypen können auch von auf NULL festlegbaren Typen verwende werden. Die Operatoren erzeugen einen NULL-Wert, wenn die Operanden NULL sind; andernfalls verwenden die Operatoren den enthaltenen Wert zur Berechnung eines Ergebnisses. Zum Beispiel:  
  
 [!code-csharp[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]  
  
 Wenn Sie Vergleiche mit auf NULL-festlegbaren Typen durchführen, ergeben alle Vergleiche `false`, nur `!=` nicht (ungleich), wenn der Wert von lediglich einem auf NULL festlegbaren Wert NULL ist. Es ist wichtig, dass Sie nicht davon ausgehen, dass der entgegengesetzte Fall `true` zurückgeben würde, nur wenn ein Vergleich `false` zurückgibt. Im folgenden Beispiel ist 10 weder größer noch kleiner noch gleich NULL. Nur `num1 != num2` ergibt `true`.  
  
 [!code-csharp[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]  
  
 Ein Gleichheitsvergleich zweier auf NULL festlegbarer Typen, die beide NULL sind, ergibt `true`.  
  
## <a name="the--operator"></a>Der ??- Operator  
 Der `??`-Operator definiert einen Standardwert, der zurückgegeben wird, wenn ein auf NULL festlegbarer Typ einem nicht auf NULL festlegbaren Typ zugewiesen wird.  
  
 [!code-csharp[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]  
  
 Dieser Operator kann auch mit mehreren auf NULL festlegbaren Typen verwendet werden. Zum Beispiel:  
  
 [!code-csharp[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]  
  
## <a name="the-bool-type"></a>Der „bool?“-Typ  
 Der `bool?`-Typ, der NULL-Werte zulässt, kann drei verschiedene Werte enthalten: [TRUE](../../../csharp/language-reference/keywords/true.md), [FALSE](../../../csharp/language-reference/keywords/false.md) und [NULL](../../../csharp/language-reference/keywords/null.md). Weitere Informationen zur Umwandlung von „bool?“ in „bool“ finden Sie unter [Vorgehensweise: Sichere Umwandlung von bool? in bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).  
  
 Boolesche Werte, die auf NULL festgelegt werden können, verhalten sich ähnlich wie der in SQL verwendete Boolesche Variablentyp. Folgende vordefinierte Operatoren stehen zur Verfügung, um sicherzustellen, dass die von den Operatoren `&` und `|` erzeugten Ergebnisse zu dem dreiwertigen Booleschen Typ in SQL passen:  
  
 `bool? operator &(bool? x, bool? y)`  
  
 `bool? operator |(bool? x, bool? y)`  
  
 Die Ergebnisse dieser Operatoren sind in der folgenden Tabelle aufgeführt:  
  
|X|u|x&y|x&#124;y|  
|-------|-------|---------|--------------|  
|true|true|true|true|  
|true|False|false|true|  
|true|NULL|NULL|true|  
|False|true|False|true|  
|False|False|False|False|  
|False|NULL|False|NULL|  
|NULL|true|NULL|true|  
|NULL|False|False|NULL|  
|NULL|NULL|NULL|NULL|  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Typen mit Nullwert](../../../csharp/programming-guide/nullable-types/index.md)  
 [Boxing von Typen mit Nullwerten](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
 [Auf NULL festlegbare Werttypen](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
