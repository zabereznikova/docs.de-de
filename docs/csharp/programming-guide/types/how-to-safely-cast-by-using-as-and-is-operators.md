---
title: "Gewusst wie: Sichere Umwandlung mit den Operatoren &quot;as&quot; und &quot;is&quot; (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "as-Operator [C#]"
  - "Umwandlungsoperatoren [C#], as und is (Operatoren)"
  - "is-Operator [C#]"
ms.assetid: c1176cea-1426-4a44-8570-3eadafa58863
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Sichere Umwandlung mit den Operatoren &quot;as&quot; und &quot;is&quot; (C#-Programmierhandbuch)
Da Objekte polymorph sind, kann eine Variable eines Basisklassentyps einen abgeleiteten Typ enthalten.  Zum Zugreifen auf die Methode des angeleiteten Typs muss der Wert wieder in den abgeleiteten Typ umgewandelt werden.  Wenn Sie in diesen Fällen jedoch versuchen, eine einfache Umwandlung durchzuführen, riskieren Sie das Auslösen einer <xref:System.InvalidCastException>.  Dies ist der Grund, warum C\# die Operatoren [is](../../../csharp/language-reference/keywords/is.md) und [as](../../../csharp/language-reference/keywords/as.md) bereitstellt.  Sie können diese Operatoren verwenden, um zu testen, ob eine Umwandlung erfolgreich sein wird, ohne dass eine Ausnahme ausgelöst wird.  Im Allgemeinen ist der Operator `as` effizienter, da er tatsächlich den Umwandlungswert zurückgibt, falls die Umwandlung erfolgreich durchgeführt werden kann.  Der `is`\-Operator gibt nur einen booleschen Wert zurück.  Er kann deshalb verwendet werden, wenn Sie nur den Objekttyp ermitteln möchten, ihn aber nicht umwandeln müssen.  
  
## Beispiel  
 In den folgenden Beispielen wird dargestellt, wie die Operatoren `is` und `as` zum Umwandeln von einem Referenztyp in einen anderen verwendet werden, ohne dass eine Ausnahme ausgelöst wird.  Im Beispiel wird auch dargestellt, wie der `as`\-Operator mit auf NULL festlegbaren Werttypen verwendet wird.  
  
 [!code-cs[csProgGuideTypes#40](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-safely-cast-by-using_1.cs)]  
  
## Siehe auch  
 [Typen](../../../csharp/programming-guide/types/index.md)   
 [Umwandlung und Typkonvertierungen](../../../csharp/programming-guide/types/casting-and-type-conversions.md)   
 [Typen, die NULL\-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md)