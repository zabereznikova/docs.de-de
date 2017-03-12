---
title: "Gewusst wie: Suchen von Zeichenfolgen mithilfe von regul&#228;ren Ausdr&#252;cken (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Suchen nach Zeichenfolgen [C#]"
  - "Zeichenfolgen [C#], Suchen mit RegEx"
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# Gewusst wie: Suchen von Zeichenfolgen mithilfe von regul&#228;ren Ausdr&#252;cken (C#-Programmierhandbuch)
Die <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName>\-Klasse kann zum Suchen von Zeichenfolgen verwendet werden.  Die Komplexität dieser Suchvorgänge kann unterschiedlich sein: Es gibt sehr einfache Suchvorgänge und solche, die umfassend Gebrauch von regulären Ausdrücken machen.  Nachfolgend sind für das Suchen von Zeichenfolgen mithilfe der <xref:System.Text.RegularExpressions.Regex>\-Klasse zwei Beispiele aufgelistet.  Weitere Informationen hierzu finden Sie unter [Reguläre Ausdrücke von .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md).  
  
## Beispiel  
 Der folgende Code ist eine Konsolenanwendung, die eine einfache Suche nach Zeichenfolgen in einem Array ausführt, wobei nicht zwischen Groß\- und Kleinschreibung unterschieden wird.  Die statische Methode <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=fullName> führt die Suche aus, wobei die zu suchende Zeichenfolge und eine Zeichenfolge mit dem Suchmuster angegeben werden müssen.  In diesem Beispiel wird ein drittes Argument verwendet, um anzugeben, dass die Groß\-\/Kleinschreibung ignoriert werden soll.  Weitere Informationen finden Sie unter <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>.  
  
 [!code-cs[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/csharp/CSRefStrings/Strings.cs#17)]  
  
## Beispiel  
 Der folgende Code ist eine Konsolenanwendung, bei der reguläre Ausdrücke verwendet werden, um das Format aller Zeichenfolgen in einem Array zu überprüfen.  Für die Validierung ist es erforderlich, dass jede Zeichenfolge wie eine Telefonnummer in drei Zahlengruppen unterteilt ist, die mit Strichen voneinander getrennt sind. Die ersten zwei Gruppen enthalten drei Ziffern, die dritte Gruppe besteht aus vier Ziffern.  Dies wird mithilfe des regulären Ausdrucks `^\\d{3}-\\d{3}-\\d{4}$` ermöglicht.  Weitere Informationen finden Sie unter [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](../Topic/Regular%20Expression%20Language%20-%20Quick%20Reference.md).  
  
 [!code-cs[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/csharp/CSRefStrings/Strings.cs#18)]  
  
## Siehe auch  
 <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md)   
 [Reguläre Ausdrücke von .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](../Topic/Regular%20Expression%20Language%20-%20Quick%20Reference.md)