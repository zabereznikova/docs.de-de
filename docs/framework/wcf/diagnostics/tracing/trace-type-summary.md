---
title: Ablaufverfolgungstyp – Zusammenfassung
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: e3bc66753dd44e1dc4c7417caf593820300f69a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486041"
---
# <a name="trace-type-summary"></a>Ablaufverfolgungstyp – Zusammenfassung
[Quellebenen](http://go.microsoft.com/fwlink/?LinkID=94943) Definieren verschiedener nachverfolgungsebenen: Kritisch, Fehler, Warnung, Informationen und ausführlich, auch als Beschreibung bietet die `ActivityTracing` -Flag, das die Ausgabe der nachverfolgungsgrenzen und der aktivitätsübertragungsereignisse zu verfolgen.  
  
 Sie können auch überprüfen, [TraceEventType](http://go.microsoft.com/fwlink/?LinkId=95169) für die Typen von ablaufverfolgungstypen, die von ausgegeben werden können <xref:System.Diagnostics>.  
  
 In der folgenden Tabelle werden die Wichtigsten aufgelistet.  
  
|Ablaufverfolgungstyp|Beschreibung|  
|----------------|-----------------|  
|Kritisch|Schwer wiegender Fehler oder Anwendungsabsturz.|  
|Fehler|Behebbarer Fehler.|  
|Warnung|Informationsnachricht.|  
|Information|Kein kritisches Problem.|  
|Ausführlich|Debuggen der Ablaufverfolgung.|  
|Starten|Starten einer logischen Verarbeitungseinheit.|  
|Suspend (Anhalten)|Anhalten einer logischen Verarbeitungseinheit.|  
|Fortsetzen|Fortsetzen einer logischen Verarbeitungseinheit.|  
|Stop|Beenden einer logischen Verarbeitungseinheit.|  
|Übertragung|Ändern der Korrelationsidentität.|  
  
 Eine Aktivität ist als Kombination der oben genannten Ablaufverfolgungstypen definiert.  
  
 Beim folgenden Beispiel handelt es sich um einen regulären Ausdruck zum Definieren einer idealen Aktivität in einem lokalen Bereich (Ablaufverfolgungsquelle):  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 Das bedeutet, dass eine Aktivität die folgenden Bedingungen erfüllen muss:  
  
-   Sie muss mithilfe der Starten-Ablaufverfolgung gestartet bzw. mithilfe der Beenden-Ablaufverfolgung beendet werden können.  
  
-   Sie muss eine Übertragen-Ablaufverfolgung besitzen, die direkt vor einer Anhalten- oder einer Fortsetzen-Ablaufverfolgung platziert ist.  
  
-   Sie darf keine Ablaufverfolgungen zwischen der Anhalten- und der Fortsetzen-Ablaufverfolgung besitzen, sofern diese beiden Ablaufverfolgungen vorhanden sind.  
  
-   Sie kann eine beliebige Kombination aus sowie eine beliebige Anzahl von Ablaufverfolgungen des Typs Wichtig/Fehler/Warnung/Information/Verbose/Übertragen besitzen, sofern die oben genannten Bedingungen erfüllt sind.  
  
 Beim folgenden Beispiel handelt es sich um einen regulären Ausdruck zum Definieren einer idealen Aktivität in einem globalen Bereich:  
  
```  
R+   
```  
  
 R steht hierbei für den regulären Ausdruck einer Aktivität im lokalen Bereich. Dies wird folgendermaßen übersetzt:  
  
```  
[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+  
```
