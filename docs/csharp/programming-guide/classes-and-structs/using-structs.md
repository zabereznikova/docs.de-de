---
title: "Verwenden von Strukturen (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "Strukturen (C#) verwenden"
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
caps.latest.revision: 28
caps.handback.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Verwenden von Strukturen (C#-Programmierhandbuch)
Der `struct`\-Typ eignet sich für die Darstellung von kompakten Objekten, z. B. `Point`, `Rectangle` und `Color`. Obwohl es ebenso einfach ist, einen Punkt als [Klasse](../../../csharp/language-reference/keywords/class.md) mit [automatisch implementierten Eigenschaften](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) darzustellen, kann eine [Struktur](../../../csharp/language-reference/keywords/struct.md) in verschiedenen Szenarien effizienter sein. Bei der Deklaration eines Arrays mit 1.000 `Point`\-Objekten belegen Sie z. B. zusätzlichen Arbeitsspeicher, damit auf jedes Objekt verwiesen werden kann. In diesem Fall wäre eine Struktur weniger speicherintensiv. Da [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] ein Objekt mit dem Namen <xref:System.Drawing.Point> enthält, wird die Struktur in diesem Beispiel stattdessen „CoOrds“ genannt.  
  
 [!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 Die Definition eines \(parameterlosen\) Standardkonstruktors für eine Struktur verursacht einen Fehler. Auch durch die Initialisierung eines Instanzenfelds in einem Strukturtext wird ein Fehler generiert. Die Strukturmember können nur mithilfe eines parametrisierten Konstruktors oder durch jeweils einzelnen Zugriff auf die Member im Anschluss an die Deklaration der Struktur initialisiert werden. Alle privaten oder auf andere Weise gesperrten Member können nur in einem Konstruktor initialisiert werden.  
  
 Wenn Sie ein Strukturobjekt mit dem Operator [new](../../../csharp/language-reference/keywords/new.md) erzeugen, wird das Objekt erstellt und der geeignete Konstruktor aufgerufen. Strukturen können im Gegensatz zu Klassen ohne den Operator `new` instanziiert werden. In einem solchen Fall gibt es keinen Konstruktoraufruf, sodass die Zuordnung effizienter ausgeführt werden kann. Die Felder werden jedoch nicht zugewiesen, und das Objekt kann erst verwendet werden, nachdem alle Felder initialisiert wurden.  
  
 Wenn eine Struktur einen Referenztyp als Member enthält, muss der Standardkonstruktor des Members explizit aufgerufen werden. Andernfalls wird der Member nicht zugeordnet, und die Struktur kann nicht verwendet werden. \(Dies führt zu Compilerfehler CS0171.\)  
  
 Bei Strukturen findet keine Vererbung wie bei Klassen statt. Eine Struktur kann nicht von einer anderen Struktur oder Klasse erben, und sie kann auch nicht die Basis einer Klasse sein. Stattdessen erben Strukturen von der <xref:System.Object>\-Basisklasse. Eine Struktur kann Schnittstellen implementieren. Dies geschieht auf dieselbe Weise wie bei Klassen.  
  
 Sie können keine Klasse mit dem `struct`\-Schlüsselwort deklarieren. Klassen und Strukturen weisen in C\# semantische Unterschiede auf. Eine Struktur ist ein Werttyp, während eine Klasse ein Referenztyp ist. Weitere Informationen finden Sie unter [Werttypen](../../../csharp/language-reference/keywords/value-types.md).  
  
 Sofern keine Semantik für Verweistypen benötigt wird, kann das System kleine Klassen effizienter verarbeiten, wenn diese als Struktur definiert werden.  
  
## Beispiel 1  
  
### Beschreibung  
 In diesem Beispiel wird die `struct`\-Initialisierung sowohl unter Verwendung von Standardkonstruktoren als auch unter Verwendung von parametrisierten Konstruktoren veranschaulicht.  
  
### Code  
 [!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 [!code-cs[csProgGuideObjects#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_2.cs)]  
  
## Beispiel 2  
  
### Beschreibung  
 Dieses Beispiel veranschaulicht ein Feature, das ausschließlich auf Strukturen anwendbar ist. Es wird ein CoOrds\-Objekt ohne Verwendung des Operators `new` erstellt. Wenn Sie den Begriff `struct` durch `class` ersetzen, wird das Programm nicht kompiliert.  
  
### Code  
 [!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 [!code-cs[csProgGuideObjects#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_3.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Strukturen](../../../csharp/programming-guide/classes-and-structs/structs.md)