---
title: "Synchrone Szenarien mit HTTP, TCP oder benannten Pipes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7e90af1b-f8f6-41b9-a63a-8490ada502b1
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Synchrone Szenarien mit HTTP, TCP oder benannten Pipes
In diesem Thema werden die Aktivitäten und Übertragungen für verschiedene synchrone Anforderungs\-\/Antwortszenarien beschrieben. Dabei werden HTTP, TCP oder benannte Pipes mit einem Singlethreadclient verwendet.Unter [Asynchrone Szenarien mit HTTP, TCP oder benannten Pipes](../../../../../docs/framework/wcf/diagnostics/tracing/asynchronous-scenarios-using-http-tcp-or-named-pipe.md) finden Sie weitere Informationen zu Multithreadanforderungen.  
  
## Synchrone Anforderung\/Antwort ohne Fehler  
 In diesem Abschnitt werden die Aktivitäten und Übertragungen für ein gültiges synchrones Anforderungs\-\/Antwortszenario mit Singlethreadclient beschrieben.  
  
### Client  
  
#### Herstellen einer Verbindung mit Dienstendpunkt  
 Ein Client wird erstellt und geöffnet.Für jeden dieser Schritte wird die Umgebungsaktivität \(A\) jeweils auf eine "Konstruktclient"\-Aktivität \(B\) und eine "Offene Client"\-Aktivität \(C\) übertragen.Für jede Aktivität, auf die übertragen wird, wird die Umgebungsaktivität unterbrochen, bis eine Übertragung zurück erfolgt, d. h. bis ServiceModel\-Code ausgeführt wird.  
  
#### Stellen einer Anforderung an einen Dienstendpunkt  
 Die Umgebungsaktivität wird auf eine "ProcessAction"\-Aktivität \(D\) übertragen.Innerhalb dieser Aktivität wird eine Anforderungsnachricht gesendet, und eine Antwortmeldung wird empfangen.Die Aktivität endet, wenn das Steuerelement zum Benutzercode zurückkehrt.Da dies eine asynchrone Anforderung ist, unterbricht die Umgebungsaktivität, bis das Steuerelement einen Wert zurückgibt.  
  
#### Schließen einer Verbindung mit Dienstendpunkt  
 Die Aktivität "Schließen" \(I\) des Clients wird aus der Umgebungsaktivität erstellt.Dies ist identisch mit "neu" und "geöffnet".  
  
### Server  
  
#### Einrichten eines Diensthosts  
 Die neuen und geöffneten Aktivitäten \(N und O\) des ServiceHost werden aus der Umgebungsaktivität \(M\) erstellt.  
  
 Eine Listeneraktivität \(P\) wird dadurch erstellt, dass ein ServiceHost für jeden Listener geöffnet wird.Die Listeneraktivität wartet darauf, Daten zu empfangen und zu verarbeiten.  
  
#### Empfangen von Daten durch Übertragung  
 Wenn Daten durch Übertragung eintreffen, wird eine "ReceiveBytes"\-Aktivität \(Q\) erstellt, wenn sie nicht bereits vorhanden ist, um die empfangenen Daten zu verarbeiten.Diese Aktivität kann für mehrere Nachrichten in einer Verbindung oder einer Warteschlange wiederverwendet werden.  
  
 Die ReceiveBytes\-Aktivität startet eine ProcessMessage\-Aktivität \(R\), wenn ausreichend Daten vorhanden sind, um eine SOAP\-Aktionsnachricht zu erstellen.  
  
 Bei der Aktivität R werden die Nachrichtenheader verarbeitet, und der activityID\-Header wird überprüft.Wenn dieser Header vorhanden ist, wird die Aktivitäts\-ID als ProcessAction\-Aktivität festgelegt; andernfalls wird eine neue ID erstellt.  
  
 Eine ProcessAction\-Aktivität \(S\) wird erstellt, und es wird auf sie übertragen, wenn der Aufruf verarbeitet wird.Diese Aktivität endet, wenn alle Verarbeitungsschritte bezüglich der eingehenden Nachricht abgeschlossen sind, ggf. einschließlich der Ausführung des Benutzercodes \(T\) und des Sendens der Antwortnachricht.  
  
#### Schließen eines Diensthosts  
 Die Aktivität "Schließen" \(Z\) des ServiceHost wird aus der Umgebungsaktivität erstellt.  
  
 ![Synchrone Szenarien mit HTTP&#47;TCP&#47;Named Pipes](../../../../../docs/framework/wcf/diagnostics/tracing/media/sync.gif "Sync")  
  
 In \<A: Name\> ist `A` ein Shortcutsymbol, das die Aktivität im vorangegangenen Text und in Tabelle 3 beschreibt.`Name` ist ein verkürzter Name der Aktivität.  
  
 Wenn `propagateActivity`\=`true` ist, haben Prozessaktionen des Clients und des Diensts dieselbe Aktivitäts\-ID.  
  
## Synchrone Anforderung\/Antwort mit Fehlern  
 Der einzige Unterschied zu dem vorherigen Szenario besteht darin, dass eine SOAP\-Fehlernachricht als Antwortnachricht zurückgegeben wird.Wenn `propagateActivity`\=`true` ist, wird die Aktivitäts\-ID der Anforderungsnachricht zur SOAP\-Fehlernachricht hinzugefügt.  
  
## Synchrone unidirektionale Kommunikation ohne Fehler  
 Der einzige Unterschied zu dem ersten Szenario ist, dass keine Nachricht an den Server zurückgegeben wird.Für HTTP\-basierte Protokolle wird immer noch ein Status \(gültig oder Fehler\) an den Client zurückgegeben.Der Grund dafür ist, dass HTTP das einzige Protokoll mit Anforderungs\-Anwort\-Semantik ist, das Teil des [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Protokollstapels ist.Da TCP\-Verarbeitung für [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] ausgeblendet wird, wird keine Bestätigung an den Client gesendet.  
  
## Synchrone unidirektionale Kommunikation mit Fehlern  
 Wenn während der Verarbeitung der Nachricht ein Fehler auftritt \(Q oder darüber hinaus\), wird keine Benachrichtigung an den Client zurückgegeben.Dies ist identisch mit dem Szenario "Synchrone unidirektionale Kommunikation ohne Fehler".Sie sollten kein unidirektionales Szenario verwenden, wenn Sie eine Fehlermeldung empfangen möchten.  
  
## Duplex  
 Der Unterschied zu den vorherigen Szenarien besteht darin, dass der Client als Dienst fungiert, wobei er die ReceiveBytes\- und die ProcessMessage\-Aktivität erstellt, ähnlich wie bei den asynchronen Szenarien.