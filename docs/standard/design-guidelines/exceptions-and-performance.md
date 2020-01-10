---
title: Ausnahmen und Leistung
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
ms.openlocfilehash: e3a7fa0f284ebf028a18cae37c050d7ceda9bb79
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709386"
---
# <a name="exceptions-and-performance"></a>Ausnahmen und Leistung
Ein häufiges Problem im Zusammenhang mit Ausnahmen besteht darin, dass die Leistung der Implementierung nicht akzeptabel ist, wenn Ausnahmen für Code verwendet werden, der routinemäßig fehlschlägt. Dies ist ein gültiges Problem. Wenn ein Member eine Ausnahme auslöst, kann die Leistung der Größenordnung langsamer sein. Es ist jedoch möglich, eine gute Leistung zu erzielen, während Sie strikt den Ausnahme Richtlinien entsprechen, die die Verwendung von Fehlercodes nicht zulassen. In den beiden in diesem Abschnitt beschriebenen Mustern werden Möglichkeiten vorgeschlagen.

 **X DO NOT** Fehlercodes aufgrund von Bedenken, dass Ausnahmen die Leistung negativ beeinträchtigen können verwendet werden.

 Um die Leistung zu verbessern, können Sie entweder das Tester-doer-Muster oder das Try-Analyse-Muster verwenden, das in den folgenden beiden Abschnitten beschrieben wird.

## <a name="tester-doer-pattern"></a>Tester-doer-Muster
 Manchmal kann die Leistung eines Ausnahme auslösenden Members verbessert werden, indem der Member in zwei unterteilt wird. Sehen wir uns die <xref:System.Collections.Generic.ICollection%601.Add%2A>-Methode der <xref:System.Collections.Generic.ICollection%601> Schnittstelle an.

```csharp
ICollection<int> numbers = ...
numbers.Add(1);
```

 Die-Methode `Add` ausgelöst, wenn die-Auflistung schreibgeschützt ist. Dies kann ein Leistungsproblem in Szenarien sein, in denen der Methodenaufrufe häufig fehlschlägt. Eine Möglichkeit, das Problem zu beheben, besteht darin, zu testen, ob die Auflistung beschreibbar ist, bevor versucht wird, einen Wert hinzuzufügen.

```csharp
ICollection<int> numbers = ...
...
if (!numbers.IsReadOnly)
{
    numbers.Add(1);
}
```

 Der zum Testen einer Bedingung verwendete Member, bei dem es sich in unserem Beispiel um die Eigenschaften `IsReadOnly`handelt, wird als Tester bezeichnet. Der Member, der verwendet wird, um einen potenziell auslösenden Vorgang auszuführen, die `Add`-Methode in unserem Beispiel, wird als doer bezeichnet.

 **✓ CONSIDER** der Tester-Ausführer-Muster für Member, die Ausnahmen auslösen können Szenarien, um Leistungsprobleme zu vermeiden gemeinsam mit Ausnahmen verknüpft.

## <a name="try-parse-pattern"></a>Try-Analyse Muster
 Bei extrem leistungsabhängigen APIs sollte ein noch schnelleres Muster verwendet werden, das nicht das im vorherigen Abschnitt beschriebene Tester-doer-Muster ist. Das Muster erfordert, dass der Elementname angepasst wird, um einen klar definierten Testfall zu einem Teil der Element Semantik zu machen. Beispielsweise definiert <xref:System.DateTime> eine <xref:System.DateTime.Parse%2A> Methode, die eine Ausnahme auslöst, wenn die Verarbeitung einer Zeichenfolge fehlschlägt. Außerdem wird eine entsprechende <xref:System.DateTime.TryParse%2A> Methode definiert, die versucht, eine Analyse durchzuführen, aber false zurückgibt, wenn die Analyse nicht erfolgreich ist und das Ergebnis einer erfolgreichen Analyse mithilfe eines `out`-Parameters zurückgibt.

```csharp
public struct DateTime
{
    public static DateTime Parse(string dateTime)
    {
        ...
    }
    public static bool TryParse(string dateTime, out DateTime result)
    {
        ...
    }
}
```

 Wenn Sie dieses Muster verwenden, ist es wichtig, die try-Funktionalität in Strict-Begriffen zu definieren. Wenn der Member aus einem anderen Grund als dem klar definierten Versuch ausfällt, muss der Member weiterhin eine entsprechende Ausnahme auslösen.

 **✓ CONSIDER** des Try-Analyse-Musters für Elemente, die Ausnahmen auslösen können Szenarien, um Leistungsprobleme zu vermeiden gemeinsam mit Ausnahmen verknüpft.

 **✓ DO** verwenden Sie das Präfix "Try" und einen booleschen Wert Rückgabetyp für Methoden, die dieses Muster implementieren.

 **✓ DO** stellen eine Ausnahme auslösen kann für jedes Element mit dem Try-Analyse-Muster.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Entwurfsrichtlinien für Ausnahmen](../../../docs/standard/design-guidelines/exceptions.md)
