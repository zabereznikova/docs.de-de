---
title: 'Vorgehensweise: Zugreifen auf Office-Interop-Objekte mithilfe von Visual C#-Funktionen (C#-Programmierhandbuch) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- optional parameters [C#], Office programming
- named and optional arguments [C#], Office programming
- dynamic [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
- Office programming [C#]
ms.assetid: 041b25c2-3512-4e0f-a4ea-ceb2999e4d5e
caps.latest.revision: 33
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: e793e0b7f21948d16da4dcb618d73c4c3114adcb
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="how-to-access-office-interop-objects-by-using-visual-c-features-c-programming-guide"></a>Gewusst wie: Zugreifen auf Office-Interop-Objekte mithilfe von Visual C#-Funktionen (C#-Programmierhandbuch)
Visual C# verfügt über Funktionen, die den Zugriff auf Office-API-Objekte vereinfachen. Zu den neuen Funktionen zählen benannte und optionale Argumente, ein neuer Typ namens `dynamic` und die Möglichkeit, Argumente an Verweisparameter in COM-Methoden zu übergeben, als handele es sich um Werteparameter.  
  
 In diesem Thema verwenden Sie die neuen Funktionen, um Code zu schreiben, mit dem ein Microsoft Office Excel-Arbeitsblatt erstellt und angezeigt wird. Dann schreiben Sie Code, um ein Office Word-Dokument hinzuzufügen, das ein Symbol enthält, das mit dem Excel-Arbeitsblatt verknüpft ist.  
  
 Um diese exemplarische Vorgehensweise auszuführen, müssen Microsoft Office Excel 2007 und Microsoft Office Word 2007 oder neuere Versionen auf Ihrem Computer installiert sein.  
  
 Wenn Sie ein Betriebssystem verwenden, das älter ist als [!INCLUDE[windowsver](../../../csharp/programming-guide/interop/includes/windowsver_md.md)], stellen Sie sicher, dass [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)] installiert ist.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-create-a-new-console-application"></a>So erstellen Sie eine Konsolenanwendung  
  
1.  Starten Sie Visual Studio.  
  
2.  Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**. Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
3.  Erweitern Sie im Bereich **Installierte Vorlagen** den Eintrag **Visual C#**, und klicken Sie dann auf **Windows**.  
  
4.  Sehen Sie sich den oberen Rand des Dialogfelds **Neues Projekt** an, um sicherzustellen, dass **.NET Framework 4** (oder höher) als Zielframework ausgewählt ist.  
  
5.  Klicken Sie im Bereich **Vorlagen** auf **Konsolenanwendung**.  
  
6.  Geben Sie einen Namen für das Projekt im Feld **Name** ein.  
  
7.  Klicken Sie auf **OK**.  
  
     Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.  
  
### <a name="to-add-references"></a>So fügen Sie Verweise hinzu  
  
1.  Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektnamen, und klicken Sie dann auf **Verweis hinzufügen**. Das Dialogfeld **Verweis hinzufügen** wird angezeigt.  
  
2.  Wählen Sie auf der Seite **Assemblys** in der Liste **Komponentenname** den Eintrag **Microsoft.Office.Interop.Word** aus, und wählen Sie bei gedrückter STRG-Taste **Microsoft.Office.Interop.Excel** aus.  Wenn keine Assemblys sichtbar sind, müssen Sie unter Umständen sicherstellen, dass sie installiert sind und angezeigt werden (siehe [Vorgehensweise: Installieren von primären Interopassemblys für Office](/visualstudio/vsto/how-to-install-office-primary-interop-assemblies)).  
  
3.  Klicken Sie auf **OK**.  
  
### <a name="to-add-necessary-using-directives"></a>So fügen Sie erforderliche using-Anweisungen hinzu  
  
1.  Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei **Program.cs** und dann auf **Code anzeigen**.  
  
2.  Fügen Sie am Anfang der Codedatei die folgenden `using`-Direktiven hinzu.  
  
     [!code-cs[csProgGuideOfficeHowTo#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_1.cs)]  
  
### <a name="to-create-a-list-of-bank-accounts"></a>So erstellen Sie eine Liste mit Bankkonten  
  
1.  Fügen Sie die folgende Klassendefinition in **Program.cs** unter der `Program`-Klasse ein.  
  
     [!code-cs[csProgGuideOfficeHowTo#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_2.cs)]  
  
2.  Fügen Sie den folgenden Code der `Main`-Methode hinzu, um eine `bankAccounts`-Liste mit zwei Konten zu erstellen.  
  
     [!code-cs[csProgGuideOfficeHowTo#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_3.cs)]  
  
### <a name="to-declare-a-method-that-exports-account-information-to-excel"></a>So deklarieren Sie eine Methode, mit der Kontoinformationen in Excel exportiert werden  
  
1.  Fügen Sie die folgende Methode der `Program`-Klasse hinzu, um ein Excel-Arbeitsblatt einzurichten.  
  
     Die Methode [Add](http://go.microsoft.com/fwlink/?LinkId=210910) hat einen optionalen Parameter zur Angabe einer bestimmten Vorlage. Optionale Parameter, die in [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] neu sind, ermöglichen es Ihnen, das Argument für diesen Parameter auszulassen, wenn Sie den Standardwert des Parameters verwenden möchten. Da im folgenden Beispiel kein Argument gesendet wird, verwendet `Add` die Standardvorlage und erstellt eine neue Arbeitsmappe. Die entsprechende Anweisung in früheren Versionen von C# erfordert ein Platzhalterargument: `ExcelApp.Workbooks.Add(Type.Missing)`.  
  
     [!code-cs[csProgGuideOfficeHowTo#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_4.cs)]  
  
2.  Fügen Sie den folgenden Code am Ende von `DisplayInExcel` hinzu. Der Code fügt Werte in die ersten beiden Spalten der ersten Zeile des Arbeitsblatts ein.  
  
     [!code-cs[csProgGuideOfficeHowTo#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_5.cs)]  
  
3.  Fügen Sie den folgenden Code am Ende von `DisplayInExcel` hinzu. Die `foreach`-Schleife fügt die Informationen aus der Liste der Konten in die ersten beiden Spalten der nachfolgenden Zeilen des Arbeitsblattes ein.  
  
     [!code-cs[csProgGuideOfficeHowTo#7](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_6.cs)]  
  
4.  Fügen Sie den folgenden Code am Ende von `DisplayInExcel` hinzu, um die Spaltenbreite an den Inhalt anzupassen.  
  
     [!code-cs[csProgGuideOfficeHowTo#13](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_7.cs)]  
  
     Frühere Versionen von C# erfordern eine explizite Umwandlung für diese Vorgänge, da `ExcelApp.Columns[1]` ein `Object` zurückgibt und `AutoFit` eine Excel [Range](http://go.microsoft.com/fwlink/?LinkId=210911)-Methode ist. Die folgenden Zeilen verdeutlichen die Umwandlung.  
  
     [!code-cs[csProgGuideOfficeHowTo#14](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_8.cs)]  
  
     [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] und höhere Versionen konvertieren das zurückgegebene `Object` automatisch in `dynamic`, wenn die Compileroption [/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md) auf die Assembly verweist oder gleichermaßen wenn die Excel-Eigenschaft **Interop-Typen einbetten** auf TRUE festgelegt ist. Der Standardwert für diese Eigenschaft ist "True".  
  
### <a name="to-run-the-project"></a>So führen Sie das Projekt aus  
  
1.  Fügen Sie die folgende Zeile am Ende von `Main` hinzu.  
  
     [!code-cs[csProgGuideOfficeHowTo#8](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_9.cs)]  
  
2.  Drücken Sie STRG+F5.  
  
     Ein Excel-Arbeitsblatt mit den Daten der beiden Konten wird angezeigt.  
  
### <a name="to-add-a-word-document"></a>So fügen Sie ein Word-Dokument hinzu  
  
1.  Um zusätzliche Wege zu zeigen, wie [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] und höhere Versionen die Office-Programmierung verbessern, öffnet der folgende Code eine Word-Anwendung und erstellt ein Symbol, das mit dem Excel-Arbeitsblatt verknüpft ist.  
  
     Fügen Sie die Methode `CreateIconInWordDoc`, die später in diesem Schritt bereitgestellt wird, in die `Program`-Klasse ein. `CreateIconInWordDoc` verwendet benannte und optionale Argumente, um die Komplexität der Methodenaufrufe von [add](http://go.microsoft.com/fwlink/?LinkId=210937) und [PasteSpecial](http://go.microsoft.com/fwlink/?LinkId=147099) zu verringern. Diese Aufrufe beinhalten zwei weitere neue Funktionen, die in [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] eingeführt wurden und die Aufrufe von COM-Methoden mit Verweisparametern vereinfachen. Erstens können Sie Argumente an die Verweisparameter senden als handele es sich um Werteparameter. Das heißt, Sie können Werte direkt senden, ohne eine Variable für jeden Verweisparameter zu erstellen. Der Compiler generiert temporäre Variablen, die die Argumentwerte enthalten, und verwirft diese Variablen bei Rückkehr vom Aufruf. Zweitens können Sie das `ref`-Schlüsselwort in der Argumentliste auslassen.  
  
     Die `Add`-Methode verfügt über vier Verweisparameter, die alle optional sind. In [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] oder höher können Sie Argumente für einen oder alle Parameter weglassen, wenn Sie deren Standardwerte verwenden möchten. In [!INCLUDE[csharp_orcas_long](../../../csharp/programming-guide/interop/includes/csharp_orcas_long_md.md)] und früheren Versionen muss ein Argument für jeden Parameter bereitgestellt werden, und das Argument muss eine Variable sein, da es sich bei den Parametern um Verweisparameter handelt.  
  
     Die `PasteSpecial`-Methode fügt den Inhalt aus der Zwischenablage ein. Die Methode verfügt über sieben Verweisparameter, die alle optional sind. Der folgende Code gibt Argumente für zwei dieser Parameter an: `Link`, um eine Verknüpfung mit der Quelle des Zwischenablage-Inhalts zu erstellen, und `DisplayAsIcon`, um die Verknüpfung als Symbol anzuzeigen. In [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] können Sie benannte Argumente für diese zwei verwenden und die anderen weglassen. Obwohl es sich um Verweisparameter handelt, müssen Sie nicht das `ref`-Schlüsselwort verwenden oder Variablen erstellen, die als Argumente gesendet werden. Sie können die Werte direkt senden. In [!INCLUDE[csharp_orcas_long](../../../csharp/programming-guide/interop/includes/csharp_orcas_long_md.md)] und früheren Versionen müssen Sie für jeden Verweisparameter ein Variablenargument senden.  
  
     [!code-cs[csProgGuideOfficeHowTo#9](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_10.cs)]  
  
     In [!INCLUDE[csharp_orcas_long](../../../csharp/programming-guide/interop/includes/csharp_orcas_long_md.md)] oder früheren Versionen der Sprache ist der folgende komplexere Code erforderlich.  
  
     [!code-cs[csProgGuideOfficeHowTo#10](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_11.cs)]  
  
2.  Fügen Sie die folgende Anweisung am Ende von `Main` hinzu.  
  
     [!code-cs[csProgGuideOfficeHowTo#11](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_12.cs)]  
  
3.  Fügen Sie die folgende Anweisung am Ende von `DisplayInExcel` hinzu. Die `Copy`-Methode fügt das Arbeitsblatt der Zwischenablage hinzu.  
  
     [!code-cs[csProgGuideOfficeHowTo#12](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_13.cs)]  
  
4.  Drücken Sie STRG+F5.  
  
     Ein Word-Dokument mit einem Symbol wird angezeigt. Doppelklicken Sie auf das Symbol, um das Arbeitsblatt in den Vordergrund zu bringen.  
  
### <a name="to-set-the-embed-interop-types-property"></a>So legen Sie die Eigenschaft "Interop-Typen einbetten" fest  
  
1.  Weitere Verbesserungen sind möglich, wenn Sie einen COM-Typ aufrufen, der keine primäre Interop-Assembly (PIA) zur Laufzeit benötigt. Das Entfernen der Abhängigkeit von PIAs führt zu einer Versionsunabhängigkeit und einfacheren Bereitstellung. Weitere Informationen zu den Vorteilen der Programmierung ohne PIAs finden Sie unter [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).  
  
     Darüber hinaus ist die Programmierung einfacher, da die Typen, die erforderlich sind und von COM-Methoden zurückgegeben werden, mithilfe des Typs `dynamic` anstelle von `Object` dargestellt werden können. Variablen vom Typ `dynamic` werden erst zur Laufzeit ausgewertet, wodurch die Notwendigkeit der expliziten Umwandlung entfällt. Weitere Informationen finden Sie unter [Verwenden von dynamischen Typen](../../../csharp/programming-guide/types/using-type-dynamic.md).  
  
     In [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] ist das Einbetten von Typinformationen anstelle eines Einsatzes von PIAs das Standardverhalten. Aufgrund dieses Standardverhaltens werden mehrere der vorherigen Beispiele vereinfacht, da keine explizite Umwandlung erforderlich ist. Beispiel: Die Deklaration von `worksheet` in `DisplayInExcel` lautet `Excel._Worksheet workSheet = excelApp.ActiveSheet` und nicht `Excel._Worksheet workSheet = (Excel.Worksheet)excelApp.ActiveSheet`. Die Aufrufe von `AutoFit` in derselben Methode würden ebenfalls eine explizite Umwandlung ohne den Standard erfordern, da `ExcelApp.Columns[1]` ein `Object` zurückgibt und `AutoFit` eine Excel-Methode ist. Im folgenden Code sind alle Umwandlungen dargestellt.  
  
     [!code-cs[csProgGuideOfficeHowTo#14](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_8.cs)]  
  
2.  Wenn Sie den Standard ändern und PIAS verwenden möchten, anstatt die Typinformationen einzubetten, erweitern Sie im **Projektmappen-Explorer** den Knoten **Verweise**, und wählen Sie dann **Microsoft.Office.Interop.Excel** oder **Microsoft.Office.Interop.Word** aus.  
  
3.  Wenn Sie das Fenster **Eigenschaften** nicht sehen, drücken Sie **F4**.  
  
4.  Suchen Sie in der Liste der Eigenschaften nach **Interop-Typen einbetten**, und ändern Sie dessen Wert in **FALSE**. Gleichermaßen können Sie die Kompilierung durchführen, wenn Sie an einer Eingabeaufforderung die [/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)-Compileroption anstelle von [/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md) verwenden.  
  
### <a name="to-add-additional-formatting-to-the-table"></a>So fügen Sie der Tabelle zusätzliche Formatierungen hinzu  
  
1.  Ersetzen Sie die beiden Aufrufe von `AutoFit` in `DisplayInExcel` mit der folgenden Anweisung.  
  
     [!code-cs[csProgGuideOfficeHowTo#15](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_14.cs)]  
  
     Die Methode [AutoFormat](http://go.microsoft.com/fwlink/?LinkId=210948) verfügt über sieben Wertparameter, die alle optional sind. Benannte und optionale Argumente ermöglichen es Ihnen, Argumente für keine, einige oder alle von ihnen bereitzustellen. In der vorherigen Anweisung wurde ein Argument für nur einen der Parameter angegeben, nämlich für `Format`. Da `Format` der erste Parameter in der Parameterliste ist, müssen Sie nicht den Parameternamen angeben. Die Anweisung ist jedoch möglicherweise leichter zu verstehen, wenn der Parametername eingeschlossen wird, wie im folgenden Code gezeigt.  
  
     [!code-cs[csProgGuideOfficeHowTo#16](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_15.cs)]  
  
2.  Drücken Sie STRG + F5, um das Ergebnis anzuzeigen. Weitere Formate sind in der [XlRangeAutoFormat](http://go.microsoft.com/fwlink/?LinkId=210967)-Enumeration aufgelistet.  
  
3.  Vergleichen Sie die Anweisung in Schritt 1 mit dem folgenden Code, der die Argumente zeigt, die in [!INCLUDE[csharp_orcas_long](../../../csharp/programming-guide/interop/includes/csharp_orcas_long_md.md)] oder früheren Versionen erforderlich sind.  
  
     [!code-cs[csProgGuideOfficeHowTo#17](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_16.cs)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code veranschaulicht das vollständige Beispiel.  
  
 [!code-cs[csProgGuideOfficeHowTo#18](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_17.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Type.Missing?displayProperty=fullName>   
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)   
 [Verwenden von dynamischen Typen](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [Benannte und optionale Argumente](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)   
 [Gewusst wie: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
