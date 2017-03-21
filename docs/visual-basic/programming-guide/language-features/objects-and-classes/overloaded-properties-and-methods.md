---
title: "Überladene Eigenschaften und Methoden (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names, multiple procedures with same
- procedures, mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword, overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
caps.latest.revision: 12
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
ms.openlocfilehash: 6f379f04ca9b75161baf2bf2c33e87f05a9edf97
ms.lasthandoff: 03/13/2017

---
# <a name="overloaded-properties-and-methods-visual-basic"></a>Überladene Eigenschaften und Methoden (Visual Basic)
Überladen ist das Erstellen von mehreren Prozeduren, Instanzkonstruktor oder Eigenschaft in einer Klasse mit dem gleichen Namen, aber unterschiedliche Argumenttypen.  
  
## <a name="overloading-usage"></a>Verwenden der Überladung  
 Überladen ist besonders nützlich, wenn das Objektmodell erforderlich macht, dass Sie identische Namen für Prozeduren verwenden, die auf unterschiedliche Datentypen angewendet werden. Angenommen, eine Klasse, die mehrere unterschiedliche Datentypen anzeigen kann verfügen über `Display` Prozeduren, die wie folgt aussehen:  
  
 [!code-vb[VbVbalrOOP&#64;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_1.vb)]  
  
 Ohne überladen müssten Sie unterschiedliche Namen für jede Prozedur erstellen, obwohl sie das gleiche tun, wie nachfolgend dargestellt:  
  
 [!code-vb[VbVbalrOOP&#65;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_2.vb)]  
  
 Überladen erleichtert es, Eigenschaften oder Methoden verwenden, da sie eine Auswahl von Datentypen enthält, die verwendet werden kann. Angenommen, die überladene `Display` beschriebene Methode zuvor kann aufgerufen werden mit den folgenden Codezeilen:  
  
 [!code-vb[VbVbalrOOP&#66;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_3.vb)]  
  
 Zur Laufzeit [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Aufrufe, die die richtige Prozedur auf der Grundlage der Datentypen der Parameter Sie angeben.  
  
## <a name="overloading-rules"></a>Überladen von Regeln  
 Erstellen Sie einen überladene Member für eine Klasse durch Hinzufügen von zwei oder mehr Eigenschaften oder Methoden mit demselben Namen. Mit Ausnahme von überladenen abgeleiteten Membern jeder überladene Member muss unterschiedliche Parameterlisten aufweisen, und die folgenden Elemente nicht als unterscheidendes Merkmal verwendet werden, wenn eine Eigenschaft oder Prozedur überladen:  
  
-   Modifizierer, wie z. B. `ByVal` oder `ByRef`, gilt für einen Member oder Parameter des Members.  
  
-   Namen von Parametern  
  
-   Rückgabetypen von Prozeduren  
  
 Die `Overloads` -Schlüsselwort ist beim Überladen optional, aber wenn eine überladene Member verwendet die `Overloads` -Schlüsselwort, und klicken Sie dann auf alle anderen überladene Member mit demselben Namen müssen auch dieses Schlüsselwort angeben.  
  
 Abgeleitete Klassen können geerbte Member mit Membern, die über identische Parameter und Parametertypen verfügen genannten überladen *mit Name und Signatur shadowing*. Wenn die `Overloads` -Schlüsselwort wird verwendet, wenn shadowing nach Name und die Signatur, die abgeleitete Klasse die Implementierung des Members anstelle der Implementierung in der Basisklasse verwendet werden, und alle anderen Überladungen für diesen Member für Instanzen der abgeleiteten Klasse verfügbar.  
  
 Wenn die `Overloads` -Schlüsselwort ausgelassen wird, wenn ein geerbtes Members mit einem Member zu überladen, die über identische Parameter und Parametertypen verfügt, dann heißt das Überladen *shadowing nach Namen*. Ein Shadowing nach dem Namen die geerbte Implementierung eines Elements ersetzt, und die alle anderen Überladungen auf Instanzen von der abgeleiteten Klasse und der Decedents nicht verfügbar.  
  
 Die `Overloads` und `Shadows` -Modifizierer können nicht zusammen mit derselben Eigenschaft oder Methode verwendet werden.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt die überladene Methoden, die entweder akzeptieren ein `String` oder `Decimal` Darstellung eines Währungsbetrag und eine Zeichenfolge mit der entsprechenden Umsatzsteuer zurück.  
  
##### <a name="to-use-this-example-to-create-an-overloaded-method"></a>In diesem Beispiel verwenden, um eine überladene Methode erstellen  
  
1.  Öffnen Sie ein neues Projekt und fügen Sie eine Klasse mit dem Namen `TaxClass`.  
  
2.  Fügen Sie der `TaxClass`-Klasse folgenden Code hinzu.  
  
     [!code-vb[VbVbalrOOP&#67;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_4.vb)]  
  
3.  Fügen Sie die folgende Prozedur in das Formular.  
  
     [!code-vb[VbVbalrOOP&#68;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_5.vb)]  
  
4.  Hinzufügen einer Schaltfläche zu Ihrem Formular ein und rufen die `ShowTax` Prozedur aus dem `Button1_Click` -Ereignis der Schaltfläche.  
  
5.  Führen Sie das Projekt, und klicken Sie auf die Schaltfläche auf dem Formular so testen Sie die überladenen `ShowTax` Verfahren.  
  
 Zur Laufzeit wählt der Compiler den geeignete überladene Funktion, die die Parametern entspricht. Wenn Sie auf die Schaltfläche klicken, die überladene Methode zuerst aufgerufen mit einem `Price` -Parameter, der eine Zeichenfolge ist und die Meldung "Preis ist eine Zeichenfolge. Steuer ist $5,12" wird angezeigt. `TaxAmount`wird aufgerufen, mit einem `Decimal` Wert erneut und der Meldung, "Preis ist eine Dezimalzahl. Steuer ist $5,12" wird angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Grundlagen der Vererbung](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [Schatten](../../../../visual-basic/language-reference/modifiers/shadows.md)   
 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)   
 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)   
 [Überladungen](../../../../visual-basic/language-reference/modifiers/overloads.md)   
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
