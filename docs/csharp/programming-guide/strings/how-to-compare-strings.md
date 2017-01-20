---
title: "Gewusst wie: Vergleichen von Zeichenfolgen (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "Vergleichen von Zeichenfolgen [C#]"
  - "Zeichenfolgen [C#], Vergleich"
ms.assetid: e1268e28-ee98-4695-98e9-92280f1c33c0
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Vergleichen von Zeichenfolgen (C#-Programmierhandbuch)
Wenn Sie Zeichenfolgen vergleichen, führt dies zu einem Ergebnis, das besagt, dass eine Zeichenfolge größer oder kleiner ist als die andere oder dass die beiden Zeichenfolgen gleich sind.  Die Regeln, nach denen das Ergebnis bestimmt wird, sind unterschiedlich, je nachdem, ob Sie einen *Ordinalvergleich* oder einen *kulturabhängigen Vergleich* durchführen.  Es ist wichtig, die richtige Art von Vergleich für eine bestimmte Aufgabe zu verwenden.  
  
 Verwenden Sie die grundlegenden ordinalen Vergleiche, wenn Sie die Werte von zwei Zeichenfolgen ohne Berücksichtigung von linguistischen Konventionen vergleichen oder sortieren müssen.  Beim grundlegenden ordinalen Vergleich \(`System.StringComparison.Ordinal`\) wird die Groß\-\/Kleinschreibung berücksichtigt. Dies bedeutet, dass die beiden Zeichenfolgen Zeichen für Zeichen übereinstimmen müssen: "und" stimmt nicht mit "Und" oder "UND" überein.  Eine häufig verwendete Variante ist `System.StringComparison.OrdinalIgnoreCase`, bei der "und", "Und" und "UND" übereinstimmen.  `StringComparison.OrdinalIgnoreCase` wird häufig verwendet, um Dateinamen, Pfadnamen, Netzwerkpfade und jede andere Zeichenfolge zu vergleichen, deren Wert sich nicht basierend auf dem Gebietsschema des Computers des Benutzers ändert.  Weitere Informationen finden Sie unter <xref:System.StringComparison?displayProperty=fullName>.  
  
 Kulturabhängige Vergleiche werden in der Regel verwendet, um Zeichenfolgen zu vergleichen oder zu sortieren, die von den Endbenutzern eingegeben werden, da die Zeichen und Sortierungskonventionen dieser Zeichenfolgen je nach Gebietsschema des Computers des Benutzers variieren können.  Sogar Zeichenfolgen, die identische Zeichen enthalten, werden je nach Kultur des aktuellen Threads verschieden sortiert.  
  
> [!NOTE]
>  Wenn Sie Zeichenfolgen vergleichen, sollten Sie die Methoden verwenden, mit denen ausdrücklich angegeben wird, welchen Vergleich Sie durchführen möchten.  So kann Ihr Code viel besser verwaltet werden und ist besser lesbar.  Verwenden Sie die Überladungen der Methoden der <xref:System.String?displayProperty=fullName>\-Klasse und der <xref:System.Array?displayProperty=fullName>\-Klasse, die einen <xref:System.StringComparison>\-Enumerationsparameter übernehmen, damit Sie angeben können, welche Art des Vergleichs ausgeführt werden soll.  Am besten vermeiden Sie die Verwendung der Operatoren `==` und `!=`, wenn Sie Zeichenfolgen vergleichen.  Vermeiden Sie auch die Verwendung der <xref:System.String.CompareTo%2A?displayProperty=fullName>\-Instanzenmethoden, da keiner der Überladungen einen <xref:System.StringComparison> akzeptiert.  
  
## Beispiel  
 Im folgenden Beispiel wird dargestellt, wie Zeichenfolgen ordnungsgemäß verglichen werden, deren Werte sich nicht basierend auf dem Gebietsschema des Computers des Benutzers ändern.  Außerdem wird auch das C\#\-Feature *Internalisierung von Zeichenfolgen* erläutert.  Wenn ein Programm mehrere identische Zeichenfolgenvariablen deklariert, speichert der Compiler alle am selben Speicherort.  Wenn Sie die <xref:System.Object.ReferenceEquals%2A>\-Methode aufrufen, sehen Sie, dass die beiden Zeichenfolgen auf dasselbe Objekt im Arbeitsspeicher verweisen.  Verwenden Sie die <xref:System.String.Copy%2A?displayProperty=fullName>\-Methode, um eine Internalisierung zu vermeiden, wie im folgenden Beispiel dargestellt.  
  
 [!code-cs[csProgGuideStrings#11](../../../csharp/programming-guide/strings/codesnippet/CSharp/CSRefStrings/Strings.cs#11)]  
  
## Beispiel  
 Im folgenden Beispiel wird dargestellt, wie Zeichenfolgen auf die bevorzugte Weise mithilfe der <xref:System.String?displayProperty=fullName>\-Methoden verglichen werden, die eine <xref:System.StringComparison>\-Enumeration akzeptieren.  Beachten Sie, dass die <xref:System.String.CompareTo%2A?displayProperty=fullName>\-Instanzenmethoden hier nicht verwendet werden, da keine der Überladungen einen <xref:System.StringComparison> akzeptiert.  
  
 [!code-cs[csProgGuideStrings#31](../../../csharp/programming-guide/strings/codesnippet/CSharp/CSRefStrings/Strings.cs#31)]  
  
## Beispiel  
 Im folgenden Beispiel wird dargestellt, wie Zeichenfolgen sortiert werden und in einem Array auf kulturabhängige Weise danach gesucht wird. Verwenden Sie dazu die statischen <xref:System.Array>\-Methoden, die einen <xref:System.StringComparer?displayProperty=fullName>\-Parameter akzeptieren.  
  
 [!code-cs[csProgGuideStrings#32](../../../csharp/programming-guide/strings/codesnippet/CSharp/CSRefStrings/Strings.cs#32)]  
  
 Auflistungsklassen, wie z. B. <xref:System.Collections.Hashtable?displayProperty=fullName>, <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> und <xref:System.Collections.Generic.List%601?displayProperty=fullName> verfügen über Konstruktoren, die einen <xref:System.StringComparer?displayProperty=fullName>\-Parameter akzeptieren, wenn der Typ der Elemente oder Schlüssel `string` lautet.  Im Allgemeinen sollten Sie wann immer möglich diese Konstruktoren verwenden und entweder `Ordinal` oder `OrdinalIgnoreCase` angeben.  
  
## Siehe auch  
 <xref:System.Globalization.CultureInfo?displayProperty=fullName>   
 <xref:System.StringComparer?displayProperty=fullName>   
 [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md)   
 [Vergleichen von Zeichenfolgen](../Topic/Comparing%20Strings%20in%20the%20.NET%20Framework.md)   
 [Globalisieren und Lokalisieren von Anwendungen](/visual-studio/ide/globalizing-and-localizing-applications)