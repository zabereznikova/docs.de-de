---
title: '&quot;&lt;Elementname&gt;&quot;ist veraltet (Visual Basic-Warnung) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40008
- bc40008
dev_langs:
- VB
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
caps.latest.revision: 12
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
ms.openlocfilehash: ccec3b2659502c84dd4db9c9c4d796362958030b
ms.lasthandoff: 03/13/2017

---
# <a name="39ltelementnamegt39-is-obsolete-visual-basic-warning"></a>'&lt;Elementname&gt;"ist veraltet (Visual Basic-Warnung)
Eine Anweisung versucht, auf ein Programmierelement zuzugreifen, das mit markiert wurde das <xref:System.ObsoleteAttribute>-Attribut und der Direktive, dies als Warnung zu behandeln.</xref:System.ObsoleteAttribute>  
  
 Sie können eines beliebigen Programmierelements als nicht mehr in Gebrauch durch <xref:System.ObsoleteAttribute>darauf</xref:System.ObsoleteAttribute> anwenden markieren. Wenn Sie dies tun, können Sie festlegen, dass des Attributs <xref:System.ObsoleteAttribute.IsError%2A>-Eigenschaft entweder `True` oder `False`.</xref:System.ObsoleteAttribute.IsError%2A> Wenn Sie sie auf `True`festlegen, behandelt der Compiler den Versuch, das Element zu verwenden, als Fehler. Wenn Sie sie auf `False`festlegen oder die Standardeinstellung `False`übernehmen, gibt der Compiler bei dem Versuch, das Element zu verwenden, eine Warnung aus.  
  
 Standardmäßig ist diese Meldung eine Warnung, da die <xref:System.ObsoleteAttribute.IsError%2A>-Eigenschaft des <xref:System.ObsoleteAttribute>ist `False`.</xref:System.ObsoleteAttribute> </xref:System.ObsoleteAttribute.IsError%2A> Weitere Informationen zum Ausblenden von Warnungen oder Warnungen als Fehler behandeln, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40008  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass der Elementname im Quellcodeverweis richtig geschrieben ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)

