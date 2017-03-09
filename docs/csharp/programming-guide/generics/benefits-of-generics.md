---
title: "Vorteile von Generika (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Generika [C#], Vorteile"
ms.assetid: 80f037cd-9ea7-48be-bfc1-219bfb2d4277
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# Vorteile von Generika (C#-Programmierhandbuch)
Generika bieten die Lösung für eine Einschränkung in früheren Versionen der Common Language Runtime \(CLR\) und von C\#: Durch Umwandlung von Typen in den bzw. aus dem universellen Basistyp <xref:System.Object> wird Verallgemeinerung erreicht.  Indem Sie eine generische Klasse erstellen, können Sie eine Auflistung erstellen, die zur Kompilierzeit typsicher ist.  
  
 Die Grenzen der Verwendung nicht generischer Auflistungsklassen werden durch ein kurzes Programm verdeutlicht, in dem die <xref:System.Collections.ArrayList>\-Auflistungsklasse aus der .NET Framework\-Klassenbibliothek verwendet wird.  <xref:System.Collections.ArrayList> ist eine äußerst praktische Auflistungsklasse, die unverändert verwendet werden kann, um beliebige Verweis\- und Werttypen zu speichern.  
  
 [!code-cs[csProgGuideGenerics#4](../../../csharp/programming-guide/generics/codesnippet/csharp/benefits-of-generics_1.cs)]  
  
 Aber dieser Komfort hat seinen Preis.  Jeder Verweis\- oder Werttyp, der <xref:System.Collections.ArrayList> hinzugefügt wird, wird implizit in <xref:System.Object> umgewandelt.  Wenn es sich bei den Elementen um Werttypen handelt, müssen sie vor dem Hinzufügen zur Liste durch Boxing und beim Abrufen durch Unboxing umgewandelt werden.  Sowohl die Umwandlung als auch die Boxing\- und Unboxingoperationen vermindern die Leistung. Die Auswirkung von Boxing und Unboxing kann sich besonders bemerkbar machen, wenn umfassende Auflistungen durchlaufen werden müssen.  
  
 Bei der anderen Einschränkung handelt es sich um das Fehlen einer Typüberprüfung zur Kompilierzeit. Da <xref:System.Collections.ArrayList> alles in <xref:System.Object> umwandelt, gibt es zur Kompilierzeit keine Möglichkeit zu verhindern, dass Clientcode Folgendes verursacht:  
  
 [!code-cs[csProgGuideGenerics#5](../../../csharp/programming-guide/generics/codesnippet/csharp/benefits-of-generics_2.cs)]  
  
 Durchaus zulässig und manchmal beim Erstellen heterogener Auflistungen vielleicht sogar beabsichtigt, scheint das Kombinieren von Zeichenfolgen und `ints` in einer gemeinsamen <xref:System.Collections.ArrayList> doch eher ein Programmierfehler zu sein, der erst zur Laufzeit entdeckt werden kann.  
  
 In den Versionen 1.0 und 1.1 der Programmiersprache C\# konnten solche Gefahren durch verallgemeinerten Code in den Auflistungsklassen der .NET Framework\-Basisklassenbibliothek nur durch selbstgeschriebene typspezifische Auflistungen vermieden werden.  Da eine solche Klasse immer nur für einen Datentyp verwendbar ist, geht der Nutzen der Verallgemeinerung natürlich verloren, sodass Sie die Klasse für jeden Typ, der gespeichert wird, neu schreiben müssen.  
  
 Deshalb wird für <xref:System.Collections.ArrayList> und ähnliche Klassen unbedingt eine Möglichkeit benötigt, im Clientcode den jeweils zu verwendenden Datentyp für jede Instanz einzeln anzugeben.  Dadurch würde die Umwandlung in `T:System.Object` überflüssig, und der Compiler könnte eine Typüberprüfung durchführen.  Mit anderen Worten: Für <xref:System.Collections.ArrayList> ist ein Typparameter erforderlich.  Genau dies wird durch Generika bereitgestellt.  In der generischen <xref:System.Collections.Generic.List%601>\-Auflistung im `N:System.Collections.Generic`\-Namespace sieht die gleiche Operation \(Hinzufügen von Elementen zur Auflistung\) folgendermaßen aus:  
  
 [!code-cs[csProgGuideGenerics#6](../../../csharp/programming-guide/generics/codesnippet/csharp/benefits-of-generics_3.cs)]  
  
 Bei Clientcode bildet das Typargument in der Deklaration und der Instanziierung die einzige Syntaxergänzung, die bei <xref:System.Collections.Generic.List%601> gegenüber <xref:System.Collections.ArrayList> vorgenommen wird.  Im Gegenzug für diese geringfügig komplexere Codierung können Sie nun eine Liste erstellen, die nicht nur sicherer ist als <xref:System.Collections.ArrayList>, sondern auch erheblich schneller, und zwar besonders dann, wenn es sich bei den Elementen um Werttypen handelt.  
  
## Siehe auch  
 <xref:System.Collections.Generic>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Boxing und Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)   
 [Best Practices für Auflistungen](http://go.microsoft.com/fwlink/?LinkId=112403)