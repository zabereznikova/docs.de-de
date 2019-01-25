---
title: Codierungskonventionen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: f2b1676ae959c5426af3021bbd340980115c5da6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724881"
---
# <a name="visual-basic-coding-conventions"></a>Codierungskonventionen in Visual Basic
Microsoft entwickelt Beispiele und Dokumentation, die den Richtlinien in diesem Thema folgen. Wenn Sie dieselben Codierungskonventionen beachten, erhalten Sie möglicherweise folgende Vorteile:  
  
-   Der Code erhält eine konsistente Gestaltung, damit sich die Leser mehr auf den Inhalt und nicht auf das Layout konzentrieren.  
  
-   Leser verstehen den Code schneller, da sie Rückschlüsse aus früheren Erfahrungen ziehen können.  
  
-   Sie können den Code kopieren, ändern und leichter pflegen.  
  
-   Sie können sicherstellen, dass der Code die "empfohlenen Vorgehensweisen" für Visual Basic berücksichtigt.  
  
## <a name="naming-conventions"></a>Namenskonventionen  
  
-   Informationen zu Benennungsrichtlinien finden Sie unter [Benennungsrichtlinien für die](../../../standard/design-guidelines/naming-guidelines.md) Thema.  
  
-   Verwenden Sie nicht "My" oder "my" als Teil eines Variablennamens. Diese Vorgehensweise führt zu Verwechslungen mit den `My`-Objekten.  
  
-   Sie müssen die Namen von Objekten in automatisch generiertem Code nicht ändern, um sie an die Richtlinien anzupassen.  
  
## <a name="layout-conventions"></a>Layoutkonventionen  
  
-   Fügen Sie Registerkarten als Leerzeichen ein, und verwenden Sie intelligenten Einzug mit vier Leerzeichen.  
  
-   Verwendung **Einrückung Einrückung des Codes** Neuformatieren von Code im Code-Editor. Weitere Informationen finden Sie unter [Optionen, Text-Editor, Standard (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).  
  
-   Verwenden Sie pro Zeile nur eine Anweisung. Verwenden Sie nicht das Visual Basic-Zeilentrennzeichen (:).  
  
-   Vermeiden Sie, das explizite Zeilenfortsetzungszeichen "_" zugunsten der impliziten Zeilenfortsetzung, wenn die Sprache dies ermöglicht.  
  
-   Verwenden Sie pro Zeile nur eine Deklaration.  
  
-   Wenn **Einrückung Einrückung des Codes** nicht Fortsetzungszeilen automatisch zum einrücken manuell Fortsetzung einen Tabstopp. In einer Liste werden jedoch die Elemente immer links ausgerichtet.  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   Fügen Sie zwischen Methoden- und Eigenschaftendefinitionen mindestens eine Leerzeile ein.  
  
## <a name="commenting-conventions"></a>Konventionen für Kommentare  
  
-   Fügen Sie den Kommentar in einer eigenen Zeile und nicht am Ende einer Codezeile ein.  
  
-   Beginnen Sie den Kommentartext mit einem Großbuchstaben, und beenden Sie ihn mit einem Punkt.  
  
-   Fügen Sie ein Leerzeichen zwischen dem Kommentartrennzeichen (') und dem Kommentartext ein.  
  
     [!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]  
  
-   Erstellen Sie keine formatierten Blöcke von Sternchen, die die Kommentare umgeben.  
  
## <a name="program-structure"></a>Programmstruktur  
  
-   Wenn Sie die `Main`-Methode verwenden, verwenden Sie das Standardkonstrukt für neue Konsolenanwendungen, und verwenden Sie `My` für Befehlszeilenargumente.  
  
     [!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]  
  
## <a name="language-guidelines"></a>Sprachrichtlinien  
  
### <a name="string-data-type"></a>String-Datentyp  
  
-   Um Zeichenfolgen verketten, verwenden Sie ein kaufmännisches Und-Zeichen (&).  
  
     [!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]  
  
-   Verwenden Sie das <xref:System.Text.StringBuilder>-Objekt, um Zeichenfolgen in Schleifen anzuhängen.  
  
     [!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a>Weniger strenge Delegaten in Ereignishandlern  
 Um Ereignishandler zu vermeiden, qualifizieren Sie die Argumente (Object und EventArgs) nicht explizit. Wenn Sie nicht die Ereignisargumente verwenden, die an ein Ereignis übergeben werden (z. B. Sender als Objekt, „e“ als EventArgs), verwenden Sie weniger strenge Delegaten, und lassen Sie die Ereignisargumente im Code aus:  
  
 [!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]  
  
### <a name="unsigned-data-type"></a>Datentyp ohne Vorzeichen  
  
-   Verwenden Sie `Integer` anstelle von Typen ohne Vorzeichen, wenn sie nicht notwendig sind.  
  
### <a name="arrays"></a>Arrays  
  
-   Verwenden Sie die kurze Syntax, wenn Sie Arrays in der Deklarationszeile initialisieren. Sie können z. B. folgende Syntax verwenden.  
  
     [!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]  
  
     Verwenden Sie nicht die folgende Syntax.  
  
     [!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]  
  
-   Legen Sie den Arraybezeichner im Typ und nicht in der Variablen ab. Sie können z. B. folgende Syntax verwenden:  
  
     [!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]  
  
     Verwenden Sie nicht die folgende Syntax:  
  
     [!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]  
  
-   Verwenden Sie die { }-Syntax, wenn Sie Arrays aus grundlegenden Datentypen deklarieren und initialisieren. Sie können z. B. folgende Syntax verwenden:  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     Verwenden Sie nicht die folgende Syntax:  
  
     [!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]  
  
### <a name="use-the-with-keyword"></a>Verwenden des with-Schlüsselworts  
 Wenn Sie eine Reihe von Aufrufen eines Objekts ausführen, sollten Sie erwägen, das `With`-Schlüsselwort zu verwenden:  
  
 [!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a>Verwenden Sie try-catch-Anweisungen zur Ausnahmebehandlung.  
 Verwenden Sie nicht `On Error Goto`.  
  
### <a name="use-the-isnot-keyword"></a>Verwenden des IsNot-Schlüsselworts  
 Verwenden Sie das Schlüsselwort `IsNot` statt `Not...Is Nothing`.  
  
### <a name="new-keyword"></a>New-Schlüsselwort  
  
-   Verwenden Sie die kurze Instanziierung. Sie können z. B. folgende Syntax verwenden:  
  
     [!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]  
  
     Die vorangehende Zeile entspricht der Folgenden:  
  
     [!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]  
  
-   Verwenden Sie für neue Objekte Objektinitialisierer anstelle des parameterlosen Konstruktors:  
  
     [!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]  
  
### <a name="event-handling"></a>Ereignisbehandlung  
  
-   Verwenden Sie eher `Handles` als `AddHandler`:  
  
     [!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]  
  
-   Verwenden Sie `AddressOf`, und instanziieren Sie den Delegaten nicht explizit:  
  
     [!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]  
  
-   Wenn Sie ein Ereignis definieren, verwenden Sie die kurze Syntax, und lassen Sie den Delegaten vom Compiler definieren:  
  
     [!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]  
  
-   Überprüfen Sie nicht, ob ein Ereignis `Nothing` (NULL) ist, bevor Sie die `RaiseEvent`-Methode aufrufen. Die `RaiseEvent`-Methode führt vor dem Auslösen des Ereignisses eine Überprüfung auf den Wert `Nothing` durch.  
  
### <a name="using-shared-members"></a>Verwenden von Shared-Membern  
 Rufen Sie `Shared`-Member über den Klassennamen auf, nicht von einer Instanzvariablen aus.  
  
### <a name="use-xml-literals"></a>Verwenden von XML-Literalen  
 XML-Literale vereinfachen allgemeine Aufgaben bei der Arbeit mit XML (z. B. Laden, Abfragen und Transformieren). Beachten Sie bei der Entwicklung mit XML die folgenden Richtlinien:  
  
-   Verwenden Sie zum Erstellen von XML-Dokumenten und –Fragmenten XML-Literale, anstatt die XML-APIs direkt aufzurufen.  
  
-   Importieren Sie XML-Namespaces auf Datei- oder Projektebene, um die Leistungsoptimierung für XML-Literale zu verwenden.  
  
-   Verwenden Sie die XML-Achseneigenschaften, um auf Elemente und Attribute in einem XML-Dokument zuzugreifen.  
  
-   Verwenden Sie eingebettete Ausdrücke, um Werte einzuschließen und XML aus vorhandenen Werten zu erstellen, anstatt API-Aufrufe wie die `Add`-Methode zu nutzen:  
  
     [!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]  
  
### <a name="linq-queries"></a>LINQ-Abfragen  
  
-   Verwenden Sie aussagekräftige Namen für Abfragevariablen:  
  
     [!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]  
  
-   Geben Sie Aliasnamen für Elemente in einer Abfrage an, um eine korrekte Großschreibung von Eigenschaftennamen anonymer Typen in Pascal-Schreibweise sicherzustellen:  
  
     [!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]  
  
-   Benennen Sie Eigenschaften um, wenn die Eigenschaftennamen im Ergebnis nicht eindeutig sind. Wenn die Abfrage beispielsweise einen Kundennamen und eine Auftrags-ID zurückgibt, sollten Sie diese im Ergebnis umbenennen, anstatt `Name` und `ID` zu übernehmen:  
  
     [!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]  
  
-   Verwenden Sie den Typrückschluss in der Deklaration von Abfragevariablen und Bereichsvariablen:  
  
     [!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]  
  
-   Richten Sie Abfrageklauseln unter der `From`-Anweisung aus:  
  
     [!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]  
  
-   Verwenden Sie vor anderen Abfrageklauseln `Where`-Klauseln, sodass die nachfolgenden Abfrageklauseln für den reduzierten, gefilterten Datensatz ausgeführt werden:  
  
     [!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]  
  
-   Verwenden Sie zum expliziten Definieren eines Verbindungsvorgangs die `Join`-Klausel anstelle der `Where`-Klausel, bei der ein Verbindungsvorgang implizit definiert wird:  
  
     [!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [Richtlinien für das Schreiben von sicherem Code](../../../standard/security/secure-coding-guidelines.md)
