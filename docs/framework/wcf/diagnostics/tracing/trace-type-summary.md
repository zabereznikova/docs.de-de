---
title: Ablaufverfolgungstyp – Zusammenfassung
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: 44446b58510e58758934a5eb964efc8643854879
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647187"
---
# <a name="trace-type-summary"></a>Ablaufverfolgungstyp – Zusammenfassung
[Quellebenen](https://go.microsoft.com/fwlink/?LinkID=94943) Definieren verschiedener nachverfolgungsebenen: Kritischen, Fehler-, Warn-, Informationen und ausführlich, darüber hinaus wird die Beschreibung des der `ActivityTracing` -Flag, das die Ausgabe des schaltet Ablaufverfolgungsereignisse und übertragen.  
  
 Sie können auch überprüfen [TraceEventType](https://go.microsoft.com/fwlink/?LinkId=95169) für die ablaufverfolgungstypen, die von ausgegeben werden, können Typen <xref:System.Diagnostics>.  
  
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
  
```  
R+   
```  
  
 R steht hierbei für den regulären Ausdruck einer Aktivität im lokalen Bereich. Dies wird folgendermaßen übersetzt:  
  
```  
[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+  
```
