---
title: "Gewusst wie: Zugreifen auf Auflistungsklassen mit foreach (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Auflistungsklassen [C#], foreach-Anweisung"
ms.assetid: a6b9cf5c-6c8d-4223-b12c-288949434493
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# Gewusst wie: Zugreifen auf Auflistungsklassen mit foreach (C#-Programmierhandbuch)
Im folgenden Codebeispiel wird das Erstellen einer nicht generischen Auflistungsklasse veranschaulicht, die mit [foreach](../../../csharp/language-reference/keywords/foreach-in.md) verwendet werden kann.  Im Beispiel wird eine Zeichenfolgentokenizerklasse definiert.  
  
> [!NOTE]
>  Dieses Beispiel entspricht nur in den Fällen der empfohlenen Vorgehensweise, in denen keine generische Auflistungsklasse verwendet werden kann.  Ein Beispiel für das Implementieren einer typsicheren generischen Auflistungsklasse, die <xref:System.Collections.Generic.IEnumerable%601> unterstützt, finden Sie unter [Iteratoren](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Im Beispiel verwendet das folgende Codesegment die `Tokens`\-Klasse, um den Satz "This is a sample sentence." unter Verwendung von " " und "\-" als Trennzeichen in Tokens aufzulösen.  Anschließend werden diese Tokens mithilfe einer `foreach`\-Anweisung angezeigt.  
  
 [!code-cs[csProgGuideCollections#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_1.cs)]  
  
## Beispiel  
 Intern verwendet die `Tokens`\-Klasse ein Array, um die Tokens zu speichern.  Da Arrays <xref:System.Collections.IEnumerator> und <xref:System.Collections.IEnumerable> implementieren, hätten im Codebeispiel auch die Enumerationsmethoden \(<xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> und <xref:System.Collections.IEnumerator.Current%2A>\) des Arrays verwendet werden können, statt sie in der `Tokens`\-Klasse zu definieren.  Die Methodendefinitionen wurden in das Beispiel aufgenommen, um zu erläutern, wie sie definiert werden und was die einzelnen Definitionen bewirken.  
  
 [!code-cs[csProgGuideCollections#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_2.cs)]  
  
 In C\# muss eine Auflistungsklasse nicht <xref:System.Collections.IEnumerable> und <xref:System.Collections.IEnumerator> implementieren, um mit `foreach` kompatibel zu sein.  Wenn die Klasse über die erforderlichen Member <xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> und <xref:System.Collections.IEnumerator.Current%2A> verfügt, ist sie mit `foreach` kompatibel.  Wenn Sie die Schnittstellen weglassen, hat dies den Vorteil, dass Sie einen Rückgabetyp für `Current` definieren können, der spezifischer als <xref:System.Object> ist.  Dies bietet Typsicherheit.  
  
 Ändern Sie beispielsweise die folgenden Zeilen im vorherigen Beispiel.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Da `Current` eine Zeichenfolge zurückgibt, kann der Compiler erkennen, ob in einer `foreach`\-Anweisung ein nicht kompatibler Typ verwendet wird, wie im folgenden Code gezeigt.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 Der Nachteil beim Weglassen von <xref:System.Collections.IEnumerable> und <xref:System.Collections.IEnumerator> besteht darin, dass die Auflistungsklasse nicht mehr mit den `foreach`\-Anweisungen oder entsprechenden Anweisungen anderer Common Language Runtime\-Sprachen verwendet werden kann.  
  
## Siehe auch  
 <xref:System.Collections.Generic>   
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Arrays](../../../csharp/programming-guide/arrays/index.md)   
 [Auflistungen](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)