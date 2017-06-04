---
title: "Ablaufverfolgungstyp – Zusammenfassung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Ablaufverfolgungstyp – Zusammenfassung
[Quellebenen](http://go.microsoft.com/fwlink/?LinkID=94943) dienen zum Definieren verschiedener Nachverfolgungsebenen: Wichtig, Fehler, Warnung, Information und Verbose. Darüber hinaus wird durch sie eine Beschreibung des `ActivityTracing`\-Flags bereitgestellt, mit dem die Ausgabe der Nachverfolgungsgrenzen und der Aktivitätsübertragungsereignisse aktiviert oder deaktiviert wird.  
  
 Zudem haben Sie die Möglichkeit zum Überprüfen von [TraceEventType](http://go.microsoft.com/fwlink/?LinkId=95169) für die Ablaufverfolgungstypen, die von <xref:System.Diagnostics> ausgegeben werden.  
  
 In der folgenden Tabelle werden die Wichtigsten aufgelistet.  
  
|Ablaufverfolgungstyp|Beschreibung|  
|--------------------------|------------------|  
|Kritisch|Schwer wiegender Fehler oder Anwendungsabsturz.|  
|Fehler|Behebbarer Fehler.|  
|Warnung|Informationsnachricht.|  
|Information|Kein kritisches Problem.|  
|Ausführlich|Debuggen der Ablaufverfolgung.|  
|Starten|Starten einer logischen Verarbeitungseinheit.|  
|Suspend \(Anhalten\)|Anhalten einer logischen Verarbeitungseinheit.|  
|Fortfahren|Fortsetzen einer logischen Verarbeitungseinheit.|  
|Stop|Beenden einer logischen Verarbeitungseinheit.|  
|Übertragung|Ändern der Korrelationsidentität.|  
  
 Eine Aktivität ist als Kombination der oben genannten Ablaufverfolgungstypen definiert.  
  
 Beim folgenden Beispiel handelt es sich um einen regulären Ausdruck zum Definieren einer idealen Aktivität in einem lokalen Bereich \(Ablaufverfolgungsquelle\):  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 Das bedeutet, dass eine Aktivität die folgenden Bedingungen erfüllen muss:  
  
-   Sie muss mithilfe der Starten\-Ablaufverfolgung gestartet bzw. mithilfe der Beenden\-Ablaufverfolgung beendet werden können.  
  
-   Sie muss eine Übertragen\-Ablaufverfolgung besitzen, die direkt vor einer Anhalten\- oder einer Fortsetzen\-Ablaufverfolgung platziert ist.  
  
-   Sie darf keine Ablaufverfolgungen zwischen der Anhalten\- und der Fortsetzen\-Ablaufverfolgung besitzen, sofern diese beiden Ablaufverfolgungen vorhanden sind.  
  
-   Sie kann eine beliebige Kombination aus sowie eine beliebige Anzahl von Ablaufverfolgungen des Typs Wichtig\/Fehler\/Warnung\/Information\/Verbose\/Übertragen besitzen, sofern die oben genannten Bedingungen erfüllt sind.  
  
 Beim folgenden Beispiel handelt es sich um einen regulären Ausdruck zum Definieren einer idealen Aktivität in einem globalen Bereich:  
  
```  
R+   
```  
  
 R steht hierbei für den regulären Ausdruck einer Aktivität im lokalen Bereich.  Dies wird folgendermaßen übersetzt:  
  
```  
[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+  
```