---
title: "Problembehandlung bei Variablen in Visual Basic | Microsoft Docs"
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
  - "Problembehandlung [Visual Basic], Variablen"
  - "Variablen [Visual Basic], Problembehandlung"
ms.assetid: 928a2dc8-e565-4ae4-8ba3-80cc0cb50090
caps.latest.revision: 20
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Problembehandlung bei Variablen in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Auf dieser Seite werden einige allgemeine Probleme aufgelistet, die bei der Arbeit mit Variablen in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] auftreten können.  
  
## Zugriff auf Member eines Objekts ist nicht möglich  
 Wenn Ihr Code versucht, auf eine Eigenschaft oder Methode eines Objekts zuzugreifen, können zwei Arten von Fehlern auftreten:  
  
-   Der Compiler kann eine Fehlermeldung generieren, wenn Sie die Objektvariable als bestimmten Typ deklarieren und dann auf einen Member verweisen, der nicht durch diesen Typ definiert ist.  
  
-   Eine Laufzeit\-<xref:System.MemberAccessException> tritt auf, wenn das einer Objektvariablen zugewiesene Objekt nicht den Member verfügbar macht, auf den Ihr Code zugreifen möchten. Bei einer Variablen von [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) können Sie diese Ausnahmemeldung auch erhalten, wenn der Member nicht `Public` ist. Der Grund ist, dass die späte Bindung nur den Zugriff auf `Public`\-Member erlaubt.  
  
 Wenn [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) für die Typüberprüfung `On` festlegt, kann eine Objektvariable nur auf die Methoden und Eigenschaften der Klasse zugreifen, mit der Sie sie deklarieren. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!CODE [VbVbalrStatements#49](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#49)]  
  
 [!code-vb[VbVbalrVariables#2](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/troubleshooting-variables_2.vb)]  
  
 In diesem Beispiel kann `p` nur die Mitglieder der <xref:System.Object>\-Klasse selbst verwenden, die nicht die `Left`\-Eigenschaft enthalten. Auf der anderen Seite wurde `q` als Typ <xref:System.Windows.Forms.Label> deklariert, sodass es alle Methoden und Eigenschaften der <xref:System.Windows.Forms.Label>\-Klasse im <xref:System.Windows.Forms>\-Namespace verwenden kann.  
  
### Richtige Vorgehensweise  
 Um auf alle Member eines Objekts einer bestimmten Klasse zugreifen zu können, deklarieren Sie die Objektvariable nach Möglichkeit als Typ der Klasse. Wenn das nicht möglich ist, z. B. weil Sie den Objekttyp zur Kompilierzeit nicht kennen, müssen Sie für `Option Strict``Off` festlegen und die Variable als [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) deklarieren. So können der Variablen Objekte beliebigen Typs zugewiesen werden, und Sie sollten Maßnahmen ergreifen, um sicherzustellen, dass das aktuell zugewiesene Objekt einen zulässigen Typ hat. Sie können diese Entscheidung mit dem [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) treffen.  
  
## Andere Komponenten können nicht auf die Variable zugreifen  
 Bei [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Namen wird die *Groß\-\/Kleinschreibung nicht beachtet*. Wenn zwei Namen sich nur in der Groß\- und Kleinschreibung unterscheiden, interpretiert der Compiler sie als identisch. Er geht z. B. davon aus, dass `ABC` und `abc` auf das gleiche deklarierte Element verweisen.  
  
 Allerdings verwendet die Common Language Runtime \(CLR\) die *Groß\-\/Kleinschreibung unterscheidende* Bindung. Wenn Sie also eine Assembly oder DLL erstellen und für andere Assemblys verfügbar machen, wird bei Ihren Namen Groß\-und Kleinschreibung unterschieden. Wenn Sie z. B. eine Klasse mit einem Element namens `ABC` definieren, müssen andere Assemblys, die die Klasse über die Common Language Runtime verwenden, auf das Element als `ABC` verweisen. Wenn Sie danach die Klasse erneut kompilieren und den Namen des Elements in `abc` ändern, können andere Assemblys, die Ihre Klasse verwenden, nicht mehr auf dieses Element zugreifen. Wenn Sie also eine aktualisierte Version einer Assembly herausgeben, sollten Sie die Groß\-\/Kleinschreibung öffentlicher Elemente nicht ändern.  
  
 Weitere Informationen finden Sie unter [Common Language Runtime](../Topic/Common%20Language%20Runtime%20\(CLR\).md).  
  
### Richtige Vorgehensweise  
 Um anderen Komponenten den Zugriff auf Ihre Variablen zu ermöglichen, behandeln Sie deren Namen so, als würde die Groß\-\/Kleinschreibung unterschieden. Stellen Sie beim Testen der Klasse oder des Moduls sicher, dass andere Assemblys sich gemäß Ihrer Erwartung an die Variablen binden. Nachdem Sie eine Komponente veröffentlicht haben, nehmen Sie keine Änderungen an vorhandenen Namen von Variablen vor, Ändern von Groß\-\/Kleinschreibung inbegriffen.  
  
## Falsche Variable wird verwendet  
 Wenn Sie über mehrere Variablen gleichen Namens verfügen, versucht der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Compiler, jeden Verweis auf diesen Namen aufzulösen. Wenn die Variablen über unterschiedliche Gültigkeitsbereiche verfügen, löst der Compiler einen Verweis auf die Deklaration mit dem engsten Gültigkeitsbereich auf. Wenn sie den gleichen Gültigkeitsbereich aufweisen, gelingt die Auflösung nicht, und der Compiler signalisiert einen Fehler. Weitere Informationen finden Sie unter [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
### Richtige Vorgehensweise  
 Vermeiden Sie, Variablen mit gleichem Namen, aber unterschiedlichen Gültigkeitsbereichen zu verwenden. Wenn Sie andere Assemblys oder Projekte verwenden, vermeiden Sie so weit wie möglich die Verwendung von Namen, die in diesen externen Komponenten definiert werden. Wenn Sie über mehrere Variablen gleichen Namens verfügen, achten Sie darauf, jeden Verweis auf sie zu qualifizieren. Weitere Informationen finden Sie unter [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## Siehe auch  
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Object Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [How to: Access Members of an Object](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)   
 [Object Variable Values](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [How to: Determine What Type an Object Variable Refers To](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)   
 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)