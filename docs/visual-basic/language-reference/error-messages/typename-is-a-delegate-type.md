---
title: '&quot;&lt;Typename&gt;&quot;ist ein Delegattyp | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32008
- vbc32008
dev_langs:
- VB
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3d6cc283f7e9815eb9b723a450731998f14b3424
ms.lasthandoff: 03/13/2017

---
# <a name="39lttypenamegt39-is-a-delegate-type"></a>'&lt;Typename&gt;"ist ein Delegattyp
'\<Typename > "ist ein Delegattyp. Erstellen eines Delegaten kann nur einen einzelnen AddressOf-Ausdruck als Argument übergeben. Ein AddressOf-Ausdruck kann oft statt einen Delegaten zu erstellen verwendet werden.  
  
 Ein `New` -Klausel erstellt eine Instanz einer Delegatklasse gibt eine ungültige Argumentliste an den Delegatkonstruktor.  
  
 Sie können angeben, dass nur eine einzige `AddressOf` Ausdruck beim Erstellen einer neuen Delegatinstanz.  
  
 Dieser Fehler kann auftreten, wenn Sie keine Argumente an den Delegatkonstruktor übergeben wenn Sie mehr als ein Argument übergeben, oder wenn Sie ein einzelnes Argument übergeben, die keine gültige `AddressOf` Ausdruck.  
  
 **Fehler-ID:** BC32008  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verwenden Sie einen einzelnen `AddressOf` Ausdruck in der Argumentliste für die Delegatklasse der `New` Klausel.  
  
## <a name="see-also"></a>Siehe auch  
 [New-Operator](../../../visual-basic/language-reference/operators/new-operator.md)   
 [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Gewusst wie: Aufrufen einer Delegatenmethode](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
