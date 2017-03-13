---
title: "Key (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.AnonymousKey"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "anonymous types [Visual Basic], key"
  - "Key [Visual Basic]"
  - "Key keyword [Visual Basic]"
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Key (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Mit dem `Key`\-Schlüsselwort kann das Verhalten von Eigenschaften anonymer Typen festgelegt werden.  In Gleichheitstests zwischen Instanzen anonymen Typs und bei der Berechnung von Hashcodewerten werden nur als Haupteigenschaften deklarierte Eigenschaften einbezogen.  Die Werte von Haupteigenschaften können nicht geändert werden.  
  
 Eine Eigenschaft eines anonymen Typs wird als Haupteigenschaft gekennzeichnet, indem der Deklaration in der Initialisierungsliste das Schlüsselwort `Key` vorangestellt wird.  Im folgenden Beispiel sind `Airline` und `FlightNo` Haupteigenschaften, `Gate` jedoch nicht.  
  
 [!code-vb[VbVbalrAnonymousTypes#26](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_1.vb)]  
  
 Wenn ein neuer anonymer Typ erstellt wird, erbt er direkt von <xref:System.Object>.  Der Compiler überschreibt drei geerbte Member: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A> und <xref:System.Object.ToString%2A>.  Der Überschreibungscode, der für <xref:System.Object.Equals%2A> erzeugt wird, und <xref:System.Object.GetHashCode%2A> basieren auf Haupteigenschaften.  Wenn der betreffende Typ keine Haupteigenschaften hat, werden <xref:System.Object.GetHashCode%2A> und <xref:System.Object.Equals%2A> nicht überschrieben.  
  
## Gleichheit  
 Zwei Instanzen eines anonymen Typs sind gleich, wenn sie Instanzen desselben Typs sind und die Werte ihrer Haupteigenschaften übereinstimmen.  In folgenden Beispielen stimmt `flight2` mit `flight1` aus dem vorigen Beispiel überein, da sie Instanzen vom gleichen anonymen Typ sind und die gleichen Werte für ihre Haupteigenschaften haben.  `flight3` entspricht allerdings nicht `flight1`, da der Wert einer Haupteigenschaft abweicht: `FlightNo`.  Die Instanz `flight4` ist nicht der gleiche Typ wie `flight1`, da sie andere Eigenschaften als Haupteigenschaften festlegen.  
  
 [!code-vb[VbVbalrAnonymousTypes#27](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_2.vb)]  
  
 Wenn zwei Instanzen ohne Haupteigenschaften deklariert werden, sind sie auch dann nicht gleich, wenn Name, Typ, Reihenfolge und Wert übereinstimmen.  Eine Instanz ohne Haupteigenschaften gleicht nur sich selbst.  
  
 Weitere Informationen zu den Bedingungen, unter denen zwei Instanzen anonymen Typs Instanzen des gleichen anonymen Typs sind, finden Sie unter [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## Hashcodeberechnung  
 Wie <xref:System.Object.Equals%2A> basiert auch die unter <xref:System.Object.GetHashCode%2A> definierte Hashfunktion für einen anonymen Typ auf den Haupteigenschaften des Typs.  In den folgenden Beispielen wird die Interaktion zwischen Haupteigenschaften und Hashcodewerten veranschaulicht.  
  
 Instanzen eines anonymen Typs mit dem gleichen Wert für alle Haupteigenschaften verfügen auch dann über den gleichen Hashcodewert, wenn die Werte der Nicht\-Haupteigenschaften nicht übereinstimmen.  Die folgende Anweisung gibt `True` zurück.  
  
 [!code-vb[VbVbalrAnonymousTypes#37](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_3.vb)]  
  
 Instanzen eines anonymen Typs mit unterschiedlichen Werten für mindestens eine Haupteigenschaft verfügen über unterschiedliche Hashcodewerte.  Die folgende Anweisung gibt `False` zurück.  
  
 [!code-vb[VbVbalrAnonymousTypes#38](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_4.vb)]  
  
 Instanzen anonymen Typs, die unterschiedliche Eigenschaften als Haupteigenschaften festlegen, sind keine Instanzen des gleichen Typs.  Sie verfügen auch dann über verschiedene Hashcodewerte, wenn die Namen und Werte aller Eigenschaften gleich sind.  Die folgende Anweisung gibt `False` zurück.  
  
 [!code-vb[VbVbalrAnonymousTypes#39](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_5.vb)]  
  
## Schreibgeschützte Werte  
 Die Werte von Haupteigenschaften können nicht geändert werden.  In `flight1` aus obigen Beispielen sind die Felder `Airline` und `FlightNo` beispielsweise schreibgeschützt, das Feld `Gate` kann jedoch geändert werden.  
  
 [!code-vb[VbVbalrAnonymousTypes#28](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_6.vb)]  
  
## Siehe auch  
 [Anonymous Type Definition](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)   
 [Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)   
 [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)