---
title: 'Gewusst wie: Erstellen einer Eigenschaft'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, properties
- properties [Visual Basic]
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
ms.openlocfilehash: ee5a9f687765ce064eb3c3f84218ed36eb916d9d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349703"
---
# <a name="how-to-create-a-property-visual-basic"></a>Gewusst wie: Erstellen einer Eigenschaft (Visual Basic)
Sie schließen eine Eigenschafts Definition zwischen einer `Property`-Anweisung und einer `End Property`-Anweisung ein. Innerhalb dieser Definition definieren Sie eine `Get` Prozedur, eine `Set` Prozedur oder beides. Der gesamte Code der Eigenschaft liegt in diesen Prozeduren.  
  
 Die Prozedur `Get` Ruft den Wert der Eigenschaft ab, und die `Set` Prozedur speichert einen Wert. Wenn Sie möchten, dass die Eigenschaft Lese-/Schreibzugriff hat, müssen Sie beide Prozeduren definieren. Für eine schreibgeschützte Eigenschaft definieren Sie nur `Get`, und für eine schreibgeschützte Eigenschaft definieren Sie nur `Set`.  
  
### <a name="to-create-a-property"></a>So erstellen Sie eine Eigenschaft  
  
1. Verwenden Sie außerhalb einer Eigenschaft oder Prozedur eine [Eigenschafts Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md), gefolgt von einer `End Property`-Anweisung.  
  
2. Wenn die Eigenschaft Parameter annimmt, befolgen Sie das `Property`-Schlüsselwort mit dem Namen der Prozedur und der Parameterliste in Klammern.  
  
3. Folgen Sie den Klammern mit einer `As`-Klausel, um den Datentyp des Eigenschafts Werts anzugeben. Sie müssen auch für eine schreibgeschützte Eigenschaft den-Datentyp angeben.  
  
4. Fügen Sie nach Bedarf `Get`-und `Set` Prozeduren hinzu. Sehen Sie sich die folgenden Anweisungen an.  
  
### <a name="to-create-a-get-procedure-that-retrieves-a-property-value"></a>So erstellen Sie eine Get-Prozedur zum Abrufen eines Eigenschafts Werts  
  
1. Schreiben Sie zwischen den Anweisungen `Property` und `End Property` eine [Get-Anweisung](../../../../visual-basic/language-reference/statements/get-statement.md), gefolgt von einer `End Get`-Anweisung. Sie müssen keine Parameter für die `Get` Prozedur definieren.  
  
2. Platzieren Sie die Code Anweisungen, um den Eigenschafts Wert zwischen den `Get`-und `End Get`-Anweisungen abzurufen. Dieser Code kann neben dem erzeugen und Zurückgeben des Eigenschafts Werts auch andere Berechnungen und Datenmanipulationen enthalten.  
  
3. Verwenden Sie eine `Return`-Anweisung, um den Wert der Eigenschaft an den aufrufenden Code zurückzugeben.  
  
 Sie müssen eine `Get` Prozedur für eine Lese-/Schreibeigenschaft und für eine schreibgeschützte Eigenschaft schreiben. Sie dürfen keine `Get` Prozedur für eine schreibgeschützte Eigenschaft definieren.  
  
### <a name="to-create-a-set-procedure-that-writes-a-propertys-value"></a>So erstellen Sie eine Set-Prozedur, die den Wert einer Eigenschaft schreibt  
  
1. Schreiben Sie zwischen den Anweisungen `Property` und `End Property` eine [Set-Anweisung](../../../../visual-basic/language-reference/statements/set-statement.md), gefolgt von einer `End Set`-Anweisung.  
  
2. Befolgen Sie in der `Set`-Anweisung das `Set`-Schlüsselwort mit einer Parameterliste in Klammern. Diese Parameterliste muss mindestens einen Wert Parameter für den Wert enthalten, der vom aufrufenden Code übergeben wird. Der Standardname für diesen value-Parameter ist `Value`, Sie können jedoch ggf. einen anderen Namen verwenden. Der value-Parameter muss denselben Datentyp aufweisen wie die Eigenschaft selbst.  
  
3. Platzieren Sie die Code Anweisungen, um einen Wert in der-Eigenschaft zwischen den Anweisungen `Set` und `End Set` zu speichern. Dieser Code kann neben dem validieren und Speichern des Eigenschafts Werts auch andere Berechnungen und Datenmanipulationen enthalten.  
  
4. Verwenden Sie den value-Parameter, um den vom aufrufenden Code bereitgestellten Wert zu akzeptieren. Sie können diesen Wert entweder direkt in einer Zuweisungsanweisung speichern oder ihn in einem Ausdruck verwenden, um den zu speichernden internen Wert zu berechnen.  
  
 Sie müssen eine `Set` Prozedur für eine Eigenschaft mit Lese-/Schreibzugriff und für eine schreibgeschützte Eigenschaft schreiben. Sie dürfen keine `Set` Prozedur für eine schreibgeschützte Eigenschaft definieren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Lese-/Schreibeigenschaft erstellt, in der ein vollständiger Name als zwei konstituierende Namen, der Vorname und der Nachname, gespeichert werden. Wenn der aufrufenden Code `fullName`liest, werden die beiden konstituierenden Namen in der `Get` Prozedur kombiniert, und der vollständige Name wird zurückgegeben. Wenn der Aufruf Code einen neuen vollständigen Namen zuweist, versucht die `Set` Prozedur, Sie in zwei Bestandteile zu zerlegen. Wenn kein Leerzeichen gefunden wird, wird alles als Vorname gespeichert.  
  
 [!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]  
  
 Das folgende Beispiel zeigt typische Aufrufe der-Eigenschaften Prozeduren `fullName`. Der erste-Befehl legt den-Eigenschafts Wert fest, und der zweite-Rückruf ruft ihn ab.  
  
 [!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)
- [Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Gewusst wie: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)
- [Vorgehensweise: Deklarieren und Abrufen einer Standard Eigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Gewusst wie: Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md)
- [Gewusst wie: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
