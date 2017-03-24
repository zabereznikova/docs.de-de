---
title: "Konstanten und VbStrConv.Narrow können nicht kombiniert werden | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrArgument_IllegalWideNarrow
ms.assetid: a53b4e6a-36b1-4e36-b2c5-8196313ec599
caps.latest.revision: 8
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8d184fab3a63bc69caa67f315a9cb0f32514e2c1
ms.lasthandoff: 03/13/2017

---
# <a name="vbstrconvwide-and-vbstrconvnarrow-cannot-be-combined"></a>VbStrConv.Wide und VbStrConv.Narrow können nicht kombiniert werden.
Die Anwendung versucht, die sich gegenseitig ausschließenden `VbStrConv` -Enumerationsmember `Wide` und `Narrow`zu kombinieren.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Entfernen Sie entweder `VbStrConv.Wide` oder `VbStrConv.Narrow`.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Globalization>   
 [NOTINBUILD VbStrConv-Enumeration](http://msdn.microsoft.com/en-us/59f83dd9-6361-47df-a836-02ba9d4cb936)   
 [Einführung in internationale Anwendungen basierend auf .NET Framework](https://docs.microsoft.com/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
