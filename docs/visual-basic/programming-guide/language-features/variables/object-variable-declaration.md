---
title: "Object Variable Declaration (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "early binding"
  - "declarations, class"
  - "classes [Visual Basic], declaring"
  - "binding, late and early"
  - "object variables, declaring"
  - "variables [Visual Basic], object"
  - "declaring variables, object variables"
  - "declaring classes"
  - "late binding"
ms.assetid: 2a5a41a3-1aa8-4236-b1f0-2382af7bf715
caps.latest.revision: 33
caps.handback.revision: 33
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Object Variable Declaration (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Normale Deklarationsanweisungen werden zum Deklarieren von Objektvariablen verwendet.  Als Datentyp, aus der das Objekt erstellt werden soll, geben Sie entweder `Object` \(d. h. [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)\) an oder eine spezifischere Klasse.  
  
 Die Deklaration einer Variablen als `Object` erfolgt wie deren Deklaration als <xref:System.Object?displayProperty=fullName>.  
  
 Eine mit einer speziellen Objektklasse deklarierte Variable kann auf alle Methoden und Eigenschaften zugreifen, die diese Klasse zur Verfügung stellt, sowie auf die Klassen, von denen sie erbt.  Wenn Sie die Variable mit <xref:System.Object> deklarieren, kann sie nur auf die Member der <xref:System.Object>\-Klasse zugreifen, es sei denn, Sie legen `Option Strict Off` fest, um eine späte Bindung zuzulassen.  
  
## Deklarationssyntax  
 Deklarieren Sie eine Objektvariable mithilfe der folgenden Syntax:  
  
```  
Dim variablename As [New] { objectclass | Object }  
```  
  
 Sie können auch [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) oder [Static](../../../../visual-basic/language-reference/modifiers/static.md) in der Deklaration angeben.  Folgende Beispieldeklarationen sind gültig:  
  
```  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## Späte Bindung und frühe Bindung  
 Manchmal ist die spezifische Klasse vor der Ausführung des Codes unbekannt.  In diesem Fall muss die Objektvariable mit dem Datentyp `Object` deklariert werden.  Dadurch wird ein allgemeiner Verweis auf ein Objekt beliebigen Typs erstellt, und die spezifische Klasse wird während der Laufzeit zugewiesen.  Dies wird als *späte Bindung* bezeichnet.  Die späte Bindung erfordert zusätzliche Ausführungszeit.  Außerdem wird der Code auf die Methoden und Eigenschaften der Klasse beschränkt, die Sie zuletzt zugewiesen haben.  Wenn der Code auf Member einer anderen Klasse zuzugreifen versucht, kann es dadurch zu Laufzeitfehlern kommen.  
  
 Wenn die spezielle Klasse zur Kompilierungszeit bekannt ist, sollten Sie die Objektvariable immer in dieser Klasse deklarieren.  Dies wird als *frühe Bindung* bezeichnet.  Die frühe Bindung erhöht die Leistung und garantiert, dass der Code auf alle Methoden und Eigenschaften der speziellen Klasse zugreifen kann.  Wenn die Variable `objA` aus den vorhergehenden Beispieldeklarationen nur Objekte der Klasse <xref:System.Windows.Forms.Label?displayProperty=fullName> verwendet, müssen Sie `As System.Windows.Forms.Label` in ihrer Deklaration angeben.  
  
### Vorteile der frühen Bindung  
 Die Deklaration einer Objektvariablen als spezielle Klasse hat mehrere Vorteile:  
  
-   Automatische Typüberprüfung  
  
-   Garantierter Zugriff auf alle Member der speziellen Klasse  
  
-   Microsoft IntelliSense\-Unterstützung im Code\-Editor  
  
-   Bessere Lesbarkeit des Codes  
  
-   Weniger Fehler im Code  
  
-   Fehler werden zur Kompilierungszeit und nicht erst zur Laufzeit abgefangen  
  
-   Schnellere Codeausführung  
  
## Zugriff auf Member von Objektvariablen  
 Wenn `Option Strict` auf `On` festgelegt ist, kann eine Objektvariable nur auf die Methoden und Eigenschaften der Klasse zugreifen, mit der sie deklariert wurde.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
```  
' Option statements must precede all other source file lines.  
Option Strict On  
' Imports statement must precede all declarations in the source file.  
Imports System.Windows.Forms  
Public Sub accessMembers()  
    Dim p As Object  
    Dim q As System.Windows.Forms.Label  
    p = New System.Windows.Forms.Label  
    q = New System.Windows.Forms.Label  
    Dim j, k As Integer  
    ' The following statement generates a compiler ERROR.  
    j = p.Left  
    ' The following statement retrieves the left edge of the label in pixels.  
    k = q.Left  
End Sub  
```  
  
 In diesem Beispiel kann `p` nur die Member der <xref:System.Object>\-Klasse verwenden, zu denen die `Left`\-Eigenschaft nicht gehört.  Andererseits wurde `q` als <xref:System.Windows.Forms.Label>\-Typ deklariert, sodass es alle Methoden und Eigenschaften der <xref:System.Windows.Forms.Label>\-Klasse im <xref:System.Windows.Forms>\-Namespace verwenden kann.  
  
## Flexibilität von Objektvariablen  
 Beim Arbeiten mit Objekten in einer Vererbungshierarchie können Sie die Klasse wählen, in der die Objektvariablen deklariert werden.  Wägen Sie dabei die Flexibilität der Objektzuweisung gegen den Zugriff auf die Member einer Klasse ab.  Beachten Sie z. B. die Vererbungshierarchie, die zur <xref:System.Windows.Forms.Form?displayProperty=fullName>\-Klasse führt:  
  
 <xref:System.Object>  
  
 `` <xref:System.ComponentModel.Component>  
  
 `` <xref:System.Windows.Forms.Control>  
  
 `` <xref:System.Windows.Forms.ScrollableControl>  
  
 `` <xref:System.Windows.Forms.ContainerControl>  
  
 `` <xref:System.Windows.Forms.Form>  
  
 Angenommen, die Anwendung definiert die Formularklasse `specialForm`, die von der <xref:System.Windows.Forms.Form>\-Klasse erbt.  Sie können dazu – wie im folgenden Beispiel gezeigt – eine Objektvariable deklarieren, die speziell auf `specialForm` verweist:  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
 Die Deklaration aus dem vorhergehenden Beispiel begrenzt die Variable `nextForm` auf Objekte der Klasse `specialForm` und macht zudem die Methoden und Eigenschaften von `specialForm` sowie die Member aller Klassen, von denen `specialForm` erbt, für `nextForm` verfügbar.  
  
 Wie im folgenden Beispiel gezeigt, wird eine Objektvariable allgemeiner gehalten, wenn Sie sie als Variable des Typs <xref:System.Windows.Forms.Form> deklarieren:  
  
<CodeContentPlaceHolder>4</CodeContentPlaceHolder>  
 Die Deklaration aus dem vorhergehenden Beispiel ermöglicht es, `anyForm` einem beliebigen Formular Ihrer Anwendung zuzuweisen.  Obwohl `anyForm` auf alle Member der Klasse <xref:System.Windows.Forms.Form> zugreifen kann, kann es keine der zusätzlichen Methoden oder Eigenschaften verwenden, die für bestimmte Formulare \(z. B. `specialForm`\) definiert wurden.  
  
 Alle Member einer Basisklasse stehen abgeleiteten Klassen zur Verfügung, die zusätzlichen Member einer abgeleiteten Klasse sind für die Basisklasse jedoch nicht verfügbar.  
  
## Siehe auch  
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Object Variable Assignment](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Object Variable Values](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [How to: Declare an Object Variable and Assign an Object to It in Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)   
 [How to: Access Members of an Object](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)   
 [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md)   
 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)