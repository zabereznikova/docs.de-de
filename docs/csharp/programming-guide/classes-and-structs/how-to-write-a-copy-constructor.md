---
title: 'Gewusst wie: Schreiben eines Kopierkonstruktors – C#-Programmierhandbuch'
description: Hier erfahren Sie, wie Sie einen Kopierkonstruktor in C# erstellen, der eine Instanz einer Klasse akzeptiert und eine neue Instanz mit den Werten der Eingabe zurückgibt.
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: 52fd5aedea6a0e3b7c22e20db523329a00bba9ad
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204007"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a>Gewusst wie: Schreiben eines Kopierkonstruktors (C#-Programmierhandbuch)

C# stellt keinen Kopierkonstruktor für Objekte bereit. Sie können jedoch selbst einen schreiben.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird von der `Person`-[Klasse](../../language-reference/keywords/class.md) ein Kopierkonstruktor definiert, der eine Instanz von `Person` als sein Argument annimmt. Die Werte der Eigenschaften des Arguments werden den Eigenschaften der neuen Instanz von `Person` zugewiesen. Der Code enthält einen alternativen Kopierkonstruktor, der die `Name`- und `Age`-Eigenschaften der Instanz sendet, die Sie in den Instanzenkonstruktor der Klasse kopieren möchten.  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ICloneable>
- [C#-Programmierhandbuch](../index.md)
- [Klassen und Strukturen](./index.md)
- [Konstruktoren](./constructors.md)
- [Finalizer](./destructors.md)
