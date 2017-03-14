---
title: "new-Operator (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "new-Operatorschlüsselwort [C#]"
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# new-Operator (C#-Referenz)
Wird verwendet, um Objekte zu erstellen und Konstruktoren aufzurufen.  Beispiele:  
  
```  
Class1 obj  = new Class1();  
```  
  
 Wird auch verwendet, um Instanzen anonymer Typen zu erstellen:  
  
```  
var query = from cust in customers  
            select new {Name = cust.Name, Address = cust.PrimaryAddress};  
```  
  
 Der Operator `new` wird auch verwendet, um den Standardkonstruktor für Werttypen aufzurufen.  Beispiele:  
  
```  
int i = new int();  
```  
  
 In der vorangehenden Anweisung wird `i` mit `0` initialisiert. Dies ist der Standardwert für den `int`\-Typ.  Diese Anweisung wirkt sich genauso aus wie die folgende:  
  
```  
int i = 0;  
```  
  
 Die vollständige Liste der Standardwerte finden Sie unter [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md).  
  
 Für eine [Struktur](../../../csharp/language-reference/keywords/struct.md) darf kein Standardkonstruktor deklariert werden, weil jeder Werttyp implizit einen öffentlichen Standardkonstruktor besitzt.  Um die Anfangswerte eines Strukturtyps festzulegen, können Sie parametrisierte Konstruktoren deklarieren. Dies ist jedoch nur erforderlich, wenn andere Werte als die Standardwerte benötigt werden.  
  
 Werttypobjekte wie Strukturen werden auf dem Stapel erstellt, während Referenztypobjekte, z. B. Klassen, auf dem Heap erstellt werden.  Beide Objekttypen werden automatisch zerstört, aber auf Werttypen basierende Objekte werden zerstört, wenn sie außerhalb des gültigen Wertebereichs liegen, während auf Referenztypen basierende Objekte nach einiger Zeit zerstört werden, wenn der letzte Verweis auf sie entfernt wurde.  Für Referenztypen, die feste Ressourcen wie große Mengen an Speicher, Dateihandles oder Netzwerkverbindungen beanspruchen, bietet es sich manchmal an, mit einem deterministischen Abschluss sicherzustellen, dass das Objekt so bald wie möglich zerstört wird.  Weitere Informationen finden Sie unter [using\-Anweisung](../../../csharp/language-reference/keywords/using-statement.md).  
  
 Der Operator `new` kann nicht überladen werden.  
  
 Falls der Operator `new` keinen Speicher belegen  kann, wird die <xref:System.OutOfMemoryException>\-Ausnahme ausgelöst.  
  
## Beispiel  
 Im folgenden Beispiel werden mit dem Operator `new` ein `struct`\-Objekt und ein Klassenobjekt erstellt und initialisiert, und dann werden ihnen Werte zugewiesen.  Die Standardwerte und die zugewiesenen Werte werden angezeigt.  
  
 [!code-cs[csrefKeywordsOperator#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-operator_1.cs)]  
  
 Beachten Sie bei dem Beispiel, dass es sich bei dem Standardwert einer Zeichenfolge um `null` handelt.  Aus diesem Grund wird er nicht angezeigt.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Operatorschlüsselwörter](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [neu](../../../csharp/language-reference/keywords/new.md)   
 [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)