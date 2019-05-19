---
title: Asynchrone Szenarien mit HTTP, TCP oder benannten Pipes
ms.date: 03/30/2017
ms.assetid: a4d62402-43a4-48a4-9ced-220633ebc4ce
ms.openlocfilehash: 48957ec0abd1b4b0623f9b613fcd94912a38845b
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881716"
---
# <a name="asynchronous-scenarios-using-http-tcp-or-named-pipe"></a>Asynchrone Szenarien mit HTTP, TCP oder benannten Pipes
In diesem Abschnitt werden die Aktivitäten und Übertragungen für verschiedene asynchrone Anforderungs-/Antwortszenarien beschrieben. Dabei werden HTTP, TCP oder benannte Pipes in Multithreadanforderungen verwendet.  
  
## <a name="asynchronous-requestreply-without-errors"></a>Asynchrone Anforderung/Antwort ohne Fehler  
 In diesem Abschnitt werden die Aktivitäten und Übertragungen für ein asynchrones Anforderungs-/Antwortszenario mit Multithreadclients beschrieben.  
  
 Die aufrufende Aktivität ist beendet, wenn `beginCall` und `endCall` zurückgegeben werden. Wenn ein Rückruf aufgerufen wird, wird der Rückruf zurückgegeben.  
  
 Die aufgerufene Aktivität ist beendet, wenn `beginCall` und `endCall` zurückgegeben werden oder bei Rückgabe des Rückrufs, wenn der Rückruf von dieser Aktivität aufgerufen wurde.  
  
### <a name="asynchronous-client-without-callback"></a>Asynchroner Client ohne Rückruf  
  
#### <a name="propagation-is-enabled-on-both-sides-using-http"></a>Weitergabe wird mit HTTP auf beiden Seiten aktiviert  
 ![Asynchroner Client mit kein Rückruf, PropagateActivity festgelegt ist, auf "true" auf beiden Seiten.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-no-callback.gif)   
  
 Wenn `propagateActivity` = `true`, gibt ProcessMessage an die ProcessAction-Aktivität die Übertragung.  
  
 Bei HTTP-basierten Szenarien wird ReceiveBytes zur ersten gesendeten Nachricht aufgerufen und bleibt so lange erhalten wie die Anforderung besteht.  
  
#### <a name="propagation-is-disabled-on-either-sides-using-http"></a>Weitergabe wird mit HTTP auf einer der Seiten deaktiviert  
 Wenn `propagateActivity` = `false` auf einer Seite, gibt ProcessMessage nicht die ProcessAction-Aktivität die Übertragung an. Deshalb wird eine neue temporäre ProcessAction-Aktivität mit einer neuen ID aufgerufen. Wenn die asynchrone Antwort mit der Anforderung im ServiceModel-Code übereinstimmt, kann die Aktivitäts-ID aus dem lokalen Kontext abgerufen werden. Die eigentliche ProcessAction-Aktivität kann mit dieser ID übertragen werden.  
  
 ![Asynchroner Client mit kein Rückruf, PropagateActivity auf "false" auf beiden Seiten festgelegt ist.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-either-side.gif)  
    
 Bei HTTP-basierten Szenarien wird ReceiveBytes zur ersten gesendeten Nachricht aufgerufen und bleibt so lange erhalten wie die Anforderung besteht.  
  
 Eine Processaction-Aktivität wird für einen asynchronen Client erstellt bei `propagateActivity` = `false` der Aufrufer oder Aufgerufener und wann die Response-Nachricht einen Action-Header nicht enthalten ist.  
  
#### <a name="propagation-is-enabled-on-both-sides-using-tcp-or-named-pipe"></a>Weitergabe wird mit TCP oder benannten Pipes auf beiden Seiten aktiviert  
 ![Asynchroner Client mit kein Rückruf, PropagateActivity, auf "true" auf beiden Seiten und benannte festgelegt ist, Pipes/TCP.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-enabled-using-tcp.gif)  
  
 Bei auf benannten Pipes oder TCP basierenden Szenarien wird ReceiveBytes beim Öffnen des Clients aufgerufen und bleibt so lange erhalten wie die Verbindung besteht.  
  
 Wie in der ersten Abbildung, wenn `propagateActivity` = `true`, gibt ProcessMessage an die ProcessAction-Aktivität die Übertragung.  
  
#### <a name="propagation-is-disabled-on-either-sides-using-tcp-or-named-pipe"></a>Weitergabe wird mit TCP oder benannten Pipes auf einer der Seiten deaktiviert  
 Bei auf benannten Pipes oder TCP basierenden Szenarien wird ReceiveBytes beim Öffnen des Clients aufgerufen und bleibt so lange erhalten wie die Verbindung besteht.  
  
 Das zweite Bild, ähnlich wie wenn `propagateActivity` = `false` auf einer Seite, gibt ProcessMessage nicht die ProcessAction-Aktivität die Übertragung an. Deshalb wird eine neue temporäre ProcessAction-Aktivität mit einer neuen ID aufgerufen. Wenn die asynchrone Antwort mit der Anforderung im ServiceModel-Code übereinstimmt, kann die Aktivitäts-ID aus dem lokalen Kontext abgerufen werden. Die eigentliche ProcessAction-Aktivität kann mit dieser ID übertragen werden.  
  
 ![Asynchroner Client mit kein Rückruf, PropagateActivity ist auf "false" auf beiden Seiten und benannte Pipes/TCP.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-using-tcp.gif)  
    
### <a name="asynchronous-client-with-callback"></a>Asynchroner Client mit Rückruf  
 In diesem Szenario werden für den Rückruf und `endCall` die Aktivitäten G und A' und deren Ein- und Ausgangsübertragung hinzugefügt.  
  
 Dieser Abschnitt veranschaulicht lediglich die Verwendung von HTTP mit `propragateActivity` = `true`. Jedoch die zusätzlichen Aktivitäten und Übertragungen gelten auch für die anderen Fällen (d. h. `propagateActivity` = `false`, mit TCP oder Named Pipes).  
  
 Der Rückruf erstellt eine neue Aktivität (G), wenn der Client Benutzercode aufruft, um anzugeben, dass Ergebnisse vorliegen. Der Benutzercode ruft dann `endCall` innerhalb des Rückrufs (siehe Abbildung 5) oder außerhalb des Rückrufs (siehe Abbildung 6) auf Da es nicht bekannt, welcher Benutzeraktivität ist `endCall` aufgerufen wird, erhält diese Aktivität die Bezeichnung `A’`. A' kann mit A identisch sein, muss aber nicht.  
  
 ![Zeigt einen asynchronen Client mit Rückruf, Endcall während Rückruf.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-in-callback.gif)  
    
 ![Zeigt einen asynchronen Client mit Rückruf, Endcall außerhalb Rückrufs.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-outside-callback.gif)  
    
### <a name="asynchronous-server-with-callback"></a>Asynchroner Server mit Rückruf  
 ![Zeigt einen asynchronen Server mit Rückruf.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-server-callback.gif)  
    
 Der Kanalstapel ruft den Client beim Nachrichtenempfang zurück: Ablaufverfolgungen für diese Verarbeitung werden direkt in der ProcessRequest-Aktivität ausgegeben.  
  
## <a name="asynchronous-requestreply-with-errors"></a>Asynchrone Anforderung/Antwort mit Fehlern  
 Fehlermeldungen werden während `endCall` empfangen. Davon abgesehen ähneln die Aktivitäten und Übertragungen den vorherigen Szenarien.  
  
## <a name="asynchronous-one-way-with-or-without-errors"></a>Asynchrone unidirektional Kommunikation mit oder ohne Fehler  
 Keine Antwort oder kein Fehler wird an den Client zurückgegeben.
