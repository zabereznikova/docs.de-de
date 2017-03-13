---
title: "Generika (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Generika"
  - "Generika [C#]"
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# Generika (C#-Programmierhandbuch)
Generika wurden in Version 2.0 der Programmiersprache C\# und der Common Language Runtime \(CLR\) hinzugefügt.  Generika führen das Konzept der Typparameter in .NET Framework ein. Dadurch wird des möglich, Klassen und Methoden zu entwerfen, in denen die Angabe eines oder mehrerer Typen verzögert wird, bis die Klasse bzw. Methode durch Clientcode deklariert und instanziiert wird.  Indem Sie beispielsweise den generischen Typparameter T wie im folgenden Beispiel verwenden, können Sie eine einzelne Klasse schreiben, die von anderem Clientcode verwendet werden kann, ohne die damit verbundenen Kosten und Risiken von Boxingoperationen oder Umwandlungen zur Laufzeit:  
  
 [!code-cs[csProgGuideGenerics#1](../../../csharp/programming-guide/generics/codesnippet/CSharp/index_1.cs)]  
  
## Übersicht über Generika  
  
-   Verwenden Sie generische Typen, um die Codewiederverwendung, Typsicherheit und Leistung zu optimieren.  
  
-   Am häufigsten werden Generika zum Erstellen von Auflistungsklassen verwendet.  
  
-   Die .NET Framework\-Klassenbibliothek enthält mehrere neue generische Auflistungsklassen im <xref:System.Collections.Generic>\-Namespace.  Diese sollten möglichst oft anstelle von Klassen wie <xref:System.Collections.ArrayList> im <xref:System.Collections>\-Namespace verwendet werden.  
  
-   Sie können eigene generische Schnittstellen, Klassen, Methoden, Ereignisse und Delegaten erstellen.  
  
-   Generische Klassen werden möglicherweise eingeschränkt, um den Zugriff auf Methoden für besondere Datentypen zu aktivieren.  
  
-   Informationen über die Typen, die in einem generischen Datentyp verwendet werden, können zur Laufzeit mittels Reflektion abgerufen werden.  
  
## Verwandte Abschnitte  
 Weitere Informationen:  
  
-   [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
  
-   [Vorteile von Generika](../../../csharp/programming-guide/generics/benefits-of-generics.md)  
  
-   [Generische Typparameter](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
-   [Einschränkungen für Typparameter](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
-   [Generische Klassen](../../../csharp/programming-guide/generics/generic-classes.md)  
  
-   [Generische Schnittstellen](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
-   [Generische Methoden](../../../csharp/programming-guide/generics/generic-methods.md)  
  
-   [Generische Delegaten](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
-   [default\-Schlüsselwort](../../../csharp/programming-guide/generics/default-keyword-in-generic-code.md)  
  
-   [Unterschiede zwischen C\+\+\-Vorlagen und C\#\-Generika](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
-   [Generische Typen und Reflektion](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
-   [Generika zur Laufzeit](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
-   [Generika in der .NET Framework\-Klassenbibliothek](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md)  
  
## C\#\-Programmiersprachenspezifikation  
 Weitere Informationen finden Sie unter [C\#\-Sprachspezifikation](../../../csharp/language-reference/language-specification.md).  
  
## Siehe auch  
 <xref:System.Collections.Generic>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Typen](../../../csharp/programming-guide/types/index.md)   
 [\<typeparam\>](../../../csharp/programming-guide/xmldoc/typeparam.md)   
 [\<typeparamref\>](../../../csharp/programming-guide/xmldoc/typeparamref.md)