---
title: Zeigerkonvertierungen – C#-Programmierhandbuch
description: Erfahren Sie mehr über Zeigerkonvertierungen. Hier finden Sie Tabellen mit impliziten und expliziten Zeigerkonvertierungen, Codebeispiele und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 7a37c4e9f6333c00c7842df0fdaf353df516974d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205073"
---
# <a name="pointer-conversions-c-programming-guide"></a>Zeigerkonvertierungen (C#-Programmierhandbuch)

Die folgende Tabelle zeigt vordefinierte implizite Zeigerkonvertierungen. Implizite Konvertierungen können in vielen Situationen auftreten, einschließlich methodenaufrufender und Zuweisungsansweisungen.  
  
## <a name="implicit-pointer-conversions"></a>Implizite Zeigerkonvertierungen  
  
|Von|Beschreibung|  
|----------|--------|  
|Beliebiger Zeigertyp|void*|  
|NULL|Beliebiger Zeigertyp|  
  
 Die explizite Zeigerkonvertierung wird verwendet, um Konvertierungen, für die keine implizite Konvertierung vorliegt, mithilfe eines CAST-Ausdrucks durchzuführen. Die folgende Tabelle zeigt diese Konvertierungen.  
  
## <a name="explicit-pointer-conversions"></a>Explizite Zeigerkonvertierungen  
  
|Von|Beschreibung|  
|----------|--------|  
|Beliebiger Zeigertyp|Ein beliebiger anderer Zeigertyp|  
|sbyte, byte, short, ushort, int, uint, long oder ulong|Beliebiger Zeigertyp|  
|Beliebiger Zeigertyp|sbyte, byte, short, ushort, int, uint, long oder ulong|  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird ein Zeiger auf `int` in einen Zeiger auf `byte` konvertiert. Beachten Sie, dass der Zeiger auf das Byte der Variable mit der niedrigsten Adresse zeigt. Wenn Sie das Ergebnis nach und nach bis auf die Größe von `int` (4 Bytes) erhöhen, können Sie die verbleibenden Bytes der Variable anzeigen.  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Zeigertypen](pointer-types.md)
- [Verweistypen](../../language-reference/keywords/reference-types.md)
- [Werttypen](../../language-reference/builtin-types/value-types.md)
- [unsafe](../../language-reference/keywords/unsafe.md)
- [fixed-Anweisung](../../language-reference/keywords/fixed-statement.md)
- [stackalloc](../../language-reference/operators/stackalloc.md)
