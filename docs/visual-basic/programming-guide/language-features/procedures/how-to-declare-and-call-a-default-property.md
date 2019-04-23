---
title: 'Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic'
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
ms.openlocfilehash: 9ca9a0ccdac3ac13429928233a0c09d58427ce74
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295639"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a>Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic
Ein *Standardeigenschaft* ist eine Klasse oder Struktur-Eigenschaft, die Ihren Code zugreifen können, ohne ihn. Beim Aufrufen von Code Namen einer Klasse oder Struktur, aber keine Eigenschaft, und der Kontext ermöglicht den Zugriff auf eine Eigenschaft, Visual Basic löst den Zugriff auf diese Klasse oder Struktur Standardeigenschaft, falls vorhanden.  
  
 Eine Klasse oder Struktur kann höchstens eine Standardeigenschaft sein. Allerdings können Sie eine Standardeigenschaft überladen und haben mehr als eine Version des Zertifikats.  
  
 Weitere Informationen finden Sie unter [Standard](../../../../visual-basic/language-reference/modifiers/default.md).  
  
### <a name="to-declare-a-default-property"></a>Um eine Standardeigenschaft zu deklarieren.  
  
1. Deklarieren Sie die Eigenschaft, auf die übliche Weise. Geben Sie nicht die `Shared` oder `Private` Schlüsselwort.  
  
2. Enthalten die `Default` -Schlüsselwort in der Deklaration der Eigenschaft.  
  
3. Geben Sie mindestens einen Parameter für die Eigenschaft an. Sie können keine Standardeigenschaft definieren, die nicht mindestens ein Argument übernimmt.  
  
     [!code-vb[VbVbcnProcedures#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#17)]  
  
### <a name="to-call-a-default-property"></a>Zum Aufrufen einer Standardeigenschaft  
  
1. Deklarieren Sie eine Variable die enthaltende Klasse oder Struktur.  
  
     [!code-vb[VbVbcnProcedures#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#16)]  
  
2. Verwenden Sie den Variablennamen in einem Ausdruck allein, müssten Sie normalerweise den Eigenschaftennamen einfügen.  
  
     [!code-vb[VbVbcnProcedures#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#21)]  
  
3. Führen Sie den Variablennamen mit einer Argumentliste in Klammern ein. Eine Standardeigenschaft muss mindestens ein Argument übernehmen.  
  
     [!code-vb[VbVbcnProcedures#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#20)]  
  
4. Um den Standardwert der Eigenschaft abzurufen, verwenden Sie den Variablennamen ein, mit einer Argumentliste, die in einem Ausdruck oder nach den Gleichheitsoperator (`=`) in einer zuweisungsanweisung anmelden.  
  
     [!code-vb[VbVbcnProcedures#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#15)]  
  
5. Um den Standardwert der Eigenschaft festzulegen, verwenden Sie den Variablennamen ein, mit einer Argumentliste, auf der linken Seite einer zuweisungsanweisung.  
  
     [!code-vb[VbVbcnProcedures#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#14)]  
  
6. Sie können den Standardnamen für die Eigenschaft zusammen mit dem Variablennamen immer angeben, wie Sie vornehmen möchten, für den Zugriff auf eine andere Eigenschaft.  
  
     [!code-vb[VbVbcnProcedures#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#19)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert eine Standardeigenschaft für eine Klasse an.  
  
 [!code-vb[VbVbcnProcedures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#12)]  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie die Standardeigenschaft Aufrufen `myProperty` Klasse `class1`. Die drei zuweisungsanweisungen speichern Sie die Werte in `myProperty`, und die <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> Aufruf liest die Werte.  
  
 [!code-vb[VbVbcnProcedures#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#13)]  
  
 Die häufigste Verwendung von eine Standardeigenschaft ist der <xref:Microsoft.VisualBasic.Collection.Item%2A> Eigenschaft in verschiedenen Auflistungsklassen.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Standardeigenschaften können dazu führen, eine kleine Reduzierung in Code-Zeichen, aber leisten können Ihren Code schwieriger zu lesen. Wenn der aufrufende Code nicht vertraut sind, mit der Klasse oder Struktur ist, wenn es sich um einen Verweis auf den Namen der Klasse oder Struktur ist es bestimmte nicht möglich, ob der Verweis der Klasse oder Struktur selbst oder an eine Standardeigenschaft greift auf. Dies kann zu Compilerfehlern oder geringfügige Laufzeitlogik-Fehler führen.  
  
 Sie können etwas reduziert die Wahrscheinlichkeit Eigenschaftenfehler standardmäßig immer mit der [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) Festlegen der Compiler die typüberprüfung zu `On`.  
  
 Wenn Sie beabsichtigen, mit einer vordefinierten Klasse oder Struktur in Ihrem Code müssen Sie bestimmen, ob es sich um eine Standardeigenschaft verfügt, und wenn Ja, ist wie der Name.  
  
 Wegen der genannten Nachteile sollten Sie keine Standardeigenschaften definieren. Sie sollten für die Lesbarkeit des Codes berücksichtigen Sie auch immer explizit verweisen, die allen Eigenschaften, auch die Standardeigenschaften.  
  
## <a name="see-also"></a>Siehe auch

- [Eigenschaftenprozeduren](./property-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Default](../../../../visual-basic/language-reference/modifiers/default.md)
- [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)
- [Vorgehensweise: Erstellen Sie eine Eigenschaft](./how-to-create-a-property.md)
- [Vorgehensweise: Deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Vorgehensweise: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)
- [Vorgehensweise: Das Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md)
- [Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
