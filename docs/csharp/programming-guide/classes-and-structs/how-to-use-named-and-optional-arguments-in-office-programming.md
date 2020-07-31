---
title: 'Gewusst wie: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung – C#-Programmierhandbuch'
description: Hier erfahren Sie, wie Sie benannte Argumente und optionale Argumente verwenden, um den Zugriff auf COM-Schnittstellen wie die Automatisierungs-APIs in Microsoft Office zu vereinfachen.
ms.date: 07/20/2015
helpviewer_keywords:
- named and optional arguments [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
ms.assetid: 65b8a222-bcd8-454c-845f-84adff5a356f
ms.openlocfilehash: 7e24331d37e8fdbe2bc66a2d9f73a5f6a7242af9
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864344"
---
# <a name="how-to-use-named-and-optional-arguments-in-office-programming-c-programming-guide"></a>Gewusst wie: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung (C#-Programmierhandbuch)

Benannte und optionale Argumente, die in C# 4 eingeführt wurden, optimieren die Praxistauglichkeit, Flexibilität und Lesbarkeit in der C#-Programmierung. Diese Funktionen erleichtern zusätzlich den Zugriff auf COM-Schnittstellen wie etwa die Automatisierungs-APIs in Microsoft Office.

In folgendem Beispiel hat die Methode [ConvertToTable](<xref:Microsoft.Office.Interop.Word.Range.ConvertToTable%2A>) sechzehn Parameter, die Eigenschaften einer Tabelle repräsentieren, wie z.B. die Zeilen- und Spaltenanzahl, das Format, die Rahmen, Schriftarten und Farben. Alle sechzehn Parameter sind optional, weil Sie oftmals keine bestimmten Werte für sie festlegen möchten. Ohne benannte und optionale Argumente muss aber trotzdem ein Wert oder Platzhalterwert für jeden Parameter angegeben werden. Mit benannten und optionalen Argumenten geben Sie nur für die Parameter Werte an, die für Ihr Projekt erforderlich sind.

Microsoft Office Word muss auf Ihrem Computer installiert sein, damit Sie diesen Vorgang abschließen können.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-new-console-application"></a>So erstellen Sie eine Konsolenanwendung

1. Starten Sie Visual Studio.

2. Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.

3. Erweitern Sie im Bereich **Templates Categories** (Vorlagenkategorien) den Eintrag **Visual C#** , und klicken Sie dann auf **Windows**.

4. Sehen Sie am oberen Rand des Bereichs **Vorlagen nach**, um sicherzustellen, dass **.NET Framework 4** im Feld **Zielframework** angezeigt wird.

5. Klicken Sie im Bereich **Vorlagen** auf **Konsolenanwendung**.

6. Geben Sie einen Namen für das Projekt im Feld **Name** ein.

7. Klicken Sie auf **OK**.

     Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.

## <a name="to-add-a-reference"></a>So fügen Sie einen Verweis hinzu

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektnamen, und klicken Sie dann auf **Verweis hinzufügen**. Das Dialogfeld **Verweis hinzufügen** wird angezeigt.

2. Wählen Sie auf der Seite **.NET** **Microsoft.Office.Interop.Word** in der Liste **Komponentenname** aus.

3. Klicken Sie auf **OK**.

## <a name="to-add-necessary-using-directives"></a>So fügen Sie erforderliche using-Anweisungen hinzu

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei *Program.cs* und dann auf **Code anzeigen**.

2. Fügen Sie am Anfang der Codedatei die folgenden `using`-Anweisungen hinzu:

     [!code-csharp[csProgGuideNamedAndOptional#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#4)]

## <a name="to-display-text-in-a-word-document"></a>So zeigen Sie Text in einem Word-Dokument an

1. Fügen Sie in der Klasse `Program` in *Program.cs* die folgende Methode hinzu, um eine Word-Anwendung und ein Word-Dokument zu erstellen. Die Methode [Hinzufügen](<xref:Microsoft.Office.Interop.Word.Documents.Add%2A>) verfügt über vier optionale Parameter. In diesem Beispiel werden ihre Standardwerte verwendet. Deshalb sind in der aufrufenden Anweisung keine Argumente erforderlich.

     [!code-csharp[csProgGuideNamedAndOptional#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#6)]

2. Fügen Sie den folgenden Code am Ende der Methode hinzu, um zu definieren, wo der Text im Dokument angezeigt werden und um welchen Text es sich dabei handeln soll:

     [!code-csharp[csProgGuideNamedAndOptional#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#7)]

## <a name="to-run-the-application"></a>So führen Sie die Anwendung aus

1. Fügen Sie die folgende Anweisung in Main hinzu:

     [!code-csharp[csProgGuideNamedAndOptional#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#8)]

2. Drücken Sie <kbd>STRG</kbd>+<kbd>F5</kbd>, um das Projekt auszuführen. Ein Word-Dokument mit dem angegebenen Text wird angezeigt.

## <a name="to-change-the-text-to-a-table"></a>So ändern Sie Text in eine Tabelle
  
1. Verwenden Sie die `ConvertToTable`-Methode, um den Text in eine Tabelle einzuschließen. Die Methode verfügt über sechzehn optionale Parameter. IntelliSense schließt optionale Parameter in Klammern ein, wie in folgender Abbildung veranschaulicht.

     ![Liste der Parameter für die ConvertToTable-Methode](./media/how-to-use-named-and-optional-arguments-in-office-programming/convert-table-parameters.png)

     Benannte und optionale Argumente ermöglichen es Ihnen, nur Werte für die Parameter anzugeben, die Sie auch ändern möchten. Fügen Sie den folgenden Code am Ende der `DisplayInWord`-Methode hinzu, um eine einfache Tabelle zu erstellen. Das Argument gibt an, dass die Kommas in der Textzeichenfolge in `range` die Zelle der Tabelle trennen.

     [!code-csharp[csProgGuideNamedAndOptional#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#9)]

     In früheren Versionen von C# erfordert der Aufruf von `ConvertToTable` ein Verweisargument für jeden Parameter, wie in folgendem Codebeispiel gezeigt:
  
     [!code-csharp[csProgGuideNamedAndOptional#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#14)]

2. Drücken Sie <kbd>STRG</kbd>+<kbd>F5</kbd>, um das Projekt auszuführen.

## <a name="to-experiment-with-other-parameters"></a>So können Sie sich auch an anderen Parametern versuchen

1. Um die Tabelle so zu ändern, dass sie nur noch eine Spalte und drei Zeilen hat, ersetzen Sie die letzte Zeile in `DisplayInWord` durch folgende Anweisung, und geben Sie dann <kbd>STRG</kbd>+<kbd>F5</kbd> ein.  

     [!code-csharp[csProgGuideNamedAndOptional#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#10)]

2. Um ein vordefiniertes Format für die Tabelle anzugeben, ersetzen Sie die letzte Zeile in `DisplayInWord` durch folgende Anweisung, und geben Sie dann <kbd>STRG</kbd>+<kbd>F5</kbd> ein. Das Format kann jede der [WdTableFormat](<xref:Microsoft.Office.Interop.Word.WdTableFormat>)-Konstanten sein.

     [!code-csharp[csProgGuideNamedAndOptional#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#11)]

## <a name="example"></a>Beispiel

Der folgende Code enthält das vollständige Beispiel:

 [!code-csharp[csProgGuideNamedAndOptional#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#12)]

## <a name="see-also"></a>Siehe auch

- [Benannte und optionale Argumente](./named-and-optional-arguments.md)
