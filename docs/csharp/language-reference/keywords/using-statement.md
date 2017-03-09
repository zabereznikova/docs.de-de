---
title: "using-Anweisung (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "using-Anweisung [C#]"
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
caps.latest.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 31
---
# using-Anweisung (C#-Referenz)
Stellt eine intuitive Syntax bereit, die die richtige Verwendung von <xref:System.IDisposable>\-Objekten sicherstellt.  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung der using\-Anweisung.  
  
 [!code-cs[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/csharp/using-statement_1.cs)]  
  
## Hinweise  
 <xref:System.IO.File> und <xref:System.Drawing.Font> sind Beispiele für verwaltete Typen, die auf nicht verwaltete Ressourcen zugreifen \(in diesem Fall Dateihandles und Gerätekontexte\).  Es gibt viele andere Arten von nicht verwalteten Ressourcen und Klassenbibliothekstypen, die sie kapseln.  Alle diese Typen müssen die <xref:System.IDisposable>\-Schnittstelle implementieren.  
  
 Wenn Sie ein `IDisposable`\-Objekt verwenden, sollten Sie es grundsätzlich deklarieren und in einer `using`\-Anweisung instanziieren.  Die `using`\-Anweisung ruft die <xref:System.IDisposable.Dispose%2A>\-Methode für das Objekt auf die richtige Weise auf und \(bei Verwendung wie oben gezeigt\) verursacht, dass das Objekt seinen Gültigkeitsbereich verlässt, sobald <xref:System.IDisposable.Dispose%2A> aufgerufen wird.  Innerhalb des `using`\-Blocks ist das Objekt schreibgeschützt und kann nicht geändert oder neu zugewiesen werden.  
  
 Mit der `using`\-Anweisung wird sichergestellt, dass <xref:System.IDisposable.Dispose%2A> auch aufgerufen wird, wenn ein Ausnahmefehler auftritt, während Sie Methoden für das Objekt aufrufen.  Sie erzielen dasselbe Ergebnis, indem Sie das Objekt in einen try\-Block einfügen und <xref:System.IDisposable.Dispose%2A> in einem finally\-Block aufrufen. Auf diese Weise wird die `using`\-Anweisung vom Compiler übersetzt.  Der Code im oben gezeigten Beispiel wird bei der Kompilierung auf folgenden Code erweitert \(beachten Sie die zusätzlichen geschweiften Klammern zur Erstellung des begrenzten Gültigkeitsbereichs für das Objekt\):  
  
 [!code-cs[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/csharp/using-statement_2.cs)]  
  
 Mehrere Instanzen eines Typs können in einer `using`\-Anweisung deklariert werden, wie im folgenden Beispiel gezeigt.  
  
 [!code-cs[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/csharp/using-statement_3.cs)]  
  
 Sie können das Ressourcenobjekt instanziieren und die Variable dann an die `using`\-Anweisung übergeben, dies empfiehlt sich jedoch nicht.  In diesem Fall bleibt das Objekt im Gültigkeitsbereich, wenn das Steuerelement den `using`\-Block verlässt, auch wenn es möglicherweise keinen Zugriff mehr auf die nicht verwalteten Ressourcen hat.  In anderen Worten, es wird nicht mehr vollständig initialisiert.  Wenn Sie versuchen, das Objekt außerhalb des `using`\-Blocks zu verwenden, riskieren Sie, dass eine Ausnahme ausgelöst wird.  Aus diesem Grund sollten Sie das Objekt in der `using`\-Anweisung instanziieren und den Gültigkeitsbereich auf den `using`\-Block beschränken.  
  
 [!code-cs[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/csharp/using-statement_4.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [using\-Direktive](../../../csharp/language-reference/keywords/using-directive.md)   
 [Garbage Collection](../Topic/Garbage%20Collection.md)   
 [Implementing a Dispose Method](../Topic/Implementing%20a%20Dispose%20Method.md)