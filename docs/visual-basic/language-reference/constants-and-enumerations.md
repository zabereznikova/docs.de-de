---
title: Konstanten und Enumerationen
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- constants [Visual Basic]
- constants [Visual Basic], list of
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
ms.openlocfilehash: 5109bf42c9caa7528c5405bb1a5cff0cfb62a5ac
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705755"
---
# <a name="constants-and-enumerations-visual-basic"></a>Konstanten und Enumerationen (Visual Basic)

Visual Basic stellt eine Reihe von vordefinierten Konstanten und Enumerationen für Entwickler bereit. Konstanten speichern Werte, die während der Ausführung einer Anwendung konstant bleiben. Durch Enumerationen wird ein bequemer Weg bereitgestellt, um mit Sätzen verknüpfter Konstanten zu arbeiten, und um konstanten Werten Namen zuzuweisen.  
  
## <a name="constants"></a>Konstanten  
  
### <a name="conditional-compilation-constants"></a>Konstanten für bedingte Kompilierung  

 In der folgenden Tabelle sind die für die bedingte Kompilierung verfügbaren vordefinierten Konstanten aufgeführt.  
  
|**Konstante**|**Beschreibung**|  
|---|---|  
|`CONFIG`|Eine Zeichenfolge, die der aktuellen Einstellung des Felds für die **aktive Projektmappenkonfiguration** im **Configuration Manager**entspricht.|  
|`DEBUG`|Ein `Boolean` Wert, der im Dialogfeld **Projekteigenschaften** festgelegt werden kann. Standardmäßig definiert die Debugkonfiguration für ein Projekt `DEBUG`. Wenn `DEBUG` definiert ist, generieren <xref:System.Diagnostics.Debug> Klassen Methoden eine Ausgabe im **Ausgabe** Fenster. Wenn Sie nicht definiert ist, werden <xref:System.Diagnostics.Debug> Klassen Methoden nicht kompiliert, und es wird keine Debugausgabe generiert.|  
|`TARGET`|Eine Zeichenfolge, die den Ausgabetyp für das Projekt oder die Einstellung der Befehlszeilen **Ziel-** Option darstellt. Die folgenden Werte sind möglich `TARGET`:<br /><br /> -"winexe" für eine Windows-Anwendung.<br />-"exe" für eine Konsolenanwendung.<br />-"Library" für eine Klassenbibliothek.<br />-"Module" für ein Modul.<br />-Die Option **-target** kann in der integrierten Entwicklungsumgebung von Visual Studio festgelegt werden. Weitere Informationen finden Sie unter [-Target (Visual Basic)](../../visual-basic/reference/command-line-compiler/target.md).|  
|`TRACE`|Ein `Boolean` Wert, der im Dialogfeld **Projekteigenschaften** festgelegt werden kann. Standardmäßig definieren alle Konfigurationen für ein Projekt `TRACE`. Wenn `TRACE` definiert ist, generieren <xref:System.Diagnostics.Trace> Klassen Methoden eine Ausgabe im **Ausgabe** Fenster. Wenn Sie nicht definiert ist, werden <xref:System.Diagnostics.Trace> Klassen Methoden nicht kompiliert, und es wird keine `Trace` Ausgabe generiert.|  
|`VBC_VER`|Eine Zahl, die die Visual Basic Version in *Major*darstellt. *neben* Format.|  
  
### <a name="print-and-display-constants"></a>Print-und Display Konstanten  

 Wenn Sie Druck-und Anzeigefunktionen aufrufen, können Sie die folgenden Konstanten in Ihrem Code anstelle der tatsächlichen Werte verwenden.  
  
|**Konstante**|**Beschreibung**|  
|---|---|  
|`vbCrLf`|Kombination aus Wagen Rücklauf/Zeilenvorschub Zeichen.|  
|`vbCr`|Wagen Rücklauf Zeichen.|  
|`vbLf`|Zeilenvorschub Zeichen.|  
|`vbNewLine`|Zeilen Trennzeichen.|  
|`vbNullChar`|NULL-Zeichen.|  
|`vbNullString`|Nicht identisch mit einer Zeichenfolge der Länge 0 (""); wird zum Aufrufen externer Prozeduren verwendet.|  
|`vbObjectError`|Fehlernummer. Benutzerdefinierte Fehlernummern sollten größer als dieser Wert sein. Beispiel:<br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|Tabstopp Zeichen.|  
|`vbBack`|RÜCKTASTE Zeichen.|  
|`vbFormFeed`|Wird in Microsoft Windows nicht verwendet.|  
|`vbVerticalTab`|Nicht nützlich in Microsoft Windows.|  
  
## <a name="enumerations"></a>Enumerationen  

 In der folgenden Tabelle sind die von Visual Basic bereitgestellten Enumerationen aufgeführt und beschrieben.  
  
|-Enumeration|Beschreibung|  
|---|---|  
|<xref:Microsoft.VisualBasic.AppWinStyle>|Gibt in Aufrufen der <xref:Microsoft.VisualBasic.Interaction.Shell%2A>-Funktion den Fensterstil an, der für das aufgerufene Programm verwendet werden soll.|  
|<xref:Microsoft.VisualBasic.AudioPlayMode>|Gibt an, wie beim Aufruf von Audiomethoden Sounds wiedergegeben werden.|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|Gibt in Aufrufen der <xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>-Methode den Typ der zu überprüfenden Rolle an.|  
|<xref:Microsoft.VisualBasic.CallType>|Gibt den Typ der Prozedur an, die beim Aufrufen der <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>-Funktion aufgerufen wird.|  
|<xref:Microsoft.VisualBasic.CompareMethod>|Gibt in Aufrufen von Vergleichsfunktionen an, wie Zeichenfolgen miteinander verglichen werden sollen.|  
|<xref:Microsoft.VisualBasic.DateFormat>|Gibt in Aufrufen der <xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>-Funktion an, wie Datumsangaben angezeigt werden sollen.|  
|<xref:Microsoft.VisualBasic.DateInterval>|Gibt an, wie Datumsintervalle beim Aufrufen von Datumsfunktionen festgelegt und formatiert werden.|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|Gibt an, was geschehen soll, wenn ein Verzeichnis, das gelöscht werden soll, Dateien oder Verzeichnisse enthält.|  
|<xref:Microsoft.VisualBasic.DueDate>|Gibt beim Aufruf von Finanzmethoden an, wann Zahlungen fällig sind.|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType>|Gibt an, ob Textfelder durch Trennzeichen oder mit fester Breite versehen werden.|  
|<xref:Microsoft.VisualBasic.FileAttribute>|Gibt beim Aufruf von Dateizugriffsfunktionen die zu verwendenden Dateiattribute an.|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek>|Gibt in Aufrufen datumsbezogener Funktionen an, welcher Tag den ersten Tag der Woche darstellen soll.|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear>|Gibt in Aufrufen datumsbezogener Funktionen die Woche an, welche die erste Woche des Jahres darstellen soll.|  
|<xref:Microsoft.VisualBasic.MsgBoxResult>|Gibt gemäß Rückgabe durch die <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>-Funktion an, welche Schaltfläche in einem Meldungsfeld gedrückt wurde.|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle>|Gibt an, welche Schaltflächen beim Aufrufen der <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>-Funktion angezeigt werden.|  
|<xref:Microsoft.VisualBasic.OpenAccess>|Gibt an, wie eine Datei beim Aufruf von Dateizugriffsfunktionen geöffnet werden kann.|  
|<xref:Microsoft.VisualBasic.OpenMode>|Gibt an, wie eine Datei beim Aufruf von Dateizugriffsfunktionen geöffnet werden kann.|  
|<xref:Microsoft.VisualBasic.OpenShare>|Gibt an, wie eine Datei beim Aufruf von Dateizugriffsfunktionen geöffnet werden kann.|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption>|Gibt an, ob eine Datei dauerhaft gelöscht oder in den Papierkorb eingefügt werden soll.|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption>|Gibt an, ob alle Verzeichnisse oder nur die Verzeichnisse der obersten Ebene durchsucht werden sollen.|  
|<xref:Microsoft.VisualBasic.TriState>|Gibt einen `Boolean` Wert an oder gibt an, ob beim Aufrufen von Zahlen Formatierungsfunktionen der Standardwert verwendet werden soll.|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption>|Gibt an, was geschehen soll, wenn der Benutzer während eines Vorgangs auf **Abbrechen** klickt.|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption>|Gibt an, ob beim Kopieren, löschen oder Verschieben von Dateien oder Verzeichnissen ein Status Dialogfeld angezeigt werden soll.|  
|<xref:Microsoft.VisualBasic.VariantType>|Gibt den Typ eines Variant-Objekts an und wird von der <xref:Microsoft.VisualBasic.Information.VarType%2A>-Funktion zurückgegeben.|  
|<xref:Microsoft.VisualBasic.VbStrConv>|Gibt an, welche Art der Konvertierung beim Aufruf der <xref:Microsoft.VisualBasic.Strings.StrConv%2A>-Funktion ausgeführt werden soll.|  
  
## <a name="see-also"></a>Siehe auch

- [Sprachreferenz zu Visual Basic](../../visual-basic/language-reference/index.md)
- [Übersicht über Konstanten](../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Übersicht über Enumerationen](../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
