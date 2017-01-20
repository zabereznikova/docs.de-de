---
title: "Overloaded Properties and Methods (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "properties [Visual Basic], overloading"
  - "methods [Visual Basic], overloading"
  - "shadowing"
  - "names, multiple procedures with same"
  - "procedures, mulltiples with same name"
  - "classes [Visual Basic], properties"
  - "classes [Visual Basic], methods"
  - "method overloading"
  - "Overloads keyword, overloaded members"
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Overloaded Properties and Methods (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Überladen ist das Erstellen von mehreren Prozeduren, Eigenschaften oder Instanzkonstruktoren in einer Klasse, die zwar denselben Namen verwenden aber über andere Argumenttypen verfügen.  
  
## Verwenden der Überladung  
 Eine Überladung ist besonders dann hilfreich, wenn es das Objektmodell erforderlich macht, identische Namen für Prozeduren zu vergeben, die auf verschiedene Datentypen angewendet werden.  So kann beispielsweise eine Klasse, die mehrere unterschiedliche Datentypen anzeigen kann, über `Display`\-Prozeduren verfügen, die folgendermaßen aussehen:  
  
 [!code-vb[VbVbalrOOP#64](../../../../visual-basic/misc/codesnippet/VisualBasic/VbVbalrOOP/OOP.vb#64)]  
  
 Ohne die Überladung müssten Sie unterschiedliche Namen für jede Prozedur erstellen, auch wenn alle dieselben Funktionen haben, wie das folgende Beispiel zeigt:  
  
 [!code-vb[VbVbalrOOP#65](../../../../visual-basic/misc/codesnippet/VisualBasic/VbVbalrOOP/OOP.vb#65)]  
  
 Durch die Überladung wird eine Reihe von optional verwendbaren Datentypen zur Verfügung gestellt, wodurch die Verwendung von Eigenschaften oder Methoden vereinfacht wird.  So kann beispielsweise die oben beschriebene überladene `Display`\-Methode durch eine der folgenden Codezeilen aufgerufen werden:  
  
 [!code-vb[VbVbalrOOP#66](../../../../visual-basic/misc/codesnippet/VisualBasic/VbVbalrOOP/OOP.vb#66)]  
  
 Zur Laufzeit ruft [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] die richtige Prozedur auf Grundlage der Datentypen der von Ihnen angegebenen Parameter auf.  
  
## Überladen von Regeln  
 Sie können einen überladenen Klassenmember erstellen, indem Sie zwei oder mehr Eigenschaften bzw. Methoden mit dem gleichen Namen hinzufügen.  Mit Ausnahme von überladenen abgeleiteten Membern muss jeder überladene Member über zwei verschiedene Parameterlisten verfügen, wobei die folgenden Elemente beim Überladen einer Eigenschaft oder Prozedur nicht als unterscheidendes Merkmal verwendet werden können:  
  
-   Modifizierer \(z. B. `ByVal` oder `ByRef`\), die für einen Member gelten, oder Parameter des Members.  
  
-   Parameternamen  
  
-   Rückgabetypen von Prozeduren  
  
 Das `Overloads`\-Schlüsselwort ist beim Überladen optional. Wenn jedoch ein beliebiger überladener Member das `Overloads`\-Schlüsselwort verwendet, müssen alle anderen überladenen Member mit demselben Namen ebenfalls dieses Schlüsselwort angeben.  
  
 Abgeleitete Klassen können geerbte Member mit Membern überladen, die über identische Parameter und Parametertypen verfügen. Dieser Prozess wird als *Shadowing nach Namen und Signatur* bezeichnet.  Wenn das `Overloads`\-Schlüsselwort beim Shadowing nach Namen und Signatur verwendet wird, wird anstelle der Basisklassenimplementierung des Members die Implementierung der abgeleiteten Klasse verwendet, und alle anderen Überladungen für diesen Member werden den Instanzen der abgeleiteten Klasse zur Verfügung gestellt.  
  
 Wenn bei der Überladung eines geerbten Members mit einem Member, dessen Parameter und Parametertypen identisch sind, das `Overloads`\-Schlüsselwort ausgelassen wird, so wird dies als *Shadowing nach Namen* bezeichnet.  Das Shadowing nach Namen ersetzt die geerbte Implementierung eines Members und bewirkt, dass alle anderen Überladungen für die Instanzen der abgeleiteten Klasse sowie für ihre Nachkommen nicht mehr verfügbar sind.  
  
 Die `Overloads`\- und `Shadows`\-Modifizierer können nicht zusammen mit derselben Eigenschaft oder Methode verwendet werden.  
  
### Beispiel  
 Im folgenden Beispiel werden überladene Methoden erstellt, die eine Darstellung eines bestimmten Dollarbetrags entweder als `String` oder als `Decimal` akzeptieren und eine Zeichenfolge mit der entsprechenden Umsatzsteuer zurückgeben.  
  
##### So verwenden Sie dieses Beispiel, um eine überladene Methode zu erstellen  
  
1.  Öffnen Sie ein neues Projekt, und fügen Sie eine Klasse mit dem Namen `TaxClass` hinzu.  
  
2.  Fügen Sie der `TaxClass`\-Klasse den folgenden Code hinzu:  
  
     [!code-vb[VbVbalrOOP#67](../../../../visual-basic/misc/codesnippet/VisualBasic/VbVbalrOOP/OOP.vb#67)]  
  
3.  Fügen Sie dem Formular die folgende Prozedur hinzu:  
  
     [!code-vb[VbVbalrOOP#68](../../../../visual-basic/misc/codesnippet/VisualBasic/VbVbalrOOP/OOP.vb#68)]  
  
4.  Fügen Sie dem Formular eine Schaltfläche hinzu, und rufen Sie die `ShowTax`\-Prozedur über das `Button1_Click`\-Ereignis der Schaltfläche auf.  
  
5.  Führen Sie das Projekt aus, und klicken Sie auf die Schaltfläche im Formular, um die überladene `ShowTax`\-Prozedur zu testen.  
  
 Der Compiler wählt zur Laufzeit die entsprechende Überladungsfunktion, die mit den verwendeten Parametern übereinstimmt.  Wenn Sie auf die Schaltfläche klicken, wird die überladene Methode zuerst mit einem `Price`\-Parameter \(Zeichenfolge\) aufgerufen, und die Meldung "Price is a String.  Tax is $5.12" wird angezeigt.  Beim zweiten Mal wird `TaxAmount` mit einem `Decimal`\-Wert aufgerufen, und die Meldung "Price is a Decimal.  Tax is $5.12" wird angezeigt.  
  
## Siehe auch  
 [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Inheritance Basics](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)   
 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)   
 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)   
 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)   
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)