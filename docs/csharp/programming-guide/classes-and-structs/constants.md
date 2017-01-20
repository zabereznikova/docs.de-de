---
title: "Konstanten (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "C#-Sprache, Konstanten"
  - "Konstanten [C#]"
ms.assetid: 1fb39621-1738-49b1-a1b3-8587f109123f
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Konstanten (C#-Programmierhandbuch)
Konstanten sind unveränderliche Werte, die bei der Kompilierung bekannt sind und sich während der Ausführung des Programms nie ändern.  Konstanten werden mit dem [const](../../../csharp/language-reference/keywords/const.md)\-Modifizierer deklariert.  Nur die integrierten Typen von C\# \(außer <xref:System.Object?displayProperty=fullName>\) können als `const` deklariert werden.  Eine Liste der integrierten Typen finden Sie unter [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md).  Benutzerdefinierte Typen, einschließlich Klassen, Strukturen und Arrays, können nicht als `const` deklariert werden.  Verwenden Sie den [readonly](../../../csharp/language-reference/keywords/readonly.md)\-Modifizierer, um eine Klasse, eine Struktur oder ein Array zu erstellen, das zur Laufzeit einmalig initialisiert wird \(beispielsweise in einem Konstruktor\) und danach nicht mehr geändert werden kann.  
  
 In C\# werden keine `const`\-Methoden, \-Eigenschaften oder \-Ereignisse unterstützt.  
  
 Mithilfe des **enum**\-Typs können benannte Konstanten für ganzzahlige integrierte Typen \(z. B. `int`, `uint`, `long` usw.\) definiert werden.  Weitere Informationen finden Sie unter [enum](../../../csharp/language-reference/keywords/enum.md).  
  
 Konstanten müssen bereits bei der Deklaration initialisiert werden.  Beispiele:  
  
 [!code-cs[csProgGuideObjects#64](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_1.cs)]  
  
 In diesem Beispiel hat die Konstante `months` stets den Wert 12. Der Wert kann auch durch die Klasse selbst nicht geändert werden.  Wenn der Compiler in C\#\-Quellcode auf einen Konstantenbezeichner trifft \(z. B. `months`\), ersetzt er den literalen Wert direkt in den von ihm erstellten Intermediate Language \(IL\)\-Code.  Da einer Konstanten zur Laufzeit keine Variablenadresse zugeordnet ist, können `const`\-Felder nicht als Verweis übergeben oder als L\-Wert in einem Ausdruck verwendet werden.  
  
> [!NOTE]
>  Seien Sie vorsichtig, wenn Sie auf in anderem Code, z. B. DLLs, definierte konstante Werte verweisen.  Wenn in einer neuen Version der DLL ein neuer Wert für die Konstante definiert wird, verwendet Ihr Programm weiterhin den alten literalen Wert, bis es mit der neuen Version erneut kompiliert wird.  
  
 Es ist möglich, mehrere Konstanten desselben Typs gleichzeitig zu deklarieren, zum Beispiel folgendermaßen:  
  
 [!code-cs[csProgGuideObjects#65](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_2.cs)]  
  
 Der Ausdruck, der für die Initialisierung einer Konstante verwendet wird, kann auf eine andere Konstante verweisen, wenn dies nicht zu einem Zirkelverweis führt.  Beispiele:  
  
 [!code-cs[csProgGuideObjects#66](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_3.cs)]  
  
 Konstanten können als [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) oder `protected` `internal` gekennzeichnet werden.  Diese Zugriffsmodifizierer definieren, wie Benutzer der Klasse auf die Konstante zugreifen können.  Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Auf Konstanten wird wie auf [static](../../../csharp/language-reference/keywords/static.md)\-Felder zugegriffen, da der Wert der Konstanten für alle Instanzen des Typs derselbe ist.  Für ihre Deklaration wird nicht das `static`\-Schlüsselwort verwendet.  In Ausdrücken außerhalb der Klasse, in der die Konstante definiert wird, erfolgt der Zugriff auf die Konstante über den Klassennamen, gefolgt von einem Punkt und dem Namen der Konstante.  Beispiele:  
  
 [!code-cs[csProgGuideObjects#67](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_4.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Typen](../../../csharp/programming-guide/types/index.md)   
 [readonly](../../../csharp/language-reference/keywords/readonly.md)   
 [Unveränderlichkeit in C\# Teil 1: Arten von Unveränderlichkeit](http://go.microsoft.com/fwlink/?LinkId=112379)