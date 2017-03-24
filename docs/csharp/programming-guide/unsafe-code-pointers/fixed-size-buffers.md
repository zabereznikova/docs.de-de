---
title: "Puffer fester Gr&#246;&#223;e (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Puffer fester Größe [C#]"
  - "Unsichere Puffer [C#]"
  - "Unsicherer Code [C#], Puffer fester Größe"
ms.assetid: 6220d454-947c-4977-ac9d-9308c6ed5051
caps.latest.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 31
---
# Puffer fester Gr&#246;&#223;e (C#-Programmierhandbuch)
In C\# können Sie mit der [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)\-Anweisung einen Puffer mit einem Array fester Größe in einer Datenstruktur erstellen.  Dies bietet sich an, wenn Sie mit vorhandenem Code wie Code aus anderen Programmiersprachen, vorhandenen DLLs oder COM\-Projekten arbeiten.  Das Array fester Größe kann sämtliche Attribute und Modifizierer verwenden, die für reguläre Strukturmember zulässig sind.  Die einzige Einschränkung ist die, dass das Array vom Typ `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` oder `double` sein muss.  
  
```  
private fixed char name[30];  
```  
  
## Hinweise  
 In frühen Versionen von C\# war es schwierig, eine Struktur im C\+\+\-Stil mit fester Größe zu deklarieren, da eine C\#\-Struktur, die ein Array enthält, die Arrayelemente nicht enthält.  Stattdessen enthält die Struktur einen Verweis auf die Elemente.  
  
 In C\# 2.0 kann ein Array fester Größe in eine [Struktur](../../../csharp/language-reference/keywords/struct.md) eingebettet werden, wenn diese in einem [unsafe](../../../csharp/language-reference/keywords/unsafe.md)\-Codeblock verwendet wird.  
  
 Zum Beispiel wäre vor C\# 2.0 die folgende `struct` 8 Bytes groß.  Das `pathName`\-Array ist ein Verweis auf das Heap\-zugeordnete Array:  
  
 [!code-cs[csProgGuidePointers#19](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_1.cs)]  
  
 Beginnend mit C\# 2.0 kann `struct` einen eingebetteten Array enthalten.  Im folgenden Beispiel hat der `fixedBuffer`\-Array eine feste Größe.  Um auf die Elemente des Arrays zuzugreifen, legen Sie mit einer `fixed`\-Anweisung einen Zeiger auf das erste Element fest.  Die `fixed`\-Anweisung fixiert eine Instanz von `fixedBuffer` an einer bestimmten Position im Arbeitsspeicher.  
  
 [!code-cs[csProgGuidePointers#20](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_2.cs)]  
  
 Die Größe des 128 Elemente umfassenden `char`\-Arrays beträgt 256 Bytes.  [char](../../../csharp/language-reference/keywords/char.md)\-Puffer fester Größe beanspruchen ungeachtet der Codierung immer zwei Bytes pro Zeichen.  Dies gilt selbst dann, wenn char\-Puffer mit `CharSet = CharSet.Auto` oder `CharSet = CharSet.Ansi` zu API\-Methoden oder Strukturen gemarshallt werden.  Weitere Informationen finden Sie unter <xref:System.Runtime.InteropServices.CharSet>.  
  
 Ein weiteres häufig verwendetes Array fester Größe ist das [bool](../../../csharp/language-reference/keywords/bool.md)\-Array.  Die Elemente in einem `bool`\-Array sind immer ein Byte groß.  `bool`\-Arrays sind nicht geeignet für das Erstellen von Bitarrays oder Puffern.  
  
> [!NOTE]
>  Außer bei mit [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md) generiertem Speicher führen der C\#\-Compiler und die Common Language Runtime \(CLR\) keine Sicherheitsprüfungen zum Pufferüberlauf durch.  Wie bei jedem unsicheren Code ist auch hier Vorsicht geboten.  
  
 Nicht sichere Puffer unterscheiden sich wie folgt von regulären Arrays:  
  
-   Sie können nicht sichere Puffer nur in einem nicht sicheren Kontext verwenden.  
  
-   Nicht sichere Puffer sind immer Vektoren oder eindimensionale Arrays.  
  
-   Die Deklaration des Arrays muss eine Anzahl enthalten, z. B. `char id[8]`.  `char id[]` dagegen ist nicht zulässig.  
  
-   Nicht sichere Puffer können nur Instanzfelder von Strukturen in einem nicht sicheren Kontext sein.  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [fixed\-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [Interoperabilität](../../../csharp/programming-guide/interop/interoperability.md)