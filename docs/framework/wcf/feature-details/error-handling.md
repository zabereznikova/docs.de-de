---
title: "Error handling | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c948841a-7db9-40ae-9b78-587d216cbcaf
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Error handling
## Fehlerbehandlung in Windows Communication Foundation  
 Wenn in einem Dienst eine unerwartete Ausnahme oder ein unerwarteter Fehler auftritt, gibt es mehrere Möglichkeiten zum Entwerfen einer Lösung für die Ausnahmebehandlung.  Es gibt keine einzige richtige oder empfohlene Lösung für die Fehlerbehandlung, sondern mehrere Möglichkeiten, die erwogen werden müssen.  Im Allgemeinen wird das Implementieren einer Hybridlösung empfohlen, die mehrere der in der folgenden Liste enthaltenen Ansätze kombiniert. Kriterien für die zu wählende Lösung sind die Komplexität der WCF\-Implementierung, der Typ und die Häufigkeit der Ausnahmen, das Verhältnis von behandelten und  nicht behandelten Ausnahmen sowie die entsprechenden Anforderungen an Ablaufverfolgung, Protokollierung oder Richtlinien.  
  
 Diese Lösungen werden im restlichen Teil dieses Abschnitts genauer erläutert.  
  
### Die Microsoft Enterprise Library  
 Der Ausnahmebehandlungs\-Anwendungsblock der Microsoft Enterprise Library erleichtert das Implementieren häufiger Entwurfsmuster und das Erstellen einer einheitlichen Strategie für die Verarbeitung von Ausnahmen, die auf allen Architekturebenen einer Unternehmensanwendung auftreten.  Er unterstützt den typischen Code in den Catch\-Anweisungen von Anwendungskomponenten.  Statt diesen Code \(z. B. Code zum Protokollieren von Ausnahmeinformationen\) in der gesamten Anwendung in identischen Catch\-Blöcken zu wiederholen, ermöglicht der Ausnahmebehandlungs\-Anwendungsblock Entwicklern das Kapseln dieser Logik als wiederverwendbare Ausnahmehandler.  
  
 Diese Bibliothek enthält standardmäßig einen Fehlervertragsausnahmehandler.  Dieser Ausnahmehandler ist für die Verwendung an den Grenzen des WCF \(Windows® Communication Foundation\)\-Diensts vorgesehen, und er generiert aus der Ausnahme einen neuen Fehlervertrag.  
  
 Anwendungsblöcke enthalten in der Regel häufig verwendete bewährte Methoden und bieten eine allgemeine Vorgehensweise für die Ausnahmebehandlung in der gesamten Anwendung.  Jedoch können benutzerdefinierte Fehlerhandler und Fehlerverträge, die selbst entwickelt wurden, ebenfalls sehr hilfreich sein.  Beispielsweise bieten benutzerdefinierte Fehlerhandler eine ausgezeichnete Möglichkeit, alle Ausnahmen automatisch auf "FaultExceptions" höher zu stufen und der Anwendung Protokollierungsfunktionen hinzuzufügen.  
  
 Weitere Informationen finden Sie unter [Microsoft Enterprise Library](http://msdn.microsoft.com/library/ff632023.aspx).  
  
### Behandeln von erwarteten Ausnahmen  
 Die ordnungsgemäße Vorgehensweise ist das Abfangen erwarteter Ausnahmen in jedem Vorgang oder an jedem relevanten Erweiterungspunkt, dann zu entscheiden, ob die Ausnahme behoben werden kann, und den ordnungsgemäßen benutzerdefinierten Fehler in einer "FaultException\<T\>" zurückzugeben.  
  
### Behandeln von unerwarteten Ausnahmen mit einem "IErrorHandler"  
 Die empfohlene Vorgehensweise zum Behandeln von unerwarteten Ausnahmen ist das Verknüpfen mit einem "IErrorHandler".  Fehlerhandler fangen nur Ausnahmen auf der WCF\-Laufzeitebene \(der Dienstmodellebene\) ab und nicht auf der Kanalebene.  Die einzige Möglichkeit, einen "IErrorHandler" auf Kanalebene zu verknüpfen, ist das Erstellen eines benutzerdefinierten Kanals, und dies wird in den meisten Szenarien nicht empfohlen.  
  
 Eine unerwartete Ausnahme ist im Allgemeinen weder eine nicht behebbare Ausnahme noch eine Verarbeitungsausnahme, sondern eine unerwartete Benutzerausnahme.  Eine nicht behebbare Ausnahme \(z. B. eine Ausnahme aufgrund eines ungenügenden Arbeitsspeichers\), die normalerweise automatisch vom [Dienstmodell\-Ausnahmehandler](http://msdn.microsoft.com/library/system.servicemodel.dispatcher.exceptionhandler.aspx) behandelt wird, kann im Allgemeinen nicht erfolgreich behandelt werden, und sie wird möglicherweise nur behandelt, damit eine zusätzliche Protokollierung erfolgt oder eine Standardausnahme an den Client zurückgegeben wird.  Eine Verarbeitungsausnahme tritt meist beim Verarbeiten der Nachricht auf, beispielsweise auf Serialisierungs\-, Encoder\- oder Formatiererebene, und kann im Allgemeinen nicht von einem Eine Verarbeitung\-Ausnahme tritt auf, bei der Verarbeitung der Nachricht – z. B. auf die Serialisierung, Encoder oder Formatierer\-Ebene – in der Regel ein IErrorHandler werden nicht behandelt, da es im Allgemeinen zu früh oder zu spät für den Fehlerhandler ist, bis zu dem Zeitpunkt einzugreifen, diese Ausnahmen auftreten. "IErrorHandler" behandelt werden, weil die Fehlerbehandlung noch nicht oder nicht mehr eingreifen kann, wenn diese Ausnahmen auftreten.  Ebenso können Transportausnahmen nicht von einem "IErrorHandler" behandelt werden.  
  
 Mit einem "IErrorHandler" können Sie das Verhalten der Anwendung explizit steuern, wenn eine Ausnahme ausgelöst wird.  Sie haben folgende Möglichkeiten:  
  
1.  Entscheiden, ob ein Fehler an den Client gesendet wird  
  
2.  Ersetzen einer Ausnahme durch einen Fehler  
  
3.  Ersetzen eines Fehlers durch einen anderen Fehler  
  
4.  Ausführen von Protokollierung oder Ablaufverfolgung  
  
5.  Ausführen von anderen benutzerdefinierten Aktivitäten  
  
 Sie können einen benutzerdefinierten Fehlerhandler installieren, indem Sie ihn der ErrorHandlers\-Eigenschaft der Kanalverteiler für den Dienst hinzufügen.  Es ist zulässig, über mehrere Fehlerhandler zu verfügen, und sie werden in der Reihenfolge aufgerufen, in der sie der Auflistung hinzugefügt werden.  
  
 "IErrorHandler.ProvideFault" steuert die Fehlermeldung, die an den Client gesendet wird.  Diese Methode wird unabhängig vom Typ der Ausnahme aufgerufen, die durch einen Vorgang im Dienst ausgelöst wird.  Wenn hier kein Vorgang ausgeführt wird, wird WCF mit dem Standardverhalten fortgesetzt und auf die gleiche Weise wie ohne benutzerdefinierte Fehlerhandler ausgeführt.  
  
 Sie können diese Herangehensweise beispielsweise verwenden, wenn Ausnahmen an einer zentralen Stelle in Fehler umgewandelt werden sollen, bevor sie an den Client gesendet werden \(um sicherzustellen, dass die Instanz nicht verworfen wird und der Kanal nicht in den Faulted\-Zustand wechselt\).  
  
 Die IErrorHandler.HandleError\-Methode wird in der Regel verwendet, um Verhalten für Fehler zu implementieren, z. B. Fehlerprotokollierung, Systembenachrichtigungen, Beenden der Anwendung usw.  "IErrorHandler.HandleError" kann an mehreren Stellen im Dienst aufgerufen werden, und je nachdem, wo der Fehler ausgelöst wird, kann die HandleError\-Methode von demselben Thread wie der Vorgang oder von einem anderen Thread aufgerufen werden. Dies lässt sich nicht eindeutig festlegen.  
  
### Behandeln von Ausnahmen außerhalb von WCF  
 Häufig treten Konfigurationsausnahmen, Ausnahmen im Hinblick auf Datenbankverbindungszeichenfolgen und ähnliche Ausnahmen im Kontext einer WCF\-Anwendung auf, ohne vom Dienstmodell oder vom Webdienst selbst verursacht worden zu sein.  Diese Ausnahmen sind reguläre Ausnahmen außerhalb des Webdiensts, und sie sollten wie andere externe Ausnahmen in der Umgebung behandelt werden.  
  
### Ablaufverfolgung von Ausnahmen  
 Die Ablaufverfolgung ist die einzige Stelle, an der potenziell alle Ausnahmen sichtbar sind.  Weitere Informationen zur Ablaufverfolgung und Protokollierung von Ausnahmen finden Sie unter "Ablaufverfolgung und Protokollierung".  
  
### URI\-Vorlagenfehler bei Verwendung von "WebGetAttribute" und "WebInvokeAttribute"  
 Mit dem WebGet\-Attribut und dem WebInvoke\-Attribut können Sie eine URI\-Vorlage angeben, die Vorgangsparametern Komponenten der Anforderungsadresse zuordnet.  Beispielsweise ordnet die URI\-Vorlage "weather\/{state}\/{city}" die Anforderungsadresse als Literaltoken, als Parameter mit dem Namen "state" und als Parameter mit dem Namen "city" zu.  Diese Parameter können dann nach Name an einige der formalen Parameter des Vorgangs gebunden werden.  
  
 Die Vorlagenparameter werden im URI als Zeichenfolgen angezeigt, während die formalen Parameter eines typisierten Vertrags möglicherweise nicht vom Typ String sind.  Daher muss eine Konvertierung erfolgen, bevor der Vorgang aufgerufen werden kann.  Es steht eine [Tabelle der Konvertierungsformate](http://msdn.microsoft.com/library/bb412172.aspx) zur Verfügung.  
  
 Wenn jedoch die Konvertierung fehlschlägt, gibt es keine Möglichkeit, dies dem Vorgang zu signalisieren.  Stattdessen wird für die Typkonvertierung ein Verteilungsfehler ausgegeben.  
  
 Ein Typkonvertierungs\-Verteilungsfehler kann wie viele andere Typen von Verteilungsfehlern durch das Installieren eines Fehlerhandlers überprüft werden.  Der IErrorHandler\-Erweiterungspunkt wird aufgerufen, um auf Dienstebene aufgetretene Ausnahmen zu behandeln.  Dort kann die an den Aufrufer zurückzusendende Antwort ausgewählt werden, und es lassen sich benutzerdefinierte Aufgaben ausführen und benutzerdefinierte Berichte erstellen.  
  
## Siehe auch  
 [Grundlegende WCF\-Fehlerbehandlung](http://msdn.microsoft.com/library/gg281715.aspx)