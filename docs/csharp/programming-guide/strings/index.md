---
title: "Zeichenfolgen (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Zeichenfolgen"
  - "Zeichenfolgen [C#]"
ms.assetid: 21580405-cb25-4541-89d5-037846a38b07
caps.latest.revision: 41
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 41
---
# Zeichenfolgen (C#-Programmierhandbuch)
Eine Zeichenfolge ist ein Objekt vom Typ <xref:System.String>, dessen Wert Text ist.  Intern wird der Text als sequenzielle schreibgeschützte Auflistung von <xref:System.Char>\-Objekten gespeichert.  Eine C\#\-Zeichenfolge wird nicht mit einem NULL\-Zeichen am Ende abgeschlossen. Deshalb kann eine C\#\-Zeichenfolge eine beliebige Anzahl eingebetteter NULL\-Zeichen \('\\0'\) enthalten.  Die <xref:System.String.Length%2A>\-Eigenschaft einer Zeichenfolge stellt die Anzahl der in ihr enthaltenen `Char`\-Objekte und nicht die Anzahl von Unicode\-Zeichen dar.  Um in einer Zeichenfolge auf die einzelnen Unicode\-Codepunkte zuzugreifen, verwenden Sie das <xref:System.Globalization.StringInfo>\-Objekt.  
  
## string im Vergleich zuSystem.String  
 In C\# ist das `string`\-Schlüsselwort ein Alias für <xref:System.String>.  Deshalb entsprechen sich `String` und `string`, und Sie können eine beliebige Namenskonvention verwenden.  Die `String`\-Klasse stellt viele Methoden zum sicheren Erstellen, Bearbeiten und Vergleichen von Zeichenfolgen bereit.  Außerdem überlädt die Programmiersprache C\# einige Operatoren, um allgemeine Zeichenfolgenoperationen zu vereinfachen.  Weitere Informationen über das Schlüsselwort finden Sie unter [string](../../../csharp/language-reference/keywords/string.md).  Weitere Informationen über den Typ und seine Methoden finden Sie unter <xref:System.String>.  
  
## Deklarieren und Initialisieren von Zeichenfolgen  
 Sie haben verschiedene Möglichkeiten, Zeichenfolgen zu initialisieren und zu deklarieren, wie im folgenden Beispiel dargestellt:  
  
 [!code-cs[csProgGuideStrings#1](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_1.cs)]  
  
 Beachten Sie, dass Sie den [new](../../../csharp/language-reference/keywords/new-operator.md)\-Operator nur dann zum Erstellen eines Zeichenfolgenobjekts verwenden, wenn Sie die Zeichenfolge mit einem Zeichenarray initialisieren.  
  
 Initialisieren Sie eine Zeichenfolge mit dem konstanten <xref:System.String.Empty>\-Wert, um ein neues <xref:System.String>\-Objekt zu erstellen, dessen Zeichenfolge die Länge NULL aufweist.  Die Zeichenfolgenliteraldarstellung einer Zeichenfolge der Länge 0 \(null\) ist "".  Durch die Initialisierung von Zeichenfolgen mit dem Wert <xref:System.String.Empty> anstelle von [null](../../../csharp/language-reference/keywords/null.md) können Sie die Chancen einer <xref:System.NullReferenceException> reduzieren.  Verwenden Sie die statische <xref:System.String.IsNullOrEmpty%28System.String%29>\-Methode, um den Wert einer Zeichenfolge zu prüfen, bevor Sie versuchen, darauf zuzugreifen.  
  
## Unveränderlichkeit von Zeichenfolgenobjekten  
 Zeichenfolgenobjekte sind *unveränderlich*. Das bedeutet, dass sie nicht mehr geändert werden können, nachdem sie erstellt wurden.  Alle <xref:System.String>\-Methoden und C\#\-Operatoren, mit denen eine Zeichenfolge geändert werden könnte, geben diese Ergebnisse in einem neuen Zeichenfolgenobjekt zurück.  Im folgenden Beispiel bleiben beim Verketten des Inhalts von `s1` und `s2` zu einer einzelnen Zeichenfolge die beiden ursprünglichen Zeichenfolgen unverändert.  Der Operator `+=` erstellt eine neue Zeichenfolge, die die kombinierten Inhalte enthält.  Dieses neue Objekt wird der Variablen `s1` zugewiesen. Das ursprüngliche Objekt, das `s1` zugewiesen wurde, wird für die Garbage Collection freigegeben, da keine andere Variable einen Verweis darauf enthält.  
  
 [!code-cs[csProgGuideStrings#2](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_2.cs)]  
  
 Da eine "Zeichenfolgenänderung" einer neuen Zeichenfolgenerstellung gleichkommt, müssen Sie beim Erstellen von Verweisen auf Zeichenfolgen vorsichtig sein.  Wenn Sie einen Verweis auf eine Zeichenfolge erstellen und dann die ursprüngliche Zeichenfolge ändern, zeigt der Verweis weiterhin auf das ursprüngliche Objekt und nicht auf das neue Objekt, das beim Ändern der Zeichenfolge erstellt wurde.  Der folgende Code veranschaulicht dieses Verhalten:  
  
 [!code-cs[csProgGuideStrings#25](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_3.cs)]  
  
 Weitere Informationen zum Erstellen neuer Zeichenfolgen, die auf Änderungen wie Such\- und Ersetzungsvorgängen basieren, finden Sie unter [Gewusst wie: Ändern von Zeichenfolgeninhalten](../../../csharp/programming-guide/strings/how-to-modify-string-contents.md).  
  
## Reguläre und wörtliche Zeichenfolgenliterale  
 Verwenden Sie reguläre Zeichenfolgenliterale, wenn Sie Escapezeichen in C\#, wie im folgenden Beispiel dargestellt, einbetten müssen:  
  
 [!code-cs[csProgGuideStrings#3](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_4.cs)]  
  
 Verwenden Sie wörtliche Zeichenfolgen zur bequemeren Verwendung und besseren Lesbarkeit, wenn der Zeichenfolgentext umgekehrte Schrägstriche, z. B. in Dateipfaden, enthält.  Da wörtliche Zeichenfolgen neue Zeilenzeichen als Teil des Zeichenfolgentexts beibehalten, können sie zum Initialisieren mehrzeiliger Zeichenfolgen verwendet werden.  Verwenden Sie doppelte Anführungszeichen, um ein Anführungszeichen in eine wörtliche Zeichenfolge einzubetten.  Im folgenden Beispiel werden einige häufige Anwendungen für wörtliche Zeichenfolgen dargestellt:  
  
 [!code-cs[csProgGuideStrings#4](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_5.cs)]  
  
## Zeichenfolgen\-Escapesequenzen  
  
|Escapesequenz|Zeichenname|Unicode\-Codierung|  
|-------------------|-----------------|------------------------|  
|\\'|Einfaches Anführungszeichen|0x0027|  
|\\"|Doppeltes Anführungszeichen|0x0022|  
|\\\\|Umgekehrter Schrägstrich|0x005C|  
|\\0|Null|0x0000|  
|\\a|Warnung|0x0007|  
|\\b|Rückschritt|0x0008|  
|\\f|Seitenvorschub|0x000C|  
|\\n|Zeilenwechsel|0x000A|  
|\\r|Wagenrücklauf|0x000D|  
|\\t|Horizontaler Tabulator|0x0009|  
|\\U|Unicode\-Escapesequenz für Ersatzzeichenpaare.|\\Unnnnnnnn|  
|\\u|Unicode\-Escapesequenzen|\\u0041 \= "A"|  
|\\v|Vertikaler Tabulator|0x000B|  
|\\x|Unicode\-Escape\-Folge ähnlich wie "\\u" außer mit variabler Länge.|\\x0041 \= "A"|  
  
> [!NOTE]
>  Wörtliche Zeichenfolgen werden zur Kompilierzeit in normale Zeichenfolgen mit gleichen Escapesequenzen umgewandelt.  Wenn Sie also eine wörtliche Zeichenfolge im Debugger\-Überwachungsfenster anzeigen, werden die Escape\-Zeichen angezeigt, die vom Compiler hinzugefügt wurden und nicht die wörtliche Version aus dem Quellcode.  Die wörtliche Zeichenfolge @"C:\\files.txt" wird beispielsweise im Überwachungsfenster als "C:\\\\files.txt" angezeigt.  
  
## Formatzeichenfolgen  
 Eine Formatzeichenfolge ist eine Zeichenfolge, deren Inhalt zur Laufzeit dynamisch bestimmt werden kann.  Sie erstellen ein Format, indem Sie die statische <xref:System.String.Format%2A>\-Methode verwenden und Platzhalter in geschweiften Klammern einbetten, die durch andere Werte zur Laufzeit ersetzt werden.  Im folgenden Beispiel wird eine Formatzeichenfolge verwendet, um das Ergebnis jeder Iteration einer Schleife auszugeben:  
  
 [!code-cs[csProgGuideStrings#26](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_6.cs)]  
  
 Eine Überladung der <xref:System.Console.WriteLine%2A>\-Methode übernimmt eine Formatzeichenfolge als Parameter.  Deshalb können Sie nur ein Formatzeichenfolgenliteral ohne einen expliziten Aufruf der Methode einbetten.  Wenn Sie jedoch die <xref:System.Diagnostics.Trace.WriteLine%2A>\-Methode zum Anzeigen der Debugausgabe im **Ausgabefenster** von Visual Studio verwenden, müssen Sie die <xref:System.String.Format%2A>\-Methode ausdrücklich aufrufen, da <xref:System.Diagnostics.Trace.WriteLine%2A> nur eine Zeichenfolge akzeptiert, aber keine Formatzeichenfolge.  Weitere Informationen zu Formatzeichenfolgen finden Sie unter [Formatierung von Typen](../Topic/Formatting%20Types%20in%20the%20.NET%20Framework.md).  
  
## Teilzeichenfolgen  
 Eine Teilzeichenfolge ist jede Sequenz von Zeichen, die in einer Zeichenfolge enthalten sind.  Verwenden Sie die <xref:System.String.Substring%2A>\-Methode, um eine neue Zeichenfolge aus einem Teil der ursprünglichen Zeichenfolge zu erstellen.  Sie können nach einem oder mehreren Vorkommen einer Teilzeichenfolge mit der <xref:System.String.IndexOf%2A>\-Methode suchen.  Verwenden Sie die <xref:System.String.Replace%2A>\-Methode, um alle Vorkommen einer angegebenen Teilzeichenfolge durch eine neue Zeichenfolge zu ersetzen.  Wie die <xref:System.String.Substring%2A>\-Methode gibt <xref:System.String.Replace%2A> eine neue Zeichenfolge zurück und ändert die ursprüngliche Zeichenfolge nicht.  Weitere Informationen finden Sie unter [Gewusst wie: Suchen von Zeichenfolgen mithilfe von Zeichenfolgenmethoden](../../../csharp/programming-guide/strings/how-to-search-strings-using-string-methods.md) und unter [Gewusst wie: Ändern von Zeichenfolgeninhalten](../../../csharp/programming-guide/strings/how-to-modify-string-contents.md).  
  
 [!code-cs[csProgGuideStrings#7](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_7.cs)]  
  
## Zugreifen auf einzelne Zeichen  
 Sie können die Arraynotation mit einem Indexwert verwenden, um schreibgeschützten Zugriff auf einzelne Zeichen zu erhalten, wie im folgenden Beispiel dargestellt:  
  
 [!code-cs[csProgGuideStrings#9](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_8.cs)]  
  
 Falls die <xref:System.String>\-Methoden nicht die Funktionen bieten, die Sie zum Ändern einzelner Zeichen in einer Zeichenfolge benötigen, können Sie ein <xref:System.Text.StringBuilder>\-Objekt zum direkten Ändern einzelner Zeichen verwenden und dann eine neue Zeichenfolge zum Speichern der Ergebnisse mithilfe der <xref:System.Text.StringBuilder>\-Methoden erstellen.  Im folgenden Beispiel wird davon ausgegangen, dass Sie die ursprüngliche Zeichenfolge auf bestimmte Weise ändern müssen und die Ergebnisse dann für eine spätere Verwendung speichern:  
  
 [!code-cs[csProgGuideStrings#8](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_9.cs)]  
  
## NULL\-Zeichenfolgen und leere Zeichenfolgen  
 Eine leere Zeichenfolge ist eine Instanz eines <xref:System.String?displayProperty=fullName>\-Objekts, die 0 \(null\) Zeichen enthält.  Leere Zeichenfolgen werden häufig in verschiedenen Programmierszenarios verwendet, um ein leeres Textfeld darzustellen.  Sie können Methoden für leere Zeichenfolgen aufrufen, da sie gültige <xref:System.String?displayProperty=fullName>\-Objekte sind.  Leere Zeichenfolgen werden wie folgt initialisiert:  
  
```  
string s = String.Empty;  
```  
  
 Eine NULL\-Zeichenfolge bezieht sich hingegen nicht auf eine Instanz eines <xref:System.String?displayProperty=fullName>\-Objekts, und jeder Versuch, eine Methode für eine NULL\-Zeichenfolge aufzurufen, führt zu einer <xref:System.NullReferenceException>.  NULL\-Zeichenfolgen können jedoch in Verkettungs\- und Vergleichsvorgängen mit anderen Zeichenfolgen verwendet werden.  Die folgenden Beispiele zeigen, wann ein Verweis auf eine NULL\-Zeichenfolge zu einer Ausnahme führt und wann nicht:  
  
 [!code-cs[csProgGuideStrings#27](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_10.cs)]  
  
## Verwenden von StringBuilder zur schnellen Zeichenfolgenerstellung  
 Zeichenfolgenoperationen in .NET sind in höchstem Maße optimiert und wirken sich nicht wesentlich auf die Leistung aus.  In einigen Szenarios, wie geschlossenen Schleifen, die Hunderte oder Tausende Male ausgeführt werden, können sich die Zeichenfolgenoperationen auf die Leistung auswirken.  Die <xref:System.Text.StringBuilder>\-Klasse erstellt einen Zeichenfolgenpuffer, der eine verbesserte Leistung gewährleistet, falls Zeichenfolgen in Ihrem Programm häufig geändert werden.  Mit der <xref:System.Text.StringBuilder>\-Zeichenfolge können auch einzelne Zeichen neu zugewiesen werden, was vom integrierten Datentyp für Zeichenfolgen nicht unterstützt wird.  Dieser Code ändert zum Beispiel den Inhalt einer Zeichenfolge, ohne eine neue Zeichenfolge zu erstellen:  
  
 [!code-cs[csProgGuideStrings#20](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_11.cs)]  
  
 In diesem Beispiel wird ein <xref:System.Text.StringBuilder>\-Objekt verwendet, um eine Zeichenfolge aus einer Reihe von numerischen Typen zu erstellen:  
  
 [!code-cs[csProgGuideStrings#15](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_12.cs)]  
  
## Zeichenfolgen, Erweiterungsmethoden und LINQ  
 Da der <xref:System.String>\-Typ <xref:System.Collections.Generic.IEnumerable%601> implementiert, können Sie die in der <xref:System.Linq.Enumerable>\-Klasse in Zeichenfolgen definierten Erweiterungsmethoden verwenden.  Aus Gründen der Übersichtlichkeit werden diese Methoden für den <xref:System.String>\-Typ aus IntelliSense ausgeschlossen, sie sind jedoch weiterhin vorhanden.  Sie können auch [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]\-Abfrageausdrücke für Zeichenfolgen verwenden.  Weitere Informationen finden Sie unter [LINQ and Strings](../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md).  
  
## Verwandte Themen  
  
|Thema|Beschreibung|  
|-----------|------------------|  
|[Gewusst wie: Ändern von Zeichenfolgeninhalten](../../../csharp/programming-guide/strings/how-to-modify-string-contents.md)|Veranschaulicht anhand eines Codebeispiels, wie der Inhalt von Zeichenfolgen geändert wird.|  
|[Gewusst wie: Verketten von mehreren Zeichenfolgen](../../../csharp/programming-guide/strings/how-to-concatenate-multiple-strings.md)|Illustriert, wie der Operator `+` und die `Stringbuilder`\-Klasse zum Verknüpfen von Zeichenfolgen zur Kompilierungs\- und Laufzeit verwendet werden.|  
|[Gewusst wie: Vergleichen von Zeichenfolgen](../../../csharp/programming-guide/strings/how-to-compare-strings.md)|Zeigt, wie ein Ordinalvergleich von Zeichenfolgen ausgeführt wird.|  
|[Gewusst wie: Analysieren von Zeichenfolgen mithilfe von String.Split ](../../../csharp/programming-guide/strings/how-to-parse-strings-using-string-split.md)|Enthält ein Codebeispiel, das illustriert, wie die `String.Split`\-Methode zum Analysieren von Zeichenfolgen verwendet wird.|  
|[Gewusst wie: Suchen von Zeichenfolgen mithilfe von Zeichenfolgenmethoden](../../../csharp/programming-guide/strings/how-to-search-strings-using-string-methods.md)|Erklärt, wie bestimmte Methoden zum Suchen von Zeichenfolgen verwendet werden.|  
|[Gewusst wie: Suchen von Zeichenfolgen mithilfe von regulären Ausdrücken](../../../csharp/programming-guide/strings/how-to-search-strings-using-regular-expressions.md)|Erklärt, wie reguläre Ausdrücke zum Suchen von Zeichenfolgen verwendet werden.|  
|[Gewusst wie: Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)|Zeigt, wie eine Zeichenfolge sicher analysiert wird, um zu sehen, ob es einen gültigen numerischen Wert hat.|  
|[Gewusst wie: Konvertieren einer Zeichenfolge in einen DateTime\-Wert](../../../csharp/programming-guide/strings/how-to-convert-a-string-to-a-datetime.md)|Zeigt, wie eine Zeichenfolge, z. B. "01\/24\/2008", in ein <xref:System.DateTime?displayProperty=fullName>\-Objekt konvertiert wird.|  
|[Grundlegende Zeichenfolgenoperationen](../Topic/Basic%20String%20Operations%20in%20the%20.NET%20Framework.md)|Stellt Links zu Themen über die Verwendung der <xref:System.String?displayProperty=fullName>\-Methode und der <xref:System.Text.StringBuilder?displayProperty=fullName>\-Methode zur Ausführung grundlegender Zeichenfolgenoperationen bereit.|  
|[Analysieren von Zeichenfolgen](../Topic/Parsing%20Strings%20in%20the%20.NET%20Framework.md)|Beschreibt, wie Zeichen oder Leerzeichen in eine Zeichenfolge eingefügt werden.|  
|[Vergleichen von Zeichenfolgen](../Topic/Comparing%20Strings%20in%20the%20.NET%20Framework.md)|Enthält Informationen darüber, wie Zeichenfolgen verglichen werden, und bietet Beispiele in C\# und Visual Basic.|  
|[Verwenden der StringBuilder\-Klasse](../Topic/Using%20the%20StringBuilder%20Class%20in%20the%20.NET%20Framework.md)|Beschreibt, wie dynamische Zeichenfolgenobjekte mit der <xref:System.Text.StringBuilder>\-Klasse erstellt und geändert werden.|  
|[LINQ and Strings](../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)|Enthält Informationen darüber, wie verschiedene Zeichenfolgenoperationen mit LINQ\-Abfragen durchgeführt werden.|  
|[C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)|Bietet Links zu Themen, in denen Programmierkonstrukte von C\# beschrieben werden.|  
  
## Enthaltenes Buchkapitel  
 [More About Variables](http://go.microsoft.com/fwlink/?LinkId=221230) in [Beginning Visual C\# 2010](http://go.microsoft.com/fwlink/?LinkId=221214)