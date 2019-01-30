---
title: 'Die erste Anweisung des Sub New-Blocks muss ein expliziter Aufruf an "MyBase.New" oder "MyClass.New" sein, da "<constructorname>" in der <baseclassname>-Basisklasse von "<derivedclassname>" als veraltet markiert ist: "<errormessage>"'
ms.date: 07/20/2015
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
ms.openlocfilehash: 31f92d1e52e50b2a87fd6a6af6e3c87292f4437f
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55268794"
---
# <a name="first-statement-of-this-sub-new-must-be-an-explicit-call-to-mybasenew-or-myclassnew-because-the-constructorname-in-the-base-class-baseclassname-of-derivedclassname-is-marked-obsolete-errormessage"></a>Die erste Anweisung dieser "Sub New" muss ein expliziter Aufruf an "MyBase.New" oder "MyClass.New" sein, da die '\<Konstruktorname >' in der Basisklasse\<Basisklassenname >' von '\<Name der abgeleiteten Klasse > "als veraltet markiert ist:"\< Fehlermeldung >'
Ein Klassenkonstruktor ruft nicht explizit einen Basisklassenkonstruktor auf, und der implizite Basisklassenkonstruktor ist mit dem Attribut <xref:System.ObsoleteAttribute> und der Direktive versehen, dies als Fehler zu behandeln.  
  
 Wenn der Konstruktor einer abgeleiteten Klasse keinen Basisklassenkonstruktor aufruft, versucht Visual Basic einen impliziten Aufruf eines parameterlosen Basisklassenkonstruktors zu generieren. Ist es kein zugänglicher Konstruktor in der Basisklasse, die ohne Argumente aufgerufen werden kann, kann nicht in Visual Basic einen impliziten Aufruf generieren. In diesem Fall wird der erforderliche Konstruktor mit markiert die <xref:System.ObsoleteAttribute> Attribut, sodass Visual Basic nicht aufrufen kann.  
  
 Sie können jedes beliebige Programmierelement als nicht mehr in Gebrauch kennzeichnen, indem Sie <xref:System.ObsoleteAttribute> darauf anwenden. Dabei können Sie die <xref:System.ObsoleteAttribute.IsError%2A> -Eigenschaft des Attributs entweder auf `True` oder `False`festlegen. Wenn Sie sie auf `True`festlegen, behandelt der Compiler den Versuch, das Element zu verwenden, als Fehler. Wenn Sie sie auf `False`festlegen oder die Standardeinstellung `False`übernehmen, gibt der Compiler bei dem Versuch, das Element zu verwenden, eine Warnung aus.  
  
 **Fehler-ID:** BC30920  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die angegebene Fehlermeldung, und ergreifen Sie entsprechende Maßnahmen.  
  
2.  Fügen Sie einen Aufruf von `MyBase.New()` oder `MyClass.New()` als erste Anweisung von `Sub New` in der abgeleiteten Klasse ein.  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)

