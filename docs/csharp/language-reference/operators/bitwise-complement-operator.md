---
title: Operator ~ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- ~_CSharpKeyword
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
ms.openlocfilehash: 8af25217f9e7e66796192783a0b8e3415604dc90
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933181"
---
# <a name="-operator-c-reference"></a>Operator ~ (C#-Referenz)
Der `~`-Operator führt einen bitweisen komplementären Vorgang für seinen Operanden durch, wodurch jedes Bit umgekehrt wird. Bitweiser Komplementoperatoren sind für [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) und [ulong](../../../csharp/language-reference/keywords/ulong.md) vordefiniert.  
  
> [!NOTE]
>  Das `~`-Symbol wird auch für das Deklarieren von Finalizern verwendet. Weitere Informationen finden Sie unter [Finalizer](../../../csharp/programming-guide/classes-and-structs/destructors.md).  
  
## <a name="remarks"></a>Hinweise  
 Benutzerdefinierte Typen können den Operator `~` überladen. Weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md). Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Operatoren](../../../csharp/language-reference/operators/index.md)  
- [Finalizer](../../../csharp/programming-guide/classes-and-structs/destructors.md)
