---
title: 'Gewusst wie: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- named and optional arguments [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
ms.assetid: 65b8a222-bcd8-454c-845f-84adff5a356f
caps.latest.revision: "34"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a453699591397224435fba1e602c305f18e84a11
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="how-to-use-named-and-optional-arguments-in-office-programming-c-programming-guide"></a>Gewusst wie: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung (C#-Programmierhandbuch)
Benannte und optionale Argumente, die in [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] eingeführt wurden, optimieren die Zweckmäßigkeit, die Flexibilität und die Lesbarkeit in der C#-Programmierung. Diese Funktionen erleichtern zusätzlich den Zugriff auf COM-Schnittstellen wie etwa die Automatisierungs-APIs in Microsoft Office.  
  
 In folgendem Beispiel hat die Methode [ConvertToTable](http://go.microsoft.com/fwlink/?LinkId=145378) sechzehn Parameter, die Eigenschaften einer Tabelle repräsentieren, wie z.B. die Zeilen- und Spaltenanzahl, das Format, die Rahmen, Schriftarten und Farben. Alle sechzehn Parameter sind optional, weil Sie oftmals keine bestimmten Werte für sie festlegen möchten. Ohne benannte und optionale Argumente muss aber trotzdem ein Wert oder Platzhalterwert für jeden Parameter angegeben werden. Mit benannten und optionalen Argumenten geben Sie nur für die Parameter Werte an, die für Ihr Projekt erforderlich sind.  
  
 Microsoft Office Word muss auf Ihrem Computer installiert sein, damit Sie diesen Vorgang abschließen können.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-new-console-application"></a>So erstellen Sie eine Konsolenanwendung  
  
1.  Starten Sie Visual Studio.  
  
2.  Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.  
  
3.  Erweitern Sie im Bereich **Templates Categories** (Vorlagenkategorien) den Eintrag **Visual C#**, und klicken Sie dann auf **Windows**.  
  
4.  Sehen Sie am oberen Rand des Bereichs **Vorlagen nach**, um sicherzustellen, dass **.NET Framework 4** im Feld **Zielframework** angezeigt wird.  
  
5.  Klicken Sie im Bereich **Vorlagen** auf **Konsolenanwendung**.  
  
6.  Geben Sie einen Namen für das Projekt im Feld **Name** ein.  
  
7.  Klicken Sie auf **OK**.  
  
     Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.  
  
### <a name="to-add-a-reference"></a>So fügen Sie einen Verweis hinzu  
  
1.  Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektnamen, und klicken Sie dann auf **Verweis hinzufügen**. Das Dialogfeld **Verweis hinzufügen** wird angezeigt.  
  
2.  Wählen Sie auf der Seite **.NET** **Microsoft.Office.Interop.Word** in der Liste **Komponentenname** aus.  
  
3.  Klicken Sie auf **OK**.  
  
### <a name="to-add-necessary-using-directives"></a>So fügen Sie erforderliche using-Anweisungen hinzu  
  
1.  Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei **Program.cs** und dann auf **Code anzeigen**.  
  
2.  Fügen Sie am Anfang der Codedatei die folgenden `using`-Direktiven hinzu.  
  
     [!code-csharp[csProgGuideNamedAndOptional#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_1.cs)]  
  
### <a name="to-display-text-in-a-word-document"></a>So zeigen Sie Text in einem Word-Dokument an  
  
1.  Fügen Sie in der Klasse `Program` in Program.cs die folgende Methode hinzu, um eine Word-Anwendung und ein Word-Dokument zu erstellen. Die Methode [Hinzufügen](http://go.microsoft.com/fwlink/?LinkId=145381) verfügt über vier optionale Parameter. In diesem Beispiel werden ihre Standardwerte verwendet. Deshalb sind in der aufrufenden Anweisung keine Argumente erforderlich.  
  
     [!code-csharp[csProgGuideNamedAndOptional#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_2.cs)]  
  
2.  Fügen Sie den folgenden Code am Ende der Methode hinzu, um zu definieren, wo der Text im Dokument angezeigt werden und um welchen Text es sich dabei handeln soll.  
  
     [!code-csharp[csProgGuideNamedAndOptional#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_3.cs)]  
  
### <a name="to-run-the-application"></a>So führen Sie die Anwendung aus  
  
1.  Fügen Sie die folgende Anweisung in Main hinzu.  
  
     [!code-csharp[csProgGuideNamedAndOptional#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_4.cs)]  
  
2.  Drücken Sie STRG+F5, um das Projekt auszuführen. Ein Word-Dokument mit dem angegebenen Text wird angezeigt.  
  
### <a name="to-change-the-text-to-a-table"></a>So ändern Sie Text in eine Tabelle  
  
1.  Verwenden Sie die `ConvertToTable`-Methode, um den Text in eine Tabelle einzuschließen. Die Methode verfügt über sechzehn optionale Parameter. IntelliSense schließt optionale Parameter in Klammern ein, wie in folgender Abbildung veranschaulicht.  
  
     ![Liste der Parameter für die ConvertToTable-Methode](../../../csharp/programming-guide/classes-and-structs/media/convert_tableparameters.png "Convert_TableParameters")  
ConvertToTable-Parameter  
  
     Benannte und optionale Argumente ermöglichen es Ihnen, nur Werte für die Parameter anzugeben, die Sie auch ändern möchten. Fügen Sie den folgenden Code am Ende der `DisplayInWord`-Methode hinzu, um eine einfache Tabelle zu erstellen. Das Argument gibt an, dass die Kommas in der Textzeichenfolge in `range` die Zelle der Tabelle trennen.  
  
     [!code-csharp[csProgGuideNamedAndOptional#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_5.cs)]  
  
     In früheren Versionen von C# erfordert der Aufruf an `ConvertToTable` ein Verweisargument für jeden Parameter, wie in folgendem Codebeispiel gezeigt.  
  
     [!code-csharp[csProgGuideNamedAndOptional#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_6.cs)]  
  
2.  Drücken Sie STRG+F5, um das Projekt auszuführen.  
  
### <a name="to-experiment-with-other-parameters"></a>So können Sie sich auch an anderen Parametern versuchen  
  
1.  Um die Tabelle so zu ändern, dass sie nur noch eine Spalte und drei Zeilen hat, ersetzen Sie die letzte Zeile in `DisplayInWord` durch folgende Anweisung, und geben Sie dann STRG+F5 ein.  
  
     [!code-csharp[csProgGuideNamedAndOptional#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_7.cs)]  
  
2.  Um ein vordefiniertes Format für eine Tabelle anzugeben, ersetzen Sie die letzte Zeile in `DisplayInWord` durch folgende Anweisung, und geben Sie dann STRG+F5 ein. Das Format kann jede der [WdTableFormat](http://go.microsoft.com/fwlink/?LinkId=145382)-Konstanten sein.  
  
     [!code-csharp[csProgGuideNamedAndOptional#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_8.cs)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code enthält das vollständige Beispiel.  
  
 [!code-csharp[csProgGuideNamedAndOptional#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_9.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [Benannte und optionale Argumente](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)
