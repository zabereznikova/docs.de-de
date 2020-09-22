---
title: Generische Klassen – C#-Programmierhandbuch
description: Erfahren Sie mehr über generische Klassen, die in Auflistungen wie verknüpften Listen, Hashtabellen, Stapeln, Warteschlangen und Strukturen verwendet werden.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generic classes
- generics [C#], classes
ms.assetid: 27d6f256-cd61-41e3-bc6e-b990a53b0224
ms.openlocfilehash: a885ae042eef939021d3a9b75616505c289bd43c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558086"
---
# <a name="generic-classes-c-programming-guide"></a>Generische Klassen (C#-Programmierhandbuch)
Generische Klassen kapseln Operationen, die nicht spezifisch für einen bestimmten Datentyp sind. Generische Klassen werden am häufigsten bei Auflistungen verwendet, z.B. bei verknüpften Listen, Hashtabellen, Stapeln, Warteschlangen, Strukturen usw. Vorgänge wie das Hinzufügen oder Entfernen von Elementen aus der Auflistung werden nahezu auf die gleiche Art und Weise ausgeführt, unabhängig vom Typ der gespeicherten Daten.  
  
 Für die meisten Szenarios, die Auflistungsklassen erfordern, wird empfohlen, die in der Klassenbibliothek von .NET bereitgestellten Auflistungsklassen zu verwenden. Weitere Informationen zur Verwendung dieser Klassen finden Sie unter [Generic Collections in .NET (Generische Auflistungen in .NET)](../../../standard/generics/collections.md).  
  
 In der Regel erstellen Sie generische Klassen, indem Sie von einer vorhandenen konkreten Klasse ausgehen und Typen in Typparameter ändern (einen nach dem anderen), bis das optimale Verhältnis zwischen Verallgemeinerung und Verwendbarkeit gefunden ist. Wenn Sie eigene generische Klassen erstellen möchten, sollten Sie die folgenden wichtigen Aspekte beachten:  
  
- Welche Typen sollen in Typparameter verallgemeinert werden.  
  
     Im Allgemeinen gilt: Je mehr Typen Sie parametrisieren können, umso flexibler und besser wiederverwendbar ist Ihr Code. Jedoch kann ein Zuviel an Verallgemeinerung zu Code führen, der von anderen Entwicklern nur schwer gelesen oder verstanden wird.  
  
- Welche Einschränkungen sollen ggf. auf die Typparameter angewendet werden (siehe [Constraints on Type Parameters (Einschränkungen für Typparameter)](./constraints-on-type-parameters.md)).  
  
     Es empfiehlt sich, alle Einschränkungen anzuwenden, die maximal möglich sind, und bei denen Sie dennoch sämtliche Typen, die Sie behandeln müssen, auch behandeln können. Wenn Sie zum Beispiel wissen, dass die generische Klasse nur mit Referenztypen verwendet werden soll, dann können Sie die Klasseneinschränkung anwenden. Dadurch wird verhindert, dass die Klasse unbeabsichtigt mit Werttypen verwendet wird. Gleichzeitig können Sie den Operator `as` für `T` verwenden und nach NULL-Werten suchen.  
  
- Ob das generische Verhalten in Basisklassen und Unterklassen zerlegt werden soll.  
  
     Da generische Klassen als Basisklassen dienen können, sind hier beim Entwurf die gleichen Aspekte zu berücksichtigen wie bei nicht generischen Klassen. Weitere Informationen bieten die Regeln zum Erben von generischen Basisklassen weiter unten in diesem Thema.  
  
- Ob eine oder mehrere generische Schnittstellen implementiert werden soll.  
  
     Wenn Sie beispielsweise eine Klasse entwerfen, die zum Erstellen von Elementen in einer Generics-basierten Auflistung verwendet wird, müssen Sie unter Umständen eine Schnittstelle implementieren, z.B. <xref:System.IComparable%601>, wobei `T` der Typ Ihrer Klasse ist.  
  
 Ein Beispiel für eine einfache generische Klasse finden Sie unter [Introduction to Generics (Einführung in Generics)](./index.md).  
  
 Die Regeln für Einschränkungen und Typparameter haben eine Reihe von Auswirkungen auf das Verhalten einer generischen Klasse, besonders im Hinblick auf Vererbung und Zugriff der Member. Bevor Sie fortfahren, sollten Sie einige Begriffe verstehen. Bei einer generischen Klasse kann der Clientcode `Node<T>,` auf die Klasse verweisen, indem er ein Typargument angibt, um einen geschlossenen konstruierten Typ (`Node<int>`) zu erstellen. Die Alternative besteht darin, den Typparameter nicht anzugeben, z.B. wenn Sie eine generische Basisklasse angeben, um einen offenen konstruierten Typ (`Node<T>`) zu erstellen. Generische Klassen können von konkreten, geschlossenen konstruierten oder offenen konstruierten Basisklassen erben:  
  
 [!code-csharp[csProgGuideGenerics#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#16)]  
  
 Nicht generische, also konkrete Klassen können von geschlossenen konstruierten Basisklassen erben, aber nicht von offenen konstruierten Klassen oder Typparametern, denn während der Laufzeit ist es für den Clientcode nicht möglich, das erforderliche Typargument bereitzustellen, das zum Instanziieren der Basisklasse benötigt wird.  
  
 [!code-csharp[csProgGuideGenerics#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#17)]  
  
 Generische Klassen, die von offenen konstruierten Typen erben, müssen für sämtliche Basisklassen-Typparameter, die von der erbenden Klasse nicht verwendet werden, Typargumente bereitstellen. Der folgende Code stellt ein Beispiel dafür dar:  
  
 [!code-csharp[csProgGuideGenerics#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#18)]  
  
 Generische Klassen, die von offenen konstruierten Typen erben, müssen Einschränkungen angeben, die den Einschränkungen des Basistyps übergeordnet sind oder diese implizieren:  
  
 [!code-csharp[csProgGuideGenerics#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#19)]  
  
 Generische Typen können mehrere Typparameter und Einschränkungen wie folgt verwenden:  
  
 [!code-csharp[csProgGuideGenerics#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#20)]  
  
 Offene konstruierte und geschlossene konstruierte Typen können als Methodenparameter verwendet werden:  
  
 [!code-csharp[csProgGuideGenerics#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#21)]  
  
 Wenn eine generische Klasse eine Schnittstelle implementiert, können alle Instanzen dieser Klasse in diese Schnittstelle umgewandelt werden.  
  
 Generische Klassen sind unveränderlich. Wenn also ein Eingabeparameter eine `List<BaseClass>` angibt, wird Ihnen ein Kompilierungsfehler angezeigt, falls Sie versuchen, eine `List<DerivedClass>` bereitzustellen.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Collections.Generic>
- [C#-Programmierhandbuch](../index.md)
- [Generics](./index.md)
- [Saving the State of Enumerators (Speichern des Zustands von Enumeratoren)](/archive/blogs/wesdyer/saving-the-state-of-enumerators)
- [An Inheritance Puzzle, Part One (Ein Vererbungs-Puzzle, Teil 1)](/archive/blogs/ericlippert/an-inheritance-puzzle-part-one)
