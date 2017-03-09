---
title: "Enumerations and Name Qualification (Visual Basic) | Microsoft Docs"
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
  - "declarations, enumerations"
  - "Imports statement, namespace declarations"
  - "declaring namespaces, enumerations"
  - "name collisions"
  - "ambiguous names, enumerations"
  - "enumerations [Visual Basic], name qualification"
  - "names, avoiding conflicts"
  - "namespaces, declaring"
  - "naming conflicts, enumerations"
  - "naming conflicts, qualifying names"
  - "declaring enumerations"
  - "references, enumeration members"
  - "naming conventions, naming conflicts"
  - "declarations, namespaces"
ms.assetid: 08ba2738-df52-4140-bc55-f57c871c9b73
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Enumerations and Name Qualification (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Wenn Sie auf einen Member in einer Enumeration verweisen, müssen Sie in der Regel den Membernamen mit dem Enumerationsnamen qualifizieren.  Wenn Sie beispielsweise auf den Member `Sunday` in der `Days`\-Enumeration verweisen möchten, würden Sie folgende Syntax verwenden:  
  
 [!code-vb[VbEnumsTask#18](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class2.vb#18)]  
  
## Verwenden der Imports\-Anweisung  
 Sie können die Angabe vollqualifizierter Namen vermeiden, indem Sie eine `Imports`\-Anweisung im Namespacedeklarationsabschnitt des Codes einfügen. Beispiel:  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class1.vb#22)]  
  
 Eine `Imports`\-Anweisung importiert Namespacenamen aus Projekten und Assemblys, auf die verwiesen wird, und aus dem Projekt des Moduls, in dem die Anweisung auftritt.  Nachdem diese Anweisung hinzugefügt wurde, können Sie ohne Qualifizierung auf die Enumerationsmember verweisen. Beispiel:  
  
 [!code-vb[VbEnumsTask#24](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class1.vb#24)]  
  
 Wenn Sie die Gruppen von verwandten Konstanten in Enumerationen zusammenfassen, können Sie dieselben Konstantennamen in verschiedenen Kontexten verwenden.  Beispielsweise können Sie die Namen der Wochentagskonstanten in der `Days`\-Enumeration auch in der `WorkDays`\-Enumeration für die Arbeitstage verwenden.  Wenn Sie für die Enumerationen die `Imports`\-Anweisung verwenden, müssen Sie darauf achten, dass die Verweise eindeutig sind.  Betrachten Sie das folgende Beispiel:  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class1.vb#22)]  
  
 [!code-vb[VbEnumsTask#25](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class1.vb#25)]  
  
 Wenn `Monday` sowohl ein Member der `Days`\-Enumeration als auch der `Workdays`\-Enumeration ist, verursacht dieser Code einen Compilerfehler.  Um beim Verweisen auf einzelne Konstanten nicht eindeutige Verweise zu vermeiden, qualifizieren Sie den Konstantennamen mit der entsprechenden Enumeration.  Der folgende Code verweist auf die `Saturday`\-Konstante in der `Days`\-Enumeration und der `WorkDays`\-Enumeration.  
  
 [!code-vb[VbEnumsTask#32](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class2.vb#32)]  
  
## Siehe auch  
 [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)   
 [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [How to: Refer to an Enumeration Member](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [How to: Iterate Through An Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [How to: Determine the String Associated with an Enumeration Value](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [When to Use an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)   
 [Constant and Literal Data Types](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Enum Statement](../../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Imports Statement \(.NET Namespace and Type\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)