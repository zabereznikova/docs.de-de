---
title: 'Die erste Anweisung des Sub New-Blocks muss ein expliziter Aufruf an "MyBase.New" oder "MyClass.New" sein, da "<constructorname>" in der <baseclassname>-Basisklasse von "<derivedclassname>" als veraltet markiert ist: "<errormessage>"'
ms.date: 07/20/2015
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
ms.openlocfilehash: 33dd15e3f5f5538963597f2b00f4214895e1f47a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403004"
---
# <a name="first-statement-of-this-sub-new-must-be-an-explicit-call-to-mybasenew-or-myclassnew-because-the-constructorname-in-the-base-class-baseclassname-of-derivedclassname-is-marked-obsolete-errormessage"></a>Die erste Anweisung des Sub New-Blocks muss ein expliziter Aufruf an "MyBase.New" oder "MyClass.New" sein, da "\<constructorname>" in der \<baseclassname>-Basisklasse von "\<derivedclassname>" als veraltet markiert ist: "\<errormessage>"
Ein Klassenkonstruktor ruft nicht explizit einen Basisklassenkonstruktor auf, und der implizite Basisklassenkonstruktor ist mit dem Attribut <xref:System.ObsoleteAttribute> und der Direktive versehen, dies als Fehler zu behandeln.  
  
 Wenn ein abgeleiteter Klassenkonstruktor keinen Basisklassenkonstruktor aufruft, versucht Visual Basic, einen impliziten-Befehl für einen Parameter losen Basisklassenkonstruktor zu generieren. Wenn kein zugänglicher Konstruktor in der Basisklasse vorhanden ist, der ohne Argumente aufgerufen werden kann, kann Visual Basic keinen impliziten Aufruf generieren. In diesem Fall wird der erforderliche Konstruktor mit dem- <xref:System.ObsoleteAttribute> Attribut markiert, sodass Visual Basic ihn nicht abrufen kann.  
  
 Sie können jedes beliebige Programmierelement als nicht mehr in Gebrauch kennzeichnen, indem Sie <xref:System.ObsoleteAttribute> darauf anwenden. Dabei können Sie die <xref:System.ObsoleteAttribute.IsError%2A> -Eigenschaft des Attributs entweder auf `True` oder `False`festlegen. Wenn Sie sie auf `True`festlegen, behandelt der Compiler den Versuch, das Element zu verwenden, als Fehler. Wenn Sie die Einstellung `False`vornehmen oder die Standardeinstellung `False`übernehmen, gibt der Compiler bei dem Versuch, das Element zu verwenden, eine Warnung aus.  
  
 **Fehler-ID:** BC30920  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Überprüfen Sie die angegebene Fehlermeldung, und ergreifen Sie entsprechende Maßnahmen.  
  
2. Fügen Sie einen Aufruf von `MyBase.New()` oder `MyClass.New()` als erste Anweisung von `Sub New` in der abgeleiteten Klasse ein.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Attribute](../../programming-guide/concepts/attributes/index.md)
