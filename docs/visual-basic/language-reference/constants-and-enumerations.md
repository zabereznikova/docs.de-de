---
title: Konstanten und Enumerationen (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- enumerations [Visual Basic]
- constants [Visual Basic]
- constants [Visual Basic], list of
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: da42d58190e8069154cd8383cf0a87e0b19f5ae4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="constants-and-enumerations-visual-basic"></a>Konstanten und Enumerationen (Visual Basic)
Visual Basic stellt eine Reihe vordefinierter Konstanten und Enumerationen für Entwickler bereit. Konstanten speichern Werte, die während der Ausführung einer Anwendung konstant bleiben. Durch Enumerationen wird ein bequemer Weg bereitgestellt, um mit Sätzen verknüpfter Konstanten zu arbeiten, und um konstanten Werten Namen zuzuweisen.  
  
## <a name="constants"></a>Konstanten  
  
### <a name="conditional-compilation-constants"></a>Konstanten für die bedingte Kompilierung  
 In der folgenden Tabelle enthält die vordefinierten Konstanten, die für die bedingte Kompilierung zur Verfügung.  
  
|**Konstante**|**Beschreibung**|  
|---|---|  
|`CONFIG`|Eine Zeichenfolge, die die aktuelle Einstellung der entspricht der **aktive Projektmappenkonfiguration** Feld der **Configuration Manager**.|  
|`DEBUG`|Ein `Boolean` -Wert, der festgelegt werden kann, in der **Projekteigenschaften** (Dialogfeld). Definiert das Debug-Konfiguration für ein Projekt standardmäßig `DEBUG`. Wenn `DEBUG` definiert ist, <xref:System.Diagnostics.Debug> Klassenmethoden Ausgabewerte erzeugt werden, die **Ausgabe** Fenster. Wenn sie nicht definiert ist, <xref:System.Diagnostics.Debug> Klassenmethoden nicht kompiliert werden und keine Debug-Ausgabe generiert wird.|  
|`TARGET`|Eine Zeichenfolge, die den Ausgabetyp für das Projekt oder die Einstellung von der Befehlszeile **/target** Option. Die möglichen Werte der `TARGET` sind:<br /><br /> -"Winexe" für eine Windows-Anwendung.<br />-"Exe" für eine Konsolenanwendung.<br />-"Library" für eine Klassenbibliothek.<br />-"Modul" für ein Modul.<br />– Der **/target** Option kann festgelegt werden, der [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] integrierten Entwicklungsumgebung. Weitere Informationen finden Sie unter [/target (Visual Basic)](../../visual-basic/reference/command-line-compiler/target.md).|  
|`TRACE`|Ein `Boolean` -Wert, der festgelegt werden kann, in der **Projekteigenschaften** (Dialogfeld). Standardmäßig alle Konfigurationen für ein Projekt definieren `TRACE`. Wenn `TRACE` definiert ist, <xref:System.Diagnostics.Trace> Klassenmethoden Ausgabewerte erzeugt werden, die **Ausgabe** Fenster. Wenn sie nicht definiert ist, <xref:System.Diagnostics.Trace> Klasse Methoden werden nicht kompiliert und keine `Trace` Ausgabe generiert wird.|  
|`VBC_VER`|Eine Zahl, die Visual Basic-Version *wichtigen*. *kleinere* Format. Die Versionsnummer für [!INCLUDE[vbprvblong](~/includes/vbprvblong-md.md)] 8.0 ist.|  
  
### <a name="print-and-display-constants"></a>Druck- und Anzeigekonstanten  
 Beim Aufrufen von Druck- und Anzeigefunktionen, können Sie die folgenden Konstanten in Ihrem Code anstelle der eigentlichen Werte.  
  
|**Konstante**|**Beschreibung**|  
|---|---|  
|`vbCrLf`|Wagenrücklauf/Zeilenvorschub-Zeichenkombination.|  
|`vbCr`|Wagenrücklaufzeichen.|  
|`vbLf`|Zeilenvorschubzeichen.|  
|`vbNewLine`|Neue-Zeile-Zeichen.|  
|`vbNullChar`|NULL-Zeichen.|  
|`vbNullString`|Nicht derselbe wie eine leere Zeichenfolge (""); für Aufrufe von externen Prozeduren verwendet.|  
|`vbObjectError`|Fehlernummer. Benutzerdefinierte Fehlernummern müssen größer als dieser Wert sein. Zum Beispiel:<br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|Tabstoppzeichen.|  
|`vbBack`|Rücktastenzeichen.|  
|`vbFormFeed`|In Microsoft Windows verwendet nicht.|  
|`vbVerticalTab`|In Microsoft Windows nicht nützlich.|  
  
## <a name="enumerations"></a>Enumerationen  
 In der folgenden Tabelle aufgeführt und beschreibt die Enumerationen von Visual Basic bereitgestellt.  
  
|Enumeration|Beschreibung|  
|---|---|  
|<xref:Microsoft.VisualBasic.AppWinStyle>|Gibt den Fensterstil für die aufgerufenen Programm verwenden, beim Aufrufen der <xref:Microsoft.VisualBasic.Interaction.Shell%2A> Funktion.|  
|<xref:Microsoft.VisualBasic.AudioPlayMode>|Gibt an, wie Sounds wiederzugeben, wenn audio Methoden aufrufen.|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|Gibt den Typ der Rolle ein, überprüfen Sie beim Aufrufen der <xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A> Methode.|  
|<xref:Microsoft.VisualBasic.CallType>|Gibt den Typ der Prozedur, die aufgerufen werden, beim Aufrufen der <xref:Microsoft.VisualBasic.Interaction.CallByName%2A> Funktion.|  
|<xref:Microsoft.VisualBasic.CompareMethod>|Gibt an, wie Zeichenfolgen verglichen, beim von Vergleichsfunktionen aufrufen.|  
|<xref:Microsoft.VisualBasic.DateFormat>|Gibt an, wie zum Anzeigen von Datumsangaben beim Aufrufen der <xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A> Funktion.|  
|<xref:Microsoft.VisualBasic.DateInterval>|Gibt an, wie Datumsintervalle beim Aufrufen von Datumsfunktionen festgelegt und formatiert werden.|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|Gibt an, was geschehen soll, wenn ein Verzeichnis, das gelöscht werden soll, Dateien oder Verzeichnisse enthält.|  
|<xref:Microsoft.VisualBasic.DueDate>|Gibt an, wann Zahlungen fällig sind beim finanzielle Methoden aufrufen.|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType>|Gibt an, ob Textfelder Trennzeichen sind oder fester Breite.|  
|<xref:Microsoft.VisualBasic.FileAttribute>|Gibt an, die Dateiattribute zu verwendende Dateizugriff Funktionen aufrufen.|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek>|Gibt den ersten Tag der Woche beim Aufrufen von Datumsfunktionen verwenden.|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear>|Gibt die erste Woche des Jahres beim Aufrufen von Datumsfunktionen verwenden.|  
|<xref:Microsoft.VisualBasic.MsgBoxResult>|Gibt gemäß Rückgabe durch die <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>-Funktion an, welche Schaltfläche in einem Meldungsfeld gedrückt wurde.|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle>|Gibt an, welche Schaltflächen beim Aufrufen der <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>-Funktion angezeigt werden.|  
|<xref:Microsoft.VisualBasic.OpenAccess>|Gibt an, wie eine Datei zu öffnen, beim Dateizugriff Funktionen aufrufen.|  
|<xref:Microsoft.VisualBasic.OpenMode>|Gibt an, wie eine Datei zu öffnen, beim Dateizugriff Funktionen aufrufen.|  
|<xref:Microsoft.VisualBasic.OpenShare>|Gibt an, wie eine Datei zu öffnen, beim Dateizugriff Funktionen aufrufen.|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption>|Gibt an, ob eine Datei dauerhaft gelöscht oder in den Papierkorb platziert werden soll.|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption>|Gibt an, ob alle oder nur die Verzeichnisse der obersten Ebene.|  
|<xref:Microsoft.VisualBasic.TriState>|Gibt eine `Boolean` Wert oder gibt an, ob die Standardeinstellung beim Aufrufen von Funktionen Formatieren von Zahlen verwendet werden soll.|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption>|Gibt an, wie sein soll, wenn der Benutzer klickt auf **"Abbrechen"** während eines Vorgangs.|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption>|Gibt an, ob ein Statusdialogfeld angezeigt, beim Kopieren, löschen oder Verschieben von Dateien oder Verzeichnisse.|  
|<xref:Microsoft.VisualBasic.VariantType>|Gibt den Typ des variant-Objekts zurückgegeben wird, indem Sie die <xref:Microsoft.VisualBasic.Information.VarType%2A> Funktion.|  
|<xref:Microsoft.VisualBasic.VbStrConv>|Gibt an, welche Art der Konvertierung beim Aufruf der <xref:Microsoft.VisualBasic.Strings.StrConv%2A>-Funktion ausgeführt werden soll.|  
  
## <a name="see-also"></a>Siehe auch  
 [Sprachreferenz zu Visual Basic](../../visual-basic/language-reference/index.md)  
 [Visual Basic](../../visual-basic/index.md)  
 [Übersicht über Konstanten](../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [Übersicht über Enumerationen](../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
