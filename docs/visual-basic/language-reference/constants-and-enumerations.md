---
title: Konstanten und Enumerationen (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- enumerations [Visual Basic]
- constants
- constants, list of
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e37ef2e3c51e96e85cb214054195016e69d52382
ms.lasthandoff: 03/13/2017

---
# <a name="constants-and-enumerations-visual-basic"></a>Konstanten und Enumerationen (Visual Basic)
[!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Stellt eine Reihe vordefinierter Konstanten und Enumerationen für Entwickler. Konstanten speichern Werte, die während der Ausführung einer Anwendung konstant bleiben. Enumerationen bieten eine bequeme Möglichkeit, mit Gruppen verwandter Konstanten zu arbeiten und Konstantenwerte mit Namen zu verknüpfen.  
  
## <a name="constants"></a>Konstanten  
  
### <a name="conditional-compilation-constants"></a>Konstanten für bedingte Kompilierung  
 Die folgende Tabelle enthält die vordefinierten Konstanten für die bedingte Kompilierung zur Verfügung.  
  
|**Konstante**|**Beschreibung**|  
|---|---|  
|`CONFIG`|Eine Zeichenfolge, die die aktuelle Einstellung entspricht, der **Konfiguration der aktuellen Projektmappe** Feld der **Configuration Manager**.|  
|`DEBUG`|Ein `Boolean` -Wert, der festgelegt werden kann, in der **Projekteigenschaften** Dialogfeld. Standardmäßig definiert die Debugkonfiguration für ein Projekt `DEBUG`. Wenn `DEBUG` definiert ist, <xref:System.Diagnostics.Debug>Klassenmethoden Generieren der **Ausgabe** Fenster.</xref:System.Diagnostics.Debug> Wenn sie nicht definiert ist, <xref:System.Diagnostics.Debug>-Klassenmethoden nicht kompiliert und keine Debugausgabe generiert.</xref:System.Diagnostics.Debug>|  
|`TARGET`|Eine Zeichenfolge, die den Ausgabetyp für das Projekt oder die Einstellung von der Befehlszeile **/target** Option. Die möglichen Werte für `TARGET` sind:<br /><br /> -"Winexe" für eine Windows-Anwendung.<br />-"Exe" für eine Konsolenanwendung.<br />-"Library" für eine Klassenbibliothek.<br />-"Modul" für ein Modul.<br />– Der **/target** Option kann festgelegt werden, der [!INCLUDE[vsprvs](../../csharp/includes/vsprvs_md.md)] -IDE. Weitere Informationen finden Sie unter [/target (Visual Basic)](../../visual-basic/reference/command-line-compiler/target.md).|  
|`TRACE`|Ein `Boolean` -Wert, der festgelegt werden kann, in der **Projekteigenschaften** Dialogfeld. Standardmäßig definieren alle Konfigurationen für ein Projekt `TRACE`. Wenn `TRACE` definiert ist, <xref:System.Diagnostics.Trace>Klassenmethoden Generieren der **Ausgabe** Fenster.</xref:System.Diagnostics.Trace> Wenn sie nicht definiert ist, <xref:System.Diagnostics.Trace>Klasse-Klassenmethoden nicht kompiliert und keine `Trace` Ausgabe generiert.</xref:System.Diagnostics.Trace>|  
|`VBC_VER`|Eine Zahl, die [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Version im *wichtigsten*.* kleinere* Format. Die Versionsnummer für [!INCLUDE[vbprvblong](../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] ist 8.0.|  
  
### <a name="print-and-display-constants"></a>Drucken und Anzeigekonstanten  
 Beim Aufrufen von Druck- und Anzeigefunktionen, können Sie die folgenden Konstanten in Ihrem Code anstelle der eigentlichen Werte.  
  
|**Konstante**|**Beschreibung**|  
|---|---|  
|`vbCrLf`|Wagenrücklauf und Zeilenvorschub-Kombination.|  
|`vbCr`|Wagenrücklaufzeichen.|  
|`vbLf`|Zeilenvorschubzeichen.|  
|`vbNewLine`|Neue-Zeile-Zeichen.|  
|`vbNullChar`|NULL-Zeichen.|  
|`vbNullString`|Nicht identisch mit einer Zeichenfolge der Länge&0; (""); zum Aufrufen externer Prozeduren verwendet.|  
|`vbObjectError`|Fehlernummer. Benutzerdefinierte Fehlernummern sollten größer als dieser Wert sein. Beispiel:<br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|Tabstoppzeichen.|  
|`vbBack`|Rücktastenzeichen.|  
|`vbFormFeed`|In Microsoft Windows verwendet nicht.|  
|`vbVerticalTab`|In Microsoft Windows nicht sinnvoll.|  
  
## <a name="enumerations"></a>Enumerationen  
 In der folgenden Tabelle aufgelistet und beschreibt die Enumerationen von bereitgestellten [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
|Enumeration|Beschreibung|  
|---|---|  
|<xref:Microsoft.VisualBasic.AppWinStyle></xref:Microsoft.VisualBasic.AppWinStyle>|Gibt den Fensterstil für das aufgerufene Programm verwendet werden soll, beim Aufrufen der <xref:Microsoft.VisualBasic.Interaction.Shell%2A>Funktion.</xref:Microsoft.VisualBasic.Interaction.Shell%2A>|  
|<xref:Microsoft.VisualBasic.AudioPlayMode></xref:Microsoft.VisualBasic.AudioPlayMode>|Gibt an, wie Sounds wiederzugeben, wenn audio-Methoden aufgerufen.|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole></xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|Gibt den Typ der Rolle, überprüfen Sie beim Aufrufen der <xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>-Methode.</xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
|<xref:Microsoft.VisualBasic.CallType></xref:Microsoft.VisualBasic.CallType>|Gibt den Typ der Prozedur, die aufgerufen wird, beim Aufrufen der <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>Funktion.</xref:Microsoft.VisualBasic.Interaction.CallByName%2A>|  
|<xref:Microsoft.VisualBasic.CompareMethod></xref:Microsoft.VisualBasic.CompareMethod>|Gibt an, wie Zeichenfolgen beim Aufrufen von Vergleichsfunktionen verglichen.|  
|<xref:Microsoft.VisualBasic.DateFormat></xref:Microsoft.VisualBasic.DateFormat>|Gibt an, wie Datumsangaben beim Aufrufen der <xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>Funktion.</xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|  
|<xref:Microsoft.VisualBasic.DateInterval></xref:Microsoft.VisualBasic.DateInterval>|Gibt an, wie Datumsintervalle beim Aufrufen von Datumsfunktionen festgelegt und formatiert werden.|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption></xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|Gibt an, was geschehen soll, wenn ein Verzeichnis, das gelöscht werden soll, Dateien oder Verzeichnisse enthält.|  
|<xref:Microsoft.VisualBasic.DueDate></xref:Microsoft.VisualBasic.DueDate>|Gibt an, wann Zahlungen fällig sind beim finanzielle Methoden aufrufen.|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType></xref:Microsoft.VisualBasic.FileIO.FieldType>|Gibt an, ob Textfelder durch Trennzeichen begrenzt werden oder eine feste Breite.|  
|<xref:Microsoft.VisualBasic.FileAttribute></xref:Microsoft.VisualBasic.FileAttribute>|Gibt die Dateiattribute beim Dateizugriff Funktionen aufrufen.|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek></xref:Microsoft.VisualBasic.FirstDayOfWeek>|Gibt den ersten Tag der Woche beim Aufrufen von Datumsfunktionen verwendet.|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear></xref:Microsoft.VisualBasic.FirstWeekOfYear>|Gibt die erste Woche des Jahres beim Aufrufen von Datumsfunktionen verwendet.|  
|<xref:Microsoft.VisualBasic.MsgBoxResult></xref:Microsoft.VisualBasic.MsgBoxResult>|Gibt an, welche Taste gedrückt wurde, in einem Meldungsfeld zurückgegeben, indem die <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>Funktion.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle></xref:Microsoft.VisualBasic.MsgBoxStyle>|Gibt an, welche Schaltflächen angezeigt werden, beim Aufrufen der <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>Funktion.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>|  
|<xref:Microsoft.VisualBasic.OpenAccess></xref:Microsoft.VisualBasic.OpenAccess>|Gibt an, wie eine Datei zu öffnen, wenn Dateizugriff Funktionen aufgerufen.|  
|<xref:Microsoft.VisualBasic.OpenMode></xref:Microsoft.VisualBasic.OpenMode>|Gibt an, wie eine Datei zu öffnen, wenn Dateizugriff Funktionen aufgerufen.|  
|<xref:Microsoft.VisualBasic.OpenShare></xref:Microsoft.VisualBasic.OpenShare>|Gibt an, wie eine Datei zu öffnen, wenn Dateizugriff Funktionen aufgerufen.|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption></xref:Microsoft.VisualBasic.FileIO.RecycleOption>|Gibt an, ob eine Datei permanent gelöscht oder im Papierkorb abgelegt werden soll.|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption></xref:Microsoft.VisualBasic.FileIO.SearchOption>|Gibt an, ob alle oder nur die Verzeichnisse der obersten Ebene.|  
|<xref:Microsoft.VisualBasic.TriState></xref:Microsoft.VisualBasic.TriState>|Gibt einen `Boolean` Wert oder ob die Standardeinstellung beim Aufrufen von Funktionen Formatieren von Zahlen verwendet werden soll.|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption></xref:Microsoft.VisualBasic.FileIO.UICancelOption>|Gibt an, welche werden soll, wenn der Benutzer klickt auf **Abbrechen** während eines Vorgangs.|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption></xref:Microsoft.VisualBasic.FileIO.UIOption>|Gibt an, ob eine Fortschrittsanzeige beim Kopieren, löschen oder Verschieben von Dateien oder Verzeichnisse zu angezeigt.|  
|<xref:Microsoft.VisualBasic.VariantType></xref:Microsoft.VisualBasic.VariantType>|Gibt den Typ des von zurückgegebenen variant-Objekts die <xref:Microsoft.VisualBasic.Information.VarType%2A>Funktion.</xref:Microsoft.VisualBasic.Information.VarType%2A>|  
|<xref:Microsoft.VisualBasic.VbStrConv></xref:Microsoft.VisualBasic.VbStrConv>|Gibt den Typ der Konvertierung ausgeführt wird, beim Aufrufen der <xref:Microsoft.VisualBasic.Strings.StrConv%2A>Funktion.</xref:Microsoft.VisualBasic.Strings.StrConv%2A>|  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Sprachreferenz](../../visual-basic/language-reference/index.md)   
 [Visual Basic](../../visual-basic/index.md)   
 [Übersicht über Konstanten](../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Übersicht über Enumerationen](../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
