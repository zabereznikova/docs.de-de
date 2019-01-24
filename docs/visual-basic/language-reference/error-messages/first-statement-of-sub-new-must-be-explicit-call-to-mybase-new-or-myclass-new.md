---
title: 'Die erste Anweisung dieser &#39;Sub New&#39; muss ein expliziter Aufruf von &#39;MyBase.New&#39; oder &#39;MyClass.New&#39; da die &#39; &lt;Konstruktorname&gt; &#39; in der Basisklasse &#39; &lt;Basisklassenname&gt; &#39; von &#39; &lt;Name der abgeleiteten Klasse&gt; &#39; als veraltet markiert ist: &#39; &lt;Errormessage&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
ms.openlocfilehash: 9d07a68fd8d9790178427c512375323f23f46772
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566775"
---
# <a name="first-statement-of-this-39sub-new39-must-be-an-explicit-call-to-39mybasenew39-or-39myclassnew39-because-the-39ltconstructornamegt39-in-the-base-class-39ltbaseclassnamegt39-of-39ltderivedclassnamegt39-is-marked-obsolete-39lterrormessagegt39"></a>Die erste Anweisung dieser &#39;Sub New&#39; muss ein expliziter Aufruf von &#39;MyBase.New&#39; oder &#39;MyClass.New&#39; da die &#39; &lt;Konstruktorname&gt; &#39; in der Basisklasse &#39; &lt;Basisklassenname&gt; &#39; von &#39; &lt;Name der abgeleiteten Klasse&gt; &#39; als veraltet markiert ist: &#39; &lt;Errormessage&gt;&#39;
Ein Klassenkonstruktor ruft nicht explizit einen Basisklassenkonstruktor auf, und der implizite Basisklassenkonstruktor ist mit dem Attribut <xref:System.ObsoleteAttribute> und der Direktive versehen, dies als Fehler zu behandeln.  
  
 Wenn der Konstruktor einer abgeleiteten Klasse keinen Basisklassenkonstruktor aufruft, versucht Visual Basic einen impliziten Aufruf eines parameterlosen Basisklassenkonstruktors zu generieren. Ist es kein zugänglicher Konstruktor in der Basisklasse, die ohne Argumente aufgerufen werden kann, kann nicht in Visual Basic einen impliziten Aufruf generieren. In diesem Fall wird der erforderliche Konstruktor mit markiert die <xref:System.ObsoleteAttribute> Attribut, sodass Visual Basic nicht aufrufen kann.  
  
 Sie können jedes beliebige Programmierelement als nicht mehr in Gebrauch kennzeichnen, indem Sie <xref:System.ObsoleteAttribute> darauf anwenden. Dabei können Sie die <xref:System.ObsoleteAttribute.IsError%2A> -Eigenschaft des Attributs entweder auf `True` oder `False`festlegen. Wenn Sie sie auf `True`festlegen, behandelt der Compiler den Versuch, das Element zu verwenden, als Fehler. Wenn Sie sie auf `False`festlegen oder die Standardeinstellung `False`übernehmen, gibt der Compiler bei dem Versuch, das Element zu verwenden, eine Warnung aus.  
  
 **Fehler-ID:** BC30920  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die angegebene Fehlermeldung, und ergreifen Sie entsprechende Maßnahmen.  
  
2.  Fügen Sie einen Aufruf von `MyBase.New()` oder `MyClass.New()` als erste Anweisung von `Sub New` in der abgeleiteten Klasse ein.  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)

