---
title: Kommentare in Code
ms.date: 07/20/2015
helpviewer_keywords:
- Uncomment button
- REM statement [Visual Basic]
- comments [Visual Basic], in code
- comments [Visual Basic], Visual Basic code
- Comment button
- buttons [Visual Basic], Uncomment
- buttons [Visual Basic], Comment
- code comments [Visual Basic], Visual Basic
- Visual Basic code, comments
- comments
- code comments
ms.assetid: 90136fba-22eb-49f9-ba81-63db629b4a47
ms.openlocfilehash: 9f9174896181e427c73936a1bb91fa13235e70be
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550988"
---
# <a name="comments-in-code-visual-basic"></a>Kommentare in Code (Visual Basic)
Wenn Sie die Codebeispiele lesen, werden Sie oft auf das Kommentarsymbol (`'`) stoßen. Dieses Symbol weist den Visual Basic Compiler an, den folgenden Text oder den *Kommentar*zu ignorieren. Kommentare sind kurze, erläuternde Hinweise, die dem Code zum Zwecke der besseren Verständlichkeit hinzugefügt werden.  
  
 Es gilt als guter Programmierstil, alle Prozeduren mit einem kurzen Kommentar zu beginnen, der die Funktionsmerkmale der Prozedur (ihre Aufgabe) beschreibt. Dies ist zu Ihrem eigenen Nutzen und zum Nutzen jeder anderen Person, die den Code liest. Dabei ist es sinnvoll, die Einzelheiten der Implementierung, d. h., wie die Prozedur funktioniert, von den Kommentaren abzugrenzen, in denen die funktionalen Eigenschaften beschrieben werden. Falls Sie in einem Kommentar Einzelheiten der Implementierung beschreiben, denken Sie daran, diese entsprechend zu aktualisieren, wenn Sie die Funktion ändern.  
  
 Kommentare können nach einer Anweisung in der gleichen Zeile eingefügt werden oder eine ganze Zeile belegen. Beide Fälle werden im folgenden Code veranschaulicht:  
  
 [!code-vb[VbVbcnConventions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#16)]  
  
 Wenn der Kommentar mehr als eine Zeile beansprucht, verwenden Sie das Kommentarsymbol in jeder neuen Zeile, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbcnConventions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#17)]  
  
## <a name="commenting-guidelines"></a>Richtlinien für Kommentare  
 Die folgende Tabelle enthält allgemeine Richtlinien für die verschiedenen Arten von Kommentaren, die einem Codeabschnitt vorangestellt werden können. Dies sind Vorschläge. Visual Basic erzwingen keine Regeln zum Hinzufügen von Kommentaren. Wenden Sie diese Empfehlungen so an, wie sie für Sie und andere Leser am sinnvollsten sind.  
  
|||  
|---|---|  
|Kommentartyp|Kommentarbeschreibung|  
|Zweck|Hier wird beschrieben, was die Prozedur bewirkt (nicht, wie sie dies bewirkt).|  
|Annahmen|Listet alle externen Variablen, Steuerelemente, offenen Dateien und andere Elemente auf, auf die die Prozedur zugreift.|  
|Effekte|Hier werden die einzelnen betroffenen externen Variablen, Steuerelemente oder Dateien sowie deren Auswirkungen genannt (falls dies nicht offensichtlich ist).|  
|Eingaben|Gibt den Zweck des Arguments an.|  
|Gibt zurück|Erläutert die von der Prozedur zurückgegebenen Werte.|  
  
 Beachten Sie Folgendes:  
  
- Vor jeder wichtigen Variablendeklaration sollte ein Kommentar stehen, der Sinn und Zweck der deklarierten Variablen beschreibt.  
  
- Variablen, Steuerelemente und Prozeduren sollten so klar benannt werden, dass Kommentare nur für komplexe Implementierungsdetails erforderlich sind.  
  
- Auf eine Zeilenfortsetzungszeichenfolge darf nicht in der gleichen Zeile ein Kommentar folgen.  
  
 Sie können Kommentar Symbole für einen Codeblock hinzufügen oder entfernen, indem Sie eine oder mehrere Codezeilen auswählen und den **Kommentar** ( ![ die Schaltfläche "Visual Basic Kommentar" in Visual Studio ](./media/comments-in-code/visual-basic-comment-button.gif) ) auswählen und die **Auskommentierung** ( ![ die Schaltfläche "Visual Basic uncomment" in Visual Studio. ](./media/comments-in-code/visual-basic-uncomment-button.gif) ) auf der Symbolleiste " **Bearbeiten** " aufheben.  
  
> [!NOTE]
> Sie können Code auch Kommentare hinzufügen, indem Sie vor dem betreffenden Text das `REM`-Schlüsselwort einfügen. Das `'` Symbol und die **Comment** / Schaltflächen zum**Entfernen** von Kommentaren sind jedoch einfacher zu verwenden und erfordern weniger Speicherplatz und Arbeitsspeicher.  
  
## <a name="see-also"></a>Siehe auch

- [Grundlegender Instinkt: Dokumentieren von Code mit XML-Kommentaren](/archive/msdn-magazine/2009/may/documenting-your-code-with-xml-comments)
- [Vorgehensweise: Erstellen einer XML-Dokumentation](how-to-create-xml-documentation.md)
- [XML-Kommentartags](../../language-reference/xmldoc/index.md)
- [Programmstruktur und Codekonventionen](program-structure-and-code-conventions.md)
- [REM-Anweisung](../../language-reference/statements/rem-statement.md)
