---
title: Definieren von Konstanten in C#
description: Hier erfahren Sie, wie Sie Konstanten in C# definieren. Dies sind Felder, deren Werte zur Kompilierzeit festgelegt werden. Verwenden Sie Konstanten, um aussagekräftige Namen für spezielle Werte bereitzustellen.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
ms.openlocfilehash: 42ea67e9012fd55fbceb8a7bad4c8df8bf6bf6da
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099386"
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
  
## <a name="see-also"></a>Siehe auch

- [Klassen und Strukturen](./index.md)
