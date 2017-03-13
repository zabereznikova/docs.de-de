---
title: "Generische Klassen (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Generische Klassen"
  - "Generika [C#], Klassen"
ms.assetid: 27d6f256-cd61-41e3-bc6e-b990a53b0224
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# Generische Klassen (C#-Programmierhandbuch)
Generische Klassen kapseln Operationen, die nicht spezifisch für einen bestimmten Datentyp sind.  Generische Klassen werden am häufigsten bei Auflistungen verwendet, z. B. bei verknüpften Listen, Hashtabellen, Stapeln, Warteschlangen, Strukturen usw.  Vorgänge wie das Hinzufügen oder Entfernen von Elementen aus der Auflistung werden nahezu auf die gleiche Art und Weise ausgeführt, unabhängig vom Typ der gespeicherten Daten.  
  
 Für die meisten Szenarios, die Auflistungsklassen erfordern, wird empfohlen, die in der Klassenbibliothek von .NET Framework 2.0 bereitgestellten Auflistungsklassen zu verwenden.  Weitere Informationen zur Verwendung dieser Klassen finden Sie unter [Generika in der .NET Framework\-Klassenbibliothek](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).  
  
 In der Regel erstellen Sie generische Klassen, indem Sie von einer vorhandenen konkreten Klasse ausgehen und Typen in Typparameter ändern \(einen nach dem anderen\), bis das optimale Verhältnis zwischen Verallgemeinerung und Verwendbarkeit gefunden ist.  Wenn Sie eigene generische Klassen erstellen möchten, sollten Sie die folgenden wichtigen Aspekte beachten:  
  
-   Welche Typen sollen in Typparameter verallgemeinert werden.  
  
     Im Allgemeinen gilt: Je mehr Typen Sie parametrisieren können, umso flexibler und besser wiederverwendbar ist Ihr Code.  Jedoch kann ein Zuviel an Verallgemeinerung zu Code führen, der von anderen Entwicklern nur schwer gelesen oder verstanden wird.  
  
-   Welche Einschränkungen sollen ggf. auf die Typparameter angewendet werden \(siehe [Einschränkungen für Typparameter](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)\).  
  
     Es empfiehlt sich, alle Einschränkungen anzuwenden, die maximal möglich sind, und bei denen Sie dennoch sämtliche Typen, die Sie behandeln müssen, auch behandeln können.  Wenn Sie zum Beispiel wissen, dass die generische Klasse nur mit Referenztypen verwendet werden soll, dann können Sie die Klasseneinschränkung anwenden.  Dadurch wird verhindert, dass die Klasse unbeabsichtigt mit Werttypen verwendet wird. Gleichzeitig können Sie den Operator `as` für `T` verwenden und nach NULL\-Werten suchen.  
  
-   Ob das generische Verhalten in Basisklassen und Unterklassen zerlegt werden soll.  
  
     Da generische Klassen als Basisklassen dienen können, sind hier beim Entwurf die gleichen Aspekte zu berücksichtigen wie bei nicht generischen Klassen.  Weitere Informationen bieten die Regeln zum Erben von generischen Basisklassen weiter unten in diesem Thema.  
  
-   Ob eine oder mehrere generische Schnittstellen implementiert werden soll.  
  
     Wenn Sie beispielsweise eine Klasse entwerfen, die zum Erstellen von Elementen in einer generisch basierten Auflistung verwendet wird, müssen Sie unter Umständen eine Schnittstelle implementieren, z. B. <xref:System.IComparable%601>, wobei `T` der Typ Ihrer Klasse ist.  
  
 Ein Beispiel für eine einfache generische Klasse finden Sie unter [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md).  
  
 Die Regeln für Einschränkungen und Typparameter haben eine Reihe von Auswirkungen auf das Verhalten einer generischen Klasse, besonders im Hinblick auf Vererbung und Zugriff der Member.  Bevor Sie fortfahren, sollten Sie einige Begriffe verstehen.  Bei einer generischen Klasse kann der `Node<T>,`\-Clientcode auf die Klasse verweisen, indem er ein Typargument angibt, um einen geschlossenen konstruierten Typ zu erstellen \(`Node<int>`\).  Die Alternative besteht darin, den Typparameter nicht anzugeben, z. B. wenn Sie eine generische Basisklasse angeben, um einen offenen konstruierten Typ \(`Node<T>`\) zu erstellen.  Generische Klassen können von konkreten, geschlossenen konstruierten oder offenen konstruierten Basisklassen erben:  
  
 [!code-cs[csProgGuideGenerics#16](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_1.cs)]  
  
 Nicht generische, d. h. konkrete Klassen können von geschlossenen konstruierten Basisklassen erben, aber nicht von offenen konstruierten Klassen oder Typparametern, denn während der Laufzeit ist es für den Clientcode nicht möglich, das erforderliche Typargument bereitzustellen, das zum Instanziieren der Basisklasse benötigt wird.  
  
 [!code-cs[csProgGuideGenerics#17](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_2.cs)]  
  
 Generische Klassen, die von offenen konstruierten Typen erben, müssen für sämtliche Basisklassen\-Typparameter, die von der erbenden Klasse nicht verwendet werden, Typargumente bereitstellen. Der folgende Code stellt ein Beispiel dafür dar:  
  
 [!code-cs[csProgGuideGenerics#18](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_3.cs)]  
  
 Generische Klassen, die von offenen konstruierten Typen erben, müssen Einschränkungen angeben, die den Einschränkungen des Basistyps übergeordnet sind oder diese implizieren.  
  
 [!code-cs[csProgGuideGenerics#19](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_4.cs)]  
  
 Generische Typen können mehrere Typparameter und Einschränkungen verwenden. Beispiel:  
  
 [!code-cs[csProgGuideGenerics#20](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_5.cs)]  
  
 Offene konstruierte und geschlossene konstruierte Typen können als Methodenparameter verwendet werden:  
  
 [!code-cs[csProgGuideGenerics#21](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_6.cs)]  
  
 Wenn eine generische Klasse eine Schnittstelle implementiert, können alle Instanzen dieser Klasse in diese Schnittstelle umgewandelt werden.  
  
 Generische Klassen sind unveränderlich.  Dies bedeutet: Wenn ein Eingabeparameter eine `List<BaseClass>` angibt, wird Ihnen ein Kompilierungsfehler angezeigt, falls Sie versuchen, eine `List<DerivedClass>` bereitzustellen.  
  
## Siehe auch  
 <xref:System.Collections.Generic>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Generika](../../../csharp/programming-guide/generics/index.md)   
 [Speichern des Zustands von Enumeratoren](http://go.microsoft.com/fwlink/?LinkId=112390)   
 [Ein Vererbungs\-Puzzle, Teil 1](http://go.microsoft.com/fwlink/?LinkId=112380)