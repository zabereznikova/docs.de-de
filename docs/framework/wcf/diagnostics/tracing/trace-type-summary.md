---
title: Ablaufverfolgungstyp – Zusammenfassung
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: 8f54f71ef63338708a29fac5557c7c7e8f257f58
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70856013"
---
# <a name="trace-type-summary"></a>Ablaufverfolgungstyp – Zusammenfassung
[Quell Ebenen](https://go.microsoft.com/fwlink/?LinkID=94943) definieren verschiedene Ablauf Verfolgungs Ebenen: "Kritisch", "Fehler", "Warnung", "Information" und "ausführlich" `ActivityTracing` sowie eine Beschreibung des Flags, das die Ausgabe von Ablauf Verfolgungs Grenzen und Aktivitäts Übertragungs Ereignissen umschaltet.  
  
 Sie können [TraceEventType](https://go.microsoft.com/fwlink/?LinkId=95169) auch für die Ablauf Verfolgungs Typen überprüfen, die von <xref:System.Diagnostics>ausgegeben werden können.  
  
 In der folgenden Tabelle werden die Wichtigsten aufgelistet.  
  
|Ablaufverfolgungstyp|Beschreibung|  
|----------------|-----------------|  
|Kritisch|Schwer wiegender Fehler oder Anwendungsabsturz.|  
|Fehler|Behebbarer Fehler.|  
|Warnung|Informationsnachricht.|  
|Information|Kein kritisches Problem.|  
|Ausführlich|Debuggen der Ablaufverfolgung.|  
|Beginn|Starten einer logischen Verarbeitungseinheit.|  
|Suspend (Anhalten)|Anhalten einer logischen Verarbeitungseinheit.|  
|Fortfahren|Fortsetzen einer logischen Verarbeitungseinheit.|  
|Beenden|Beenden einer logischen Verarbeitungseinheit.|  
|Übertragung|Ändern der Korrelationsidentität.|  
  
 Eine Aktivität ist als Kombination der oben genannten Ablaufverfolgungstypen definiert.  
  
 Beim folgenden Beispiel handelt es sich um einen regulären Ausdruck zum Definieren einer idealen Aktivität in einem lokalen Bereich (Ablaufverfolgungsquelle):  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 Das bedeutet, dass eine Aktivität die folgenden Bedingungen erfüllen muss:  
  
- Sie muss mithilfe der Starten-Ablaufverfolgung gestartet bzw. mithilfe der Beenden-Ablaufverfolgung beendet werden können.  
  
- Sie muss eine Übertragen-Ablaufverfolgung besitzen, die direkt vor einer Anhalten- oder einer Fortsetzen-Ablaufverfolgung platziert ist.  
  
- Sie darf keine Ablaufverfolgungen zwischen der Anhalten- und der Fortsetzen-Ablaufverfolgung besitzen, sofern diese beiden Ablaufverfolgungen vorhanden sind.  
  
- Sie kann eine beliebige Kombination aus sowie eine beliebige Anzahl von Ablaufverfolgungen des Typs Wichtig/Fehler/Warnung/Information/Verbose/Übertragen besitzen, sofern die oben genannten Bedingungen erfüllt sind.  
  
 Beim folgenden Beispiel handelt es sich um einen regulären Ausdruck zum Definieren einer idealen Aktivität in einem globalen Bereich:  
  
`R+`  
  
 R steht hierbei für den regulären Ausdruck einer Aktivität im lokalen Bereich. Dies wird folgendermaßen übersetzt:  
  
`[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+`
