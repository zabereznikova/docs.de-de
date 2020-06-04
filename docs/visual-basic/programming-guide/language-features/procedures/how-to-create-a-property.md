---
title: 'Vorgehensweise: Erstellen einer Eigenschaft'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, properties
- properties [Visual Basic]
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
ms.openlocfilehash: fa220998d12206e620c242b9b39df3dc1b639d29
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388257"
---
# <a name="how-to-create-a-property-visual-basic"></a>Gewusst wie: Erstellen einer Eigenschaft (Visual Basic)
Sie schließen eine Eigenschafts Definition zwischen einer `Property` -Anweisung und einer- `End Property` Anweisung ein. Innerhalb dieser Definition definieren Sie eine `Get` Prozedur, eine `Set` Prozedur oder beides. Der gesamte Code der Eigenschaft liegt in diesen Prozeduren.  
  
 Die `Get` Prozedur ruft den Wert der Eigenschaft ab, und die `Set` Prozedur speichert einen Wert. Wenn Sie möchten, dass die Eigenschaft Lese-/Schreibzugriff hat, müssen Sie beide Prozeduren definieren. Für eine schreibgeschützte Eigenschaft definieren Sie nur `Get` , und für eine schreibgeschützte Eigenschaft definieren Sie nur `Set` .  
  
### <a name="to-create-a-property"></a>So erstellen Sie eine Eigenschaft  
  
1. Verwenden Sie außerhalb einer Eigenschaft oder Prozedur eine [Eigenschafts Anweisung](../../../language-reference/statements/property-statement.md), gefolgt von einer- `End Property` Anweisung.  
  
2. Wenn die Eigenschaft Parameter annimmt, befolgen Sie das `Property` Schlüsselwort mit dem Namen der Prozedur und der Parameterliste in Klammern.  
  
3. Folgen Sie den Klammern mit einer- `As` Klausel, um den Datentyp des Eigenschafts Werts anzugeben. Sie müssen auch für eine schreibgeschützte Eigenschaft den-Datentyp angeben.  
  
4. Fügen Sie nach Bedarf `Get` -und- `Set` Prozeduren hinzu. Sehen Sie sich die folgenden Anweisungen an.  
  
### <a name="to-create-a-get-procedure-that-retrieves-a-property-value"></a>So erstellen Sie eine Get-Prozedur zum Abrufen eines Eigenschafts Werts  
  
1. `Property` `End Property` Schreiben Sie zwischen den Anweisungen und eine [Get-Anweisung](../../../language-reference/statements/get-statement.md), gefolgt von einer- `End Get` Anweisung. Sie müssen keine Parameter für die `Get` Prozedur definieren.  
  
2. Platzieren Sie die Code Anweisungen zum Abrufen des Eigenschafts Werts zwischen der `Get` -Anweisung und der- `End Get` Anweisung. Dieser Code kann neben dem erzeugen und Zurückgeben des Eigenschafts Werts auch andere Berechnungen und Datenmanipulationen enthalten.  
  
3. Verwenden Sie eine- `Return` Anweisung, um den Wert der Eigenschaft an den aufrufenden Code zurückzugeben.  
  
 Sie müssen eine `Get` Prozedur für eine Lese-/Schreibeigenschaft und für eine schreibgeschützte Eigenschaft schreiben. Sie dürfen keine `Get` Prozedur für eine schreibgeschützte Eigenschaft definieren.  
  
### <a name="to-create-a-set-procedure-that-writes-a-propertys-value"></a>So erstellen Sie eine Set-Prozedur, die den Wert einer Eigenschaft schreibt  
  
1. Schreiben Sie zwischen den `Property` `End Property` Anweisungen und eine [Set-Anweisung](../../../language-reference/statements/set-statement.md), gefolgt von einer- `End Set` Anweisung.  
  
2. Befolgen Sie in der- `Set` Anweisung das- `Set` Schlüsselwort mit einer Parameterliste in Klammern. Diese Parameterliste muss mindestens einen Wert Parameter für den Wert enthalten, der vom aufrufenden Code übergeben wird. Der Standardname für diesen Wert Parameter ist `Value` , aber Sie können ggf. einen anderen Namen verwenden. Der value-Parameter muss denselben Datentyp aufweisen wie die Eigenschaft selbst.  
  
3. Platzieren Sie die Code Anweisungen, um einen Wert in der-Eigenschaft zwischen der `Set` -und der-Anweisung zu speichern `End Set` . Dieser Code kann neben dem validieren und Speichern des Eigenschafts Werts auch andere Berechnungen und Datenmanipulationen enthalten.  
  
4. Verwenden Sie den value-Parameter, um den vom aufrufenden Code bereitgestellten Wert zu akzeptieren. Sie können diesen Wert entweder direkt in einer Zuweisungsanweisung speichern oder ihn in einem Ausdruck verwenden, um den zu speichernden internen Wert zu berechnen.  
  
 Sie müssen eine `Set` Prozedur für eine Eigenschaft mit Lese-/Schreibzugriff und für eine schreibgeschützte Eigenschaft schreiben. Sie dürfen keine `Set` Prozedur für eine schreibgeschützte Eigenschaft definieren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Lese-/Schreibeigenschaft erstellt, in der ein vollständiger Name als zwei konstituierende Namen, der Vorname und der Nachname, gespeichert werden. Wenn der Aufruf Code liest `fullName` , `Get` kombiniert die Prozedur die beiden Namen der einzelnen Teile und gibt den vollständigen Namen zurück. Wenn der Aufruf Code einen neuen vollständigen Namen zuweist, `Set` versucht die Prozedur, Sie in zwei konstituierende Namen zu unterteilen. Wenn kein Leerzeichen gefunden wird, wird alles als Vorname gespeichert.  
  
 [!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]  
  
 Das folgende Beispiel zeigt typische Aufrufe der-Eigenschaften Prozeduren von `fullName` . Der erste-Befehl legt den-Eigenschafts Wert fest, und der zweite-Rückruf ruft ihn ab.  
  
 [!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweisen](./index.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)
- [Vorgehensweise: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Vorgehensweise: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)
- [Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Vorgehensweise: Ablegen eines Werts in eine Eigenschaft](./how-to-put-a-value-in-a-property.md)
- [Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
