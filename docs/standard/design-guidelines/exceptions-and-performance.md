---
title: Ausnahmen und Leistung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9c2d7cfcb228c492d2adbe614d0ed88a3b02bb68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="exceptions-and-performance"></a>Ausnahmen und Leistung
Eine allgemeine Sorge, die im Zusammenhang mit Ausnahmen ist, dass Ausnahmen für Code verwendet werden, die routinemäßig fehlschlägt, die Leistung der Implementierung nicht akzeptabel ist. Dies ist eine gültige relevant. Wenn ein Element eine Ausnahme auslöst, kann die Leistung erheblich langsamer sein. Allerdings ist es möglich, die gute Leistung bei der Einhaltung streng an die Ausnahme, die mit Fehlercodes zu unterbinden, erzielen. Zwei Muster, die in diesem Abschnitt beschriebenen Möglichkeiten vorgeschlagen, dies zu tun.  
  
 **X nicht** Fehlercodes aufgrund von Bedenken, dass Ausnahmen die Leistung negativ beeinträchtigen können verwendet werden.  
  
 Um die Leistung zu verbessern, ist es möglich, verwenden Sie entweder die Tester-Ausführer oder Wiederholen Sie den Analyse-Muster, in den nächsten beiden Abschnitten beschrieben.  
  
## <a name="tester-doer-pattern"></a>Tester-Ausführer-Muster  
 Manchmal kann die Leistung eines Members eine Ausnahme auslösen kann durch das Element in zwei wichtige verbessert werden. Sehen wir uns die <xref:System.Collections.Generic.ICollection%601.Add%2A> Methode der <xref:System.Collections.Generic.ICollection%601> Schnittstelle.  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 Die Methode `Add` löst aus, wenn die Auflistung schreibgeschützt ist. Dies kann ein Leistungsproblem in Szenarien, in dem häufig ein Aufruf der Methode erwartet wird. Eine der Methoden, um das Problem zu lindern ist zu prüfen, ob die Auflistung schreibgeschützt ist, bevor Sie versuchen, einen Wert hinzufügen.  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 Das Element verwendet, um eine Bedingung zu testen, in unserem Beispiel die Eigenschaft ist `IsReadOnly`, wird als der Tester bezeichnet. Das Element verwendet, um eine potenziell auslösenden Vorgang die `Add` Methode in unserem Beispiel ist als der Ausführer bezeichnet.  
  
 **✓ GGF.** der Tester-Ausführer-Muster für Member, die Ausnahmen auslösen können Szenarien, um Leistungsprobleme zu vermeiden gemeinsam mit Ausnahmen verknüpft.  
  
## <a name="try-parse-pattern"></a>Wiederholen Sie den Analyse-Muster  
 Für extrem leistungsabhängigen-APIs sollte eine schnellere Muster als das Tester-Ausführer-Muster, die im vorherigen Abschnitt beschrieben verwendet werden. Das Muster Ruft für die Anpassung der Elementname, um einen klar definierten Test case-Teil der Member-Semantik zu machen. Beispielsweise <xref:System.DateTime> definiert eine <xref:System.DateTime.Parse%2A> Methode, die eine Ausnahme auslöst, wenn Analysieren einer Zeichenfolge ein Fehler auftritt. Er definiert außerdem eine entsprechende <xref:System.DateTime.TryParse%2A> -Methode, die versucht, zu analysieren, jedoch "false" zurückgegeben, wenn die Analyse nicht erfolgreich, und gibt das Ergebnis eines erfolgreichen Analyse mithilfe einer `out` Parameter.  
  
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
  
 Wenn Sie dieses Muster zu verwenden, ist es wichtig, die Funktionen der Try strict ausgedrückt definieren. Wenn das Element aus irgendeinem Grund klar definierten wiederholen Sie dann ein Fehler auftritt, muss das Element noch eine entsprechende Ausnahme auslösen.  
  
 **✓ GGF.** des Try-Analyse-Musters für Elemente, die Ausnahmen auslösen können Szenarien, um Leistungsprobleme zu vermeiden gemeinsam mit Ausnahmen verknüpft.  
  
 **Führen Sie ✓** verwenden Sie das Präfix "Try" und einen booleschen Wert Rückgabetyp für Methoden, die dieses Muster implementieren.  
  
 **Führen Sie ✓** stellen eine Ausnahme auslösen kann für jedes Element mit dem Try-Analyse-Muster.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Entwurfsrichtlinien für Ausnahmen](../../../docs/standard/design-guidelines/exceptions.md)
