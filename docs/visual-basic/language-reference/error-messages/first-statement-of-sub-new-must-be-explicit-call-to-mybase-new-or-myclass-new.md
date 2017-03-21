---
title: Die erste Anweisung dieses &quot;Sub New&quot; muss ein expliziter Aufruf an &quot;MyBase.New&quot; oder &quot;MyClass.New&quot; sein, da die &quot;&lt;Constructorname&gt;&quot;in der Basisklasse&quot;&lt;Baseclassname&gt;&quot;of&quot;&lt;Derivedclassname&gt;&quot;als veraltet markiert ist:&quot;&lt;Errormessage&gt;&quot; | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30920
- bc30920
dev_langs:
- VB
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
caps.latest.revision: 10
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: feb04d426b7e050b7ad05cdfd4d481172dda3a49
ms.lasthandoff: 03/13/2017

---
# <a name="first-statement-of-this-39sub-new39-must-be-an-explicit-call-to-39mybasenew39-or-39myclassnew39-because-the-39ltconstructornamegt39-in-the-base-class-39ltbaseclassnamegt39-of-39ltderivedclassnamegt39-is-marked-obsolete-39lterrormessagegt39"></a>Die erste Anweisung dieses "Sub New" muss ein expliziter Aufruf an "MyBase.New" oder "MyClass.New" sein, da die '&lt;Constructorname&gt;"in der Basisklasse"&lt;Baseclassname&gt;"of"&lt;Derivedclassname&gt;"als veraltet markiert ist:"&lt;Errormessage&gt;'
Ein Klassenkonstruktor ist nicht explizit einen Basisklassenkonstruktor aufrufen und die implizite Basisklassenkonstruktor gekennzeichnet, mit dem <xref:System.ObsoleteAttribute>-Attribut und der Direktive, dies als Fehler zu behandeln.</xref:System.ObsoleteAttribute>  
  
 Wenn der Konstruktor einer abgeleiteten Klasse keinen Basisklassenkonstruktor aufruft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] versucht, einen impliziten Aufruf eines parameterlosen Basisklassenkonstruktors zu generieren. Wenn kein zugreifbarer Konstruktor vorhanden ist, in der Basisklasse, die ohne Argumente aufgerufen werden kann [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] einen impliziten Aufruf kann nicht generiert werden. In diesem Fall wird der erforderliche Konstruktor mit markiert die <xref:System.ObsoleteAttribute>Attribut, also [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] it. nicht aufrufen</xref:System.ObsoleteAttribute>  
  
 Sie können eines beliebigen Programmierelements als nicht mehr in Gebrauch durch <xref:System.ObsoleteAttribute>darauf</xref:System.ObsoleteAttribute> anwenden markieren. Wenn Sie dies tun, können Sie festlegen, dass des Attributs <xref:System.ObsoleteAttribute.IsError%2A>-Eigenschaft entweder `True` oder `False`.</xref:System.ObsoleteAttribute.IsError%2A> Wenn Sie sie auf `True`festlegen, behandelt der Compiler den Versuch, das Element zu verwenden, als Fehler. Wenn Sie sie auf `False`festlegen oder die Standardeinstellung `False`übernehmen, gibt der Compiler bei dem Versuch, das Element zu verwenden, eine Warnung aus.  
  
 **Fehler-ID:** BC30920  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die angegebene Fehlermeldung, und ergreifen Sie entsprechende Maßnahmen.  
  
2.  Fügen Sie einen Aufruf von `MyBase.New()` oder `MyClass.New()` als erste Anweisung von `Sub New` in der abgeleiteten Klasse ein.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)
 
