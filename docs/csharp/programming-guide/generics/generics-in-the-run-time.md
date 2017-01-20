---
title: "Generika zur Laufzeit (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Generika [C#], Zur Laufzeit"
ms.assetid: 119df7e6-9ceb-49df-af36-24f8f8c0747f
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Generika zur Laufzeit (C#-Programmierhandbuch)
Beim Kompilieren eines generischen Typs oder einer generischen Methode in Microsoft Intermediate Language \(MSIL\) wird über Metadaten auf das Vorkommen von Typparametern hingewiesen.  Die Art der Verwendung von MSIL für einen generischen Typ hängt davon ab, ob es sich bei dem übergebenen Typparameter um einen Werttyp oder einen Referenztyp handelt.  
  
 Wenn das erste Mal ein generischer Typ mit einem Werttyp als Parameter erstellt wird, erstellt die Laufzeit einen spezialisierten generischen Typ, bei dem übergebene Parameter an den entsprechenden Stellen in MSIL ersetzt werden.  Spezialisierte generische Typen werden für jeden eindeutigen Werttyp, der als Parameter verwendet wird, einmal erstellt.  
  
 Angenommen, im Programmcode wurde ein Stapel deklariert, der aus ganzen Zahlen erstellt wurde:  
  
 [!code-cs[csProgGuideGenerics#42](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_1.cs)]  
  
 An diesem Punkt generiert die Laufzeit eine spezialisierte Version der <xref:System.Collections.Generic.Stack%601>\-Klasse, in der der Parameter durch die entsprechende ganze Zahl ersetzt wird.  Bei Verwendung eines Stapels aus ganzen Zahlen wird jetzt immer die generierte spezialisierte <xref:System.Collections.Generic.Stack%601>\-Klasse verwendet.  Im folgenden Beispiel werden zwei Instanzen eines Stapels aus ganzen Zahlen erstellt, die eine Instanz des `Stack<int>`\-Codes gemeinsam nutzen.  
  
 [!code-cs[csProgGuideGenerics#43](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_2.cs)]  
  
 Angenommen, dass an anderer Stelle im Code jedoch eine weitere <xref:System.Collections.Generic.Stack%601>\-Klasse erstellt wird, mit einem anderen Werttyp, z. B. `long`, oder einer benutzerdefinierten Struktur als Parameter.  Daraufhin generiert die Laufzeit eine andere Version des generischen Typs und ersetzt `long` an den entsprechenden Stellen in MSIL.  Konvertierungen sind nicht mehr notwendig, da jede spezialisierte generische Klasse den Werttyp systemeigen enthält.  
  
 Bei Referenztypen unterscheidet sich die Funktionsweise von Generika geringfügig.  Wenn das erste Mal ein generischer Typ mit einem beliebigem Referenztyp erstellt wird, erstellt die Laufzeit einen spezialisierten generischen Typ, bei dem die Parameter durch Objektverweise in MSIL ersetzt werden.  Wenn jetzt ein konstruierter Typ mit einem Referenztyp als Parameter instanziiert wird \(unabhängig davon, um welchen Typ es sich dabei handelt\), wird die zuvor erstellte spezialisierte Version des generischen Typs verwendet.  Dies ist möglich, da alle Verweise die gleiche Größe haben.  
  
 Angenommen, Sie verfügen über zwei Referenztypen, eine `Customer`\-Klasse und eine `Order`\-Klasse, und Sie haben einen Stapel von `Customer`\-Typen erstellt:  
  
 [!code-cs[csProgGuideGenerics#47](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_3.cs)]  
  
 [!code-cs[csProgGuideGenerics#44](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_4.cs)]  
  
 An dieser Stelle generiert die Laufzeit eine spezialisierte Version der <xref:System.Collections.Generic.Stack%601>\-Klasse, die anstelle von Daten Objektverweise speichert, die zu einem späteren Zeitpunkt mit Daten gefüllt werden.  Angenommen, die nächste Codezeile erstellt einen Stapel eines anderen Referenztyps mit dem Namen `Order`:  
  
 [!code-cs[csProgGuideGenerics#45](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_5.cs)]  
  
 Anders als bei Werttypen wird für den `Order`\-Typ keine weitere spezialisierte Version der <xref:System.Collections.Generic.Stack%601>\-Klasse erstellt.  Stattdessen wird eine Instanz der spezialisierten Version der <xref:System.Collections.Generic.Stack%601>\-Klasse erstellt und die `orders`\-Variable so festgelegt, dass sie darauf verweist.  Angenommen, Sie würden dann auf eine Codezeile stoßen, die einen Stapel des Typs `Customer` erstellt:  
  
 [!code-cs[csProgGuideGenerics#46](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_6.cs)]  
  
 Wie auch bei der vorherigen Verwendung der mit dem `Order`\-Typ erstellten <xref:System.Collections.Generic.Stack%601>\-Klasse wird eine weitere Instanz der spezialisierten <xref:System.Collections.Generic.Stack%601>\-Klasse erstellt.  Die darin enthaltenen Zeiger werden so festgelegt, dass sie auf einen Arbeitsspeicherbereich von der Größe eines `Customer`\-Typs verweisen.  Da die Anzahl der Referenztypen von Programm zu Programm sehr unterschiedlich sein kann, wird bei der C\#\-Implementierung von Generika eine übermäßige Zunahme des Codeumfangs dadurch verhindert, dass die Anzahl der spezialisierten Klassen, die vom Compiler für generische Klassen von Referenztypen erstellt werden, auf eine reduziert wird.  
  
 Weiterhin gilt, dass eine mit einem Werttyp\- oder Referenztypparameter instanziierte generische C\#\-Klasse zur Laufzeit mittels Reflektion abgefragt werden kann. Dabei können sowohl der tatsächliche Typ als auch der Typparameter ermittelt werden.  
  
## Siehe auch  
 <xref:System.Collections.Generic>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Generika](../Topic/Generics%20in%20the%20.NET%20Framework.md)