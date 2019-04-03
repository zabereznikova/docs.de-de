---
title: Konstanten und Enumerationen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- constants [Visual Basic]
- constants [Visual Basic], list of
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
ms.openlocfilehash: 0a9c01269e12c2d84be4f30c236c439012a88153
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839587"
---
# <a name="constants-and-enumerations-visual-basic"></a>Konstanten und Enumerationen (Visual Basic)
Visual Basic stellt eine Reihe vordefinierter Konstanten und Enumerationen für Entwickler bereit. Konstanten speichern Werte, die während der Ausführung einer Anwendung konstant bleiben. Durch Enumerationen wird ein bequemer Weg bereitgestellt, um mit Sätzen verknüpfter Konstanten zu arbeiten, und um konstanten Werten Namen zuzuweisen.  
  
## <a name="constants"></a>Konstanten  
  
### <a name="conditional-compilation-constants"></a>Konstanten für bedingte Kompilierung  
 Die folgende Tabelle enthält die vordefinierten Konstanten, die für die bedingte Kompilierung zur Verfügung.  
  
|**Konstante**|**Beschreibung**|  
|---|---|  
|`CONFIG`|Eine Zeichenfolge, die die aktuelle Einstellung entspricht, der **aktive Projektmappenkonfiguration** im Feld der **Configuration Manager**.|  
|`DEBUG`|Ein `Boolean` -Wert, der festgelegt werden kann, in der **Projekteigenschaften** Dialogfeld. Definiert die Debug-Konfiguration für ein Projekt standardmäßig `DEBUG`. Wenn `DEBUG` definiert ist, <xref:System.Diagnostics.Debug> -Klasse, Methoden Generieren von Ausgaben für die **Ausgabe** Fenster. Wenn es nicht definiert ist, <xref:System.Diagnostics.Debug> -Klassenmethoden nicht kompiliert und keine Debug-Ausgabe generiert.|  
|`TARGET`|Eine Zeichenfolge, die den Ausgabetyp für das Projekt oder die Einstellung von der Befehlszeile **/target** Option. Die möglichen Werte der `TARGET` sind:<br /><br /> -"Winexe", für eine Windows-Anwendung.<br />-"Exe" für eine Konsolenanwendung.<br />-"Library" für eine Klassenbibliothek.<br />-"Modul" für ein Modul.<br />– Die **/target** Option kann festgelegt werden, in der integrierten Entwicklungsumgebung von Visual Studio. Weitere Informationen finden Sie unter [/target (Visual Basic)](../../visual-basic/reference/command-line-compiler/target.md).|  
|`TRACE`|Ein `Boolean` -Wert, der festgelegt werden kann, in der **Projekteigenschaften** Dialogfeld. Definieren Sie in der Standardeinstellung alle Konfigurationen für ein Projekt `TRACE`. Wenn `TRACE` definiert ist, <xref:System.Diagnostics.Trace> -Klasse, Methoden Generieren von Ausgaben für die **Ausgabe** Fenster. Wenn es nicht definiert ist, <xref:System.Diagnostics.Trace> Klasse-Klassenmethoden nicht kompiliert und keine `Trace` Ausgabe generiert.|  
|`VBC_VER`|Eine Zahl, die Visual Basic-Version, *wichtigen*. *kleinere* Format. Die Versionsnummer für [!INCLUDE[vbprvblong](~/includes/vbprvblong-md.md)] ist 8.0.|  
  
### <a name="print-and-display-constants"></a>Druck- und Anzeigekonstanten  
 Beim Aufrufen von Druck- und Anzeigefunktionen, können Sie die folgenden Konstanten in Ihrem Code anstelle der tatsächlichen Werte.  
  
|**Konstante**|**Beschreibung**|  
|---|---|  
|`vbCrLf`|Wagenrücklauf und Zeilenvorschub-Kombination.|  
|`vbCr`|Wagenrücklaufzeichen.|  
|`vbLf`|Zeilenvorschubzeichen.|  
|`vbNewLine`|Neue-Zeile-Zeichen.|  
|`vbNullChar`|NULL-Zeichen.|  
|`vbNullString`|Nicht identisch mit der eine Zeichenfolge der Länge 0 (null) (""); zum Aufrufen externer Prozeduren verwendet.|  
|`vbObjectError`|Fehlernummer. Benutzerdefinierte Fehlernummern sollten größer als dieser Wert sein. Zum Beispiel:<br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|Tabstoppzeichen.|  
|`vbBack`|Rücktastenzeichen.|  
|`vbFormFeed`|In Microsoft Windows verwendet nicht.|  
|`vbVerticalTab`|In Microsoft Windows nicht nützlich.|  
  
## <a name="enumerations"></a>Enumerationen  
 Die folgende Tabelle enthält und beschreibt die Enumerationen, die von Visual Basic bereitgestellt.  
  
|Enumeration|Beschreibung|  
|---|---|  
|<xref:Microsoft.VisualBasic.AppWinStyle>|Gibt den Fensterstil für das aufgerufene Programm verwendet werden soll, beim Aufrufen der <xref:Microsoft.VisualBasic.Interaction.Shell%2A> Funktion.|  
|<xref:Microsoft.VisualBasic.AudioPlayMode>|Gibt an, wie Sie den Aufruf von Audiomethoden Sounds wiedergeben.|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|Gibt den Typ der zu überprüfenden beim Aufrufen von Rolle der <xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A> Methode.|  
|<xref:Microsoft.VisualBasic.CallType>|Gibt den Typ der Prozedur, die aufgerufen wird, beim Aufrufen der <xref:Microsoft.VisualBasic.Interaction.CallByName%2A> Funktion.|  
|<xref:Microsoft.VisualBasic.CompareMethod>|Gibt an, wie Zeichenfolgen verglichen werden soll, wenn Vergleichsfunktionen aufgerufen.|  
|<xref:Microsoft.VisualBasic.DateFormat>|Gibt an, wie Datumsangaben angezeigt werden sollen beim Aufrufen der <xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A> Funktion.|  
|<xref:Microsoft.VisualBasic.DateInterval>|Gibt an, wie Datumsintervalle beim Aufrufen von Datumsfunktionen festgelegt und formatiert werden.|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|Gibt an, was geschehen soll, wenn ein Verzeichnis, das gelöscht werden soll, Dateien oder Verzeichnisse enthält.|  
|<xref:Microsoft.VisualBasic.DueDate>|Gibt an, wann Zahlungen fällig sind beim Aufruf von finanzmethoden.|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType>|Gibt an, ob Textfelder Trennzeichen sind oder eine feste Breite.|  
|<xref:Microsoft.VisualBasic.FileAttribute>|Gibt den zu verwendenden Dateiattribute beim Aufruf von Dateizugriffsfunktionen an.|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek>|Gibt den ersten Tag der Woche verwendet werden, wenn datumsbezogene Funktionen aufgerufen.|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear>|Gibt an, die erste Woche des Jahres darstellen soll, wenn datumsbezogene Funktionen aufgerufen.|  
|<xref:Microsoft.VisualBasic.MsgBoxResult>|Gibt gemäß Rückgabe durch die <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>-Funktion an, welche Schaltfläche in einem Meldungsfeld gedrückt wurde.|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle>|Gibt an, welche Schaltflächen beim Aufrufen der <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>-Funktion angezeigt werden.|  
|<xref:Microsoft.VisualBasic.OpenAccess>|Gibt an, wie eine Datei beim Aufruf von Dateizugriffsfunktionen geöffnet.|  
|<xref:Microsoft.VisualBasic.OpenMode>|Gibt an, wie eine Datei beim Aufruf von Dateizugriffsfunktionen geöffnet.|  
|<xref:Microsoft.VisualBasic.OpenShare>|Gibt an, wie eine Datei beim Aufruf von Dateizugriffsfunktionen geöffnet.|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption>|Gibt an, ob eine Datei endgültig gelöscht oder im Papierkorb abgelegt werden soll.|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption>|Gibt an, ob alle oder nur die Verzeichnisse der obersten Ebene.|  
|<xref:Microsoft.VisualBasic.TriState>|Gibt eine `Boolean` Wert oder ob der Standardwert verwendet werden soll, wenn Zahlenformatierungsfunktionen aufgerufen.|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption>|Gibt an, wie sein soll, wenn der Benutzer klickt **Abbrechen** während eines Vorgangs.|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption>|Gibt an, ob ein Statusdialogfeld angezeigt, wenn kopieren, löschen oder Verschieben von Dateien oder Verzeichnisse.|  
|<xref:Microsoft.VisualBasic.VariantType>|Gibt den Typ eines variant-Objekts, vom dem <xref:Microsoft.VisualBasic.Information.VarType%2A> Funktion.|  
|<xref:Microsoft.VisualBasic.VbStrConv>|Gibt an, welche Art der Konvertierung beim Aufruf der <xref:Microsoft.VisualBasic.Strings.StrConv%2A>-Funktion ausgeführt werden soll.|  
  
## <a name="see-also"></a>Siehe auch

- [Sprachreferenz zu Visual Basic](../../visual-basic/language-reference/index.md)
- [Visual Basic](../../visual-basic/index.md)
- [Übersicht über Konstanten](../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Übersicht über Enumerationen](../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
