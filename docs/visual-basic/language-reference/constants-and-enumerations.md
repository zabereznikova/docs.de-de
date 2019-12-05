---
title: Konstanten und Enumerationen
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- constants [Visual Basic]
- constants [Visual Basic], list of
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
ms.openlocfilehash: e47fd1c606f7d4cd0cf2fa6398beaa183ed95076
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838155"
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
|`TARGET`|Eine Zeichenfolge, die den Ausgabetyp für das Projekt oder die Einstellung der **/target** -Option der Befehlszeile darstellt. Die folgenden Werte sind möglich `TARGET`:<br /><br /> -"winexe" für eine Windows-Anwendung.<br />-"exe" für eine Konsolenanwendung.<br />-"Library" für eine Klassenbibliothek.<br />-"Module" für ein Modul.<br />-Die **/target** -Option kann in der integrierten Entwicklungsumgebung von Visual Studio festgelegt werden. Weitere Informationen finden Sie unter [-Target (Visual Basic)](../../visual-basic/reference/command-line-compiler/target.md).|  
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
|`vbObjectError`|Fehlernummer. Benutzerdefinierte Fehlernummern müssen größer als dieser Wert sein. Beispiel:<br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|Tabstopp Zeichen.|  
|`vbBack`|RÜCKTASTE Zeichen.|  
|`vbFormFeed`|Wird in Microsoft Windows nicht verwendet.|  
|`vbVerticalTab`|Nicht nützlich in Microsoft Windows.|  
  
## <a name="enumerations"></a>Enumerationen  

 In der folgenden Tabelle sind die von Visual Basic bereitgestellten Enumerationen aufgeführt und beschrieben.  
  
|-Enumeration|Beschreibung|  
|---|---|  
|<xref:Microsoft.VisualBasic.AppWinStyle>|Gibt den Fenster Stil an, der für das aufgerufene Programm verwendet wird, wenn die <xref:Microsoft.VisualBasic.Interaction.Shell%2A>-Funktion aufgerufen wird.|  
|<xref:Microsoft.VisualBasic.AudioPlayMode>|Gibt an, wie Sounds beim Aufrufen von Audiomethoden abgespielt werden.|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|Gibt den Typ der Rolle an, die beim Aufrufen der <xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A> Methode überprüft werden soll.|  
|<xref:Microsoft.VisualBasic.CallType>|Gibt den Typ der Prozedur an, die aufgerufen wird, wenn die <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>-Funktion aufgerufen wird.|  
|<xref:Microsoft.VisualBasic.CompareMethod>|Gibt an, wie Zeichen folgen verglichen werden, wenn Vergleichsfunktionen aufgerufen werden.|  
|<xref:Microsoft.VisualBasic.DateFormat>|Gibt an, wie Datumsangaben angezeigt werden, wenn die <xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A> Funktion aufgerufen wird.|  
|<xref:Microsoft.VisualBasic.DateInterval>|Gibt an, wie Datumsintervalle beim Aufrufen von Datumsfunktionen festgelegt und formatiert werden.|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|Gibt an, was geschehen soll, wenn ein Verzeichnis, das gelöscht werden soll, Dateien oder Verzeichnisse enthält.|  
|<xref:Microsoft.VisualBasic.DueDate>|Gibt an, wann Zahlungen fällig werden, wenn Finanz Methoden aufgerufen werden.|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType>|Gibt an, ob Textfelder durch Trennzeichen oder mit fester Breite versehen werden.|  
|<xref:Microsoft.VisualBasic.FileAttribute>|Gibt die Dateiattribute an, die beim Aufrufen von Datei Zugriffs Funktionen verwendet werden sollen.|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek>|Gibt den ersten Tag der Woche an, der verwendet werden soll, wenn datumsbezogene Funktionen aufgerufen werden.|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear>|Gibt die erste Woche des Jahres an, die verwendet werden soll, wenn datumsbezogene Funktionen aufgerufen werden.|  
|<xref:Microsoft.VisualBasic.MsgBoxResult>|Gibt gemäß Rückgabe durch die <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>-Funktion an, welche Schaltfläche in einem Meldungsfeld gedrückt wurde.|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle>|Gibt an, welche Schaltflächen beim Aufrufen der <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>-Funktion angezeigt werden.|  
|<xref:Microsoft.VisualBasic.OpenAccess>|Gibt an, wie eine Datei geöffnet wird, wenn Datei Zugriffs Funktionen aufgerufen werden.|  
|<xref:Microsoft.VisualBasic.OpenMode>|Gibt an, wie eine Datei geöffnet wird, wenn Datei Zugriffs Funktionen aufgerufen werden.|  
|<xref:Microsoft.VisualBasic.OpenShare>|Gibt an, wie eine Datei geöffnet wird, wenn Datei Zugriffs Funktionen aufgerufen werden.|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption>|Gibt an, ob eine Datei dauerhaft gelöscht oder in den Papierkorb eingefügt werden soll.|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption>|Gibt an, ob alle oder nur Verzeichnisse der obersten Ebene durchsucht werden sollen.|  
|<xref:Microsoft.VisualBasic.TriState>|Gibt einen `Boolean` Wert an oder gibt an, ob beim Aufrufen von Zahlen Formatierungsfunktionen der Standardwert verwendet werden soll.|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption>|Gibt an, was geschehen soll, wenn der Benutzer während eines Vorgangs auf **Abbrechen** klickt.|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption>|Gibt an, ob beim Kopieren, löschen oder Verschieben von Dateien oder Verzeichnissen ein Status Dialogfeld angezeigt werden soll.|  
|<xref:Microsoft.VisualBasic.VariantType>|Gibt den Typ eines Variant-Objekts an, das von der <xref:Microsoft.VisualBasic.Information.VarType%2A>-Funktion zurückgegeben wird.|  
|<xref:Microsoft.VisualBasic.VbStrConv>|Gibt an, welche Art der Konvertierung beim Aufruf der <xref:Microsoft.VisualBasic.Strings.StrConv%2A>-Funktion ausgeführt werden soll.|  
  
## <a name="see-also"></a>Siehe auch

- [Sprachreferenz zu Visual Basic](../../visual-basic/language-reference/index.md)
- [Übersicht über Konstanten](../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Übersicht über Enumerationen](../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
