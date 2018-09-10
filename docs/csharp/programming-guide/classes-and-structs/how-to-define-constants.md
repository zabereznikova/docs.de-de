---
title: 'Gewusst wie: Definieren von Konstanten in C#'
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
ms.openlocfilehash: 09d19f708570b55509a3ec2a41e439cb9c9de973
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43739694"
---
# <a name="how-to-define-constants-in-c"></a>Gewusst wie: Definieren von Konstanten in C#
Konstanten sind Felder, deren Wert bei der Kompilierung festgelegt wird und nie geändert werden kann. Verwenden Sie Konstanten, um aussagekräftige Namen anstelle numerischer Literale („magische Zahlen“) für spezielle Werte bereitzustellen.  
  
> [!NOTE]
>  In C# kann die Präprozessoranweisung [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) nicht verwendet werden, um Konstanten zu definieren, so wie Sie es normalerweise in C und C++ tun würden.  
  
 Verwenden Sie zum Definieren von konstanten Werten integraler Typen (`int`, `byte` usw.) einen enumerierten Typ. Weitere Informationen finden Sie unter [enum](../../../csharp/language-reference/keywords/enum.md).  
  
 Zum Definieren nicht-integraler Konstanten ist eine Methode, diese in einer einzelnen statischen Klasse namens `Constants` zu gruppieren. Dies erfordert, dass allen Verweise auf die Konstanten, so wie im folgenden Beispiel gezeigt, der Klassenname vorangestellt wird.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideObjects#89](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-constants_1.cs)]  
  
 Die Verwendung des Klassennamenqualifizierers hilft Ihnen sicherzustellen, dass Sie und andere Benutzer der Konstante verstehen, dass diese konstant ist und nicht verändert werden kann.  
  
## <a name="see-also"></a>Siehe auch

- [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)
