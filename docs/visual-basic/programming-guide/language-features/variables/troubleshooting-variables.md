---
title: Problembehandlung bei Variablen in Visual Basic | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- troubleshooting [Visual Basic], variables
- variables [Visual Basic], troubleshooting
ms.assetid: 928a2dc8-e565-4ae4-8ba3-80cc0cb50090
caps.latest.revision: 20
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9cddf7ced50c42514ebc9a613f49adee31edde0b
ms.lasthandoff: 03/13/2017

---
# <a name="troubleshooting-variables-in-visual-basic"></a>Problembehandlung bei Variablen in Visual Basic
Auf dieser Seite sind einige allgemeine Probleme, die auftreten können, beim Arbeiten mit Variablen in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## <a name="unable-to-access-members-of-an-object"></a>Zugriff auf Member eines Objekts ist nicht möglich  
 Wenn Ihr Code versucht, auf eine Eigenschaft oder Methode eines Objekts zuzugreifen, können zwei Arten von Fehlern auftreten:  
  
-   Der Compiler kann eine Fehlermeldung generieren, wenn Sie die Objektvariable als bestimmten Typ deklarieren und dann auf einen Member verweisen, der nicht durch diesen Typ definiert ist.  
  
-   Ein Laufzeit- <xref:System.MemberAccessException>tritt auf, wenn das einer Objektvariablen zugewiesene Objekt nicht den Member verfügbar macht, Code zugreifen möchten.</xref:System.MemberAccessException> Bei einer Variablen vom [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md), Sie können diese Ausnahme auch abrufen, wenn das Element nicht ist `Public`. Der Grund ist, dass die späte Bindung nur den Zugriff auf `Public` -Member erlaubt.  
  
 Wenn die [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) typüberprüfung legt `On`, nur die Methoden und Eigenschaften der Klasse, mit der Sie wurde deklariert, kann eine Objektvariable zugreifen. Dies wird anhand des folgenden Beispiels veranschaulicht.  

 [!code-vb[VbVbalrVariables&#2;](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/troubleshooting-variables_1.vb)]  
  
 In diesem Beispiel `p` können nur die Mitglieder der <xref:System.Object>-Klasse selbst, die enthalten nicht die `Left` Eigenschaft.</xref:System.Object> Auf der anderen Seite `q` Typ deklariert wurde <xref:System.Windows.Forms.Label>, sodass es alle Methoden und Eigenschaften verwenden kann die <xref:System.Windows.Forms.Label>-Klasse in die <xref:System.Windows.Forms>Namespace.</xref:System.Windows.Forms> </xref:System.Windows.Forms.Label> </xref:System.Windows.Forms.Label>  
  
### <a name="correct-approach"></a>Richtige Vorgehensweise  
 Um auf alle Member eines Objekts einer bestimmten Klasse zugreifen zu können, deklarieren Sie die Objektvariable nach Möglichkeit als Typ der Klasse. Wenn nicht möglich ist, z. B. Wenn Sie den Objekttyp zur Kompilierzeit nicht bekannt ist, müssen Sie festlegen `Option Strict` zu `Off` und deklarieren Sie die Variable in einer der [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md). So können der Variablen Objekte beliebigen Typs zugewiesen werden, und Sie sollten Maßnahmen ergreifen, um sicherzustellen, dass das aktuell zugewiesene Objekt einen zulässigen Typ hat. Sie können die [TypeOf-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) um diese Entscheidung zu treffen.  
  
## <a name="other-components-cannot-access-your-variable"></a>Andere Komponenten können nicht auf die Variable zugreifen  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Namen sind *Groß-und Kleinschreibung*. Wenn zwei Namen sich nur in der Groß- und Kleinschreibung unterscheiden, interpretiert der Compiler sie als identisch. Er geht z. B. davon aus, dass `ABC` und `abc` auf das gleiche deklarierte Element verweisen.  
  
 Allerdings verwendet die Common Language Runtime (CLR) die *Groß-/Kleinschreibung unterscheidende* Bindung. Wenn Sie also eine Assembly oder DLL erstellen und für andere Assemblys verfügbar machen, wird bei Ihren Namen Groß-und Kleinschreibung unterschieden. Wenn Sie z. B. eine Klasse mit einem Element namens `ABC`definieren, müssen andere Assemblys, die die Klasse über die Common Language Runtime verwenden, auf das Element als `ABC`verweisen. Wenn Sie danach die Klasse erneut kompilieren und den Namen des Elements in `abc`ändern, können andere Assemblys, die Ihre Klasse verwenden, nicht mehr auf dieses Element zugreifen. Wenn Sie also eine aktualisierte Version einer Assembly herausgeben, sollten Sie die Groß-/Kleinschreibung öffentlicher Elemente nicht ändern.  
  
 Weitere Informationen finden Sie unter [Common Language Runtime](http://msdn.microsoft.com/library/059a624e-f7db-4134-ba9f-08b676050482).  
  
### <a name="correct-approach"></a>Richtige Vorgehensweise  
 Um anderen Komponenten den Zugriff auf Ihre Variablen zu ermöglichen, behandeln Sie deren Namen so, als würde die Groß-/Kleinschreibung unterschieden. Stellen Sie beim Testen der Klasse oder des Moduls sicher, dass andere Assemblys sich gemäß Ihrer Erwartung an die Variablen binden. Nachdem Sie eine Komponente veröffentlicht haben, nehmen Sie keine Änderungen an vorhandenen Namen von Variablen vor, Ändern von Groß-/Kleinschreibung inbegriffen.  
  
## <a name="wrong-variable-being-used"></a>Falsche Variable wird verwendet  
 Wenn Sie mehr als eine Variable mit dem gleichen Namen, haben die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] versucht der Compiler, jeden Verweis auf diesen Namen aufzulösen. Wenn die Variablen über unterschiedliche Gültigkeitsbereiche verfügen, löst der Compiler einen Verweis auf die Deklaration mit dem engsten Gültigkeitsbereich auf. Wenn sie den gleichen Gültigkeitsbereich aufweisen, gelingt die Auflösung nicht, und der Compiler signalisiert einen Fehler. Weitere Informationen finden Sie unter [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
### <a name="correct-approach"></a>Richtige Vorgehensweise  
 Vermeiden Sie, Variablen mit gleichem Namen, aber unterschiedlichen Gültigkeitsbereichen zu verwenden. Wenn Sie andere Assemblys oder Projekte verwenden, vermeiden Sie so weit wie möglich die Verwendung von Namen, die in diesen externen Komponenten definiert werden. Wenn Sie über mehrere Variablen gleichen Namens verfügen, achten Sie darauf, jeden Verweis auf sie zu qualifizieren. Weitere Informationen finden Sie unter [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Gewusst wie: Zugreifen auf Member eines Objekts](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)   
 [Werte von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [Gewusst wie: Bestimmen des Typs, auf den eine Objektvariable verweist](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)   
 [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Namen deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
