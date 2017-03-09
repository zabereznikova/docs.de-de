---
title: "How to: Declare Enumerations (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declarations, enumerations"
  - "enumerations [Visual Basic], declaring"
  - "declaring enumerations"
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
caps.latest.revision: 24
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 24
---
# How to: Declare Enumerations (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Sie können eine Enumeration mithilfe der `Enum`\-Anweisung im Deklarationsabschnitt einer Klasse oder eines Moduls erstellen.  Es ist nicht möglich, eine Enumeration innerhalb einer Methode zu deklarieren.  Zur Angabe der geeigneten Zugriffsebene verwenden Sie `Private`, `Protected`, `Friend` oder `Public`.  
  
 Ein `Enum`\-Typ hat einen Namen, einen zugrunde liegenden Typ und eine Reihe von Feldern, die jeweils eine Konstante darstellen.  Der Name muss ein gültiger [!INCLUDE[vbprvblong](../../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)]\-Qualifizierer sein.  Bei dem zugrunde liegenden Typ muss es sich um einen ganzzahligen Typ handeln, d. h. `Byte`, `Short`, `Long` oder `Integer`.  Standardmäßig ist `Integer` festgelegt.  Enumerationen sind immer stark typisiert und nicht mit Ganzzahltypen austauschbar.  
  
 Enumerationen dürfen keine Gleitkommawerte haben.  Wenn `Option Strict On` aktiviert ist und einer Enumeration ein Gleitkommawert zugewiesen wird, führt dies zu einem Compilerfehler.  Wenn für `Option Strict` die Einstellung `Off` gewählt ist, wird der Wert automatisch in den `Enum`\-Typ konvertiert.  
  
 Weitere Informationen zu Namen und zur Verwendung der `Imports`\-Anweisung zur Umgehung der Qualifizierung von Namen finden Sie unter [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### So deklarieren Sie eine Enumeration  
  
1.  Erstellen Sie eine Deklaration, die eine Codezugriffsebene, das Schlüsselwort `Enum` und einen gültigen Namen umfasst, wie in den folgenden Beispielen gezeigt, in denen mit `Enum` jeweils verschiedene Enumerationen deklariert werden.  
  
     [!code-vb[VbEnumsTask#3](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class2.vb#3)]  
  
2.  Definieren Sie die Konstanten der Enumeration.  Die erste Konstante einer Enumeration wird standardmäßig mit `0` initialisiert, für alle nachfolgenden Konstanten wird der Initialisierungswert jeweils um 1 erhöht.  Die folgende Enumeration \(`Days`\) enthält beispielsweise eine Konstante mit dem Namen `Sunday` mit dem Wert `0`, eine Konstante mit dem Namen `Monday` mit dem Wert `1`, eine Konstante mit dem Namen `Tuesday` mit dem Wert `2` usw.  
  
     [!code-vb[VbEnumsTask#4](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class2.vb#4)]  
  
3.  Sie können Konstanten in einer Enumeration explizit Werte zuweisen, indem Sie eine Zuweisungsanweisung verwenden.  Es kann ein beliebiger ganzzahliger Wert \(auch negative Zahlen\) zugewiesen werden.  Konstanten mit Werten unter 0 können beispielsweise zur Darstellung von Fehlerbedingungen verwendet werden.  In der folgenden Enumeration wird der Konstanten `Invalid` explizit der Wert `–1` zugewiesen, und der Konstanten `Sunday` wird der Wert `0` zugewiesen.  Weil es sich um die erste Konstante der Enumeration handelt, wird `Saturday` zudem mit dem Wert `0` initialisiert.  Die Konstante `Monday` hat den Wert `1` \(der um eins höher ist als der Wert von `Sunday`\); die Konstante `Tuesday` hat den Wert `2` usw.  
  
     [!code-vb[VbEnumsTask#5](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class2.vb#5)]  
  
### So deklarieren Sie eine Enumeration als expliziten Typ  
  
-   Geben Sie den Typ der Enumeration mit der `As`\-Klausel an, wie im folgenden Beispiel gezeigt.  
  
     [!code-vb[VbEnumsTask#6](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class2.vb#6)]  
  
## Siehe auch  
 [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [How to: Refer to an Enumeration Member](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [How to: Iterate Through An Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [How to: Determine the String Associated with an Enumeration Value](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [When to Use an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)   
 [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Constant and Literal Data Types](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)