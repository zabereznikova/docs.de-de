---
title: "Grundlegendes zu Zustands&#228;nderungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a79ed2aa-e49a-47a8-845a-c9f436ec9987
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Grundlegendes zu Zustands&#228;nderungen
In diesem Thema werden die Zustände und Übergänge in Kanälen, die Typen zum Strukturieren von Kanalzuständen und deren Implementierung erläutert.  
  
## Zustandsautomaten und Kanäle  
 Objekte, die die Kommunikation behandeln, wie z. B. Sockets, weisen in der Regel einen Zustandsautomaten auf, dessen Zustandsübergänge sich auf das Zuordnen von Netzwerkressourcen, Herstellen oder Annehmen von Verbindungen oder das Schließen und Beenden einer Kommunikation beziehen.Der Kanalzustandsautomat stellt ein einheitliches Modell der Zustände eines Kommunikationsobjekt bereit, das die zugrunde liegende Implementierung dieses Objekts abstrahiert.Die <xref:System.ServiceModel.ICommunicationObject>\-Schnittstelle umfasst eine Reihe von Zuständen, Zustandsübergangsmethoden und Zustandsübergangsereignisse.Alle Kanäle, Kanalfactorys und Kanallistener implementieren den Kanalzustandsautomaten.  
  
 Die Ereignisse Closed, Closing, Faulted, Opened und Opening informieren einen externen Beobachter über einen stattgefundenen Zustandsübergang.  
  
 Die Methoden Abort, Close und Open \(und deren asynchrone Entsprechungen\) verursachen Zustandsübergänge.  
  
 Die Zustandseigenschaft gibt den von <xref:System.ServiceModel.CommunicationState> definierten aktuellen Zustand zurück:  
  
## ICommunicationObject, CommunicationObject, Zustände und Zustandsübergänge  
 Ein <xref:System.ServiceModel.ICommunicationObject> beginnt im Created\-Zustand, in dem seine verschiedenen Eigenschaften konfiguriert werden können.Sobald sich das Objekt im Opened\-Zustand befindet, kann es zum Senden und Empfangen von Nachrichten verwendet werden, seine Eigenschaften sind jedoch unveränderlich.Im Closing\-Zustand kann das Objekt keine neuen Anforderungen senden oder empfangen. Vorhandene Anforderungen können jedoch abgeschlossen werden, sofern der Close\-Timeout nicht überschritten wird.Bei einem nicht behebbaren Fehler geht das Objekt in den Faulted\-Zustand über und kann auf Informationen zum Fehler überprüft und letztendlich geschlossen werden.Im Closed\-Zustand hat das Objekt im Wesentlichen das Ende des Zustandsautomats erreicht.Nachdem ein Objekt aus einen Zustand in den nächsten übergegangen ist, wechselt es nicht mehr zurück in einen früheren Zustand.  
  
 Das folgende Diagramm veranschaulicht die Zustände und Zustandsübergänge von <xref:System.ServiceModel.ICommunicationObject>.Zustandsübergänge können durch einen Aufruf der folgenden drei Methoden verursacht werden: Abort, Open oder Close.Sie können auch durch einen Aufruf anderer Methoden, die von der Implementierung abhängen, verursacht werden.Ein Übergang in den Faulted\-Zustand kann das Ergebnis von Fehlern beim oder nach dem Öffnen eines Kommunikationsobjekts sein.  
  
 Jedes <xref:System.ServiceModel.ICommunicationObject> beginnt im Created\-Zustand.In diesem Zustand kann eine Anwendung das Objekt konfigurieren, indem dessen Eigenschaften festgelegt werden.Sobald sich ein Objekt in einen anderen Zustand als Created befindet, gilt es als unveränderlich.  
  
 ![Kanalzustandsübergang](../../../../docs/framework/wcf/extending/media/channelstatetranitionshighleveldiagram.gif "ChannelStateTranitionsHighLevelDiagram")  
Abbildung 1.Der ICommunicationObject\-Zustandsautomat.  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] stellt eine abstrakte Basisklasse mit dem Namen <xref:System.ServiceModel.Channels.CommunicationObject> bereit, die <xref:System.ServiceModel.ICommunicationObject> und den Kanalzustandsautomaten implementiert.In der folgenden Grafik wird ein Diagramm mit Zustandsänderungen dargestellt, das sich auf <xref:System.ServiceModel.Channels.CommunicationObject> bezieht.Neben dem <xref:System.ServiceModel.ICommunicationObject>\-Zustandsautomaten zeigt es die zeitliche Steuerung, nach der weitere <xref:System.ServiceModel.Channels.CommunicationObject>\-Methoden aufgerufen werden.  
  
 ![Statusänderungen](../../../../docs/framework/wcf/extending/media/wcfc-wcfchannelsigure5statetransitionsdetailsc.gif "wcfc\_WCFChannelsigure5StateTransitionsDetailsc")  
Abbildung 2.Die CommunicationObject\-Implementierung des ICommunicationObject\-Zustandsautomats, einschließlich Aufrufe von Ereignissen und geschützte Methoden.  
  
### ICommunicationObject\-Ereignisse  
 <xref:System.ServiceModel.Channels.CommunicationObject> macht die fünf von <xref:System.ServiceModel.ICommunicationObject> definierten Ereignisse verfügbar.Diese Ereignisse sind für Code vorgesehen, in dem das Kommunikationsobjekt für eine Benachrichtigung über Zustandsübergänge verwendet wird.Wie oben in Abbildung 2 dargestellt, wird jedes Ereignis einmal ausgelöst, nachdem der Zustand des Objekts in den durch das Ereignis bezeichneten Zustand übergegangen ist.Alle fünf Ereignisse sind vom Typ `EventHandler`, der folgendermaßen definiert wird:  
  
 `public delegate void EventHandler(object sender, EventArgs e);`  
  
 In der <xref:System.ServiceModel.Channels.CommunicationObject>\-Implementierung ist der Absender entweder <xref:System.ServiceModel.Channels.CommunicationObject> direkt oder das, was darin als Absender an den <xref:System.ServiceModel.Channels.CommunicationObject>\-Konstruktor übergeben wurde \(wenn diese Konstruktorüberladung verwendet wurde\).Der EventArgs\-Parameter `e` ist immer `EventArgs.Empty`.  
  
### Abgeleitete Objektrückrufe  
 Abgesehen von den fünf Ereignissen deklariert <xref:System.ServiceModel.Channels.CommunicationObject> acht geschützte virtuelle Methoden, mit denen ein abgeleitetes Objekt vor und nach dem Eintreten eines Zustandsübergang zurückgerufen werden kann.  
  
 Den Methoden <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=fullName> und <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=fullName> sind jeweils drei solcher Rückrufe zugeordnete.Beispielsweise gehören zu <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=fullName> die Rückrufe <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A?displayProperty=fullName>, <xref:System.ServiceModel.Channels.CommunicationObject.OnOpen%2A?displayProperty=fullName> und <xref:System.ServiceModel.Channels.CommunicationObject.OnOpened%2A?displayProperty=fullName>.<xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=fullName> sind die Methoden <xref:System.ServiceModel.Channels.CommunicationObject.OnClose%2A?displayProperty=fullName>, <xref:System.ServiceModel.Channels.CommunicationObject.OnClosing%2A?displayProperty=fullName> und <xref:System.ServiceModel.Channels.CommunicationObject.OnClosed%2A?displayProperty=fullName> zugeordnet.  
  
 Entsprechend verfügt die <xref:System.ServiceModel.Channels.CommunicationObject.Abort%2A?displayProperty=fullName>\-Methode über eine zugehörige <xref:System.ServiceModel.Channels.CommunicationObject.OnAbort%2A?displayProperty=fullName>\-Methode.  
  
 <xref:System.ServiceModel.Channels.CommunicationObject.OnOpen%2A?displayProperty=fullName>, <xref:System.ServiceModel.Channels.CommunicationObject.OnClose%2A?displayProperty=fullName> und <xref:System.ServiceModel.Channels.CommunicationObject.OnAbort%2A?displayProperty=fullName> weisen keine Standardimplementierung auf. Die anderen Rückrufe besitzen hingegen eine Standardimplementierung, die für die Richtigkeit des Zustandsautomats erforderlich ist.Stellen Sie beim Überschreiben dieser Methoden sicher, dass Sie die Basisimplementierung aufrufen oder ordnungsgemäß ersetzen.  
  
 <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A?displayProperty=fullName>, <xref:System.ServiceModel.Channels.CommunicationObject.OnClosing%2A?displayProperty=fullName> und <xref:System.ServiceModel.Channels.CommunicationObject.OnFaulted%2A?displayProperty=fullName> lösen das entsprechende Ereignis <xref:System.ServiceModel.Channels.CommunicationObject.Opening?displayProperty=fullName>, <xref:System.ServiceModel.Channels.CommunicationObject.Closing?displayProperty=fullName> und <xref:System.ServiceModel.Channels.CommunicationObject.Faulted?displayProperty=fullName> aus.<xref:System.ServiceModel.Channels.CommunicationObject.OnOpened%2A?displayProperty=fullName> und <xref:System.ServiceModel.Channels.CommunicationObject.OnClosed%2A?displayProperty=fullName> legen den Objektstatus auf jeweils Opened und Closed fest und lösen dann die entsprechenden Ereignisse <xref:System.ServiceModel.Channels.CommunicationObject.Opened?displayProperty=fullName> und <xref:System.ServiceModel.Channels.CommunicationObject.Closed?displayProperty=fullName> aus.  
  
### Zustandsübergangsmethoden  
 <xref:System.ServiceModel.Channels.CommunicationObject> stellt Implementierungen von Abort, Close und Open bereit.Bereitgestellt wird außerdem eine Fault\-Methode, die einen Zustandsübergang in den Faulted\-Zustand verursacht.Abbildung 2 zeigt den <xref:System.ServiceModel.ICommunicationObject>\-Zustandsautomaten. Dabei wird jeder Übergang durch die Methode bezeichnet, die ihn verursacht hat \(nicht bezeichnete Übergänge treten innerhalb der Implementierung der Methode auf, die den letzten bezeichneten Übergang verursacht hat\).  
  
> [!NOTE]
>  Bei allen <xref:System.ServiceModel.Channels.CommunicationObject>\-Implementierungen des Kommunikationszustands gets\/sets sind die Threads synchronisiert.  
  
 Konstruktor  
  
 <xref:System.ServiceModel.Channels.CommunicationObject> stellt drei Konstruktoren bereit, von denen alle das Objekt im Created\-Zustand belassen.Die Konstruktoren werden wie folgt definiert:  
  
 Der erste Konstruktor ist ein Standardkonstruktor und führt eine Delegierung an die Konstruktorüberladung aus, die ein Objekt akzeptiert:  
  
 `protected CommunicationObject() : this(new object()) { … }`  
  
 Der Konstruktor, der ein Objekt akzeptiert, verwendet diesen Parameter als das zu sperrende Objekt, wenn der Zugriff auf den Zustand des Kommunikationsobjekts synchronisiert wird:  
  
 `protected CommunicationObject(object mutex) { … }`  
  
 Ein dritter Konstruktor akzeptiert einen weiteren Parameter, der als Absenderargument verwendet, wenn <xref:System.ServiceModel.ICommunicationObject>\-Ereignisse ausgelöst werden.  
  
 `protected CommunicationObject(object mutex, object eventSender) { … }`  
  
 Die vorherigen beiden Konstruktoren legen den Absender auf dieses Argument fest.  
  
 Open\-Methode  
  
 Vorbedingung: Der Zustand ist Created.  
  
 Nachbedingung: Der Zustand ist Opened oder Faulted.Möglicherweise wird eine Ausnahme ausgelöst.  
  
 Die Open\(\)\-Methode versucht, das Kommunikationsobjekt zu öffnen und den Zustand auf Opened festzulegen.Falls ein Fehler auftritt, legt sie den Zustand auf Faulted festgelegt.  
  
 Die Methode, überprüft zuerst, ob Created der aktuelle Zustand ist.Wenn der aktuelle Zustand Opening oder Opened lautet, löst sie <xref:System.InvalidOperationException> aus.Ist Closing oder Closed der aktuelle Zustand, löst sie <xref:System.ServiceModel.CommunicationObjectAbortedException> aus, wenn das Objekt beendet worden ist, andernfalls löst sie <xref:System.ObjectDisposedException> aus.Ist Faulted der aktuelle Zustand, löst sie <xref:System.ServiceModel.CommunicationObjectFaultedException> aus.  
  
 Anschließend legt sie den Zustand auf Opening fest und ruft OnOpening\(\) \(wodurch das Opening\-Ereignis ausgelöst wird\), OnOpen\(\) und OnOpened\(\) in dieser Reihenfolge auf.OnOpened\(\) legt den Zustand auf Opened fest und löst das Opened\-Ereignis aus.Wenn währenddessen eine Ausnahme ausgelöst wird, ruft Open\(\) Fault\(\) auf und übergibt die Ausnahme.Das folgende Diagramm zeigt den Open\-Prozess im Detail.  
  
 ![Statusänderungen](../../../../docs/framework/wcf/extending/media/wcfc-wcfchannelsigurecoopenflowchartf.gif "wcfc\_WCFChannelsigureCOOpenFlowChartf")  
Überschreiben Sie die OnOpen\-Methode, und implementieren Sie eine benutzerdefinierte Open\-Logik, z. B. das Öffnen eines inneren Kommunikationsobjekts.  
  
 Close\-Methode  
  
 Vorbedingung: Keine.  
  
 Nachbedingung: Der Zustand ist Closed.Möglicherweise wird eine Ausnahme ausgelöst.  
  
 Die Close\(\)\-Methode kann bei jedem Zustand aufgerufen werden.Sie versucht, das Objekt ordnungsgemäß zu schließen.Bei einem Fehler beendet sie das Objekt.Die Methode bewirkt nichts, wenn der aktuelle Zustand Closing oder Closed lautet.Andernfalls legt sie den Zustand auf Closing fest.Wenn der ursprüngliche Zustand Created, Opening oder Faulted lautete, ruft sie Abort\(\) auf \(siehe folgendes Diagramm\).Wenn der ursprüngliche Zustand Opened lautete, ruft sie OnClosing \(wodurch das Opening\-Ereignis ausgelöst wird\), OnOpen\(\) und OnOpened\(\) in dieser Reihenfolge auf.Wenn währenddessen eine Ausnahme ausgelöst wird, ruft Close\(\) Abort\(\) auf und übergibt die Ausnahme.OnClosed\(\) legt den Zustand auf Closed fest und löst das Closed\-Ereignis aus.Das folgende Diagramm zeigt den Close\-Prozess im Detail.  
  
 ![Statusänderungen](../../../../docs/framework/wcf/extending/media/wcfc-wcfchannelsguire7ico-closeflowchartc.gif "wcfc\_WCFChannelsguire7ICO\-CloseFlowChartc")  
Überschreiben Sie die OnClose\-Methode und implementieren Sie eine benutzerdefinierte Close\-Logik, z. B. das Schließen eines inneren Kommunikationsobjekts.Jede ordnungsgemäß schließende Logik, die eine längere Blockierung mit sich bringt \(z. B. das Warten auf eine Antwort\) sollte in OnClose\(\) implementiert werden, da diese Methode einen Timeoutparameter akzeptiert und nicht als Teil von Abort\(\) aufgerufen wird.  
  
 Abort\-Methode  
  
 Vorbedingung: Keine.  
Nachbedingung: Der Zustand ist Closed.Möglicherweise wird eine Ausnahme ausgelöst.  
  
 Die Abort\(\)\-Methode bewirkt nichts, wenn der aktuelle Zustand Closed lautet oder wenn das Objekt zuvor beendet worden ist \(z. B. indem Abort\(\) für einen anderen Thread ausgeführt wird\).Andernfalls legt sie den Zustand auf Closing fest und ruft OnClosing\(\) \(wodurch das Closing\-Ereignis ausgelöst wird\), OnAbort\(\) und OnClosed\(\) in dieser Reihenfolge auf. \(OnClose wird nicht aufgerufen, da das Objekt beendet, nicht geschlossen wird.\)OnClosed\(\) legt den Zustand auf Closed fest und löst das Closed\-Ereignis aus.Wenn währenddessen eine Ausnahme ausgelöst wird, wird sie erneut für den Aufrufer von Abort ausgelöst.Implementierungen von OnClosing\(\), OnClosed\(\) und OnAbort\(\) sollten keine Blockierung hervorrufen \(z. B. bei Ein\-\/Ausgaben\).Das folgende Diagramm zeigt den Abort\-Prozess im Detail.  
  
 ![Statusänderungen](../../../../docs/framework/wcf/extending/media/wcfc-wcfchannelsigure8ico-abortflowchartc.gif "wcfc\_WCFChannelsigure8ICO\-AbortFlowChartc")  
Überschreiben Sie die OnAbort\-Methode, und implementieren Sie eine benutzerdefinierte Terminate\-Logik, z. B. das Beenden eines inneren Kommunikationsobjekts.  
  
 Fault\-Methode  
  
 Die Fault\-Methode bezieht sich speziell auf <xref:System.ServiceModel.Channels.CommunicationObject> und ist kein Bestandteil der <xref:System.ServiceModel.ICommunicationObject>\-Schnittstelle.Sie wird hier nur aus Gründen der Vollständigkeit aufgeführt.  
  
 Vorbedingung: Keine.  
  
 Nachbedingung: Der Zustand ist Faulted.Möglicherweise wird eine Ausnahme ausgelöst.  
  
 Die Fault\(\)\-Methode bewirkt nichts, wenn der aktuelle Zustand Faulted oder Closed lautet.Andernfalls legt sie den Zustand auf Faulted fest und ruft OnFaulted\(\) auf, wodurch das Faulted\-Ereignis ausgelöst wird.Wenn OnFaulted eine Ausnahme auslöst, wird sie erneut ausgelöst.  
  
### ThrowIfXxx\-Methoden  
 CommunicationObject verfügt über drei geschützte Methoden, mit denen Ausnahmen ausgelöst werden können, wenn sich das Objekt in einem bestimmten Zustand befindet.  
  
 <xref:System.ServiceModel.Channels.CommunicationObject.ThrowIfDisposed%2A> löst eine Ausnahme aus, wenn der Zustand Closing, Closed oder Faulted lautet.  
  
 <xref:System.ServiceModel.Channels.CommunicationObject.ThrowIfDisposedOrImmutable%2A> löst eine Ausnahme aus, wenn der Zustand nicht Created lautet.  
  
 <xref:System.ServiceModel.Channels.CommunicationObject.ThrowIfDisposedOrNotOpen%2A> löst eine Ausnahme aus, wenn der Zustand nicht Opened lautet.  
  
 Die ausgelösten Ausnahmen hängen vom Zustand ab.Die folgende Tabelle enthält die verschiedenen Zustände und den entsprechende Ausnahmetyp, der durch einen Aufruf von ThrowIfXxx zu diesem Zustand ausgelöst wird.  
  
|Zustand|Wurde Abort aufgerufen?|Ausnahme|  
|-------------|-----------------------------|--------------|  
|Created|Nicht zutreffend|<xref:System.InvalidOperationException?displayProperty=fullName>|  
|Opening|Nicht zutreffend|<xref:System.InvalidOperationException?displayProperty=fullName>|  
|Opened|Nicht zutreffend|<xref:System.InvalidOperationException?displayProperty=fullName>|  
|Schließende|Ja|<xref:System.ServiceModel.CommunicationObjectAbortedException?displayProperty=fullName>|  
|Closing|Nein|<xref:System.ObjectDisposedException?displayProperty=fullName>|  
|Closed|Ja|<xref:System.ServiceModel.CommunicationObjectAbortedException?displayProperty=fullName> im Fall, dass ein Objekt durch einen vorherigen, expliziten Aufruf von Abort geschlossen wurde.Wenn Sie Close für das Objekt aufrufen, wird <xref:System.ObjectDisposedException?displayProperty=fullName> ausgelöst.|  
|Closed|Nein|<xref:System.ObjectDisposedException?displayProperty=fullName>|  
|Faulted|Nicht zutreffend|<xref:System.ServiceModel.CommunicationObjectFaultedException?displayProperty=fullName>|  
  
### Timeouts  
 Mehrere der besprochenen Methoden akzeptieren Timeoutparameter.Dazu gehören Close, Open \(bestimmte Überladungen und asynchrone Versionen\), OnClose und OnOpen.Diese Methoden wurden für langwierige Vorgänge entwickelt \(z. B. das Blockieren bei Ein\-\/Ausgaben beim ordnungsgemäßen Schließen einer Verbindung\)\), damit mit dem Timeoutparameter angegeben werden kann, wie lange dieser Vorgang dauern darf, bevor er unterbrochen wird.Implementierungen dieser Methoden sollten den bereitgestellten Timeoutwert verwenden, um sicherzustellen, dass die Rückgabe an den Aufrufer innerhalb dieses Timeouts erfolgt.Implementierungen anderer Methoden, die keinen Timeoutwert akzeptieren, sind nicht für langwierige Vorgänge bestimmt und sollten bei Ein\-\/Ausgaben keine Blockierung verursachen.  
  
 Zu den Ausnahmen zählen die Überladungen Open\(\) und Close\(\), die keinen Timeout akzeptieren.Diese Überladungen verwenden einen Timeoutwert, der von der abgeleiteten Klasse bereitgestellt wird.<xref:System.ServiceModel.Channels.CommunicationObject> macht zwei geschützte abstrakte Eigenschaften mit der Bezeichnung <xref:System.ServiceModel.Channels.CommunicationObject.DefaultCloseTimeout%2A> und <xref:System.ServiceModel.Channels.CommunicationObject.DefaultOpenTimeout%2A> verfügbar, die wie folgt definiert werden:  
  
 `protected abstract TimeSpan DefaultCloseTimeout { get; }`  
  
 `protected abstract TimeSpan DefaultOpenTimeout { get; }`  
  
 Eine abgeleitete Klasse implementiert diese Eigenschaften, um für die Überladungen Open\(\) und Close\(\), die keinen Timeoutwert akzeptieren, den Standardtimeout bereitzustellen.Dann führen die Implementierungen von Open\(\) und Close\(\) eine Delegierung an die Überladung aus, die einen Timeout akzeptiert und übergeben ihr den Standardtimeoutwert. Beispiel:  
  
 `public void Open()`  
  
 `{`  
  
 `this.Open(this.DefaultOpenTimeout);`  
  
 `}`  
  
#### IDefaultCommunicationTimeouts  
 Diese Schnittstelle verfügt über vier schreibgeschützte Eigenschaften, um Standardtimeoutwerte für Open, Send, Receive und Close bereitzustellen.Jede Implementierung muss die Standardwerte auf die entsprechend angebrachte Weise implementieren.Zur Vereinfachung lege <xref:System.ServiceModel.Channels.ChannelFactoryBase> und <xref:System.ServiceModel.Channels.ChannelListenerBase> diese Werte standardmäßig auf jeweils 1 Minute fest.