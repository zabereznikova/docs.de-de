---
title: '&#39; &lt;Typename&gt;&#39; ein Delegattyp'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9428f0ac321b90e36d4d987381ed69b6c968894c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="39lttypenamegt39-is-a-delegate-type"></a>&#39; &lt;Typename&gt;&#39; ein Delegattyp
"\<Typname >' ein Delegattyp ist. Erstellen eines Delegaten kann nur einen einzelnen AddressOf-Ausdruck als Argument übergeben. AddressOf-Ausdruck kann häufig statt eine Delegatkonstruktion verwendet werden.  
  
 Ein `New` -Klausel erstellt eine Instanz einer Delegatklasse liefert eine ungültige Argumentliste an den Delegatkonstruktor.  
  
 Sie können angeben, dass nur ein einzelner `AddressOf` Ausdruck beim Erstellen einer neuen Delegatinstanz.  
  
 Dieser Fehler kann auftreten, wenn Sie keine Argumente an den Delegatkonstruktor übergeben wenn Sie mehr als ein Argument übergeben, oder wenn Sie ein einzelnes Argument übergeben, die keine gültige `AddressOf` Ausdruck.  
  
 **Fehler-ID:** BC32008  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Ein einzelnes `AddressOf` Ausdruck in der Argumentliste für die Delegate-Klasse in der `New` Klausel.  
  
## <a name="see-also"></a>Siehe auch  
 [New-Operator](../../../visual-basic/language-reference/operators/new-operator.md)  
 [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Gewusst wie: Aufrufen einer Delegatenmethode](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
