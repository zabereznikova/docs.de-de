---
title: "Gewusst wie: &#196;ndern von Zeichenfolgeninhalten (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "Zeichenfolgen [C#], Ändern"
ms.assetid: b6c20bba-ce22-43d7-ad1b-5ce65f714055
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: &#196;ndern von Zeichenfolgeninhalten (C#-Programmierhandbuch)
Da Zeichenfolgen *unveränderlich* sind, ist es \(ohne Verwendung von unsicheren Code\) nicht möglich, den Wert eines Zeichenfolgenobjekts zu ändern, nachdem es erstellt wurde.  Es gibt jedoch viele Möglichkeiten, den Wert einer Zeichenfolge zu ändern und das Ergebnis in einem neuen Zeichenfolgenobjekt zu speichern.  Die <xref:System.String?displayProperty=fullName>\-Klasse stellt Methoden bereit, die für eine Eingabezeichenfolge ausgeführt werden und ein neues Zeichenfolgenobjekt zurückgeben.  In vielen Fällen können Sie der Variablen, die die ursprüngliche Zeichenfolge enthielt, das neue Objekt zuweisen.  Die <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName>\-Klasse stellt zusätzliche Methoden bereit, die auf ähnliche Weise funktionieren.  Die <xref:System.Text.StringBuilder?displayProperty=fullName>\-Klasse stellt einen Zeichenpuffer bereit, den Sie "direkt" ändern können. Sie rufen die <xref:System.Text.StringBuilder.ToString%2A?displayProperty=fullName>\-Methode zum Erstellen eines neuen Zeichenfolgenobjekts auf, das den aktuellen Inhalt des Puffers enthält.  
  
## Beispiel  
 Im folgenden Beispiel werden verschiedene Möglichkeiten dargestellt, Teilzeichenfolgen in einer angegebenen Zeichenfolge zu ersetzen oder zu entfernen.  
  
 [!code-cs[csProgGuideStrings#28](../../../csharp/programming-guide/strings/codesnippet/CSharp/CSRefStrings/Strings.cs#28)]  
  
## Beispiel  
 Um auf die einzelnen Zeichen in einer Zeichenfolge mithilfe der Arraynotation zuzugreifen, können Sie das <xref:System.Text.StringBuilder>\-Objekt, das den `[]`\-Operator überlädt, für den Zugriff auf den internen Zeichenpuffer verwenden.  Sie können auch die Zeichenfolge mit der <xref:System.String.ToCharArray%2A>\-Methode in ein Array von Zeichen konvertieren.  Im folgenden Beispiel wird `ToCharArray` zum Erstellen des Arrays verwendet.  Einige Elemente dieses Arrays werden dann geändert.  Ein Zeichenfolgenkonstruktor, der ein Zeichenarray als Eingabeparameter akzeptiert, wird dann zum Erstellen einer neuen Zeichenfolge aufgerufen.  
  
 [!code-cs[csProgGuideStrings#24](../../../csharp/programming-guide/strings/codesnippet/CSharp/CSRefStrings/Strings.cs#24)]  
  
## Beispiel  
 Das folgende Beispiel gilt für die sehr seltenen Situationen, in denen Sie eine Zeichenfolge mithilfe des unsicheren Codes direkt ändern möchten, ähnlich wie bei Zeichenfolgenarrays im C\-Format.  Es wird dargestellt, wie mit dem fixed\-Schlüsselwort direkt auf die einzelnen Zeichen zugegriffen wird.  Es zeigt auch einen möglichen Nebeneffekt von unsicheren Operationen für Zeichenfolgen, der daraus resultiert, wie der C\#\-Compiler Zeichenfolgen intern speichert.  Im Allgemeinen sollten Sie diese Methode nicht verwenden, wenn es nicht absolut notwendig ist.  
  
 [!code-cs[csProgGuideStrings#29](../../../csharp/programming-guide/strings/codesnippet/CSharp/CSRefStrings/Strings.cs#29)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md)