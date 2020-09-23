---
title: Codierungskonventionen
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: eae283c757ddeb1290c15d82a41c8028a8941e63
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059157"
---
# <a name="visual-basic-coding-conventions"></a>Codierungskonventionen in Visual Basic

Microsoft entwickelt Beispiele und Dokumentation, die den Richtlinien in diesem Thema folgen. Wenn Sie dieselben Codierungskonventionen beachten, erhalten Sie möglicherweise folgende Vorteile:  
  
- Der Code erhält eine konsistente Gestaltung, damit sich die Leser mehr auf den Inhalt und nicht auf das Layout konzentrieren.  
  
- Leser verstehen den Code schneller, da sie Rückschlüsse aus früheren Erfahrungen ziehen können.  
  
- Sie können den Code kopieren, ändern und leichter pflegen.  
  
- Sie können sicherstellen, dass der Code die "empfohlenen Vorgehensweisen" für Visual Basic berücksichtigt.  
  
## <a name="naming-conventions"></a>Namenskonventionen  
  
- Informationen zu Benennungs Richtlinien finden Sie im Thema [Benennungs Richtlinien](../../../standard/design-guidelines/naming-guidelines.md) .  
  
- Verwenden Sie nicht "My" oder "my" als Teil eines Variablennamens. Diese Vorgehensweise führt zu Verwechslungen mit den `My`-Objekten.  
  
- Sie müssen die Namen von Objekten in automatisch generiertem Code nicht ändern, um sie an die Richtlinien anzupassen.  
  
## <a name="layout-conventions"></a>Layoutkonventionen  
  
- Fügen Sie Registerkarten als Leerzeichen ein, und verwenden Sie intelligenten Einzug mit vier Leerzeichen.  
  
- Verwenden Sie eine **ganz Zahl Auflistung (Neuformatierung) von Code** , um den Code im Code-Editor neu zu formatieren. Weitere Informationen finden Sie unter [Optionen, Text-Editor, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).  
  
- Verwenden Sie pro Zeile nur eine Anweisung. Verwenden Sie nicht das Visual Basic-Zeilentrennzeichen (:).  
  
- Vermeiden Sie, das explizite Zeilenfortsetzungszeichen "_" zugunsten der impliziten Zeilenfortsetzung, wenn die Sprache dies ermöglicht.  
  
- Verwenden Sie pro Zeile nur eine Deklaration.  
  
- Wenn **durch eine Auflistung (Neuformatierung) des Codes** keine Fortsetzungs Zeilen automatisch formatiert werden, werden Fortsetzungs Zeilen manuell mit einem Tabstopp Einzug eingelesen. In einer Liste werden jedoch die Elemente immer links ausgerichtet.  
  
    ```vb  
    a As Integer,  
    b As Integer  
    ```  
  
- Fügen Sie zwischen Methoden- und Eigenschaftendefinitionen mindestens eine Leerzeile ein.  
  
## <a name="commenting-conventions"></a>Konventionen für Kommentare  
  
- Fügen Sie den Kommentar in einer eigenen Zeile und nicht am Ende einer Codezeile ein.  
  
- Beginnen Sie den Kommentartext mit einem Großbuchstaben, und beenden Sie ihn mit einem Punkt.  
  
- Fügen Sie ein Leerzeichen zwischen dem Kommentartrennzeichen (') und dem Kommentartext ein.  
  
     [!code-vb[VbVbalrGuidelines#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#2)]  
  
- Erstellen Sie keine formatierten Blöcke von Sternchen, die die Kommentare umgeben.  
  
## <a name="program-structure"></a>Programmstruktur  
  
- Wenn Sie die `Main`-Methode verwenden, verwenden Sie das Standardkonstrukt für neue Konsolenanwendungen, und verwenden Sie `My` für Befehlszeilenargumente.  
  
     [!code-vb[VbVbalrGuidelines#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#3)]  
  
## <a name="language-guidelines"></a>Sprachrichtlinien  
  
### <a name="string-data-type"></a>String-Datentyp  
  
- Verwenden Sie die [Zeichenfolgeninterpolation](../language-features/strings/interpolated-strings.md), um wie im folgenden Code gezeigt kurze Zeichenfolgen zu verketten.
  
     ```vb
     MsgBox($"hello{vbCrLf}goodbye")
     ```
  
- Verwenden Sie das <xref:System.Text.StringBuilder>-Objekt, um Zeichenfolgen in Schleifen anzuhängen.  
  
     [!code-vb[VbVbalrGuidelines#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#5)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a>Weniger strenge Delegaten in Ereignishandlern  

 Um Ereignishandler zu vermeiden, qualifizieren Sie die Argumente (Object und EventArgs) nicht explizit. Wenn Sie nicht die Ereignisargumente verwenden, die an ein Ereignis übergeben werden (z. B. Sender als Objekt, "e" als EventArgs), verwenden Sie weniger strenge Delegaten, und lassen Sie die Ereignisargumente im Code aus:  
  
 [!code-vb[VbVbalrGuidelines#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#7)]  
  
### <a name="unsigned-data-type"></a>Datentyp ohne Vorzeichen  
  
- Verwenden Sie `Integer` anstelle von Typen ohne Vorzeichen, wenn sie nicht notwendig sind.  
  
### <a name="arrays"></a>Arrays  
  
- Verwenden Sie die kurze Syntax, wenn Sie Arrays in der Deklarationszeile initialisieren. Sie können z. B. folgende Syntax verwenden.  
  
     [!code-vb[VbVbalrGuidelines#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#8)]  
  
     Verwenden Sie nicht die folgende Syntax.  
  
     [!code-vb[VbVbalrGuidelines#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#9)]  
  
- Legen Sie den Arraybezeichner im Typ und nicht in der Variablen ab. Sie können z. B. folgende Syntax verwenden:  
  
     [!code-vb[VbVbalrGuidelines#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#11)]  
  
     Verwenden Sie nicht die folgende Syntax:  
  
     [!code-vb[VbVbalrGuidelines#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#10)]  
  
- Verwenden Sie die { }-Syntax, wenn Sie Arrays aus grundlegenden Datentypen deklarieren und initialisieren. Sie können z. B. folgende Syntax verwenden:  
  
     [!code-vb[VbVbalrGuidelines#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#12)]  
  
     Verwenden Sie nicht die folgende Syntax:  
  
     [!code-vb[VbVbalrGuidelines#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#13)]  
  
### <a name="use-the-with-keyword"></a>Verwenden des with-Schlüsselworts  

 Wenn Sie eine Reihe von Aufrufen eines Objekts ausführen, sollten Sie erwägen, das `With`-Schlüsselwort zu verwenden:  
  
 [!code-vb[VbVbalrGuidelines#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#15)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a>Verwenden Sie try-catch-Anweisungen zur Ausnahmebehandlung.  

 Verwenden Sie nicht `On Error Goto`.  
  
### <a name="use-the-isnot-keyword"></a>Verwenden des IsNot-Schlüsselworts  

 Verwenden Sie das Schlüsselwort `IsNot` statt `Not...Is Nothing`.  
  
### <a name="new-keyword"></a>New-Schlüsselwort  
  
- Verwenden Sie die kurze Instanziierung. Sie können z. B. folgende Syntax verwenden:  
  
     [!code-vb[VbVbalrGuidelines#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#21)]  
  
     Die vorangehende Zeile entspricht der Folgenden:  
  
     [!code-vb[VbVbalrGuidelines#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#22)]  
  
- Verwenden Sie für neue Objekte Objektinitialisierer anstelle des parameterlosen Konstruktors:  
  
     [!code-vb[VbVbalrGuidelines#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#23)]  
  
### <a name="event-handling"></a>Ereignisbehandlung  
  
- Verwenden Sie eher `Handles` als `AddHandler`:  
  
     [!code-vb[VbVbalrGuidelines#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#24)]  
  
- Verwenden Sie `AddressOf`, und instanziieren Sie den Delegaten nicht explizit:  
  
     [!code-vb[VbVbalrGuidelines#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#25)]  
  
- Wenn Sie ein Ereignis definieren, verwenden Sie die kurze Syntax, und lassen Sie den Delegaten vom Compiler definieren:  
  
     [!code-vb[VbVbalrGuidelines#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#26)]  
  
- Überprüfen Sie nicht, ob ein Ereignis `Nothing` (NULL) ist, bevor Sie die `RaiseEvent`-Methode aufrufen. Die `RaiseEvent`-Methode führt vor dem Auslösen des Ereignisses eine Überprüfung auf den Wert `Nothing` durch.  
  
### <a name="using-shared-members"></a>Verwenden von Shared-Membern  

 Rufen Sie `Shared`-Member über den Klassennamen auf, nicht von einer Instanzvariablen aus.  
  
### <a name="use-xml-literals"></a>Verwenden von XML-Literalen  

 XML-Literale vereinfachen allgemeine Aufgaben bei der Arbeit mit XML (z. B. Laden, Abfragen und Transformieren). Beachten Sie bei der Entwicklung mit XML die folgenden Richtlinien:  
  
- Verwenden Sie zum Erstellen von XML-Dokumenten und –Fragmenten XML-Literale, anstatt die XML-APIs direkt aufzurufen.  
  
- Importieren Sie XML-Namespaces auf Datei- oder Projektebene, um die Leistungsoptimierung für XML-Literale zu verwenden.  
  
- Verwenden Sie die XML-Achseneigenschaften, um auf Elemente und Attribute in einem XML-Dokument zuzugreifen.  
  
- Verwenden Sie eingebettete Ausdrücke, um Werte einzuschließen und XML aus vorhandenen Werten zu erstellen, anstatt API-Aufrufe wie die `Add`-Methode zu nutzen:  
  
     [!code-vb[VbVbalrGuidelines#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#27)]  
  
### <a name="linq-queries"></a>LINQ-Abfragen  
  
- Verwenden Sie aussagekräftige Namen für Abfragevariablen:  
  
     [!code-vb[VbVbalrGuidelines#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#28)]  
  
- Geben Sie Aliasnamen für Elemente in einer Abfrage an, um eine korrekte Großschreibung von Eigenschaftennamen anonymer Typen in Pascal-Schreibweise sicherzustellen:  
  
     [!code-vb[VbVbalrGuidelines#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#29)]  
  
- Benennen Sie Eigenschaften um, wenn die Eigenschaftennamen im Ergebnis nicht eindeutig sind. Wenn die Abfrage beispielsweise einen Kundennamen und eine Auftrags-ID zurückgibt, sollten Sie diese im Ergebnis umbenennen, anstatt `Name` und `ID` zu übernehmen:  
  
     [!code-vb[VbVbalrGuidelines#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#30)]  
  
- Verwenden Sie den Typrückschluss in der Deklaration von Abfragevariablen und Bereichsvariablen:  
  
     [!code-vb[VbVbalrGuidelines#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#31)]  
  
- Richten Sie Abfrageklauseln unter der `From`-Anweisung aus:  
  
     [!code-vb[VbVbalrGuidelines#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#32)]  
  
- Verwenden Sie vor anderen Abfrageklauseln `Where`-Klauseln, sodass die nachfolgenden Abfrageklauseln für den reduzierten, gefilterten Datensatz ausgeführt werden:  
  
     [!code-vb[VbVbalrGuidelines#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#33)]  
  
- Verwenden Sie zum expliziten Definieren eines Verbindungsvorgangs die `Join`-Klausel anstelle der `Where`-Klausel, bei der ein Verbindungsvorgang implizit definiert wird:  
  
     [!code-vb[VbVbalrGuidelines#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für das Schreiben von sicherem Code](../../../standard/security/secure-coding-guidelines.md)
