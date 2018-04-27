---
title: 'Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9c4f471eba42e47d6bef45a4d38abc0cbd2d32bc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a>Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic
Ein *Standardeigenschaft* ist eine Klasse oder Struktur-Eigenschaft, die der Code zugreifen kann, ohne dass es. Beim Aufrufen von Code Namen einer Klasse oder Struktur, nicht jedoch eine Eigenschaft angibt und den Kontext ermöglicht den Zugriff auf eine Eigenschaft, Visual Basic löst den Zugriff auf diese Klasse oder Struktur Standardeigenschaft, falls vorhanden.  
  
 Eine Klasse oder Struktur kann höchstens eine Standardeigenschaft haben. Allerdings können Sie eine Standardeigenschaft überladen und haben mehr als eine Version.  
  
 Weitere Informationen finden Sie unter [Standard](../../../../visual-basic/language-reference/modifiers/default.md).  
  
### <a name="to-declare-a-default-property"></a>Um eine Standardeigenschaft zu deklarieren.  
  
1.  Deklarieren Sie die Eigenschaft auf die übliche Weise. Geben Sie keine der `Shared` oder `Private` Schlüsselwort.  
  
2.  Enthalten die `Default` -Schlüsselwort in der Deklaration der Eigenschaft.  
  
3.  Geben Sie mindestens einen Parameter für die Eigenschaft an. Sie können keine Standardeigenschaft definieren, die nicht mindestens ein Argument akzeptiert.  
  
     [!code-vb[VbVbcnProcedures#17](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]  
  
### <a name="to-call-a-default-property"></a>Aufrufen eine Standardeigenschaft  
  
1.  Deklarieren Sie eine Variable den enthaltenden Typ der Klasse oder Struktur an.  
  
     [!code-vb[VbVbcnProcedures#16](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]  
  
2.  Verwenden Sie den Variablennamen Allein in einem Ausdruck, bei denen Sie normalerweise den Namen der Eigenschaft enthalten würde.  
  
     [!code-vb[VbVbcnProcedures#21](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]  
  
3.  Führen Sie den Variablennamen mit einer Argumentliste in Klammern ein. Eine Standardeigenschaft muss mindestens ein Argument annehmen.  
  
     [!code-vb[VbVbcnProcedures#20](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]  
  
4.  Um den Standardwert der Eigenschaft abzurufen, verwenden Sie den Variablennamen ein, mit der eine Argumentliste in einem Ausdruck oder nach dem Gleichheitszeichen (`=`) in einer zuweisungsanweisung signieren.  
  
     [!code-vb[VbVbcnProcedures#15](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]  
  
5.  Um den Standardwert der Eigenschaft festzulegen, verwenden Sie den Variablennamen ein, mit einer Argumentliste, auf der linken Seite einer zuweisungsanweisung.  
  
     [!code-vb[VbVbcnProcedures#14](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]  
  
6.  Sie können den Standardnamen für die Eigenschaft zusammen mit dem Variablennamen immer angeben, ebenso wie Sie vornehmen möchten, für den Zugriff auf eine andere Eigenschaft.  
  
     [!code-vb[VbVbcnProcedures#19](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert eine Standardeigenschaft für eine Klasse an.  
  
 [!code-vb[VbVbcnProcedures#12](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die Standardeigenschaft Aufrufen `myProperty` Klasse `class1`. Die drei zuweisungsanweisungen speichern Sie die Werte in `myProperty`, und die <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> Aufruf liest die Werte.  
  
 [!code-vb[VbVbcnProcedures#13](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]  
  
 Die häufigste Verwendung der Standardeigenschaft ist der <xref:Microsoft.VisualBasic.Collection.Item%2A> -Eigenschaft für verschiedene Auflistungsklassen.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Standardeigenschaften können dazu führen, eine kleine Verkleinerung an Code Quellzeichen können, sie jedoch Code schwieriger zu lesen. Wenn der aufrufende Code nicht mit der Klasse oder Struktur vertraut ist, wenn es sich um einen Verweis auf den Namen der Klasse oder Struktur enthält kann nicht bestimmte darauf, ob der Verweis der Klasse oder Struktur selbst oder eine Standardeigenschaft greift auf. Dies kann zu Compilerfehlern oder geringfügige Logikfehler zur Laufzeit führen.  
  
 Sie können das Risiko von Fehlern der Standard-Eigenschaft etwas reduzieren, indem immer mithilfe der [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) Compilertyp das Einchecken festlegen `On`.  
  
 Wenn Sie beabsichtigen, eine vordefinierte Klasse oder Struktur in Ihrem Code müssen Sie bestimmen, ob es sich um eine Standardeigenschaft verfügt, und wenn Ja, ist was seinen Namen aus.  
  
 Aufgrund dieser Nachteile sollten Sie keine Standardeigenschaften definieren. Für die Lesbarkeit des Codes sollten Sie auch sollten Sie immer alle Eigenschaften explizit auf, auch die Standardeigenschaften.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenprozeduren](./property-procedures.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Default](../../../../visual-basic/language-reference/modifiers/default.md)  
 [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)  
 [Gewusst wie: Erstellen einer Eigenschaft](./how-to-create-a-property.md)  
 [Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Gewusst wie: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)  
 [Gewusst wie: Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md)  
 [Gewusst wie: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
