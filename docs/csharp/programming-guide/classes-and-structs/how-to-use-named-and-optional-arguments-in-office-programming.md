---
title: "Gewusst wie: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Benannte und optionale Argumente [C#], Office-Programmierung"
  - "Benannte Argumente [C#], Office-Programmierung"
  - "Optionale Argumente [C#], Office-Programmierung"
ms.assetid: 65b8a222-bcd8-454c-845f-84adff5a356f
caps.latest.revision: 34
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 34
---
# Gewusst wie: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung (C#-Programmierhandbuch)
Benannte Argumente und optionale Argumente, die mit [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp-dev10-long-md.md)] eingeführt wurden, erhöhen Benutzerfreundlichkeit, Flexibilität und Lesbarkeit bei der C\#\-Programmierung. Darüber hinaus wird durch diese Funktionen der Zugriff auf COM\-Schnittstellen, z. B. die Microsoft Office\-Automatisierungs\-APIs, erheblich erleichtert.  
  
 Die [ConvertToTable](http://go.microsoft.com/fwlink/?LinkId=145378)\-Methode im folgenden Beispiel verfügt über 16 Parameter, die Eigenschaften einer Tabelle darstellen, wie z. B. Spalten\- und Zeilenanzahl, Formatierung, Rahmen, Schriftarten und Farben.  Alle 16 Parameter sind optional, da Sie in der Regel keine bestimmten Werte für diese Parameter angeben möchten, die von den Standardwerten abweichen.  Ohne benannte und optionale Argumente müssen Sie jedoch für jeden dieser Parameter einen Wert bzw. einen Platzhalterwert bereitstellen.  Mit benannten und optionalen Argumenten müssen Sie nur für die Parameter Werte angeben, die für Ihr Projekt erforderlich sind.  
  
 Zur Durchführung dieser Prozeduren muss Microsoft Office Word auf Ihrem Computer installiert sein.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### So erstellen Sie eine neue Konsolenanwendung  
  
1.  Starten Sie Visual Studio.  
  
2.  Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.  
  
3.  Erweitern Sie im Bereich **Vorlagenkategorien** den Eintrag **Visual C\#**, und klicken Sie dann auf **Windows**.  
  
4.  Stellen Sie oben im Bereich **Vorlagen** sicher, dass im Feld **Zielframework** der Eintrag **.NET Framework 4** angezeigt wird.  
  
5.  Klicken Sie im Bereich **Vorlagen** auf **Konsolenanwendung**.  
  
6.  Geben Sie einen Namen für das Projekt in das Feld **Name** ein.  
  
7.  Klicken Sie auf **OK**.  
  
     Das neue Projekt wird im **Projektmappen\-Explorer** angezeigt.  
  
### So fügen Sie einen Verweis hinzu  
  
1.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf den Namen des Projekts, und klicken Sie auf **Verweis hinzufügen**.  Das Dialogfeld **Verweis hinzufügen** wird angezeigt.  
  
2.  Wählen Sie auf der Seite **.NET** den Eintrag **Microsoft.Office.Interop.Word** aus der Liste **Komponentenname** aus.  
  
3.  Klicken Sie auf **OK**.  
  
### So fügen Sie erforderliche Direktiven hinzu  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf die Datei **Program.cs**, und klicken Sie dann auf **Code anzeigen**.  
  
2.  Fügen Sie am Anfang der Codedatei die folgenden `using`\-Direktiven hinzu:  
  
     [!code-cs[csProgGuideNamedAndOptional#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/namedandoptionalsnippets/wordprogram.cs#4)]  
  
### So zeigen Sie Text in einem Word\-Dokument an  
  
1.  Fügen Sie in der `Program`\-Klasse in Program.cs die folgende Methode hinzu, um eine Word\-Anwendung und ein Word\-Dokument zu erstellen.  Die [Add](http://go.microsoft.com/fwlink/?LinkId=145381)\-Methode verfügt über vier optionale Parameter.  In diesem Beispiel werden die Standardwerte dieser Parameter verwendet.  Somit sind keine Argumente in der aufrufenden Anweisung erforderlich.  
  
     [!code-cs[csProgGuideNamedAndOptional#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/namedandoptionalsnippets/wordprogram.cs#6)]  
  
2.  Fügen Sie am Ende der Methode den folgenden Code hinzu, um zu definieren, an welcher Position im Dokument welcher Text angezeigt werden soll.  
  
     [!code-cs[csProgGuideNamedAndOptional#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/namedandoptionalsnippets/wordprogram.cs#7)]  
  
### So führen Sie die Anwendung aus  
  
1.  Fügen Sie Main die folgende Anweisung hinzu.  
  
     [!code-cs[csProgGuideNamedAndOptional#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/namedandoptionalsnippets/wordprogram.cs#8)]  
  
2.  Drücken Sie STRG\+F5, um das Projekt auszuführen.  Ein Word\-Dokument mit dem angegebenen Text wird angezeigt.  
  
### So konvertieren Sie den Text in eine Tabelle  
  
1.  Verwenden Sie die `ConvertToTable`\-Methode, um den Text in eine Tabelle einzubinden.  Die Methode verfügt über sechzehn optionale Parameter.  IntelliSense schließt optionale Parameter in Klammern ein, wie in der folgenden Abbildung dargestellt.  
  
     ![Liste der Parameter für ConvertToTable&#45;Methode.](../../../csharp/programming-guide/classes-and-structs/media/convert-tableparameters.png "Convert\_TableParameters")  
ConvertToTable\-Parameter  
  
     Benannte und optionale Argumente ermöglichen Ihnen die Angabe von Werten ausschließlich für Parameter, die geändert werden sollen.  Fügen Sie am Ende der `DisplayInWord`\-Methode den folgenden Code hinzu, um eine einfache Tabelle zu erstellen.  Das Argument gibt an, dass die Kommas in der Textzeichenfolge in `range` die Zellen der Tabelle trennen.  
  
     [!code-cs[csProgGuideNamedAndOptional#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/namedandoptionalsnippets/wordprogram.cs#9)]  
  
     In früheren Versionen von C\# erfordert der Aufruf von `ConvertToTable` ein Verweisargument für jeden Parameter, wie im folgenden Code gezeigt.  
  
     [!code-cs[csProgGuideNamedAndOptional#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/namedandoptionalsnippets/wordprogram.cs#14)]  
  
2.  Drücken Sie STRG\+F5, um das Projekt auszuführen.  
  
### So experimentieren Sie mit anderen Parametern  
  
1.  Um die Tabelle so zu ändern, dass sie eine Spalte und drei Zeilen enthält, ersetzen Sie die letzte Zeile in `DisplayInWord` durch die folgende Anweisung, und drücken Sie dann STRG\+F5.  
  
     [!code-cs[csProgGuideNamedAndOptional#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/namedandoptionalsnippets/wordprogram.cs#10)]  
  
2.  Um ein vordefiniertes Format für die Tabelle anzugeben, ersetzen Sie die letzte Zeile in `DisplayInWord` durch die folgende Anweisung, und drücken Sie dann STRG\+F5.  Das Format kann eine beliebige [WdTableFormat](http://go.microsoft.com/fwlink/?LinkId=145382)\-Konstante sein.  
  
     [!code-cs[csProgGuideNamedAndOptional#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/namedandoptionalsnippets/wordprogram.cs#11)]  
  
## Beispiel  
 Der folgende Code umfasst das vollständige Beispiel.  
  
 [!code-cs[csProgGuideNamedAndOptional#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/namedandoptionalsnippets/wordprogram.cs#12)]  
  
## Siehe auch  
 [Benannte und optionale Argumente](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)