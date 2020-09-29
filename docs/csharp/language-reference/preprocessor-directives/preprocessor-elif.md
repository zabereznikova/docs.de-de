---
description: '#elif – C#-Referenz'
title: '#elif – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: 383c143792a39bb3abcd255804360ad5e2f8ef74
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168698"
---
# <a name="elif-c-reference"></a>#elif (C#-Referenz)

Mit `#elif` können zusammengesetzte bedingte Direktiven erstellt werden. Der `#elif`-Ausdruck wird ausgewertet, wenn weder der Ausdruck der vorangehenden [#if](./preprocessor-if.md)-Anweisung noch der Ausdruck einer vorangehenden optionalen `#elif`-Anweisung zu `true` ausgewertet wird. Wenn ein `#elif`-Ausdruck zu `true` ausgewertet wird, wird der gesamte Code zwischen der `#elif`-Direktive und der nächsten bedingten Direktive vom Compiler ausgewertet. Beispiel:  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.WriteLine("Debug build");  
#elif VC7  
    Console.WriteLine("Visual Studio 7");  
#endif  
```  
  
 Die Operatoren `==` (Gleichheit), `!=` (Ungleichheit), `&&` (und) und `||` (oder) können zur Auswertung mehrerer Symbole verwendet werden. Symbole und Operatoren können auch mit Klammern gruppiert werden.  
  
## <a name="remarks"></a>Bemerkungen  

 `#elif` ist identisch mit der Verwendung von:  
  
```csharp
#else  
#if  
```  
  
 Die Verwendung von `#elif` ist einfacher, da für jedes `#if` ein [#endif](./preprocessor-endif.md) erforderlich ist, während ein `#elif` ohne ein entsprechendes `#endif` verwendet werden kann.  
  
 Unter [#if](./preprocessor-if.md) finden Sie ein Beispiel zur Verwendung von `#elif`.  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Präprozessoranweisungen](./index.md)
