---
title: Asynchrone Szenarien mit HTTP, TCP oder benannten Pipes
ms.date: 03/30/2017
ms.assetid: a4d62402-43a4-48a4-9ced-220633ebc4ce
ms.openlocfilehash: 6ae96c0aac5010adf37eb78ed57d1549885ece58
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185786"
---
# <a name="asynchronous-scenarios-using-http-tcp-or-named-pipe"></a>Asynchrone Szenarien mit HTTP, TCP oder benannten Pipes
In diesem Abschnitt werden die Aktivitäten und Übertragungen für verschiedene asynchrone Anforderungs-/Antwortszenarien beschrieben. Dabei werden HTTP, TCP oder benannte Pipes in Multithreadanforderungen verwendet.  
  
## <a name="asynchronous-requestreply-without-errors"></a>Asynchrone Anforderung/Antwort ohne Fehler  
 In diesem Abschnitt werden die Aktivitäten und Übertragungen für ein asynchrones Anforderungs-/Antwortszenario mit Multithreadclients beschrieben.  
  
 Die aufrufende Aktivität ist beendet, wenn `beginCall` und `endCall` zurückgegeben werden. Wenn ein Rückruf aufgerufen wird, wird der Rückruf zurückgegeben.  
  
 Die aufgerufene Aktivität ist beendet, wenn `beginCall` und `endCall` zurückgegeben werden oder bei Rückgabe des Rückrufs, wenn der Rückruf von dieser Aktivität aufgerufen wurde.  
  
### <a name="asynchronous-client-without-callback"></a>Asynchroner Client ohne Rückruf  
  
#### <a name="propagation-is-enabled-on-both-sides-using-http"></a>Weitergabe wird mit HTTP auf beiden Seiten aktiviert  
 ![Asynchroner Client ohne Rückruf, bei dem propagateActivity auf beiden Seiten auf true festgelegt ist.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-no-callback.gif)
  
 Wenn `propagateActivity=true`, gibt ProcessMessage an, an welche ProcessAction-Aktivität übertragen werden soll.  
  
 Bei HTTP-basierten Szenarien wird ReceiveBytes zur ersten gesendeten Nachricht aufgerufen und bleibt so lange erhalten wie die Anforderung besteht.  
  
#### <a name="propagation-is-disabled-on-either-sides-using-http"></a>Weitergabe wird mit HTTP auf einer der Seiten deaktiviert  
 Wenn `propagateActivity=false` auf beiden Seiten, gibt ProcessMessage nicht an, an welche ProcessAction-Aktivität übertragen werden soll. Deshalb wird eine neue temporäre ProcessAction-Aktivität mit einer neuen ID aufgerufen. Wenn die asynchrone Antwort mit der Anforderung im ServiceModel-Code übereinstimmt, kann die Aktivitäts-ID aus dem lokalen Kontext abgerufen werden. Die eigentliche ProcessAction-Aktivität kann mit dieser ID übertragen werden.  
  
 ![Asynchroner Client ohne Rückruf, bei dem propagateActivity auf beiden Seiten auf false festgelegt ist.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-either-side.gif)  

 Bei HTTP-basierten Szenarien wird ReceiveBytes zur ersten gesendeten Nachricht aufgerufen und bleibt so lange erhalten wie die Anforderung besteht.  
  
 Eine Prozessaktionsaktivität wird auf einem asynchronen Client erstellt, wenn `propagateActivity=false` sie beim Aufrufer oder Aufrufer ist und wenn die Antwortnachricht keinen Aktionsheader enthält.  
  
#### <a name="propagation-is-enabled-on-both-sides-using-tcp-or-named-pipe"></a>Weitergabe wird mit TCP oder benannten Pipes auf beiden Seiten aktiviert  
 ![Asynchroner Client ohne Rückruf, bei dem propagateActivity auf beiden Seiten auf true und mit dem Namen pipe/TCP festgelegt ist.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-enabled-using-tcp.gif)  
  
 Bei auf benannten Pipes oder TCP basierenden Szenarien wird ReceiveBytes beim Öffnen des Clients aufgerufen und bleibt so lange erhalten wie die Verbindung besteht.  
  
 Ähnlich wie beim ersten `propagateActivity=true`Abbild gibt ProcessMessage an, an welche ProcessAction-Aktivität übertragen werden soll.  
  
#### <a name="propagation-is-disabled-on-either-sides-using-tcp-or-named-pipe"></a>Weitergabe wird mit TCP oder benannten Pipes auf einer der Seiten deaktiviert  
 Bei auf benannten Pipes oder TCP basierenden Szenarien wird ReceiveBytes beim Öffnen des Clients aufgerufen und bleibt so lange erhalten wie die Verbindung besteht.  
  
 Ähnlich wie beim zweiten `propagateActivity=false` Bild gibt ProcessMessage, wenn auf beiden Seiten, nicht an, an welche ProcessAction-Aktivität übertragen werden soll. Deshalb wird eine neue temporäre ProcessAction-Aktivität mit einer neuen ID aufgerufen. Wenn die asynchrone Antwort mit der Anforderung im ServiceModel-Code übereinstimmt, kann die Aktivitäts-ID aus dem lokalen Kontext abgerufen werden. Die eigentliche ProcessAction-Aktivität kann mit dieser ID übertragen werden.  
  
 ![Asynchroner Client ohne Rückruf, bei dem propagateActivity auf beiden Seiten auf false und mit dem Namen pipe/TCP festgelegt ist.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-using-tcp.gif)  

### <a name="asynchronous-client-with-callback"></a>Asynchroner Client mit Rückruf  
 In diesem Szenario werden für den Rückruf und `endCall` die Aktivitäten G und A' und deren Ein- und Ausgangsübertragung hinzugefügt.  
  
 In diesem Abschnitt wird `propagateActivity` = `true`nur die Verwendung von HTTP mit veranschaulicht. Die zusätzlichen Aktivitäten und Übertragungen gelten jedoch auch `propagateActivity` = `false`für die anderen Fälle (d. h. mit TCP oder Named-Pipe).  
  
 Der Rückruf erstellt eine neue Aktivität (G), wenn der Client Benutzercode aufruft, um anzugeben, dass Ergebnisse vorliegen. Der Benutzercode ruft dann `endCall` innerhalb des Rückrufs (siehe Abbildung 5) oder außerhalb des Rückrufs (siehe Abbildung 6) auf Da nicht bekannt ist, `endCall` von welcher Benutzeraktivität aufgerufen `A’`wird, wird diese Aktivität als gekennzeichnet. A' kann mit A identisch sein, muss aber nicht.  
  
 ![Zeigt einen asynchronen Client mit Rückruf, Endaufruf im Rückruf an.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-in-callback.gif)  

 ![Zeigt einen asynchronen Client mit Rückruf, Endaufruf außerhalb des Rückrufs an.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-outside-callback.gif)  

### <a name="asynchronous-server-with-callback"></a>Asynchroner Server mit Rückruf  
 ![Zeigt einen asynchronen Server mit Rückruf an.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-server-callback.gif)  

 Der Kanalstapel ruft den Client beim Nachrichtenempfang zurück: Ablaufverfolgungen für diese Verarbeitung werden direkt in der ProcessRequest-Aktivität ausgegeben.  
  
## <a name="asynchronous-requestreply-with-errors"></a>Asynchrone Anforderung/Antwort mit Fehlern  
 Fehlermeldungen werden während `endCall` empfangen. Davon abgesehen ähneln die Aktivitäten und Übertragungen den vorherigen Szenarien.  
  
## <a name="asynchronous-one-way-with-or-without-errors"></a>Asynchrone unidirektional Kommunikation mit oder ohne Fehler  
 Keine Antwort oder kein Fehler wird an den Client zurückgegeben.
