---
title: Definieren von Konstanten in C#
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
ms.openlocfilehash: 15526655de8af6fed464376db1ac761468215210
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75337656"
---
# <a name="how-to-define-constants-in-c"></a>Definieren von Konstanten in C\#
Konstanten sind Felder, deren Wert bei der Kompilierung festgelegt wird und nie geändert werden kann. Verwenden Sie Konstanten, um aussagekräftige Namen anstelle numerischer Literale („magische Zahlen“) für spezielle Werte bereitzustellen.  
  
> [!NOTE]
> In C# kann die Präprozessoranweisung [#define](../../language-reference/preprocessor-directives/preprocessor-define.md) nicht verwendet werden, um Konstanten zu definieren, so wie Sie es normalerweise in C und C++ tun würden.  
  
 Verwenden Sie zum Definieren von konstanten Werten integraler Typen (`int`, `byte` usw.) einen enumerierten Typ. Weitere Informationen finden Sie unter [enum](../../language-reference/builtin-types/enum.md).  
  
 Zum Definieren nicht-integraler Konstanten ist eine Methode, diese in einer einzelnen statischen Klasse namens `Constants` zu gruppieren. Dies erfordert, dass allen Verweise auf die Konstanten, so wie im folgenden Beispiel gezeigt, der Klassenname vorangestellt wird.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideObjects#89](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#89)]  
  
 Die Verwendung des Klassennamenqualifizierers hilft Ihnen sicherzustellen, dass Sie und andere Benutzer der Konstante verstehen, dass diese konstant ist und nicht verändert werden kann.  
  
## <a name="see-also"></a>Weitere Informationen

- [Klassen und Strukturen](./index.md)
