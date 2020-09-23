---
title: Problembehandlung bei Variablen
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting [Visual Basic], variables
- variables [Visual Basic], troubleshooting
ms.assetid: 928a2dc8-e565-4ae4-8ba3-80cc0cb50090
ms.openlocfilehash: e2bcf0b779d98ea4b109ea6d33b69a15110d423c
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91080165"
---
# <a name="troubleshooting-variables-in-visual-basic"></a>Problembehandlung bei Variablen in Visual Basic

Auf dieser Seite werden einige allgemeine Probleme aufgelistet, die bei der Arbeit mit Variablen in Visual Basic auftreten können.  
  
## <a name="unable-to-access-members-of-an-object"></a>Zugriff auf Member eines Objekts ist nicht möglich  

 Wenn Ihr Code versucht, auf eine Eigenschaft oder Methode eines Objekts zuzugreifen, können zwei Arten von Fehlern auftreten:  
  
- Der Compiler kann eine Fehlermeldung generieren, wenn Sie die Objektvariable als bestimmten Typ deklarieren und dann auf einen Member verweisen, der nicht durch diesen Typ definiert ist.  
  
- Eine Laufzeit- <xref:System.MemberAccessException> tritt auf, wenn das einer Objektvariablen zugewiesene Objekt nicht den Member verfügbar macht, auf den Ihr Code zugreifen möchten. Bei einer Variablen von [Object Data Type](../../../language-reference/data-types/object-data-type.md)können Sie diese Ausnahmemeldung auch erhalten, wenn der Member nicht `Public`auftreten können. Der Grund ist, dass die späte Bindung nur den Zugriff auf `Public` -Member erlaubt.  
  
 Wenn [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md) für die Typüberprüfung `On`festlegt, kann eine Objektvariable nur auf die Methoden und Eigenschaften der Klasse zugreifen, mit der Sie sie deklarieren. Dies wird anhand des folgenden Beispiels veranschaulicht.  

 [!code-vb[VbVbalrVariables#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrVariables/VB/Class1.vb#2)]  
  
 In diesem Beispiel kann `p` nur die Mitglieder der <xref:System.Object> -Klasse selbst verwenden, die nicht die `Left` -Eigenschaft enthalten. Auf der anderen Seite wurde `q` als Typ <xref:System.Windows.Forms.Label>deklariert, sodass es alle Methoden und Eigenschaften der <xref:System.Windows.Forms.Label> -Klasse im <xref:System.Windows.Forms> -Namespace verwenden kann.  
  
### <a name="correct-approach"></a>Richtige Vorgehensweise  

 Um auf alle Member eines Objekts einer bestimmten Klasse zugreifen zu können, deklarieren Sie die Objektvariable nach Möglichkeit als Typ der Klasse. Wenn dies nicht möglich ist, z. b. Wenn Sie den Objekttyp zur Kompilierzeit nicht kennen, müssen Sie `Option Strict` auf festlegen `Off` und die Variable als [Objekt Datentyp](../../../language-reference/data-types/object-data-type.md)deklarieren. So können der Variablen Objekte beliebigen Typs zugewiesen werden, und Sie sollten Maßnahmen ergreifen, um sicherzustellen, dass das aktuell zugewiesene Objekt einen zulässigen Typ hat. Sie können den [typeof-Operator](../../../language-reference/operators/typeof-operator.md) verwenden, um diese Entscheidung zu treffen.  
  
## <a name="other-components-cannot-access-your-variable"></a>Andere Komponenten können nicht auf die Variable zugreifen  

 Bei Visual Basic Namen wird *Groß-/Kleinschreibung*nicht beachtet. Wenn zwei Namen sich nur in der Groß- und Kleinschreibung unterscheiden, interpretiert der Compiler sie als identisch. Er geht z. B. davon aus, dass `ABC` und `abc` auf das gleiche deklarierte Element verweisen.  
  
 Allerdings verwendet die Common Language Runtime (CLR) die *Groß-/Kleinschreibung unterscheidende* Bindung. Wenn Sie also eine Assembly oder DLL erstellen und für andere Assemblys verfügbar machen, wird bei Ihren Namen Groß-und Kleinschreibung unterschieden. Wenn Sie z. B. eine Klasse mit einem Element namens `ABC`definieren, müssen andere Assemblys, die die Klasse über die Common Language Runtime verwenden, auf das Element als `ABC`verweisen. Wenn Sie danach die Klasse erneut kompilieren und den Namen des Elements in `abc`ändern, können andere Assemblys, die Ihre Klasse verwenden, nicht mehr auf dieses Element zugreifen. Wenn Sie also eine aktualisierte Version einer Assembly herausgeben, sollten Sie die Groß-/Kleinschreibung öffentlicher Elemente nicht ändern.  
  
 Weitere Informationen finden Sie unter [Common Language Runtime](../../../../standard/clr.md).  
  
### <a name="correct-approach"></a>Richtige Vorgehensweise  

 Um anderen Komponenten den Zugriff auf Ihre Variablen zu ermöglichen, behandeln Sie deren Namen so, als würde die Groß-/Kleinschreibung unterschieden. Stellen Sie beim Testen der Klasse oder des Moduls sicher, dass andere Assemblys sich gemäß Ihrer Erwartung an die Variablen binden. Nachdem Sie eine Komponente veröffentlicht haben, nehmen Sie keine Änderungen an vorhandenen Namen von Variablen vor, Ändern von Groß-/Kleinschreibung inbegriffen.  
  
## <a name="wrong-variable-being-used"></a>Falsche Variable wird verwendet  

 Wenn Sie über mehr als eine Variable mit demselben Namen verfügen, versucht der Visual Basic-Compiler, jeden Verweis auf diesen Namen aufzulösen. Wenn die Variablen über unterschiedliche Gültigkeitsbereiche verfügen, löst der Compiler einen Verweis auf die Deklaration mit dem engsten Gültigkeitsbereich auf. Wenn sie den gleichen Gültigkeitsbereich aufweisen, gelingt die Auflösung nicht, und der Compiler signalisiert einen Fehler. Weitere Informationen finden Sie unter [References to Declared Elements](../declared-elements/references-to-declared-elements.md).  
  
### <a name="correct-approach"></a>Richtige Vorgehensweise  

 Vermeiden Sie, Variablen mit gleichem Namen, aber unterschiedlichen Gültigkeitsbereichen zu verwenden. Wenn Sie andere Assemblys oder Projekte verwenden, vermeiden Sie so weit wie möglich die Verwendung von Namen, die in diesen externen Komponenten definiert werden. Wenn Sie über mehrere Variablen gleichen Namens verfügen, achten Sie darauf, jeden Verweis auf sie zu qualifizieren. Weitere Informationen finden Sie unter [References to Declared Elements](../declared-elements/references-to-declared-elements.md).  
  
## <a name="see-also"></a>Siehe auch

- [Variablen](index.md)
- [Variablen Deklaration](variable-declaration.md)
- [Objektvariablen](object-variables.md)
- [Deklaration von Objektvariablen](object-variable-declaration.md)
- [Vorgehensweise: Zugreifen auf Member eines Objekts](how-to-access-members-of-an-object.md)
- [Werte von Objektvariablen](object-variable-values.md)
- [Vorgehensweise: Bestimmen des Typs, auf den eine Objektvariable verweist](how-to-determine-what-type-an-object-variable-refers-to.md)
- [References to Declared Elements](../declared-elements/references-to-declared-elements.md)
- [Declared Element Names](../declared-elements/declared-element-names.md)
