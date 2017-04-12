---
title: "Typ &quot;&lt;Typename&gt;&quot; verfügt über keine Konstruktoren | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30251
- vbc30251
dev_langs:
- VB
helpviewer_keywords:
- BC30251
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
caps.latest.revision: 9
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
ms.openlocfilehash: 505e3bbdfa830394efcea7226897ec0d3e6d2b02
ms.lasthandoff: 03/13/2017

---
# <a name="type-39lttypenamegt39-has-no-constructors"></a>Typ '&lt;Typename&gt;' verfügt über keine Konstruktoren
Ein Typ unterstützt nicht den Aufruf von `Sub New()`. Eine mögliche Ursache ist ein beschädigter Compiler oder eine fehlerhafte Binärdatei.  
  
 **Fehler-ID:** BC30251  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Wenn sich der Typ in einem anderen Projekt oder in einer referenzierten Datei befindet, installieren Sie das Projekt oder die Datei erneut.  
  
2.  Wenn sich der Typ im gleichen Projekt befindet, kompilieren Sie die Assembly mit dem Typ neu.  
  
3.  Wenn der Fehler erneut auftritt, installieren Sie den [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Compiler neu.  
  
4.  Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.  
  
## <a name="see-also"></a>Siehe auch  
 [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Sprechen Sie mit uns](https://docs.microsoft.com/visualstudio/ide/talk-to-us)
