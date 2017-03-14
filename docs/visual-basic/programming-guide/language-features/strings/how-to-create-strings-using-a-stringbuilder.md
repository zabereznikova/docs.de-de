---
title: "How to: Create Strings Using a StringBuilder in Visual Basic | Microsoft Docs"
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
  - "StringBuilder class"
  - "strings [Visual Basic], using StringBuilder"
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# How to: Create Strings Using a StringBuilder in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

In diesem Beispiel wird mit der <xref:System.Text.StringBuilder>\-Klasse aus vielen kleineren Zeichenfolgen eine lange Zeichenfolge erstellt.  Die Verkettung vieler Zeichenfolgen lässt sich mit der <xref:System.Text.StringBuilder>\-Klasse rationeller ausführen als mit dem Operator `&=`.  
  
## Beispiel  
 Im folgenden Beispiel wird eine Instanz der <xref:System.Text.StringBuilder>\-Klasse erstellt, 1.000 Zeichenfolgen werden an diese Instanz angehängt, und dann wird die Zeichenfolgendarstellung der Instanz zurückgegeben.  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## Siehe auch  
 [Verwenden der StringBuilder\-Klasse](../Topic/Using%20the%20StringBuilder%20Class%20in%20the%20.NET%20Framework.md)   
 [&\= Operator](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)   
 [Strings](../../../../visual-basic/programming-guide/language-features/strings/index.md)   
 [Erstellen neuer Zeichenfolgen](../Topic/Creating%20New%20Strings%20in%20the%20.NET%20Framework.md)   
 [Bearbeiten von Zeichenfolgen](../Topic/Manipulating%20Strings%20in%20the%20.NET%20Framework.md)   
 [Strings Sample](http://msdn.microsoft.com/de-de/be9e82a3-dc95-4aaa-9396-61b66e467e02)