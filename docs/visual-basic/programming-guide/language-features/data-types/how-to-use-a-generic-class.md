---
title: "Gewusst wie: Verwenden einer generischen Klasse (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Typparameter, Definieren"
  - "Datentypargumente, Definieren"
  - "Argumente [Visual Basic], Datentypen"
  - "Of-Schlüsselwort, Verwenden"
  - "Generische Parameter"
  - "Datentypparameter"
  - "Generika [Visual Basic], Informationen über Generika"
  - "Datentypen [Visual Basic], Als Parameter"
  - "Datentypen [Visual Basic], Als Argumente"
  - "Parameter, Typ"
  - "Typen [Visual Basic], Generische"
  - "Parameter, Generische"
  - "Generika [Visual Basic], Erstellen generischer Typen"
  - "Datentypargumente"
  - "Parameter, Datentyp"
  - "Datentypparameter, Definieren"
  - "Typargumente, Definieren"
  - "Argumente [Visual Basic], Typ"
ms.assetid: 242dd2a6-86c4-4ce7-83f2-f2661803f752
caps.latest.revision: 24
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 24
---
# Gewusst wie: Verwenden einer generischen Klasse (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine Klasse, die *Typparameter* akzeptiert, wird *generische Klasse*genannt. Wenn Sie eine generische Klasse verwenden, können Sie daraus eine *erzeugte Klasse* generieren, indem Sie ein *Typargument* für jeden dieser Parameter angeben. Sie können dann eine Variable vom Typ der erzeugten Klasse deklarieren, und Sie können eine Instanz der erzeugten Klasse erstellen und dieser Variablen zuweisen.  
  
 Zusätzlich zu generischen Klassen können Sie auch generische Strukturen, Schnittstellen, Prozeduren und Delegaten definieren und verwenden.  
  
 Beim folgenden Verfahren wird eine generische Klasse verwendet, die in [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] definiert ist, und eine Instanz daraus erstellt.  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a>Eine Klasse verwenden, die einen Typparameter braucht  
  
1.  Fügen Sie am Anfang Ihrer Quelldatei eine [Imports-Anweisung (.NET-Namespace und -Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) ein, um den Namespace <xref:System.Collections.Generic?displayProperty=fullName> zu importieren. Dadurch können Sie auf die Klasse <xref:System.Collections.Generic.Queue%601?displayProperty=fullName> verweisen, ohne sie zur Unterscheidung von anderen Warteschlangenklassen, z.B. <xref:System.Collections.Queue?displayProperty=fullName>, vollständig qualifizieren zu müssen.  
  
2.  Erstellen Sie das Objekt auf die übliche Weise, aber fügen Sie sofort nach dem Klassennamen `(Of` `type``)` hinzu.  
  
     Im folgenden Beispiel wird dieselbe Klasse (<xref:System.Collections.Generic.Queue%601?displayProperty=fullName>) verwendet, um zwei Warteschlangenobjekte zu erstellen, die Elemente mit unterschiedlichen Datentypen enthalten. Es fügt Elemente am Ende jeder Warteschlange ein und entfernt und zeigt Elemente am Beginn jeder Warteschlange.  
  
     [!code-vb[VbVbalrDataTypes#9](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-use-a-generic-class_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Generische Typen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Sprachunabhängigkeit und sprachunabhängige Komponenten](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)   
 [Of](../../../../visual-basic/language-reference/statements/of-clause.md)   
 [Imports-Anweisung (.NET-Namespace und -Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Gewusst wie: Definieren einer Klasse, die für unterschiedliche Datentypen die gleiche Funktionalität bereitstellen kann](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)   
 [Iteratoren](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)