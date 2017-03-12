---
title: "Eigenschaften (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cs.properties"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Eigenschaften"
  - "Eigenschaften [C#]"
ms.assetid: e295a8a2-b357-4ee7-a12e-385a44146fa8
caps.latest.revision: 38
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 38
---
# Eigenschaften (C#-Programmierhandbuch)
Eine Eigenschaft ist ein Member, das einen flexiblen Mechanismus zum Lesen, Schreiben oder Berechnen des Werts eines privaten Felds bietet.  Eigenschaften können wie öffentliche Datenmember verwendet werden, es sind jedoch spezielle Methoden namens *Accessoren*.  Dies ermöglicht den problemlosen Datenzugriff und unterstützt weiterhin die Sicherheit und Flexibilität der Methoden.  
  
 In diesem Beispiel speichert die `TimePeriod`\-Klasse einen Zeitraum.  Intern speichert die Klasse die Zeit in Sekunden, jedoch ermöglicht eine Eigenschaft mit dem Namen `Hours` die Angabe einer Zeit in Stunden durch den Client.  Die Accessoren für die `Hours`\-Eigenschaft führen die Konvertierung zwischen Stunden und Sekunden durch.  
  
## Beispiel  
 [!code-cs[csProgGuideProperties#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/properties_1.cs)]  
  
## Ausdruckstextdefinitionen  
 Es ist üblich, Eigenschaften zu verwenden, die umgehend das Ergebnis des Ausdrucks zurückgeben.  Es ist eine Syntaxabkürzung zur Definition dieser Eigenschaften mithilfe von `=>` verfügbar:  
  
```c#  
public string Name => First + " " + Last;   
```  
  
 Die Eigenschaft muss schreibgeschützt sein. Verwenden Sie darüber hinaus nicht das `get`\-Accessorschlüsselwort.  
  
## Übersicht über Eigenschaften  
  
-   Mithilfe von Eigenschaften kann eine Klasse eine öffentliche Methode zum Abrufen und Festlegen von Werten verfügbar machen und dabei den Implementierungs\- oder Verifizierungscode ausblenden.  
  
-   Ein [get](../../../csharp/language-reference/keywords/get.md)\-Eigenschaftenaccessor wird verwendet, um den Wert der Eigenschaft zurückzugegeben. Ein [set](../../../csharp/language-reference/keywords/set.md)\-Accessor wird verwendet, um einen neuen Wert zuzuweisen.  Diese Accessoren können über verschiedene Zugriffsebenen verfügen.  Weitere Informationen finden Sie unter [Einschränken des Accessorzugriffs](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).  
  
-   Das [value](../../../csharp/language-reference/keywords/value.md)\-Schlüsselwort wird verwendet, um den Wert zu definieren, der vom `set`\-Accessor zugewiesen wird.  
  
-   Eigenschaften, die keinen `set`\-Accessor implementieren, sind schreibgeschützt.  
  
-   Ziehen Sie für einfache Eigenschaften, die keinen benutzerdefinierten Accessorcode erfordern, die Möglichkeit der Verwendung automatisch implementierter Eigenschaften in Betracht.  Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).  
  
## Verwandte Abschnitte  
  
-   [Verwenden von Eigenschaften](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [Schnittstelleneigenschaften](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)  
  
-   [Vergleich zwischen Eigenschaften und Indexern](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [Einschränken des Accessorzugriffs](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
-   [Automatisch implementierte Eigenschaften](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Verwenden von Eigenschaften](../../../csharp/programming-guide/classes-and-structs/using-properties.md)   
 [Indexer](../../../csharp/programming-guide/indexers/index.md)