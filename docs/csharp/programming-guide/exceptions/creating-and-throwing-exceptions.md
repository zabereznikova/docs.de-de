---
title: "Erstellen und Ausl&#246;sen von Ausnahmen (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Abfangen von Ausnahmen [C#]"
  - "Ausnahmen [C#], Erstellen"
  - "Ausnahmen [C#], Auslösen"
  - "Auslösen von Ausnahmen [C#]"
ms.assetid: 6bbba495-a115-4c6d-90cc-1f4d7b5f39e2
caps.latest.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# Erstellen und Ausl&#246;sen von Ausnahmen (C#-Programmierhandbuch)
Ausnahmen werden verwendet, um anzuzeigen, dass während der Programmausführung ein Fehler aufgetreten ist.  Ausnahmeobjekte, die einen Fehler beschreiben, werden erstellt und dann mit dem [throw](../../../csharp/language-reference/keywords/throw.md)\-Schlüsselwort *ausgelöst*.  Die Laufzeit sucht dann nach dem kompatibelsten Ausnahmehandler.  
  
 Programmierer sollten Ausnahmen auslösen, wenn mindestens eine der folgenden Bedingungen zutrifft:  
  
-   Die Methode kann die definierte Funktionalität nicht erfüllen.  
  
     Wenn beispielsweise ein Parameter zu einer Methode einen ungültigen Wert hat:  
  
     [!code-cs[csProgGuideExceptions#12](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_1.cs)]  
  
-   Auf Grundlage des Objektzustands erfolgt ein unpassender Aufruf an ein Objekt.  
  
     Ein Beispiel wäre der Versuch, in eine schreibgeschützte Datei zu schreiben.  Lösen Sie in Fällen, in denen der Objektzustand einen bestimmten Vorgang nicht zulässt, eine Instanz von <xref:System.InvalidOperationException> oder ein auf einer Ableitung dieser Klasse basierendes Objekt aus.  Im folgenden Beispiel wird eine Methode veranschaulicht, die ein <xref:System.InvalidOperationException>\-Objekt auslöst:  
  
     [!code-cs[csProgGuideExceptions#13](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_2.cs)]  
  
-   Wenn ein Argument einer Methode eine Ausnahme verursacht.  
  
     In diesem Fall sollte die ursprüngliche Ausnahme abgefangen werden, und es sollte eine <xref:System.ArgumentException>\-Instanz erstellt werden.  Die ursprüngliche Ausnahme sollte als <xref:System.Exception.InnerException%2A>\-Parameter an den Konstruktor von <xref:System.ArgumentException> übergeben werden:  
  
     [!code-cs[csProgGuideExceptions#14](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_3.cs)]  
  
 Ausnahmen enthalten eine Eigenschaft namens <xref:System.Exception.StackTrace%2A>.  Diese Zeichenfolge enthält die Namen der aktuell in der Aufrufliste befindlichen Methoden sowie den Dateinamen und die Zeilennummer der Stelle, an der die Ausnahme für die jeweilige Methode ausgelöst wurde.  Die Common Language Runtime \(CLR\) erstellt an der Position der `throw`\-Anweisung automatisch ein <xref:System.Exception.StackTrace%2A>\-Objekt. Ausnahmen müssen also an der Stelle ausgelöst werden, an der die Stapelüberwachung beginnen soll.  
  
 Alle Ausnahmen enthalten eine Eigenschaft namens <xref:System.Exception.Message%2A>.  Diese Zeichenfolge sollte festgelegt werden, um den Grund für die Ausnahme zu erklären.  Beachten Sie, dass in den Meldungstext keine sicherheitsrelevanten Informationen eingefügt werden sollten.  Zusätzlich zu <xref:System.Exception.Message%2A> enthält <xref:System.ArgumentException> eine Eigenschaft mit dem Namen <xref:System.ArgumentException.ParamName%2A>, die auf den Namen des Arguments festgelegt werden sollte, das die Ausnahme ausgelöst hat.  Für einen Set\-Accessor einer Eigenschaft muss <xref:System.ArgumentException.ParamName%2A> auf `value` festgelegt werden.  
  
 Member öffentlicher und geschützter Methoden müssen Ausnahmen immer auslösen, wenn sie die ihnen zugewiesenen Funktionen nicht erfüllen können.  Die ausgelöste Ausnahmeklasse sollte für den Fehlerzustand so spezifisch wie möglich sein.  Diese Ausnahmen sollten als Teil der Klassenfunktionalität dokumentiert werden, und abgeleitete Klassen oder Aktualisierungen der ursprünglichen Klasse sollten dasselbe Verhalten beibehalten, um Rückwärtskompatibilität zu gewährleisten.  
  
## Was beim Auslösen von Ausnahmen zu vermeiden ist  
 Die folgende Liste enthält Vorgehensweisen, die beim Auslösen von Ausnahmen vermieden werden sollten:  
  
-   Ausnahmen sollten nicht verwendet werden, um den Programmfluss als Teil der normalen Ausführung zu ändern.  Ausnahmen sollten nur verwendet werden, um Fehlerzustände zu melden und zu behandeln.  
  
-   Geben Sie Ausnahmen nicht als Rückgabewert oder Parameter zurück, anstatt sie auszulösen.  
  
-   Lösen Sie <xref:System.Exception?displayProperty=fullName>, <xref:System.SystemException?displayProperty=fullName>, <xref:System.NullReferenceException?displayProperty=fullName> oder <xref:System.IndexOutOfRangeException?displayProperty=fullName> nicht absichtlich über den eigenen Quellcode aus.  
  
-   Erstellen Sie keine Ausnahmen, die im Debugmodus ausgelöst werden können, aber nicht im Releasemodus.  Verwenden Sie stattdessen die Debug Assert\-Methode, um Laufzeitfehler während der Entwicklungsphase zu identifizieren.  
  
## Definieren von Ausnahmeklassen  
 In Programmen kann eine vordefinierte Ausnahmeklasse \(mit Ausnahme der oben genannten\) im <xref:System>\-Namespace ausgelöst werden, oder es können eigene Ausnahmeklassen durch Ableiten von <xref:System.Exception> erstellt werden.  Die abgeleiteten Klassen müssen mindestens vier Konstruktoren definieren: einen Standardkonstruktor, einen zum Festlegen der message\-Eigenschaft und einen, der sowohl die <xref:System.Exception.Message%2A>\-Eigenschaft als auch die <xref:System.Exception.InnerException%2A>\-Eigenschaft festlegt.  Der vierte Konstruktor wird verwendet, um die Ausnahme zu serialisieren.  Neue Ausnahmeklassen sollten serialisierbar sein.  Beispiele:  
  
 [!code-cs[csProgGuideExceptions#15](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_4.cs)]  
  
 Neue Eigenschaften sollten zur Ausnahmeklasse nur hinzugefügt werden, wenn die Daten, die durch sie bereitgestellt werden, zur Bearbeitung der Ausnahme benötigt werden.  Wenn der abgeleiteten Ausnahmeklasse neue Eigenschaften hinzugefügt werden, sollte `ToString()` überschrieben werden, um die ergänzenden Informationen zurückzugeben.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Ausnahmen und Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)   
 [Ausnahmenhierarchie](../Topic/Exception%20Hierarchy.md)   
 [Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/exception-handling.md)