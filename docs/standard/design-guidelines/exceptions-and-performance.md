---
title: Ausnahmen und Leistung
ms.date: 10/22/2008
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
ms.openlocfilehash: 1d9e4ff3cfb02b1db358c19786322622621329fe
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821202"
---
# <a name="exceptions-and-performance"></a>Ausnahmen und Leistung
Ein häufiges Problem im Zusammenhang mit Ausnahmen besteht darin, dass die Leistung der Implementierung nicht akzeptabel ist, wenn Ausnahmen für Code verwendet werden, der routinemäßig fehlschlägt. Dieses Bedenken ist berechtigt. Wenn ein Member eine Ausnahme auslöst, kann die Leistung der Größenordnung langsamer sein. Es ist jedoch möglich, eine gute Leistung zu erzielen, während Sie strikt den Ausnahme Richtlinien entsprechen, die die Verwendung von Fehlercodes nicht zulassen. In den beiden in diesem Abschnitt beschriebenen Mustern werden Möglichkeiten vorgeschlagen.

 ❌ Fehlercodes sollten nicht verwendet werden, da sich Ausnahmen möglicherweise negativ auf die Leistung auswirken.

 Um die Leistung zu verbessern, können Sie entweder das Tester-Doer Muster oder das Try-Parse Muster verwenden, das in den folgenden beiden Abschnitten beschrieben wird.

## <a name="tester-doer-pattern"></a>Tester-Doer Muster
 Manchmal kann die Leistung eines Ausnahme auslösenden Members verbessert werden, indem der Member in zwei unterteilt wird. Sehen wir uns die- <xref:System.Collections.Generic.ICollection%601.Add%2A> Methode der- <xref:System.Collections.Generic.ICollection%601> Schnittstelle an.

```csharp
ICollection<int> numbers = ...
numbers.Add(1);
```

 Die-Methode wird ausgelöst, `Add` Wenn die-Auflistung schreibgeschützt ist. Dies kann ein Leistungsproblem in Szenarien sein, in denen der Methodenaufrufe häufig fehlschlägt. Eine Möglichkeit, das Problem zu beheben, besteht darin, zu testen, ob die Auflistung beschreibbar ist, bevor versucht wird, einen Wert hinzuzufügen.

```csharp
ICollection<int> numbers = ...
...
if (!numbers.IsReadOnly)
{
    numbers.Add(1);
}
```

 Der Member, der zum Testen einer Bedingung verwendet wird, die in unserem Beispiel die-Eigenschaft ist `IsReadOnly` , wird als Tester bezeichnet. Der Member, der verwendet wird, um einen potenziell auslösenden Vorgang auszuführen, die- `Add` Methode in unserem Beispiel, wird als doer bezeichnet.

 Beachten Sie ✔️ die Tester-Doer Muster für Member, die möglicherweise Ausnahmen in häufigen Szenarien auslösen, um Leistungsprobleme im Zusammenhang mit Ausnahmen zu vermeiden.

## <a name="try-parse-pattern"></a>Try-Parse Muster
 Bei extrem leistungsabhängigen APIs sollte ein noch schnelleres Muster verwendet werden, das nicht das im vorherigen Abschnitt beschriebene Tester-Doer Muster ist. Das Muster erfordert, dass der Elementname angepasst wird, um einen klar definierten Testfall zu einem Teil der Element Semantik zu machen. <xref:System.DateTime>Definiert z. b <xref:System.DateTime.Parse%2A> . eine Methode, die eine Ausnahme auslöst, wenn die Verarbeitung einer Zeichenfolge fehlschlägt. Außerdem wird eine entsprechende Methode definiert, <xref:System.DateTime.TryParse%2A> die versucht, eine Analyse durchzuführen, aber false zurückgibt, wenn die Analyse nicht erfolgreich ist und das Ergebnis einer erfolgreichen Analyse mithilfe eines- `out` Parameters zurückgibt.

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

 Beachten Sie ✔️ die Try-Parse Muster für Member, die möglicherweise Ausnahmen in häufigen Szenarien auslösen, um Leistungsprobleme im Zusammenhang mit Ausnahmen zu vermeiden.

 ✔️ Verwenden Sie das Präfix "Try" und den booleschen Rückgabetyp für Methoden, die dieses Muster implementieren.

 ✔️ einen auslösenden Member für jedes Element mithilfe des Try-Parse Musters bereitstellen.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Framework-Entwurfs Richtlinien](index.md)
- [Entwurfsrichtlinien für Ausnahmen](exceptions.md)
