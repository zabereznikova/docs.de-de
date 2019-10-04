---
title: Strukturen – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: df2a235651a2242ffe18df377dce9995af31e99f
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392451"
---
# <a name="structs-c-programming-guide"></a>Strukturen (C#-Programmierhandbuch)

Strukturen werden mit dem [struct](../../language-reference/keywords/struct.md)-Schlüsselwort definiert, beispielsweise:  
  
 [!code-csharp[csProgGuideObjects#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#39)]  
  
Strukturen weisen größtenteils die gleiche Syntax wie Klassen auf. Der Name der Struktur muss ein gültiger C#- [Bezeichnername](../inside-a-program/identifier-names.md) sein. Strukturen sind auf folgende Weisen eingeschränkter als Klassen:  
  
- Innerhalb einer Strukturdeklaration können Felder nicht initialisiert werden, außer Sie werden als const oder static deklariert.  
- Eine Struktur kann keinen parameterlosen Konstruktor (einen Konstruktor ohne Parameter) oder Finalizer deklarieren.  
- Strukturen werden bei Zuweisung kopiert. Wenn eine Struktur einer neuen Variable zugewiesen wird, werden alle Daten kopiert, und jede Änderung an der neuen Kopie ändert nicht die Daten für das Original. Es ist wichtig, sich das zu merken, wenn Sie mit Sammlungen von Wertetypen wie `Dictionary<string, myStruct>` arbeiten.  
- Im Gegensatz zu Klassen, die Verweistypen sind, sind Strukturen Werttypen.  
- Strukturen können im Gegensatz zu Klassen ohne den Operator `new` instanziiert werden.  
- Strukturen können Konstruktoren deklarieren, die Parameter besitzen.
- Eine Struktur kann nicht von einer anderen Struktur oder Klasse erben, und sie kann auch nicht die Basis einer Klasse sein. Alle Strukturen erben direkt von <xref:System.ValueType>, das von <xref:System.Object> erbt.  
- Eine Struktur kann Schnittstellen implementieren.
- Eine Struktur kann nicht `null` sein, und eine Strukturvariable kann nicht `null` zugewiesen werden, wenn die Variable nicht als Nullable-Werttyp deklariert ist.
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Klassen und Strukturen](index.md)
- [Klassen](classes.md)
- [Auf NULL festlegbare Werttypen](../nullable-types/index.md)
- [Bezeichnernamen](../inside-a-program/identifier-names.md)
- [Verwenden von Strukturen](using-structs.md)
- [Vorgehensweise: Unterschiede zwischen dem Übergeben einer Struktur und dem Übergeben eines Klassenverweises an eine Methode](how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)
