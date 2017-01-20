---
title: "partial (Typ) (C#-Referenz) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "partialtype"
  - "partialtype_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Partielle Typen [C#]"
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# partial (Typ) (C#-Referenz)
Die Definitionen partieller Typen ermöglichen es, die Definition einer Klasse, einer Struktur oder einer Schnittstelle auf mehrere Dateien aufzuteilen.  
  
 In Datei1.cs:  
  
 [!code-cs[csrefKeywordsContextual#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_1.cs)]  
  
 In File2.cs die Deklaration:  
  
 [!code-cs[csrefKeywordsContextual#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_2.cs)]  
  
## Hinweise  
 Einen Klassen\-, Struktur\- oder Schnittstellentyp auf mehrere Dateien aufzuteilen kann hilfreich sein, wenn Sie mit großen Projekten oder mit automatisch generiertem Code wie dem von [Windows Forms Designer](http://msdn.microsoft.com/de-de/3c3d61f8-f36c-4d41-b9c3-398376fabb15) bereitgestellten Code arbeiten.  Ein partieller Typ kann eine [partielle Methode](../../../csharp/language-reference/keywords/partial-method.md) enthalten.  Weitere Informationen finden Sie unter [Partielle Klassen und Methoden](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)   
 [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md)