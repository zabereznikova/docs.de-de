---
title: "Ausnahmen und Leistung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Tester-Ausführer-Muster"
  - "TryParse-Muster"
  - "Auslösen von Ausnahmen"
  - "Ausnahmen und Leistung"
  - "Auslösen von Ausnahmen, Leistung"
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Ausnahmen und Leistung
Ein häufig auftretendes Problem darstellt aufgrund von Ausnahmen ist, dass Ausnahmen für Code verwendet, der routinemäßig fehlschlägt, die Leistung der Implementierung nicht akzeptabel ist. Dies ist ein berechtigter Einwand. Wenn ein Element eine Ausnahme auslöst, kann die Leistung erheblich langsamer sein. Allerdings ist es möglich, gute Leistung genau befolgen Sie die Ausnahme\-Richtlinien, die nicht die Verwendung von Fehlercodes zulassen. Zwei Muster, die in diesem Abschnitt beschriebenen vorschlagen Methoden zur Verfügung.  
  
 **X nicht** mithilfe des Fehlercodes aufgrund von Bedenken, dass Ausnahmen Leistung beeinträchtigen.  
  
 Zur Verbesserung der Leistung ist es möglich, die Tester\-Ausführer\-Muster oder dem Try\-Analyse\-Muster in den nächsten beiden Abschnitten beschrieben.  
  
## Tester\-Ausführer\-Muster  
 Manchmal kann die Leistung eines Members eine Ausnahme auslösen durch das Mitglied in zwei wichtige verbessert werden. Sehen wir uns die <xref:System.Collections.Generic.ICollection%601.Add%2A> Methode der <xref:System.Collections.Generic.ICollection%601> Schnittstelle.  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 Die Methode `Add` wird ausgelöst, wenn die Auflistung schreibgeschützt ist. Dies kann ein Leistungsproblem in Szenarien, in dem Aufruf der Methode schlagen häufig fehl, erwartet wird. Eine der Methoden, um das Problem zu beheben ist zu prüfen, ob die Auflistung schreibgeschützt ist, bevor Sie versuchen, einen Wert hinzufügen.  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 Das Element, das zum Testen einer Bedingung, die in diesem Beispiel die Eigenschaft wird `IsReadOnly`, als der Tester bezeichnet wird. Das Element verwendet, um eine potenziell auslösenden Operation ausführen, die `Add` \-Methode in unserem Beispiel ist als der Ausführer bezeichnet.  
  
 **✓ ggf.** der Tester\-Ausführer\-Muster für Member, die Ausnahmen auslösen kann in gängigen Szenarien, um Leistungsprobleme zu vermeiden bezüglich Ausnahmen.  
  
## Try\-Analyse\-Muster  
 Für äußerst leistungsrelevanten APIs sollte ein noch schneller Muster wie das im vorherigen Abschnitt beschriebenen Tester\-Ausführer\-Muster verwendet werden. Das Muster Ruft für die Anpassung der Membername stellen einen klar definierten Test case\-Teil der Member\-Semantik. Z. B. <xref:System.DateTime> definiert eine <xref:System.DateTime.Parse%2A> Methode, die eine Ausnahme auslöst, wenn Analysieren einer Zeichenfolge ein Fehler auftritt. Es definiert auch eine entsprechende <xref:System.DateTime.TryParse%2A> \-Methode, die versucht, zu analysieren, gibt jedoch false zurück, wenn die Analyse fehl und gibt das Ergebnis einer erfolgreichen Analyse mit einer `out` Parameter.  
  
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
  
 Wenn Sie dieses Muster verwenden, ist es wichtig, die Try\-Funktionalität in strenge Begriffe zu definieren. Wenn das Element aus irgendeinem Grund klar definierten Try fehlschlägt, darf das Element immer noch eine entsprechende Ausnahme auslösen.  
  
 **✓ ggf.** dem Try\-Analyse\-Muster für Member, die Ausnahmen auslösen kann in gängigen Szenarien, um Leistungsprobleme zu vermeiden bezüglich Ausnahmen.  
  
 **✓ führen** verwenden Sie das Präfix "Try" und einen booleschen Wert Rückgabetyp für Methoden, die dieses Muster implementieren.  
  
 **✓ führen** stellen eine Ausnahme auslösen für jedes Element mit dem Try\-Analyse\-Muster.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Entwurfsrichtlinien für Ausnahmen](../../../docs/standard/design-guidelines/exceptions.md)