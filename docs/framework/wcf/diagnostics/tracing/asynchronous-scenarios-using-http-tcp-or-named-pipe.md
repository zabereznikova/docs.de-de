---
title: "Asynchrone Szenarien mit HTTP, TCP oder benannten Pipes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a4d62402-43a4-48a4-9ced-220633ebc4ce
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Asynchrone Szenarien mit HTTP, TCP oder benannten Pipes
In diesem Abschnitt werden die Aktivitäten und Übertragungen für verschiedene asynchrone Anforderungs\-\/Antwortszenarien beschrieben. Dabei werden HTTP, TCP oder benannte Pipes in Multithreadanforderungen verwendet.  
  
## Asynchrone Anforderung\/Antwort ohne Fehler  
 In diesem Abschnitt werden die Aktivitäten und Übertragungen für ein asynchrones Anforderungs\-\/Antwortszenario mit Multithreadclients beschrieben.  
  
 Die aufrufende Aktivität ist beendet, wenn `beginCall` und `endCall` zurückgegeben werden.Wenn ein Rückruf aufgerufen wird, wird der Rückruf zurückgegeben.  
  
 Die aufgerufene Aktivität ist beendet, wenn `beginCall` und `endCall` zurückgegeben werden oder bei Rückgabe des Rückrufs, wenn der Rückruf von dieser Aktivität aufgerufen wurde.  
  
### Asynchroner Client ohne Rückruf  
  
#### Weitergabe wird mit HTTP auf beiden Seiten aktiviert  
 ![Asynchrone Szenarien](../../../../../docs/framework/wcf/diagnostics/tracing/media/asyn1.gif "Asyn1")  
  
 Abbildung 1.Asynchroner Client, kein Rückruf, `propagateActivity`\=`true` auf beiden Seiten, HTTP  
  
 Wenn `propagateActivity`\=`true`, gibt ProcessMessage an, zu welcher ProcessAction\-Aktivität die Übertragung erfolgen soll.  
  
 Bei HTTP\-basierten Szenarien wird ReceiveBytes zur ersten gesendeten Nachricht aufgerufen und bleibt so lange erhalten wie die Anforderung besteht.  
  
#### Weitergabe wird mit HTTP auf einer der Seiten deaktiviert  
 Wenn `propagateActivity`\=`false` auf einer Seite, gibt ProcessMessage nicht an, zu welcher ProcessAction\-Aktivität die Übertragung erfolgen soll.Deshalb wird eine neue temporäre ProcessAction\-Aktivität mit einer neuen ID aufgerufen.Wenn die asynchrone Antwort mit der Anforderung im ServiceModel\-Code übereinstimmt, kann die Aktivitäts\-ID aus dem lokalen Kontext abgerufen werden.Die eigentliche ProcessAction\-Aktivität kann mit dieser ID übertragen werden.  
  
 ![Asynchrone Szenarien mit HTTP&#47;TCP&#47;Named Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/async2.gif "Async2")  
  
 Abbildung 2.Asynchroner Client, kein Rückruf, `propagateActivity`\=`false` auf einer Seite, HTTP  
  
 Bei HTTP\-basierten Szenarien wird ReceiveBytes zur ersten gesendeten Nachricht aufgerufen und bleibt so lange erhalten wie die Anforderung besteht.  
  
 Eine ProcessAction\-Aktivität wird für einen asynchronen Client erstellt, wenn auf der aufrufenden oder der aufgerufenen Seite `propagateActivity`\=`false` und wenn die Antwortnachricht keinen Action\-Header enthält.  
  
#### Weitergabe wird mit TCP oder benannten Pipes auf beiden Seiten aktiviert  
 ![Asynchrone Szenarien mit HTTP&#47;TCP&#47;Named Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/async3.gif "Async3")  
  
 Abbildung 3.Asynchroner Client, kein Rückruf, `propagateActivity`\=`true` auf beiden Seiten, benannte Pipes\/TCP  
  
 Bei auf benannten Pipes oder TCP basierenden Szenarien wird ReceiveBytes beim Öffnen des Clients aufgerufen und bleibt so lange erhalten wie die Verbindung besteht.  
  
 Ähnlich wie in Abbildung 1, wenn `propagateActivity`\=`true`, gibt ProcessMessage an, zu welcher ProcessAction\-Aktivität die Übertragung erfolgen soll.  
  
#### Weitergabe wird mit TCP oder benannten Pipes auf einer der Seiten deaktiviert  
 Bei auf benannten Pipes oder TCP basierenden Szenarien wird ReceiveBytes beim Öffnen des Clients aufgerufen und bleibt so lange erhalten wie die Verbindung besteht.  
  
 Ähnlich wie in Abbildung 2, wenn `propagateActivity`\=`false` auf einer Seite, gibt ProcessMessage nicht an, zu welcher ProcessAction\-Aktivität die Übertragung erfolgen soll.Deshalb wird eine neue temporäre ProcessAction\-Aktivität mit einer neuen ID aufgerufen.Wenn die asynchrone Antwort mit der Anforderung im ServiceModel\-Code übereinstimmt, kann die Aktivitäts\-ID aus dem lokalen Kontext abgerufen werden.Die eigentliche ProcessAction\-Aktivität kann mit dieser ID übertragen werden.  
  
 ![Asynchrone Szenarien mit HTTP&#47;TCP&#47;Named Pipes](../../../../../docs/framework/wcf/diagnostics/tracing/media/async4.gif "Async4")  
  
 Abbildung 4.Asynchroner Client, kein Rückruf, `propagateActivity`\=`false` auf einer Seite, benannte Pipes\/TCP  
  
### Asynchroner Client mit Rückruf  
 In diesem Szenario werden für den Rückruf und `endCall` die Aktivitäten G und A' und deren Ein\- und Ausgangsübertragung hinzugefügt.  
  
 Dieser Abschnitt veranschaulicht lediglich die Verwendung von HTTP mit `propragateActivity`\=`true`.Die zusätzlichen Aktivitäten und Übertragungen treffen jedoch auch auf die anderen Fälle zu \(d. h. `propagateActivity`\=`false` unter Verwendung von TCP oder benannten Pipes\).  
  
 Der Rückruf erstellt eine neue Aktivität \(G\), wenn der Client Benutzercode aufruft, um anzugeben, dass Ergebnisse vorliegen.Der Benutzercode ruft dann `endCall` innerhalb des Rückrufs \(siehe Abbildung 5\) oder außerhalb des Rückrufs \(siehe Abbildung 6\) aufDa nicht bekannt ist, aus welcher Benutzeraktivität `endCall` aufgerufen wird, erhält diese Aktivität die Bezeichnung `A’`.A' kann mit A identisch sein, muss aber nicht.  
  
 ![Asynchrone Szenarien](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback1.gif "AsyncCallback1")  
  
 Abbildung 5.Asynchroner Client mit Rückruf, `endCall` im Rückruf  
  
 ![Asynchrone Szenarien](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback2.gif "AsyncCallback2")  
  
 Abbildung 6.Asynchroner Client mit Rückruf, `endCall` außerhalb des Rückrufs  
  
### Asynchroner Server mit Rückruf  
 ![Asynchrone Szenarien mit HTTP&#47;TCP&#47;Named Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/aynchserver.gif "AynchServer")  
  
 Abbildung 7.Asynchroner Server mit Rückruf  
  
 Der Kanalstapel ruft den Client beim Nachrichtenempfang zurück: Ablaufverfolgungen für diese Verarbeitung werden direkt in der ProcessRequest\-Aktivität ausgegeben.  
  
## Asynchrone Anforderung\/Antwort mit Fehlern  
 Fehlermeldungen werden während `endCall` empfangen.Davon abgesehen ähneln die Aktivitäten und Übertragungen den vorherigen Szenarien.  
  
## Asynchrone unidirektional Kommunikation mit oder ohne Fehler  
 Keine Antwort oder kein Fehler wird an den Client zurückgegeben.