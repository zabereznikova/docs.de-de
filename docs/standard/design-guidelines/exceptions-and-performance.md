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
author: KrzysztofCwalina
ms.openlocfilehash: f9fe3045d8bd8b4d625c5cd49bc18574ebb740de
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54707725"
---
# <a name="exceptions-and-performance"></a>Ausnahmen und Leistung
Eine häufige Problem im Zusammenhang mit Ausnahmen ist, wenn Ausnahmen für Code, die routinemäßig ein Fehler auftritt verwendet werden, die Leistung der Implementierung nicht akzeptabel sein wird. Dies ist ein Grund zur Sorge. Wenn ein Element eine Ausnahme auslöst, kann die Leistung erheblich langsamer sein. Allerdings ist es möglich, erzielen gute Leistung bei strikt befolgen Sie die Ausnahme-Richtlinien, die nicht zulassen, mit Fehlercodes. Zwei Muster, die in diesem Abschnitt beschriebenen Möglichkeiten vorgeschlagen, dies zu tun.  
  
 **X DO NOT** Fehlercodes aufgrund von Bedenken, dass Ausnahmen die Leistung negativ beeinträchtigen können verwendet werden.  
  
 Zur Verbesserung der Leistung ist es möglich, verwenden entweder die Tester-Doer-Muster oder dem Versuch der Analyse Muster in den nächsten beiden Abschnitten beschrieben.  
  
## <a name="tester-doer-pattern"></a>Tester-Doer-Muster  
 Leistung der ein Element eine Ausnahme auslösen kann manchmal verbessert werden, von der Members in zwei wichtige. Sehen wir uns die <xref:System.Collections.Generic.ICollection%601.Add%2A> Methode der <xref:System.Collections.Generic.ICollection%601> Schnittstelle.  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 Die Methode `Add` wird ausgelöst, wenn die Auflistung schreibgeschützt ist. Dies kann ein Leistungsproblem in Szenarien sein, die dem Aufruf der Methode erwartet wird, häufig fehlschlägt. Eine der Möglichkeiten, um das Problem zu lindern ist zum Überprüfen, ob die Auflistung schreibgeschützt ist, bevor Sie versuchen, einen Wert hinzufügen.  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 Der Member, die mit dem Testen einer Bedingung, die in unserem Beispiel die Eigenschaft ist `IsReadOnly`, wird als der Tester bezeichnet. Das Element verwendet, um eine ggf. auslösenden Operation ausführen, die `Add` -Methode in unserem Beispiel ist als die Doer bezeichnet.  
  
 **✓ CONSIDER** der Tester-Ausführer-Muster für Member, die Ausnahmen auslösen können Szenarien, um Leistungsprobleme zu vermeiden gemeinsam mit Ausnahmen verknüpft.  
  
## <a name="try-parse-pattern"></a>Try-Analysemuster  
 Für äußerst leistungsabhängigen-APIs sollte eine Muster für die sogar noch schnellere als das Tester-Doer-Muster, das im vorherigen Abschnitt beschrieben verwendet werden. Das Muster Ruft für die Anpassung der Membername, um eine klar definierte Test case-Teil von der Members-Semantik zu machen. Z. B. <xref:System.DateTime> definiert eine <xref:System.DateTime.Parse%2A> -Methode, die eine Ausnahme auslöst, wenn ein Fehler mit der Analyse einer Zeichenfolge auftritt. Sie definiert außerdem eine entsprechende <xref:System.DateTime.TryParse%2A> -Methode, die versucht, zu analysieren, gibt aber "false" zurück, wenn die Analyse nicht erfolgreich ist, und gibt das Ergebnis eines erfolgreichen Analyse mit einer `out` Parameter.  
  
```  
public struct DateTime {  
    public static DateTime Parse(string dateTime){   
        ...   
    }  
    public static bool TryParse(string dateTime, out DateTime result){  
        ...  
    }  
}  
```  
  
 Wenn Sie dieses Muster verwenden, ist es wichtig, die die Funktionalität versuchen Sie es im strict-Bedingungen zu definieren. Wenn das Element einem anderen Grund als der klar definierte Versuch fehlschlägt, muss das Element immer noch eine entsprechende Ausnahme auslösen.  
  
 **✓ CONSIDER** des Try-Analyse-Musters für Elemente, die Ausnahmen auslösen können Szenarien, um Leistungsprobleme zu vermeiden gemeinsam mit Ausnahmen verknüpft.  
  
 **✓ DO** verwenden Sie das Präfix "Try" und einen booleschen Wert Rückgabetyp für Methoden, die dieses Muster implementieren.  
  
 **✓ DO** stellen eine Ausnahme auslösen kann für jedes Element mit dem Try-Analyse-Muster.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Entwurfsrichtlinien für Ausnahmen](../../../docs/standard/design-guidelines/exceptions.md)
