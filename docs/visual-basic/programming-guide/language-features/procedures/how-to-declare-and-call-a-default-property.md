---
title: 'Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft'
ms.date: 07/20/2015
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
ms.openlocfilehash: 4de5d94a94e764d1fc543ffae41b00a9bb729c94
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388153"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a>Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic
Eine *Standard Eigenschaft* ist eine Klassen-oder Struktur Eigenschaft, auf die der Code zugreifen kann, ohne ihn anzugeben. Beim Aufrufen von Code wird eine Klasse oder Struktur, aber keine Eigenschaft benannt, und der Kontext ermöglicht den Zugriff auf eine Eigenschaft, Visual Basic den Zugriff auf die Standard Eigenschaft der Klasse oder Struktur, sofern vorhanden, auflöst.  
  
 Eine Klasse oder Struktur kann höchstens eine Standard Eigenschaft aufweisen. Sie können jedoch eine Standard Eigenschaft überladen und mehr als eine Version davon haben.  
  
 Weitere Informationen finden Sie unter [default (Standard](../../../language-reference/modifiers/default.md)).  
  
### <a name="to-declare-a-default-property"></a>So deklarieren Sie eine Standard Eigenschaft  
  
1. Deklarieren Sie die Eigenschaft auf die übliche Weise. Geben Sie das `Shared` Schlüsselwort oder nicht an `Private` .  
  
2. Fügen Sie das- `Default` Schlüsselwort in die Eigenschaften Deklaration ein  
  
3. Geben Sie mindestens einen Parameter für die Eigenschaft an. Sie können keine Standard Eigenschaft definieren, die nicht mindestens ein Argument annimmt.  
  
     [!code-vb[VbVbcnProcedures#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#17)]  
  
### <a name="to-call-a-default-property"></a>So wird eine Standard Eigenschaft aufgerufen  
  
1. Deklarieren Sie eine Variable vom enthaltenden Klassen-oder Strukturtyp.  
  
     [!code-vb[VbVbcnProcedures#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#16)]  
  
2. Verwenden Sie den Variablennamen allein in einem Ausdruck, in dem Sie normalerweise den Eigenschaftsnamen einschließen.  
  
     [!code-vb[VbVbcnProcedures#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#21)]  
  
3. Befolgen Sie den Variablennamen mit einer Argumentliste in Klammern. Eine Standard Eigenschaft muss mindestens ein Argument annehmen.  
  
     [!code-vb[VbVbcnProcedures#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#20)]  
  
4. Um den Standard Eigenschafts Wert abzurufen, verwenden Sie den Variablennamen, mit einer Argumentliste, in einem Ausdruck oder nach dem Gleichheits `=` Zeichen () in einer Zuweisungsanweisung.  
  
     [!code-vb[VbVbcnProcedures#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#15)]  
  
5. Um den Standard Eigenschafts Wert festzulegen, verwenden Sie den Variablennamen auf der linken Seite einer Zuweisungsanweisung mit einer Argumentliste.  
  
     [!code-vb[VbVbcnProcedures#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#14)]  
  
6. Sie können den Standard Eigenschaftsnamen wie für den Zugriff auf jede andere Eigenschaft immer mit dem Variablennamen angeben.  
  
     [!code-vb[VbVbcnProcedures#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#19)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Default-Eigenschaft für eine-Klasse deklariert.  
  
 [!code-vb[VbVbcnProcedures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#12)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die Default-Eigenschaft für die-Klasse aufgerufen wird `myProperty` `class1` . Die drei Zuweisungs Anweisungen speichern Werte in `myProperty` , und der-Befehl <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> liest die-Werte.  
  
 [!code-vb[VbVbcnProcedures#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#13)]  
  
 Die häufigste Verwendung einer Standard Eigenschaft ist die- <xref:Microsoft.VisualBasic.Collection.Item%2A> Eigenschaft für verschiedene Auflistungs Klassen.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Standardeigenschaften können zu einer geringfügigen Reduzierung der Quell Code Zeichen führen, aber Sie können den Code schwieriger lesbar machen. Wenn der aufrufende Code nicht mit der Klasse oder Struktur vertraut ist, kann er, wenn er einen Verweis auf den Klassen-oder Struktur Namen erstellt, nicht sicher sein, ob dieser Verweis auf die Klasse oder Struktur selbst oder eine Standard Eigenschaft zugreift. Dies kann zu Compilerfehlern oder geringfügigen Lauf Zeit Logik-Fehlern führen.  
  
 Sie können die Wahrscheinlichkeit von Fehlern bei Standardeigenschaften verringern, indem Sie immer die [Option Strict-Anweisung](../../../language-reference/statements/option-strict-statement.md) verwenden, um die Compilertypüberprüfung auf festzulegen `On` .  
  
 Wenn Sie beabsichtigen, eine vordefinierte Klasse oder Struktur in Ihrem Code zu verwenden, müssen Sie feststellen, ob Sie über eine Default-Eigenschaft verfügt. wenn dies der Fall ist, müssen Sie den Namen angeben.  
  
 Aufgrund dieser Nachteile sollten Sie das Definieren von Standardeigenschaften in Erwägung gezogen. Zur besseren Lesbarkeit des Codes sollten Sie auch immer eine explizite Verweis auf alle Eigenschaften in Erwägung ziehen. Dies gilt auch für Standardeigenschaften.  
  
## <a name="see-also"></a>Weitere Informationen

- [Eigenschaftenprozeduren](./property-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [Standard](../../../language-reference/modifiers/default.md)
- [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)
- [Vorgehensweise: Erstellen einer Eigenschaft](./how-to-create-a-property.md)
- [Vorgehensweise: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Vorgehensweise: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)
- [Vorgehensweise: Ablegen eines Werts in eine Eigenschaft](./how-to-put-a-value-in-a-property.md)
- [Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
