---
title: Automatisch implementierte Eigenschaften
ms.date: 07/20/2015
f1_keywords:
- vb.AutoProperty
- vb.AutoImplementedProperty
helpviewer_keywords:
- properties [Visual Basic], auto-implemented
- auto-implemented properties [Visual Basic]
ms.assetid: 5c669f0b-cf95-4b4e-ae84-9cc55212ca87
ms.openlocfilehash: b322bd2215c95298be0a33ace1f3590a63878e24
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350386"
---
# <a name="auto-implemented-properties-visual-basic"></a>Automatisch implementierte Eigenschaften (Visual Basic)
*Automatisch implementierte Eigenschaften* ermöglichen es Ihnen, schnell eine Eigenschaft einer Klasse anzugeben, ohne Code schreiben zu müssen, um die Eigenschaft zu `Get` und zu `Set`. Wenn Sie Code für eine automatisch implementierte Eigenschaft schreiben, erstellt der Visual Basic-Compiler automatisch ein privates Feld zum Speichern der Eigenschaftsvariablen zusätzlich zum Erstellen der zugeordneten `Get` und `Set` Prozeduren.  
  
 Mit automatisch implementierten Eigenschaften kann eine Eigenschaft, einschließlich eines Standardwerts, in einer einzelnen Zeile deklariert werden. Im folgenden Beispiel werden drei Eigenschaftendeklarationen gezeigt.  
  
 [!code-vb[VbVbalrAutoImplementedProperties#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#1)]  
  
 Eine automatisch implementierte Eigenschaft entspricht einer Eigenschaft, deren Eigenschaftswert in einem privaten Feld gespeichert wird. Im folgenden Codebeispiel wird eine automatisch implementierte Eigenschaft veranschaulicht.  
  
 [!code-vb[VbVbalrAutoImplementedProperties#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#5)]  
  
 Im folgenden Codebeispiel wird der entsprechende Code für das vorherige Beispiel der automatisch implementierten Eigenschaft veranschaulicht.  
  
 [!code-vb[VbVbalrAutoImplementedProperties#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#2)]  
  
 Der folgende Code veranschaulicht die Implementierung von Readonly-Eigenschaften:  
  
```vb  
Class Customer  
   Public ReadOnly Property Tags As New List(Of String)  
   Public ReadOnly Property Name As String = ""  
   Public ReadOnly Property File As String  
  
   Sub New(file As String)  
      Me.File = file  
   End Sub  
End Class  
```  
  
 Sie können die Eigenschaft mit Initialisierungsausdrücken zuweisen, wie im Beispiel gezeigt, oder Sie können die Eigenschaften im Konstruktor des enthaltenden Typs zuweisen.  Sie können jederzeit auf die dahinter liegenden Felder der Readonly-Eigenschaften zuweisen.  
  
## <a name="backing-field"></a>Dahinter liegendes Feld  
 Wenn Sie eine automatisch implementierte Eigenschaft deklarieren, erstellt Visual Basic automatisch ein verborgenes privates Feld, das als dahinter liegendes *Feld* bezeichnet wird und den Eigenschafts Wert enthält. Der dahinter liegende Feldname ist die automatisch implementierte Eigenschaft mit einem vorangestellten Unterstrich (_). Angenommen, Sie deklarieren eine automatisch implementierte Eigenschaft mit dem Namen `ID`, dann heißt das dahinter liegende Feld `_ID`. Wenn Sie ein Member der Klasse mit einschließen, das ebenfalls den Namen `_ID` trägt, erzeugen Sie einen Namenskonflikt und Visual Basic meldet einen Compilerfehler.  
  
 Das dahinter liegende Feld verfügt ebenfalls über die folgenden Eigenschaften:  
  
- Der Zugriffsmodifizierer für das dahinter liegende Feld ist immer `Private`, selbst wenn die Eigenschaft selbst über eine andere Zugriffsebene verfügt, z. B `Public`.  
  
- Wenn die Eigenschaft als `Shared` markiert ist, wird das dahinter liegende Feld auch freigegeben.  
  
- Für die Eigenschaft angegebene Attribute gelten nicht für das dahinter liegende Feld.  
  
- Auf das dahinter liegende Feld kann durch Code innerhalb der Klasse und von Debugtools, wie dem Überwachungsfenster, zugegriffen werden. Das dahinter liegende Feld wird jedoch nicht in einer IntelliSense-Vervollständigungsliste für Word angezeigt.  
  
## <a name="initializing-an-auto-implemented-property"></a>So definieren Sie eine automatisch implementierte Eigenschaft  
 Jeder Ausdruck, der verwendet werden kann, um ein Feld zu initialisieren, ist gültig für die Initialisierung einer automatisch implementierte Eigenschaft. Wenn Sie eine automatisch implementierte Eigenschaft initialisieren, wird der Ausdruck ausgewertet und der `Set` Prozedur für die Eigenschaft übergeben. Die folgenden Codebeispiele zeigen einige automatisch implementierte Eigenschaften, die Anfangswerte enthalten.  
  
 [!code-vb[VbVbalrAutoImplementedProperties#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#3)]  
  
 Sie können eine automatisch implementierte Eigenschaft nicht initialisieren, wenn sie ein Member von `Interface` oder `MustOverride` gekennzeichnet ist.  
  
 Wenn Sie eine automatisch implementierte Eigenschaft als Member von `Structure` deklarieren, dann können Sie nur dann die automatisch implementierte Eigenschaft initialisieren, wenn sie als `Shared` gekennzeichnet ist.  
  
 Wenn Sie eine automatisch implementierte Eigenschaft als Array deklarieren, können keine expliziten Arraygrenzen festgelegt werden. Allerdings können Sie einen Wert mit einem Arrayinitialisierer angeben, wie in den folgenden Beispielen gezeigt.  
  
 [!code-vb[VbVbalrAutoImplementedProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#4)]  
  
## <a name="property-definitions-that-require-standard-syntax"></a>Eigenschaftendefinitionen, die Standardsyntax erfordern  
 Automatisch implementierte Eigenschaften sind praktisch und unterstützen viele Programmierszenarien. Es gibt jedoch Situationen, in denen eine automatisch implementierte Eigenschaft nicht verwendet werden kann und stattdessen die standardmäßige oder *Erweiterte*Eigenschafts Syntax verwendet werden muss.  
  
 In diesem Fall müssen Sie eine erweiterte Eigenschaftsdefinition-Syntax verwenden, wenn Sie eine der folgenden durchführen möchten:  
  
- Hinzufügen von Code für die Prozedur `Get` oder `Set` einer Eigenschaft, z. B. Code zum Überprüfen eingehender Werte in der Prozedur `Set`. Sie möchten z. B. überprüfen, ob eine Zeichenfolge, die eine Telefonnummer darstellt, die erforderliche Anzahl von Ziffern enthält, bevor der Eigenschaftswert festgelegt wird.  
  
- Angeben unterschiedlicher Zugriffsmöglichkeiten für die Prozeduren `Get` und `Set`. Sie möchten z. B. die `Set` Prozedur `Private` und die `Get` Prozedur `Public` erstellen.  
  
- Erstellen von Eigenschaften mit `WriteOnly`.  
  
- Verwenden von parametrisierten Eigenschaften (einschließlich `Default` Eigenschaften). Sie müssen eine erweiterte Eigenschaft deklarieren, um einen Parameter für die Eigenschaft oder zusätzliche Parameter für die `Set` Prozedur zu spezifizieren.  
  
- Platzieren Sie ein Attribut für das dahinter liegende Feld oder ändern Sie die Zugriffsebene des dahinter liegenden Felds.  
  
- Geben Sie XML-Kommentaren für das dahinter liegende Feld an.  
  
## <a name="expanding-an-auto-implemented-property"></a>So erweitern Sie eine automatisch implementierte Eigenschaft  
 Wenn Sie eine automatisch implementierte Eigenschaft zu einer erweiterten Eigenschaft konvertieren müssen, die eine `Get` oder `Set` Prozedur enthält, dann kann der Visual Basic-Code-Editor automatisch die `Get` und `Set` Prozeduren und `End Property` -Anweisung für die Eigenschaft generieren. Der Code wird generiert, wenn Sie den Cursor in einer leeren Zeile nach der `Property`-Anweisung platzieren, eine `G` (für `Get`) oder eine `S` (für `Set`) eingeben und die EINGABETASTE drücken. Der Visual Basic-Code-Editor generiert automatisch `Get` oder `Set` für schreibgeschützte und lesegeschützte Eigenschaften beim Drücken der EINGABETASTE am Ende der Prozedur eine `Property` Anweisung.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Deklarieren und Abrufen einer Standard Eigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md)
- [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md)
- [WriteOnly](../../../../visual-basic/language-reference/modifiers/writeonly.md)
- [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
