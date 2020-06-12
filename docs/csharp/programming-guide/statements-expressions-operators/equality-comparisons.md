---
title: Übereinstimmungsvergleiche – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- object equality [C#]
ms.assetid: 10b865ea-4e7b-4127-9242-c9b8f57d9f04
ms.openlocfilehash: 46d6881955252b21de6a92e25d65d1f76c8ec06c
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241915"
---
# <a name="equality-comparisons-c-programming-guide"></a>Übereinstimmungsvergleiche (C#-Programmierhandbuch)

Unter bestimmten Umständen ist es erforderlich, die Gleichheit zweier Werte zu prüfen. In einigen Fällen prüfen Sie die *Wertgleichheit*, die auch als *Äquivalenz* bezeichnet wird. Das bedeutet, Sie prüfen, ob die in zwei Variablen enthaltenen Werte gleich sind. In anderen Fällen müssen Sie ermitteln, ob zwei Variablen auf das gleiche zugrunde liegende Objekt im Arbeitsspeicher verweisen. Diese Art von Gleichheit wird als *Verweisgleichheit* oder *Identität* bezeichnet. In diesem Thema werden diese zwei Arten der Gleichheit beschrieben. Außerdem finden Sie hier Links zu verwandten Themen mit weiteren Informationen.  
  
## <a name="reference-equality"></a>Verweisgleichheit

 Verweisgleichheit ist gegeben, wenn zwei Objektverweise auf dasselbe zugrunde liegende Objekt verweisen. Die Ursache hierfür kann eine einfache Zuweisung sein, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[csProgGuideStatements#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#18)]  
  
 In diesem Code werden zwei Objekte erstellt, nach der Zuweisungsanweisung verweisen jedoch beide Verweise auf das gleiche Objekt. Es liegt eine Verweisgleichheit vor. Verwenden Sie die <xref:System.Object.ReferenceEquals%2A>-Methode, um zu ermitteln, ob zwei Verweise auf das gleiche Objekt verweisen.  
  
Das Konzept der Verweisgleichheit gilt nur für Verweistypen. Bei Werttypobjekten kann keine Verweisgleichheit vorliegen, da bei Zuweisung einer Werttypinstanz zu einer Variablen eine Kopie des Werts erstellt wird. Aus diesem Grund ist es unmöglich, dass zwei nicht geschachtelte Strukturen vorhanden sind, die auf die gleiche Position im Arbeitsspeicher verweisen. Wenn Sie zwei Werttypen mit der <xref:System.Object.ReferenceEquals%2A>-Methode vergleichen, ist das Ergebnis immer `false`, selbst wenn die in den Objekten enthaltenen Werte alle identisch sind. Der Grund hierfür ist, dass jede Variable in einer eigenen Objektinstanz geschachtelt ist. Weitere Informationen finden Sie unter [Vorgehensweise: Überprüfen auf Verweisgleichheit (Identität)](./how-to-test-for-reference-equality-identity.md).

## <a name="value-equality"></a>Wertgleichheit

 Eine Wertgleichheit liegt dann vor, wenn zwei Objekte den gleichen Wert bzw. die gleichen Werte enthalten. Die Prüfung auf Wertgleichheit für primitive Werttypen wie [int](../../language-reference/builtin-types/integral-numeric-types.md) oder [bool](../../language-reference/builtin-types/bool.md) ist einfach. Sie können den [==](../../language-reference/operators/equality-operators.md#equality-operator-)-Operator verwenden, wie im folgenden Beispiel gezeigt.  
  
```csharp  
int a = GetOriginalValue();  
int b = GetCurrentValue();  
  
// Test for value equality.
if (b == a)
{  
    // The two integers are equal.  
}  
```  
  
 Für die meisten anderen Typen ist die Prüfung auf Wertgleichheit komplexer, da es darauf ankommt, wie die Wertgleichheit für den jeweiligen Typ definiert wird. Für Klassen und Strukturen mit mehreren Feldern oder Eigenschaften wird Wertgleichheit oft so definiert, dass alle Felder oder Eigenschaften den gleichen Wert aufweisen. Zwei `Point`-Objekte werden z. B. als äquivalent definiert, wenn pointA.X gleich pointB.X und pointA.Y gleich pointB.Y ist.  
  
Die Äquivalenz muss jedoch nicht unbedingt auf allen Feldern in einem Typ basieren. Die Basis kann auch eine Teilmenge sein. Wenn Sie Typen von einem anderen Besitzer vergleichen, vergewissern Sie sich, wie die Gleichheit für den jeweiligen Typ definiert ist. Informationen zum Definieren von Wertgleichheit für Ihre eigenen Klassen und Strukturen finden Sie unter [Vorgehensweise: Definieren von Wertgleichheit für einen Typ](./how-to-define-value-equality-for-a-type.md).
  
### <a name="value-equality-for-floating-point-values"></a>Wertgleichheit für Gleitkommawerte

 Übereinstimmungsvergleiche für Gleitkommawerte ([double](../../language-reference/builtin-types/floating-point-numeric-types.md) und [float](../../language-reference/builtin-types/floating-point-numeric-types.md)) sind aufgrund der Ungenauigkeit der Gleitkommaarithmetik auf Computern mit Binärlogik problematisch. Weitere Informationen finden Sie in den Hinweisen im Thema <xref:System.Double?displayProperty=nameWithType>.  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Vorgehensweise: Überprüfen auf Verweisgleichheit (Identität)](./how-to-test-for-reference-equality-identity.md)|Beschreibt, wie zwei Variablen auf Verweisgleichheit geprüft werden.|  
|[Vorgehensweise: Definieren von Wertgleichheit für einen Typ](./how-to-define-value-equality-for-a-type.md)|Beschreibt, wie eine benutzerdefinierte Definition der Wertgleichheit für einen Typ erstellt wird.|  
|[C#-Programmierhandbuch](../index.md)|Links zu ausführlichen Informationen zu wichtigen Features der C#-Sprache sowie zu Features, die über .NET für C# verfügbar sind.|  
|[Typen](../types/index.md)|Informationen zum C#-Typsystem und Links zu weiteren Informationen.|  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
