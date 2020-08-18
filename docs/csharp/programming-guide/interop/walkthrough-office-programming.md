---
title: 'Exemplarische Vorgehensweise: Office-Programmierung (C# und Visual Basic)'
description: Lernen Sie die Features kennen, die Visual Studio in C# und Visual Basic zur Verbesserung der Programmierung für Microsoft Office bietet.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Office, programming in Visual Basic and C#
- Office programming [C#]
- Office programming [Visual Basic]
ms.assetid: 519cff31-f80b-4f0e-a56b-26358d0f8c51
ms.openlocfilehash: 76f0e2eccb5d1a59d9aaa3eed11b25dd2dd9cac3
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063002"
---
# <a name="walkthrough-office-programming-c-and-visual-basic"></a>Exemplarische Vorgehensweise: Office-Programmierung (C# und Visual Basic)

Visual Studio bietet Funktionen in C# und Visual Basic, die die Microsoft Office-Programmierung verbessern. Zu nützlichen C#-Funktionen gehören benannte und optionale Argumente und Rückgabewerte des Typs `dynamic`. Bei der COM-Programmierung können Sie das `ref`-Schlüsselwort weglassen und Zugriff auf indizierte Eigenschaften erhalten. Funktionen in Visual Basic umfassen automatisch implementierte Eigenschaften, Anweisungen in Lambdaausdrücken sowie Auflistungsinitialisierer.

Beide Sprachen ermöglichen das Einbetten von Typinformationen, wodurch Assemblys bereitgestellt werden können, die mit COM-Komponenten interagieren, ohne primäre Interop-Assemblys (PIAs) auf dem Computer des Benutzers bereitzustellen. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys](../../../standard/assembly/embed-types-visual-studio.md).

Diese exemplarische Vorgehensweise veranschaulicht diese Funktionen im Kontext der Office-Programmierung, aber viele dieser Funktionen sind auch bei der allgemeinen Programmierung nützlich. In der exemplarischen Vorgehensweise verwenden Sie eine Excel-Add-In-Anwendung, um eine Excel-Arbeitsmappe zu erstellen. Als nächstes erstellen Sie ein Word-Dokument, das einen Link zur Arbeitsmappe enthält. Zum Schluss sehen Sie, wie Sie die PIA-Abhängigkeit aktivieren und deaktivieren können.

## <a name="prerequisites"></a>Voraussetzungen

Auf Ihrem Computer müssen Microsoft Office Excel und Microsoft Office Word oder neuere Versionen installiert sein, um diese exemplarische Vorgehensweise ausführen zu können.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

### <a name="to-set-up-an-excel-add-in-application"></a>So richten Sie eine Excel-Add-In-Anwendung ein

1. Starten Sie Visual Studio.

2. Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.

3. Erweitern Sie im Bereich **Installierte Vorlagen** die Option **Visual Basic** oder **Visual C#** , erweitern Sie dann **Office**, und klicken Sie auf die Jahreszahl der Version des Office-Produkts.

4. Klicken Sie im Bereich **Vorlagen** auf **Excel \<version> Add-in**.

5. Sehen Sie am oberen Rand des Bereichs **Vorlagen** nach, um sicherzustellen, dass **.NET Framework 4** oder eine höhere Version im Feld **Zielframework** angezeigt wird.

6. Geben Sie, wenn gewünscht, einen Namen für das Projekt in das Feld **Name** ein.

7. Klicken Sie auf **OK**.

8. Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.

### <a name="to-add-references"></a>So fügen Sie Verweise hinzu

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektnamen, und klicken Sie dann auf **Verweis hinzufügen**. Das Dialogfeld **Verweis hinzufügen** wird angezeigt.

2. Wählen Sie auf der Registerkarte **Assemblys** die Option **Microsoft.Office.Interop.Excel**, Version `<version>.0.0.0` (einen Schlüssel für die Versionsnummer des Office-Produkts finden Sie unter [Microsoft Versions (in englischer Sprache)](https://en.wikipedia.org/wiki/Microsoft_Office#Versions)), in der Liste **Komponentenname** aus, und halten Sie dann die STRG-Taste gedrückt, während Sie **Microsoft.Office.Interop.Word**, `version <version>.0.0.0` auswählen. Wenn keine Assemblys sichtbar sind, müssen Sie unter Umständen sicherstellen, dass sie installiert sind und angezeigt werden (siehe [Vorgehensweise: Installieren von primären Interopassemblys für Office](/visualstudio/vsto/how-to-install-office-primary-interop-assemblies)).

3. Klicken Sie auf **OK**.

### <a name="to-add-necessary-imports-statements-or-using-directives"></a>So fügen Sie erforderliche Imports-Anweisungen oder using-Anweisungen hinzu

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei **ThisAddIn.vb** oder **ThisAddIn.cs**, und klicken Sie dann auf **Code anzeigen**.

2. Fügen Sie die folgenden `Imports`-Anweisungen (Visual Basic) oder `using`-Direktiven (C#) am Anfang der Codedatei ein, wenn sie noch nicht vorhanden sind.

     [!code-csharp[csOfficeWalkthrough#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/thisaddin.cs#1)]

     [!code-vb[csOfficeWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csofficewalkthrough/vb/thisaddin.vb#1)]

### <a name="to-create-a-list-of-bank-accounts"></a>So erstellen Sie eine Liste mit Bankkonten

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektnamen, klicken Sie auf **Hinzufügen** und dann auf **Klasse**. Benennen Sie die Klasse "Account.vb", wenn Sie Visual Basic verwenden, oder "Account.cs", wenn Sie C# verwenden. Klicken Sie auf **Hinzufügen**.

2. Ersetzen Sie die Definition der `Account`-Klasse durch den folgenden Code. Die Klassendefinitionen verwenden *automatisch implementierte Eigenschaften*. Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).

     [!code-csharp[csOfficeWalkthrough#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/account.cs#2)]

     [!code-vb[csOfficeWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csofficewalkthrough/vb/account.vb#2)]

3. Fügen Sie den folgenden Code in die `ThisAddIn_Startup`-Methode in *ThisAddIn.vb* oder *ThisAddIn.cs* ein, um eine `bankAccounts`-Liste mit zwei Konten zu erstellen. Die Listendeklarationen verwenden *Auflistungsinitialisierer*. Weitere Informationen finden Sie unter [Auflistungsinitialisierer](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).

     [!code-csharp[csOfficeWalkthrough#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/thisaddin.cs#3)]

     [!code-vb[csOfficeWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csofficewalkthrough/vb/thisaddin.vb#3)]

### <a name="to-export-data-to-excel"></a>So exportieren Sie Daten nach Excel

1. Fügen Sie in der gleichen Datei die folgende Methode der `ThisAddIn`-Klasse hinzu. Die Methode richtet eine Excel-Arbeitsmappe ein, in die die Daten exportiert werden.

     [!code-csharp[csOfficeWalkthrough#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/thisaddin.cs#4)]

     [!code-vb[csOfficeWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csofficewalkthrough/vb/thisaddin.vb#4)]

     Bei dieser Methode werden zwei neue C#-Funktionen verwendet. Beide Funktionen existieren bereits in Visual Basic.

    - Die Methode [Add](<xref:Microsoft.Office.Interop.Excel.Workbooks.Add%2A>) hat einen *optionalen Parameter* zum Angeben einer bestimmten Vorlage. Optionale Parameter – neu in C# 4 – ermöglichen es Ihnen, das Argument für diesen Parameter auszulassen, wenn Sie den Standardwert des Parameters verwenden möchten. Da im vorherigen Beispiel kein Argument gesendet wurde, verwendet `Add` die Standardvorlage und erstellt eine neue Arbeitsmappe. Die entsprechende Anweisung in früheren Versionen von C# erfordert ein Platzhalterargument: `excelApp.Workbooks.Add(Type.Missing)`.

         Weitere Informationen finden Sie unter [Benannte und optionale Argumente](../classes-and-structs/named-and-optional-arguments.md).

    - Die Eigenschaften `Range` und `Offset` des [range](<xref:Microsoft.Office.Interop.Excel.Range>)-Objekts verwenden die Funktion *Indizierte Eigenschaften*. Diese Funktion ermöglicht es Ihnen, diese Eigenschaften von COM-Typen zu nutzen, indem Sie die folgende typische C#-Syntax verwenden. Indizierte Eigenschaften ermöglichen es Ihnen außerdem, die `Value`-Eigenschaft des `Range`-Objekts zu verwenden, sodass Sie die `Value2`-Eigenschaft nicht mehr verwenden müssen. Die `Value`-Eigenschaft ist indiziert, der Index ist jedoch optional. Optionale Argumente und indizierte Eigenschaften arbeiten im folgenden Beispiel zusammen.

         [!code-csharp[csOfficeWalkthrough#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/thisaddin.cs#5)]

         In früheren Versionen der Sprache ist die folgende spezielle Syntax erforderlich.

         [!code-csharp[csOfficeWalkthrough#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/thisaddin.cs#6)]

         Sie können nicht Ihre eigenen indizierten Eigenschaften erstellen. Die Funktion unterstützt nur die Nutzung vorhandener indizierter Eigenschaften.

         Weitere Informationen finden Sie unter [Vorgehensweise: Indizierte Eigenschaften bei der COM-Interop-Programmierung](./how-to-use-indexed-properties-in-com-interop-rogramming.md).

2. Fügen Sie den folgenden Code am Ende von `DisplayInExcel` hinzu, um die Spaltenbreite an den Inhalt anzupassen.

     [!code-csharp[csOfficeWalkthrough#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/thisaddin.cs#7)]

     [!code-vb[csOfficeWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csofficewalkthrough/vb/thisaddin.vb#7)]

     Diese Ergänzungen veranschaulichen eine weitere Funktion in C#: die Behandlung von `Object`-Werten, die von COM-Hosts wie z.B. Office zurückgegeben wurden, als wären sie vom Typ [dynamic](../../language-reference/builtin-types/reference-types.md). Dies geschieht automatisch, wenn **Einbetten von Interop-Typen** auf den Standardwert `True` festgelegt ist, und ebenfalls, wenn die [-link](../../language-reference/compiler-options/link-compiler-option.md)-Compileroption auf die Assembly verweist. Der Typ `dynamic` ermöglicht eine späte Bindung, bereits in Visual Basic verfügbar, und vermeidet die in C# 3.0 und in früheren Sprachversionen erforderliche explizite Umwandlung.

     `excelApp.Columns[1]` gibt z.B.`Object` zurück, und `AutoFit` ist eine [Range](<xref:Microsoft.Office.Interop.Excel.Range>)-Methode von Excel. Ohne `dynamic` müssen Sie das von `excelApp.Columns[1]` zurückgegebene Objekt als eine Instanz von `Range` umwandeln, bevor Sie die Methode `AutoFit` aufrufen.

     [!code-csharp[csOfficeWalkthrough#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/thisaddin.cs#8)]

     Weitere Informationen zum Einbetten von Interop-Typen finden Sie in den Verfahren "So suchen Sie den PIA-Verweis" und "So stellen Sie die PIA-Abhängigkeit wieder her" weiter unten in diesem Thema. Weitere Informationen zu `dynamic` finden Sie unter [dynamic](../../language-reference/builtin-types/reference-types.md) oder [Verwenden von dynamischen Typen](../types/using-type-dynamic.md).

### <a name="to-invoke-displayinexcel"></a>So rufen Sie DisplayInExcel auf

1. Fügen Sie den folgenden Code am Ende der `ThisAddIn_StartUp`-Methode hinzu. Der Aufruf von `DisplayInExcel` enthält zwei Argumente. Das erste Argument ist der Name der Liste mit Konten, die verarbeitet werden sollen. Das zweite Argument ist ein mehrzeiliger Lambda-Ausdruck, der definiert, wie die Daten verarbeitet werden. Die `ID`- und `balance`-Werte für jedes Konto werden in angrenzenden Zellen angezeigt, und die Zeile wird rot dargestellt, wenn der Saldo kleiner als Null ist. Weitere Informationen finden Sie unter [Lambdaausdrücke](../../language-reference/operators/lambda-expressions.md).

     [!code-csharp[csOfficeWalkthrough#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/thisaddin.cs#9)]

     [!code-vb[csOfficeWalkthrough#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csofficewalkthrough/vb/thisaddin.vb#9)]

2. Drücken Sie F5, um das Programm auszuführen. Ein Excel-Arbeitsblatt wird mit den Kontendaten angezeigt.

### <a name="to-add-a-word-document"></a>So fügen Sie ein Word-Dokument hinzu

1. Fügen Sie den folgenden Code am Ende der `ThisAddIn_StartUp`-Methode hinzu, um ein Word-Dokument zu erstellen, das einen Link zur Excel-Arbeitsmappe enthält.

     [!code-csharp[csOfficeWalkthrough#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/thisaddin.cs#10)]

     [!code-vb[csOfficeWalkthrough#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csofficewalkthrough/vb/thisaddin.vb#10)]

     Dieser Code veranschaulicht mehrere der neuen Funktionen in C#: die Möglichkeit, das `ref`-Schlüsselwort in der COM-Programmierung auszulassen, benannte Argumente sowie optionale Argumente. Diese Funktionen sind bereits in Visual Basic vorhanden. Die Methode [PasteSpecial](<xref:Microsoft.Office.Interop.Word.Selection.PasteSpecial%2A>) verfügt über sieben Parameter, die als optionale Verweisparameter definiert sind. Benannte und optionale Argumente ermöglichen es Ihnen, die Parameter festzulegen, auf die Sie namentlich zugreifen möchten, und Argumente nur an diese Parameter zu senden. In diesem Beispiel werden Argumente gesendet, um anzugeben, dass ein Link zur Arbeitsmappe in der Zwischenablage erstellt werden soll (Parameter `Link`) und dass der Link im Word-Dokument als Symbol angezeigt werden soll (Parameter `DisplayAsIcon`). Visual C# ermöglicht auch das Weglassen des `ref`-Schlüsselworts für diese Argumente.

### <a name="to-run-the-application"></a>So führen Sie die Anwendung aus

1. Drücken Sie F5, um die Anwendung auszuführen. Excel wird gestartet und zeigt eine Tabelle mit den Informationen der beiden Konten in `bankAccounts` an. Anschließend wird ein Word-Dokument angezeigt, das einen Link zur Excel-Tabelle enthält.

### <a name="to-clean-up-the-completed-project"></a>So bereinigen Sie das abgeschlossene Projekt

1. Klicken Sie in Visual Studio auf **Projektmappe bereinigen** im Menü **Erstellen**. Andernfalls wird das Add-In jedes Mal ausgeführt, wenn Sie Excel auf Ihrem Computer öffnen.

### <a name="to-find-the-pia-reference"></a>So suchen Sie den PIA-Verweis

1. Führen Sie die Anwendung erneut aus, klicken Sie jedoch nicht auf **Projektmappe bereinigen**.

2. Wählen Sie **Start** aus. Suchen Sie **Microsoft Visual Studio \<version>** , und öffnen Sie eine Entwicklereingabeaufforderung.

3. Geben Sie in der Developer-Eingabeaufforderung für Visual Studio `ildasm` ein, und drücken Sie dann die EINGABETASTE. Das IL DASM-Fenster wird angezeigt.

4. Klicken Sie im IL DASM-Fenster im Menü **Datei** auf **Datei** > **Öffnen**. Doppelklicken Sie nacheinander auf **Visual Studio\<version>** und **Projekte**. Öffnen Sie den Ordner für das Projekt, und suchen Sie im Ordner „bin/Debug“ nach der Datei *Projektname*.dll. Doppelklicken Sie auf *Projektname*.dll. In einem neuen Fenster werden die Attribute Ihres Projekts sowie Verweise auf andere Module und Assemblys angezeigt. Beachten Sie, dass die Namespaces `Microsoft.Office.Interop.Excel` und `Microsoft.Office.Interop.Word` in der Assembly enthalten sind. Standardmäßig importiert der Compiler in Visual Studio die benötigten Typen aus einer referenzierten PIA in Ihre Assembly.

     Weitere Informationen finden Sie unter [Vorgehensweise: View Assembly Contents (Vorgehensweise: Anzeigen von Assemblyinhalt)](../../../standard/assembly/view-contents.md).

5. Doppelklicken Sie auf das Symbol **MANIFEST**. Es wird ein Fenster angezeigt, das eine Liste von Assemblys enthält, die vom Projekt referenzierte Elemente enthalten. `Microsoft.Office.Interop.Excel` und `Microsoft.Office.Interop.Word` sind nicht in der Liste enthalten. Da die Typen, die das Projekt benötigt, in die Assembly importiert wurden, sind keine Verweise auf eine PIA erforderlich. Dadurch wird die Bereitstellung vereinfacht. Die PIAs müssen nicht auf dem Computer des Benutzers vorhanden sein, und da für eine Anwendung keine bestimmte PIA-Version bereitgestellt werden muss, können die Anwendungen so konzipiert sein, dass sie mit mehreren Versionen von Office funktionieren, sofern die erforderlichen APIs in allen Versionen vorhanden sind.

     Da die Bereitstellung von primären Interop-Assemblys nicht mehr benötigt wird, können Sie eine Anwendung in erweiterten Szenarien erstellen, bei denen mehrere Versionen von Office, einschließlich früherer Versionen, verwendet werden. Dies funktioniert jedoch nur, wenn Ihr Code keine APIs verwendet, die nicht in der Version von Office verfügbar sind, mit der Sie arbeiten. Es ist nicht immer klar, ob eine bestimmte API in einer früheren Version verfügbar war; daher wird die Arbeit mit früheren Office-Versionen nicht empfohlen.

    > [!NOTE]
    > Office hat vor Office 2003 keine PIAs veröffentlicht. Aus diesem Grund besteht die einzige Möglichkeit zum Generieren einer Interop-Assembly für Office 2002 oder früheren Versionen darin, den COM-Verweis zu importieren.

6. Schließen Sie das Manifest-Fenster und das Assembly-Fenster.

### <a name="to-restore-the-pia-dependency"></a>So stellen Sie die PIA-Abhängigkeit wieder her

1. Klicken Sie im **Projektmappen-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**. Erweitern Sie den Ordner **Verweise**, und wählen Sie **Microsoft.Office.Interop.Excel** aus. Drücken Sie F4, um das Fenster **Eigenschaften** anzuzeigen.

2. Ändern Sie im Fenster **Eigenschaften** die Eigenschaft **Einbetten von Interop-Typen** von **True** zu **False**.

3. Wiederholen Sie die Schritte 1 und 2 in dieser Prozedur für `Microsoft.Office.Interop.Word`.

4. Kommentieren Sie in C# die beiden Aufrufe von `Autofit` am Ende der `DisplayInExcel`-Methode aus.

5. Drücken Sie F5, um sicherzustellen, dass das Projekt immer noch ordnungsgemäß ausgeführt wird.

6. Wiederholen Sie die Schritte 1 bis 3 der vorherigen Prozedur, um das Assembly-Fenster zu öffnen. Beachten Sie, dass `Microsoft.Office.Interop.Word` und `Microsoft.Office.Interop.Excel` nicht mehr in der Liste der eingebetteten Assemblys sind.

7. Doppelklicken Sie auf das Symbol **MANIFEST**, und führen Sie einen Bildlauf durch die Liste der referenzierten Assemblys durch. `Microsoft.Office.Interop.Word` und `Microsoft.Office.Interop.Excel` befinden sich in der Liste. Da die Anwendung auf die Excel- und Word-PIAs verweist und die Eigenschaft **Einbetten von Interop-Typen** auf **False** gesetzt ist, müssen beide Assemblys auf dem Computer des Endbenutzers vorhanden sein.

8. Klicken Sie in Visual Studio im Menü **Erstellen** auf **Projektmappe bereinigen**, um das abgeschlossene Projekt zu bereinigen.

## <a name="see-also"></a>Siehe auch

- [Automatisch implementierte Eigenschaften (Visual Basic)](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)
- [Automatisch implementierte Eigenschaften (C#)](../classes-and-structs/auto-implemented-properties.md)
- [Auflistungsinitialisierer](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Objekt- und Auflistungsinitialisierer](../classes-and-structs/object-and-collection-initializers.md)
- [Optionale Parameter](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [Übergeben von Argumenten nach Position und Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)
- [Benannte und optionale Argumente](../classes-and-structs/named-and-optional-arguments.md)
- [Frühes und spätes Binden](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [dynamic](../../language-reference/builtin-types/reference-types.md)
- [Verwenden von dynamischen Typen](../types/using-type-dynamic.md)
- [Lambdaausdrücke (Visual Basic)](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Lambdaausdrücke (C#)](../../language-reference/operators/lambda-expressions.md)
- [Indizierte Eigenschaften bei der COM-Interop-Programmierung](./how-to-use-indexed-properties-in-com-interop-rogramming.md)
- [Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office-Assemblys in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ee317478(v%3dvs.120))
- [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio](../../../standard/assembly/embed-types-visual-studio.md)
- [Exemplarische Vorgehensweise: Creating Your First VSTO Add-in for Excel (Exemplarische Vorgehensweise: Erstellen Ihres ersten VSTO-Add-Ins für Excel)](/visualstudio/vsto/walkthrough-creating-your-first-vsto-add-in-for-excel)
- [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md)
- [Interoperabilität](./index.md)
