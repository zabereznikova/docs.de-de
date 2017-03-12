---
title: "Constants and Enumerations (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "enumerations [Visual Basic]"
  - "constants"
  - "constants, list of"
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Constants and Enumerations (Visual Basic)
[!INCLUDE[vs2017banner](../../visual-basic/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] stellt eine Reihe vordefinierter Konstanten und Enumerationen für Entwickler bereit.  Konstanten speichern Werte, die während der gesamten Ausführung der Anwendung nicht geändert werden.  Enumerationen bieten eine bequeme Möglichkeit, mit Gruppen verwandter Konstanten zu arbeiten und Konstantenwerte mit Namen zu verknüpfen.  
  
## Konstanten  
  
### Bedingte Kompilierungskonstanten  
 Die folgende Tabelle enthält die vordefinierten Konstanten, die für die bedingte Kompilierung verfügbar sind.  
  
|||  
|-|-|  
|**Konstante**|**Beschreibung**|  
|`CONFIG`|Eine Zeichenfolge, die der aktuellen Einstellung des Felds **Konfiguration der aktuellen Projektmappe** im **Konfigurations\-Manager** entspricht.|  
|`DEBUG`|Ein `Boolean`\-Wert, der im Dialogfeld **Projekteigenschaften** festgelegt werden kann.  Standardmäßig definiert die Debugkonfiguration für ein Projekt `DEBUG`.  Wenn `DEBUG` definiert wurde, generieren die <xref:System.Diagnostics.Debug>\-Klassenmethoden Ausgabedaten für das Fenster **Ausgabe**.  Ist das nicht der Fall, so werden die <xref:System.Diagnostics.Debug>\-Klassenmethoden nicht kompiliert, und es wird keine Debugausgabe generiert.|  
|`TARGET`|Eine Zeichenfolge, die den Ausgabetyp für das Projekt oder die Einstellung der **\/target**\-Befehlszeilenoption darstellt.  Mögliche Werte von `TARGET` sind:<br /><br /> -   "winexe" für eine Windows\-Anwendung<br />-   "exe" für eine Konsolenanwendung<br />-   "library" für eine Klassenbibliothek<br />-   "module" für ein Modul<br />-   Die **\/target**\-Option kann in der [!INCLUDE[vsprvs](../../csharp/includes/vsprvs-md.md)]\-integrierten Entwicklungsumgebung festgelegt werden.  Weitere Informationen finden Sie unter [\/target](../../visual-basic/reference/command-line-compiler/target.md).|  
|`TRACE`|Ein `Boolean`\-Wert, der im Dialogfeld **Projekteigenschaften** festgelegt werden kann.  Standardmäßig definieren alle Konfigurationen für ein Projekt `TRACE`.  Wenn `TRACE` definiert wurde, generieren die <xref:System.Diagnostics.Trace>\-Klassenmethoden Ausgabedaten für das Fenster **Ausgabe**.  Ist das nicht der Fall, so werden die <xref:System.Diagnostics.Trace>\-Klassenmethoden nicht kompiliert, und es wird keine `Trace`\-Ausgabe generiert.|  
|`VBC_VER`|Eine Zahl, die die [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Version im Format *Hauptversion*.*Nebenversion* darstellt.  Die Versionsnummer für [!INCLUDE[vbprvblong](../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] ist 8.0.|  
  
### Druck\- und Anzeigekonstanten  
 Beim Aufrufen von Druck\- und Anzeigekonstanten können Sie anstelle der eigentlichen Werte die folgenden Konstanten im Code verwenden.  
  
|||  
|-|-|  
|**Konstante**|**Beschreibung**|  
|`vbCrLf`|Wagenrücklaufzeichen\/ Zeilenvorschubzeichen.|  
|`vbCr`|Wagenrücklaufzeichen|  
|`vbLf`|Zeilenvorschubzeichen|  
|`vbNewLine`|Zeilenendemarke|  
|`vbNullChar`|NULL\-Zeichen.|  
|`vbNullString`|Entspricht nicht einer Zeichenfolge mit 0\-Länge \(""\); für den Aufruf externer Prozeduren.|  
|`vbObjectError`|Fehlernummer.  Benutzerdefinierte Fehlernummern sollten größer als dieser Wert sein.  Beispiele:<br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|Tabulatorzeichen|  
|`vbBack`|Rückschrittzeichen|  
|`vbFormFeed`|Wird in Microsoft Windows nicht verwendet.|  
|`vbVerticalTab`|In Microsoft Windows nicht sinnvoll.|  
  
## Enumerationen  
 In der folgenden Tabelle sind einige der von [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] bereitgestellten Enumerationen aufgeführt und beschrieben.  
  
|||  
|-|-|  
|Enumeration|Beschreibung|  
|<xref:Microsoft.VisualBasic.AppWinStyle>|Gibt in Aufrufen der <xref:Microsoft.VisualBasic.Interaction.Shell%2A>\-Funktion den Fensterstil an, der für das aufgerufene Programm verwendet werden soll.|  
|<xref:Microsoft.VisualBasic.AudioPlayMode>|Gibt an, wie beim Aufruf von Audiomethoden Sounds wiedergegeben werden.|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|Gibt in Aufrufen der <xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>\-Methode den Typ der zu überprüfenden Rolle an.|  
|<xref:Microsoft.VisualBasic.CallType>|Gibt den Typ der Prozedur an, die beim Aufrufen der <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>\-Funktion aufgerufen wird.|  
|<xref:Microsoft.VisualBasic.CompareMethod>|Gibt in Aufrufen von Vergleichsfunktionen an, wie Zeichenfolgen miteinander verglichen werden sollen.|  
|<xref:Microsoft.VisualBasic.DateFormat>|Gibt in Aufrufen der <xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>\-Funktion an, wie Datumsangaben angezeigt werden sollen.|  
|<xref:Microsoft.VisualBasic.DateInterval>|Gibt beim Aufruf datumsbezogener Funktionen an, wie Datumsintervalle bestimmt und formatiert werden sollen.|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|Gibt an, was geschehen soll, wenn ein Verzeichnis, das gelöscht werden soll, Dateien oder Verzeichnisse enthält.|  
|<xref:Microsoft.VisualBasic.DueDate>|Gibt beim Aufruf von Finanzmethoden an, wann Zahlungen fällig sind.|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType>|Gibt an, ob Textfelder durch Trennzeichen begrenzt werden oder eine feste Breite haben.|  
|<xref:Microsoft.VisualBasic.FileAttribute>|Gibt beim Aufruf von Dateizugriffsfunktionen die zu verwendenden Dateiattribute an.|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek>|Gibt in Aufrufen datumsbezogener Funktionen an, welcher Tag den ersten Tag der Woche darstellen soll.|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear>|Gibt in Aufrufen datumsbezogener Funktionen die Woche an, welche die erste Woche des Jahres darstellen soll.|  
|<xref:Microsoft.VisualBasic.MsgBoxResult>|Gibt an, welche Schaltfläche in einem Meldungsfeld aktiviert wurde, und wird von der <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>\-Funktion zurückgegeben.|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle>|Gibt in Aufrufen der <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>\-Funktion an, welche Schaltflächen angezeigt werden sollen.|  
|<xref:Microsoft.VisualBasic.OpenAccess>|Gibt an, wie eine Datei beim Aufruf von Dateizugriffsfunktionen geöffnet werden kann.|  
|<xref:Microsoft.VisualBasic.OpenMode>|Gibt an, wie eine Datei beim Aufruf von Dateizugriffsfunktionen geöffnet werden kann.|  
|<xref:Microsoft.VisualBasic.OpenShare>|Gibt an, wie eine Datei beim Aufruf von Dateizugriffsfunktionen geöffnet werden kann.|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption>|Gibt an, ob eine Datei permanent gelöscht oder in den Papierkorb verschoben werden soll.|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption>|Gibt an, ob alle Verzeichnisse oder nur die Verzeichnisse der obersten Ebene durchsucht werden sollen.|  
|<xref:Microsoft.VisualBasic.TriState>|Gibt in Aufrufen von Funktionen zur Zahlenformatierung einen `Boolean`\-Wert an oder legt fest, ob der Standard verwendet werden soll.|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption>|Legt fest, was geschehen soll, wenn der Benutzer während eines Vorganges auf **Abbrechen** klickt.|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption>|Legt fest, ob beim Kopieren, Löschen oder Verschieben von Dateien oder Verzeichnissen eine Fortschrittsanzeige angezeigt wird.|  
|<xref:Microsoft.VisualBasic.VariantType>|Gibt den Typ eines Variant\-Objekts an und wird von der <xref:Microsoft.VisualBasic.Information.VarType%2A>\-Funktion zurückgegeben.|  
|<xref:Microsoft.VisualBasic.VbStrConv>|Gibt in Aufrufen der <xref:Microsoft.VisualBasic.Strings.StrConv%2A>\-Funktion an, welche Art von Konvertierung ausgeführt werden soll.|  
  
## Siehe auch  
 [Visual Basic Language Reference](../../visual-basic/language-reference/index.md)   
 [Visual Basic](../../visual-basic/index.md)   
 [Constants Overview](../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Enumerations Overview](../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)