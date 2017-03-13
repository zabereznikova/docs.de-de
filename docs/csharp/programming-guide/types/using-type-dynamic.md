---
title: "Verwenden des Typs dynamic (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Dynamisch [C#], Informationen über dynamischen Typ"
  - "Dynamischer Typ [C#]"
ms.assetid: 3828989d-c967-4a51-b948-857ebc8fdf26
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# Verwenden des Typs dynamic (C#-Programmierhandbuch)
[!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp-dev10-long-md.md)] stellt den neuen Typ `dynamic` bereit.  Es handelt sich zwar um einen statischen Typ, aber ein Objekt des Typs `dynamic` umgeht die Überprüfung statischer Typen.  Die Funktionsweise stimmt in den meisten Fällen mit der des Typs `object` überein.  Zur Kompilierzeit wird davon ausgegangen, dass ein Element vom Typ `dynamic` jeden beliebigen Vorgang unterstützt.  Aus diesem Grund müssen Sie sich keine Gedanken darüber machen, ob der Wert des Objekts von einer COM\-API, von einer dynamischen Sprache wie IronPython, vom HTML\-Dokumentobjektmodell \(DOM\), durch Reflektion oder von einem anderen Element im Programm abgerufen wird.  Wenn der Code jedoch nicht gültig ist, werden zur Laufzeit Fehler abgefangen.  
  
 Beispiel: Wenn die Instanzmethode `exampleMethod1` im folgenden Code nur einen Parameter aufweist, erkennt der Compiler den ersten Aufruf der Methode, `ec.exampleMethod1(10, 4)`, als nicht gültig, weil darin zwei Argumente enthalten sind.  Der Aufruf löst einen Compilerfehler aus.  Der zweite Aufruf der Methode, `dynamic_ec.exampleMethod1(10, 4)`, wird nicht vom Compiler überprüft, da der Typ von `dynamic_ec` `dynamic` ist.  Somit wird kein Compilerfehler gemeldet.  Der Fehler wird jedoch nicht unendlich verborgen.  Er wird zur Laufzeit abgefangen und löst eine Laufzeitausnahme aus.  
  
 [!code-cs[CsProgGuideTypes#50](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_1.cs)]  
  
 [!code-cs[CsProgGuideTypes#56](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_2.cs)]  
  
 Die Rolle des Compilers in diesen Beispielen besteht darin, Informationen zu den Vorgängen zusammenzufassen, die die einzelnen Anweisungen für das Objekt oder den Ausdruck vom Typ `dynamic` vorsehen.  Zur Laufzeit werden die gespeicherten Informationen geprüft, und nicht gültige Anweisungen lösen eine Laufzeitausnahme aus.  
  
 Das Ergebnis der meisten dynamischen Vorgänge ist ebenfalls `dynamic`.  Wenn Sie z. B. im folgenden Beispiel mit der Maus auf die Verwendung von `testSum` zeigen, zeigt IntelliSense den Typ **\(lokale Variable\) dynamic testSum** an.  
  
 [!code-cs[CsProgGuideTypes#51](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_3.cs)]  
  
 Zu den Vorgängen, bei denen das Ergebnis nicht `dynamic` ist, zählen Konvertierungen von `dynamic` in einen anderen Typ sowie Konstruktoraufrufe, die Argumente vom Typ `dynamic` einschließen.  Beispiel: Der Typ von `testInstance` in der folgenden Deklaration ist `ExampleClass`, nicht `dynamic`.  
  
 [!code-cs[CsProgGuideTypes#52](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_4.cs)]  
  
 Konvertierungsbeispiele werden im folgenden Abschnitt "Konvertierungen" gezeigt.  
  
## Konvertierungen  
 Konvertierungen zwischen dynamischen Objekten und anderen Typen sind einfach.  So können Entwickler zwischen dynamischem und nicht dynamischem Verhalten wechseln.  
  
 Jedes beliebige Objekt kann implizit in den dynamic\-Typ konvertiert werden, wie in den folgenden Beispielen gezeigt.  
  
 [!code-cs[CsProgGuideTypes#53](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_5.cs)]  
  
 Ebenso kann eine implizite Konvertierung dynamisch auf jeden beliebigen Ausdruck vom Typ `dynamic` angewendet werden.  
  
 [!code-cs[CsProgGuideTypes#54](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_6.cs)]  
  
## Überladungsauflösung mit Argumenten vom Typ dynamic  
 Die Überladungsauflösung tritt zur Laufzeit statt zur Kompilierzeit auf, wenn mindestens eines der Argumente in einem Methodenaufruf den Typ `dynamic` aufweist, oder wenn der Empfänger des Methodenaufrufs den Typ `dynamic` aufweist.  Wenn im folgenden Beispiel die einzige zugreifbare `exampleMethod2`\-Methode so definiert wird, dass sie ein Zeichenfolgenargument erfordert, löst das Senden von `d1` als Argument keinen Compilerfehler, aber eine Laufzeitausnahme aus.  Die Überladungsauflösung schlägt zur Laufzeit fehl, da `d1` den Laufzeittyp `int` aufweist und `exampleMethod2` eine Zeichenfolge erfordert.  
  
 [!code-cs[CsProgGuideTypes#55](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_7.cs)]  
  
## Dynamic Language Runtime  
 Die Dynamic Language Runtime \(DLR\) ist eine neue API in [!INCLUDE[net_v40_short](../../../csharp/programming-guide/types/includes/net-v40-short-md.md)].  Diese stellt die Infrastruktur bereit, die den `dynamic`\-Typ in C\# sowie die Implementierung von dynamischen Programmiersprachen wie IronPython und IronRuby unterstützt.  Weitere Informationen zur DLR finden Sie unter [Übersicht über die Dynamic Language Runtime](../Topic/Dynamic%20Language%20Runtime%20Overview.md).  
  
## COM\-Interop  
 [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp-dev10-long-md.md)] bietet mehrere Funktionen zur Verbesserung der Interoperation mit COM\-APIs, wie beispielsweise Office\-Automatisierungs\-APIs.  Dazu zählen der `dynamic`\-Typ sowie [benannte und optionale Argumente](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md).  
  
 Viele COM\-Methoden ermöglichen die Variation von Argumenttypen und Rückgabetyp durch Festlegen der Typen als `object`.  Dies erforderte zur Koordination mit stark typisierten Variablen in C\# die explizite Umwandlung der Werte.  Wenn Sie mit der [\/link \(Link to COM Assembly\)](../../../csharp/language-reference/compiler-options/link-compiler-option.md)\-Option kompilieren, ermöglicht Ihnen der neue `dynamic`\-Typ, die `object`\-Vorkommen in COM\-Signaturen wie Elemente vom Typ `dynamic` zu behandeln, sodass ein Großteil der Umwandlung nicht mehr erforderlich ist.  Anhand der folgenden Beispielanweisungen können Sie den Zugriff auf eine Zelle in einem Microsoft Office Excel\-Arbeitsblatt mit dem `dynamic`\-Typ und ohne den `dynamic`\-Typ vergleichen.  
  
 [!code-cs[csOfficeWalkthrough#12](../../../csharp/programming-guide/interop/codesnippet/CSharp/using-type-dynamic_8.cs)]  
  
 [!code-cs[csOfficeWalkthrough#13](../../../csharp/programming-guide/interop/codesnippet/CSharp/using-type-dynamic_9.cs)]  
  
## Verwandte Themen  
  
|Titel|Description|  
|-----------|-----------------|  
|[dynamic](../../../csharp/language-reference/keywords/dynamic.md)|Beschreibt die Verwendung des `dynamic`\-Schlüsselworts.|  
|[Übersicht über die Dynamic Language Runtime](../Topic/Dynamic%20Language%20Runtime%20Overview.md)|Bietet einen Überblick über die Dynamic Language Runtime \(DLR\), eine Laufzeitumgebung, welche die Common Language Runtime \(CLR\) um eine Reihe von Diensten für dynamische Sprachen ergänzt.|  
|[Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)|Stellt schrittweise Anweisungen zum Erstellen eines benutzerdefinierten dynamischen Objekts und eines auf eine `IronPython`\-Bibliothek zugreifenden Projekts bereit.|  
|[Gewusst wie: Zugreifen auf Office\-Interop\-Objekte mithilfe von Visual C\#\-Funktionen](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)|Veranschaulicht die Erstellung eines Projekts mit benannten und optionalen Argumenten, mit dem `dynamic`\-Typ und mit weiteren Verbesserungen, die den Zugriff auf Office\-API\-Objekte vereinfachen.|