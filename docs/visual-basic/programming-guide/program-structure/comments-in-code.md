---
title: Kommentare in Code (Visual Basic)
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
ms.openlocfilehash: a8094397ff2a076cf474d735e65298b3d2f0a9cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050557"
---
# <a name="comments-in-code-visual-basic"></a>Kommentare in Code (Visual Basic)
Wenn Sie die Codebeispiele lesen, werden Sie oft auf das Kommentarsymbol (`'`) stoßen. Dieses Symbol weist Visual Basic-Compiler ignoriert den darauf folgenden Text, oder die *Kommentar*. Kommentare sind kurze, erläuternde Hinweise, die dem Code zum Zwecke der besseren Verständlichkeit hinzugefügt werden.  
  
 Es gilt als guter Programmierstil, alle Prozeduren mit einem kurzen Kommentar zu beginnen, der die Funktionsmerkmale der Prozedur (ihre Aufgabe) beschreibt. Dies ist zu Ihrem eigenen Nutzen und zum Nutzen jeder anderen Person, die den Code liest. Dabei ist es sinnvoll, die Einzelheiten der Implementierung, d. h., wie die Prozedur funktioniert, von den Kommentaren abzugrenzen, in denen die funktionalen Eigenschaften beschrieben werden. Falls Sie in einem Kommentar Einzelheiten der Implementierung beschreiben, denken Sie daran, diese entsprechend zu aktualisieren, wenn Sie die Funktion ändern.  
  
 Kommentare können nach einer Anweisung in der gleichen Zeile eingefügt werden oder eine ganze Zeile belegen. Beide Fälle werden im folgenden Code veranschaulicht:  
  
 [!code-vb[VbVbcnConventions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#16)]  
  
 Wenn der Kommentar mehr als eine Zeile beansprucht, verwenden Sie das Kommentarsymbol in jeder neuen Zeile, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbcnConventions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#17)]  
  
## <a name="commenting-guidelines"></a>Richtlinien für Kommentare  
 Die folgende Tabelle enthält allgemeine Richtlinien für die verschiedenen Arten von Kommentaren, die einem Codeabschnitt vorangestellt werden können. Dabei handelt es sich um Vorschläge. Visual Basic erzwingt keine Regeln für das Hinzufügen von Kommentaren. Wenden Sie diese Empfehlungen so an, wie sie für Sie und andere Leser am sinnvollsten sind.  
  
|||  
|---|---|  
|Kommentartyp|Kommentarbeschreibung|  
|Zweck|Hier wird beschrieben, was die Prozedur bewirkt (nicht, wie sie dies bewirkt).|  
|Annahmen|Listet alle externen Variablen, Steuerelemente, offenen Dateien und andere Elemente auf, auf die die Prozedur zugreift.|  
|Effekte|Hier werden die einzelnen betroffenen externen Variablen, Steuerelemente oder Dateien sowie deren Auswirkungen genannt (falls dies nicht offensichtlich ist).|  
|Eingaben|Gibt den Zweck des Arguments an.|  
|Rückgabe|Erläutert die von der Prozedur zurückgegebenen Werte.|  
  
 Beachten Sie Folgendes:  
  
- Vor jeder wichtigen Variablendeklaration sollte ein Kommentar stehen, der Sinn und Zweck der deklarierten Variablen beschreibt.  
  
- Variablen, Steuerelemente und Prozeduren sollten so klar benannt werden, dass Kommentare nur für komplexe Implementierungsdetails erforderlich sind.  
  
- Auf eine Zeilenfortsetzungszeichenfolge darf nicht in der gleichen Zeile ein Kommentar folgen.  
  
 Sie können auch hinzufügen oder entfernen Sie Kommentarsymbole für einen Codeblock, indem Sie eine oder mehrere Codezeilen markieren und die **Kommentar** (![der Visual Basic-Kommentar (Schaltfläche) in Visual Studio.](./media/comments-in-code/visual-basic-comment-button.gif)) und **Auswahlkommentar löschen**  (![Kommentieren Sie die Visual Basic-Schaltfläche in Visual Studio.](./media/comments-in-code/visual-basic-uncomment-button.gif)) Schaltflächen auf der **bearbeiten** Symbolleiste.  
  
> [!NOTE]
>  Sie können Code auch Kommentare hinzufügen, indem Sie vor dem betreffenden Text das `REM`-Schlüsselwort einfügen. Allerdings die `'` Symbol und die **Kommentar**/**Auswahlkommentar löschen** Schaltflächen sind einfacher zu verwenden und erfordern weniger Speicherplatz und Arbeitsspeicher.  
  
## <a name="see-also"></a>Siehe auch

- [Basic Instincts – Dokumentieren von Code mit XML-Kommentaren](https://msdn.microsoft.com/magazine/dd722812.aspx)
- [Vorgehensweise: Erstellen von XML-Dokumentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
- [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [REM-Anweisung](../../../visual-basic/language-reference/statements/rem-statement.md)
