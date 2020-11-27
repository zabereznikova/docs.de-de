---
title: Synchrone Szenarien mit HTTP, TCP oder benannten Pipes
ms.date: 03/30/2017
ms.assetid: 7e90af1b-f8f6-41b9-a63a-8490ada502b1
ms.openlocfilehash: 906bceadf56d82570b41cfbb2c96e4b89d595d02
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274438"
---
# <a name="synchronous-scenarios-using-http-tcp-or-named-pipe"></a>Synchrone Szenarien mit HTTP, TCP oder benannten Pipes

In diesem Thema werden die Aktivitäten und Übertragungen für verschiedene synchrone Anforderungs-/Antwortszenarien beschrieben. Dabei werden HTTP, TCP oder benannte Pipes mit einem Singlethreadclient verwendet. Weitere Informationen zu Multithreaded-Anforderungen finden [Sie unter asynchrone Szenarien mit http, TCP oder Named Pipe](asynchronous-scenarios-using-http-tcp-or-named-pipe.md) .  
  
## <a name="synchronous-requestreply-without-errors"></a>Synchrone Anforderung/Antwort ohne Fehler  

 In diesem Abschnitt werden die Aktivitäten und Übertragungen für ein gültiges synchrones Anforderungs-/Antwortszenario mit Singlethreadclient beschrieben.  
  
### <a name="client"></a>Client  
  
#### <a name="establishing-communication-with-service-endpoint"></a>Herstellen einer Verbindung mit Dienstendpunkt  

 Ein Client wird erstellt und geöffnet. Für jeden dieser Schritte wird die Ambient-Aktivität (a) an eine "Konstrukt Client" (B)-und "Open Client"-Aktivität (C) übertragen. Für jede Aktivität, auf die übertragen wird, wird die Umgebungsaktivität unterbrochen, bis eine Übertragung zurück erfolgt, d. h. bis ServiceModel-Code ausgeführt wird.  
  
#### <a name="making-a-request-to-service-endpoint"></a>Stellen einer Anforderung an einen Dienstendpunkt  

 Die Ambient-Aktivität wird an eine "ProcessAction"-Aktivität (D) übertragen. Innerhalb dieser Aktivität wird eine Anforderungsnachricht gesendet, und eine Antwortmeldung wird empfangen. Die Aktivität endet, wenn das Steuerelement zum Benutzercode zurückkehrt. Da dies eine asynchrone Anforderung ist, unterbricht die Umgebungsaktivität, bis das Steuerelement einen Wert zurückgibt.  
  
#### <a name="closing-communication-with-service-endpoint"></a>Schließen einer Verbindung mit Dienstendpunkt  

 Die Aktivität "Schließen" (I) des Clients wird aus der Umgebungsaktivität erstellt. Dies ist identisch mit "neu" und "geöffnet".  
  
### <a name="server"></a>Server  
  
#### <a name="setting-up-a-service-host"></a>Einrichten eines Diensthosts  

 Die neuen und geöffneten Aktivitäten (N und O) des ServiceHost werden aus der Umgebungsaktivität (M) erstellt.  
  
 Eine Listeneraktivität (P) wird dadurch erstellt, dass ein ServiceHost für jeden Listener geöffnet wird. Die Listeneraktivität wartet darauf, Daten zu empfangen und zu verarbeiten.  
  
#### <a name="receiving-data-on-the-wire"></a>Empfangen von Daten durch Übertragung  

 Wenn Daten bei der Übertragung eintreffen, wird eine "ReceiveBytes"-Aktivität erstellt, wenn Sie nicht bereits vorhanden ist (Q), um die empfangenen Daten zu verarbeiten. Diese Aktivität kann für mehrere Nachrichten in einer Verbindung oder einer Warteschlange wiederverwendet werden.  
  
 Die ReceiveBytes-Aktivität startet eine ProcessMessage-Aktivität (R), wenn ausreichend Daten vorhanden sind, um eine SOAP-Aktionsnachricht zu erstellen.  
  
 Bei der Aktivität R werden die Nachrichtenheader verarbeitet, und der activityID-Header wird überprüft. Wenn dieser Header vorhanden ist, wird die Aktivitäts-ID als ProcessAction-Aktivität festgelegt; andernfalls wird eine neue ID erstellt.  
  
 Eine ProcessAction-Aktivität (S) wird erstellt, und es wird auf sie übertragen, wenn der Aufruf verarbeitet wird. Diese Aktivität endet, wenn alle Verarbeitungsschritte bezüglich der eingehenden Nachricht abgeschlossen sind, ggf. einschließlich der Ausführung des Benutzercodes (T) und des Sendens der Antwortnachricht.  
  
#### <a name="closing-a-service-host"></a>Schließen eines Diensthosts  

 Die Aktivität "Schließen" (Z) des ServiceHost wird aus der Umgebungsaktivität erstellt.  
  
 ![Das Diagramm zeigt synchrone Szenarios: http, TCP oder Named Pipes.](./media/synchronous-scenarios-using-http-tcp-or-named-pipe/synchronous-scenario-http-tcp-named-pipes.gif)  
  
 In \<A: name> `A` ist ein Verknüpfungs Symbol, das die Aktivität im vorherigen Text und in Tabelle 3 beschreibt. `Name` ist ein verkürzter Name der Aktivität.  
  
 Gibt `propagateActivity` = `true` an, dass die Prozess Aktion sowohl für den Client als auch für den Dienst dieselbe Aktivitäts-ID aufweisen.  
  
## <a name="synchronous-requestreply-with-errors"></a>Synchrone Anforderung/Antwort mit Fehlern  

 Der einzige Unterschied zu dem vorherigen Szenario besteht darin, dass eine SOAP-Fehlernachricht als Antwortnachricht zurückgegeben wird. Wenn der Wert ist `propagateActivity` = `true` , wird die Aktivitäts-ID der Anforderungs Nachricht der SOAP-Fehlermeldung hinzugefügt.  
  
## <a name="synchronous-one-way-without-errors"></a>Synchrone unidirektionale Kommunikation ohne Fehler  

 Der einzige Unterschied zu dem ersten Szenario ist, dass keine Nachricht an den Server zurückgegeben wird. Für HTTP-basierte Protokolle wird immer noch ein Status (gültig oder Fehler) an den Client zurückgegeben. Dies liegt daran, dass http das einzige Protokoll mit einer Anforderung/Antwort-Semantik ist, die Teil des WCF-Protokoll Stapels ist. Da die TCP-Verarbeitung in WCF ausgeblendet ist, wird keine Bestätigung an den Client gesendet.  
  
## <a name="synchronous-one-way-with-errors"></a>Synchrone unidirektionale Kommunikation mit Fehlern  

 Wenn während der Verarbeitung der Nachricht ein Fehler auftritt (Q oder darüber hinaus), wird keine Benachrichtigung an den Client zurückgegeben. Dies ist identisch mit dem Szenario „Synchrone unidirektionale Kommunikation ohne Fehler“. Sie sollten kein unidirektionales Szenario verwenden, wenn Sie eine Fehlermeldung empfangen möchten.  
  
## <a name="duplex"></a>Duplex  

 Der Unterschied zu den vorherigen Szenarien besteht darin, dass der Client als Dienst fungiert, wobei er die ReceiveBytes- und die ProcessMessage-Aktivität erstellt, ähnlich wie bei den asynchronen Szenarien.
